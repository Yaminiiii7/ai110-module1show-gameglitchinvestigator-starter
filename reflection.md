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
  attempts initilisation was given but it confused the purpose of fix

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

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
