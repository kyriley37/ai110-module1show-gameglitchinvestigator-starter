# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

  Bug 1: Hint messages are backwards
When you guess a number that is too low, the hint tells you to go lower. When you guess a number that is too high, the hint tells you to go higher. The "Go Higher" and "Go Lower" messages are swapped, so the hint always points you in the wrong direction.

Bug 2: New Game button doesn't work after winning
When you win the game and click "New Game," the game does not actually restart. The screen stays frozen on the win state. The button only works correctly if you click it before winning. I think this might be because winning sets a "won" status that never gets cleared when the new game starts.

Bug 3: I noticed the attempts counter was always one number ahead of the actual number of guesses made. For example, after making 6 guesses the counter showed 7, and "Attempts left" showed one less than it should. I traced this to the session state initialization — attempts was set to 1 at the start of the game instead of 0, so the game was already counting a fake first attempt before the player did anything. Fixing the starting value to 0 made the counter match the actual number of guesses in the history.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
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

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
