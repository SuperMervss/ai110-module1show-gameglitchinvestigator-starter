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

- The game's purpose is to guess a chosen number between 1 and 50, 100, or 200 depending on the difficulty. The game tells you to guess higher or lower relative to the number you have chosen.
- Detail which bugs you found.
  1. Hard difficulty range incorrect — Hard difficulty was originally 1–50 which was easier than Normal which had 1-100.
  2. Scoring logic — Guessing a number higher than the chosen number on even attempts rewarded +5 points instead of deducting points.
  3. New game reset bug — Clicking "New Game" always generated a secret using randint(1, 100), ignoring the selected difficulty, and reset attempts to 1 instead of 0.
  4. Secret type bug — On even attempts, the secret was cast to a string, breaking the higher/lower comparison in check_guess.

- Explain what fixes you applied.
  1. Changed Hard difficulty range to 1–200 so it is harder than Normal.
  2. Removed the attempt_number % 2 condition so that guessing a wrong number always deducts 5 points.
  3. Fixed "New Game" to reset attempts to 0 and use random.randint(low, high) based on selected difficulty.
  4. Removed the string conversion so the secret is always compared as an integer.

## 📸 Demo

- ![Screenshot](<Winning Screenshot.png>)

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
