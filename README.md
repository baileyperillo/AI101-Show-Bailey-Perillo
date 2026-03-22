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

- [x] Describe the game's purpose.
The game's purpose was for the coder to find bugs while playing the game and then use AI to fix these problems. We had to practice our own debugging skills as we tested and debugged AI code.
- [x] Detail which bugs you found.
There were multiple bugs. The first bug I worked on was changing the hint message when the player's guess was wrong. The messages were switched. The second bug I worked was changing the level of difficulty since the Hard level was easier than the Normal level. I also decided to change the number of attempts since I found it hard to test the changes.
- [x] Explain what fixes you applied.
I asked Claude both times to change the code in #logic_utils.py, then import it back into ap.py. To fix the first bug, the AI changed the check_guess function logic so now in the "Too High" condition would result with "Go LOWER!" and the "Too Low" condition would result with "Go HIGHER" message. Testing it resulted in Error that "'>' not supported between 'int' and 'str' in line 137 and the same logic bug in update_score on line 29. In check_guess, secret becomes a string and can't be compared to guess_int, which affects update_score as well. the AI fixed it by removing str() all together in line 137 and changing the formula to remove +1 from line 29.
The second bug was fixed by changing the difficulty range from (1, 100) to (1, 500). There was a miscommunication with the AI in that it ended up removing the function from app.py to logic_utils.py and not putting the updated version back. I had attempt multiple times to do so as it would try to put the original version back into app.py. It was eventually fixed.



## 📸 Demo

- [ ] [Insert a screenshot of your fixed, winning game here]
![Hard Difficulty](<../Desktop/Codepath AI101 Show Difficulty.png>)
![Go HIGHER!](<../Desktop/Codepath AI101 Show guess1.png>)
![Go LOWER!](<../Desktop/Codepath AI101 Show guess2.png>)

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
