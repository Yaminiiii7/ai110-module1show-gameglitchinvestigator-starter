# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

### Game's purpose
A Streamlit number-guessing game called "Glitchy Guesser." The app picks a
secret number within a range that depends on the chosen difficulty (Easy 1–20,
Normal 1–50, Hard 1–100). The player types guesses, gets "Too High" / "Too Low"
hints, has a limited number of attempts per difficulty, and earns a score.

### Bugs found
1. **New Game doesn't reset the display** — clicking "New Game 🔁" left the old
   game on screen instead of starting fresh.
2. **Hints were backwards** — guessing too high told you to go HIGHER and too
   low told you to go LOWER (the Lower/Higher logic was reversed).


### Fixes applied
- **Hints (Bug 2):** Implemented `check_guess` in `logic_utils.py` so a guess
  above the secret returns `"Too High"` with a "Go LOWER" message and a guess
  below returns `"Too Low"` with a "Go HIGHER" message.

- **Fix2 New game:** Updating with the right history


## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

## Demo Walkthrough
1. User enters a guess of 40
2. Game returns "Too Low"
3. User enters a guess of 70 → "Too High"
4. Score updates correctly after each guess
5. Game ends after the correct guess
change the difficulty level as per your wish


## 🧪 Test Results

```
$ python -m pytest tests/test_game_logic.py
tests/test_game_logic.py::test_winning_guess PASSED              [ 33%]
tests/test_game_logic.py::test_guess_too_high PASSED             [ 66%]
tests/test_game_logic.py::test_guess_too_low PASSED              [100%]

========================== 3 passed in 0.05s ==========================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
