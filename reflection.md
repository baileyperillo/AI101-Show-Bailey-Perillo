# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

  1. it takes inputs beyond the input - attempts variable initializes to 1, not 0
  2. the history is delayed when entering a number. It doesn't update the current number I put in, just the previous one - AI: banner subtracts attempt_limit - attempts

  2. wrong hint when input wrong asnwer
  3. It gives me the answer and penalty when I have 1 chance left.
  4. New Game button doesn't work
  5. The input box says I can press enter to submit when not true; does not appear again after you enter an input
  6. After I get penalty, it doesn't record another answer but will increase number of attempts
  
  With AI:
  7. Hard difficulty is easier than Normal difficulty in get_range_for_difficulty(difficulty) - CHOSEN PHASE 2
  2. wrong hint when input wrong answer check_guess(guess, secret) - CHOSEN PHASE 2
  8. update_score(current_score, outcome, attempt_number) rewards wrong guesses on even turns



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
