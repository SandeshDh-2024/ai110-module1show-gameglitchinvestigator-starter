# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
=> The game looked like a normal number guessing game when I first ran it. It seemed to work as expected, but after a few tries you start noticing a few things that seem off.
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
=> Type Mismatch in Guess Comparison: On even attempts, secret is converted to string, causing TypeError and incorrect string-based comparisons (fails for multi-digit numbers like '50' vs '100'). 
=> Backwards Hints: Messages are inverted – "Too High" suggests going higher (should be lower), and "Too Low" suggests going lower (should be higher).
=> New Game State Reset Issues: Doesn't reset status or history; secret hardcoded to 1-100 instead of difficulty range.
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
=>Copilot
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
=> 
The suggestion was correct.
I’m noticing a bug in the check_guess function: it returns "Too High" with the advice "Go HIGHER," which is inverted. I need to fix this, so if the guess is greater than the secret, the message should instead say "📉 Go LOWER!" Actually, looks like the hints might be reversed too. I’ll need to adjust the messages accordingly and open the tests to verify expectations. Let's make sure everything aligns!
I used pytest created by copilot to verify.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
=> I checked the streamlit website after the fix for one of the bugs and copilot created test cases for another one.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  => I used pytest to test the Backwards Hints bug. It showed that the bug was fixed as the pytest checked three separate tests passing.
- Did AI help you design or understand any tests? How?
=> The AI designed and executed the pytest. It did not let me help or help me build or test anything.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
=> Streamlit "reruns" is a feature in python to rerun the entire code from top to bottom everytime a user interacts with the website. Whereas session state is a dictionary that lets the variables to be stay and be shared during a user's session.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
  => I will start by allowing the AI to focus on specific task rather than just allowing it to do whatever it wants by giving specific prompts and comments in the code.
- What is one thing you would do differently next time you work with AI on a coding task?
=> Generating pytest cases might be one thing i might do regularly in my future projects.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
=> I thought AI generated code was not good and with a lot of bugs, but with a few tweaks here and there I realized it is not that bad. 
