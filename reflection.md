# 💭 Reflection: Game Glitch Investigator

## 1. What was broken when you started?

When I first ran the game, it seemed to work, but there were some problems with the gameplay. The hints were giving the wrong directions, and it was hard to tell if the game was comparing my guess correctly with the secret number. I also noticed that most of the code was inside app.py, which made it harder to read.
Two bugs I found were that the hint messages were backwards and that the game sometimes had issues comparing values correctly. After testing different guesses, I found that some of the logic needed to be fixed.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|Guess 60 when secret is 50 |Display "Go LOWER" | Displayed "Go HIGHER"| None |
|Guess 40 when secret is 50	 |Display "Go HIGHER"	 | Displayed "Go LOWER"| None|
| Winning guess| Consistent win detection| Comparison could fail due to string/int mismatch| None |

---

## 2. How did you use AI as a teammate?

I used ChatGPT to help me understand the bugs and figure out what parts of the code needed changes. It explained how Streamlit session state works and suggested moving some of the logic into a separate file.One helpful suggestion was moving reusable functions into logic_utils.py. After doing this, the code became easier to organize and test. I checked that everything still worked by running the app and using pytest. One suggestion was not completely correct because it focused on session state before checking the main game logic. After testing the game myself, I realized the biggest issue was the incorrect hint messages. This showed me that AI suggestions should always be tested.


---

## 3. Debugging and testing your fixes

I knew a bug was fixed when I could recreate the problem before the change and then confirm it was gone afterward. I tested the game by entering different guesses and checking the results.One test I ran was entering a number higher than the secret number. After fixing the bug, the game correctly displayed "Go LOWER." I also ran pytest to make sure the check_guess() function returned the correct results. AI helped me understand what the tests were checking and why they were important. It also showed me how separating code into functions makes testing easier.

---

## 4. What did you learn about Streamlit and state?

I learned that Streamlit reruns the whole script whenever a user interacts with the app. Because of this, variables can reset unless they are stored in st.session_state.
I would explain session state as a place where the app saves information so it can remember things between user actions. Without it, the game could forget values like the score or secret number.

---

## 5. Looking ahead: your developer habits
One habit I want to keep using is testing each bug after making a change. This helped me make sure my fixes worked and did not create new problems.
Next time I use AI for coding, I will spend more time checking its suggestions before applying them. I learned that it is important to test ideas instead of assuming they are correct. This project changed the way I think about AI-generated code because it showed me that AI can be helpful, but it can also make mistakes. Developers still need to test, debug, and verify the final code.
