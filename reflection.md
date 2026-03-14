# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

---
  ### 1. The Guess hint message is misleading. 
  While testing the guessing feature, I noticed the message below the input says, “Guess a number between 1 and 100.” I decided to test whether the program would accept values outside this range by entering negative numbers. The application accepted -1 and generated the hint “Go LOWER!”, which seemed misleading since the guess was already outside the stated range. I also tested -100 and received the same hint, and when I entered 199, the game responded with “Go HIGHER!”. This suggests the hint logic may not be validating whether the users guess is within the intended range before generating guidance.

  ### 2. The Show hint check box
  I noticed there is a Show Hint checkbox located below the input where the user submits their guess. To test its functionality, I unchecked the tick from the box to see if the hint message would disappear. However, the hint still appeared below the “Make a guess” message even after the checkbox was unchecked. From what I observed, the checkbox does not seem to control the visibility of the hint as expected. This may indicate that the checkbox state is not connected to the hint display logic.

  ### 3. Score?
  So it seems like the score after I attempted all 8 attempts is -30. Still need to further envistage this. 

  ### 4. New Game generator button
  After using all eight attempts, the game displayed the message “Game over. Start a new game to try again.” I clicked the New Game generator button expecting it to start a new guessing session. However, it did not appear to reset the game or allow me to begin another round. From my testing, the button seems to work while a session is still active but not after all attempts have been exhausted. Ideally, the button should allow users to start a new game both during and after a completed session.

  ### 5. No Session Renewal after switching from Difficulty levels
  I navigated to the settings sidebar where users can choose the difficulty level for the guessing game. After finishing a session in Easy mode, I selected Normal difficulty to start another game. However, the application did not allow me to submit a guess and instead displayed a message asking me to start a new game. This behavior appears related to the issue where the New Game button does not properly reset the session. It seems possible that switching difficulty levels is not creating a new game session.

  ### 6.  Range per Difficulty level is not updated in hint message
  While switching between difficulty levels, I noticed that each level displays a different range for the numbers. For example, when I selected Easy, the range shown below the difficulty selector was “Range: 1 to 20.” However, the hint message below the guess input still said “Guess a number between 1 and 100. Attempts left: 4.” This suggests the hint message is not updating to reflect the range associated with the selected difficulty level. I did notice that the number of attempts does update correctly when the difficulty changes.

  ### 7. Attempts mismatch between difficutly level selector and Hint message
  While testing different difficulty levels, I noticed a mismatch in the number of attempts displayed. For example, the Hard difficulty indicates “Attempts allowed: 5,” but the hint message below the input shows “Attempts left: 4” before any guess is submitted. The same behavior appears with other difficulty levels as well. For instance, Normal shows “Attempts allowed: 8,” while the hint message displays “Attempts left: 7” immediately when the game starts. This suggests the hint message may be decrementing the attempt counter before the user submits the first guess..

  ### 8. The Guess message hint is misleading II
  While testing the game, I used the Developer Debug Info feature displayed below the hint message. The debug panel revealed the secret number for the session (for example, Secret: 47). I then entered 50 as my guess, but the hint message responded with “Go HIGHER!”, even though the correct direction should be lower to reach 47. I also noticed the guess history displayed in the debug panel did not record my first guess immediately. The first input only appeared in the history after I submitted a second guess, suggesting the guess tracking may be delayed or not updating on the first entry. 

  ### 9. Possible Difficulty Range Incosistency 
  While exploring the difficulty levels, I noticed that Easy uses a range of 1 to 20, Normal uses 1 to 100, and Hard uses 1 to 50. This ordering seemed unusual because the ranges do not progressively increase with difficulty. I initially expected something like Easy: 1–20, Normal: 1–50, and Hard: 1–100 so that the guessing range becomes larger as the difficulty increases. Because of this, I was unsure whether the current configuration is intentional or if the ranges may be incorrectly assigned. This may not necessarily be a bug, but it stood out while testing the different difficulty settings.


## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
  I used Claude Code. 
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
