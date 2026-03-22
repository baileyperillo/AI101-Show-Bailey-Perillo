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
I used Claude Copilot for this project. One of the AI suggestions that were correct was when finding to find the source of the bugs in the code. I verified it when I changed some of the code and got an error in the game. One of the AI suggestions that were incorrect was when the AI changed the code and it caused a big error in the game because it did not look at the whole code or consider how it would affect other functions.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed? 
    I ran the game and tried the specific features I changed.
- Describe at least one test you ran (manual or using pytest)
  and what it showed you about your code.
  I inputted different inputs, usually numbers, and submitted it to see what message I was given, then compared it to the secret number and the history. In the code, it showed that the messages were in the wrong conditions. 

- Did AI help you design or understand any tests? How?
    The AI helped me understand some of the tests in that I didn't really know what line of code specifically caused some of the found bugs. The AI was able to name the line and explain why it was not correct, and then I verified.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
  I didn't really think about the reason why. My guess is because a random function was used to generate the secret number. Using random and state could change the random generator for every new game.

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
Stramlit is an open-source python library used for creating interative web apps. Streamlit "rerun" halts Streamlit from executing anymore code, puts the code script into a queue, then reruns the script. This is good for seeing updates in the application in realtime. However, can lead to slower performance as it is rerunning each time. Session state is a way to share variables between reruns.


- What change did you make that finally gave the game a stable secret number?
I didn't know I had to give the game a stable secret number. I don't even think I encountered that during testing in Phase1. Therefore, I did not change anything to give the game a stable secret number.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
I want to practice looking at the AI code before actually testing it. I would more find the problems after running the code. I also should practice being more aware of what the AI is doing rather than trusting that it has the same logic as me when solving. I would like to practice better prompts.

- What is one thing you would do differently next time you work with AI on a coding task?
I would like to look at the code or maybe even ask the AI to explain how they are changing the code before approving it. It was a little difficult for me to focus on what was changed before approving.

- In one or two sentences, describe how this project changed the way you think about AI generated code.
It has changed the way I think about AI generated code in the fact that I realize that I have to be more aware of the actions that the AI does when making code and that I ,myself, understand the logic of both what the original code is doing, what it's supposed to do, and what the AI is trying to code. I also need to be careful about closing the AI chats.