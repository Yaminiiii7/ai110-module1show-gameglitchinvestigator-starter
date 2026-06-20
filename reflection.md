# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
      Bug 1: New game button do not flash a new game
      Bug 2: Lower/higher work oppositely
      Bug 3: App asks us to guess a number from 1 and n in different levels.But Score is negative from debug info
      Bug 4: Each level displays different no of attempts.But in the game, it is attempts left is n-1 before the game starts.
      Bug 5:Show hint just flashed the title of the app. 

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input         | Expected Behavior             |    Actual Behavior            | Console Output / Error |
| -------       |-------------------            |-----------------              |------------------------|
|Hit New game   | To give a new game            | But old game still on display | No display of game     | 
|Lower/Higher   | Lower and higher              | Higher and lower              |  gives opposite        |
|wrong range    | range over difficulty level   | display of  range |                                        

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
  Claudecode
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
  fixing low and high. it was viceverse and AI suggested perfectly and I verified by running the live game.
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
  attempts initilization was given but it confused the purpose of fix

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
  By running the live game

- Describe at least one test you ran (manual or using pytest) 
  It calls check_guess with a guess of 60 and a secret of 50. Since 60 is higher than 50, the game should recognize this as "Too High" and tell the player to go lower. The assert line checks that the function returns that expected outcome
  and what it showed you about your code.

- Did AI help you design or understand any tests? How?
  Yes. I used Claude Code to both understand and improve my tests. First, it explained the difference between manual testing (running streamlit run app.py and clicking buttons myself) and pytest (writing assert checks that run automatically), which helped me see that pytest is best for the pure logic functions like check_guess

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
  Streamlit is a Python tool that turns a plain Python script into a web app — you just write st.button(...), st.text_input(...), etc., and it builds the page for you.every time you click or type, Streamlit re-runs your whole script from the top, so normal variables get reset each time.

  State (st.session_state) is the app's memory — a special box that keeps values (like your secret number, score, attempts) alive across those re-runs.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
  One habit I want to reuse is keeping a bug reproduction log before fixing anything — writing down the input, the expected behavior, and the actual behavior. Doing this forced me to confirm a bug was real and understand it clearly before I touched the code, instead of guessing. I also want to keep my habit of verifying every fix by running the live game, since that's how I caught that the Lower/Higher hints were backwards. And for pure logic like check_guess, I'll keep writing small pytest asserts so I can re-check the logic instantly without clicking through the app each time.
- What is one thing you would do differently next time you work with AI on a coding task?
  One thing I'd do differently is add my own # FIXME comments right where I spot a bug, before asking AI to fix it. In this project the starter code already had # FIXME: Logic breaks here markers, and they made it much easier to find the broken spots — so next time I want to leave my own markers as I investigate. This would help me give the AI a clearer, more specific prompt pointing to the exact line, instead of describing the bug vaguely. It would also keep me organized so I fix one tagged issue at a time and don't lose track of what's left.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
  This project showed me that AI-generated code can look polished and "production-ready" while still hiding real bugs, like the backwards Lower/Higher hints and the broken New Game button. Now I treat AI output as a starting draft I have to test and verify myself, not something I can trust just because it runs.
