# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
The hints were backwards. When guessed higher, it says go higher
- List at least two concrete bugs you noticed at the start  
Hints being backward. and the developer tools had a glich when you open it
  (for example: "the secret number kept changing" or "the hints were backwards").

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
Initailly i aksed it to plan and suggest based on what i see as error. I saw that the hint was opposite, points was obshet and new game didnot start.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
Suggestion about hint being opposite was valid and it changed it correctly
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

Still finding trouble with the bug with openinig developer panel. 
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I tried running in streamlit and also tried some edge cases
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?
When using 100 or 0 as your guess sometimes the code broke and AI helped me change the code

---

## 4. What did you learn about Streamlit and state?

The secret number kept changing because Streamlit reruns the entire Python script from top to bottom every time any widget changes  including clicking a button. In the broken app, st.session_state.secret = random.randint(low, high) was inside a block that ran on every rerun, so a fresh random number was generated each time. Streamlit "reruns" means the script executes again as if from scratch; st.session_state is a dictionary that survives between those reruns, so any value you want to persist (like the secret number) must be stored there and only initialized with an if "key" not in st.session_state guard. The fix that gave the game a stable secret was wrapping the initialization in if "secret" not in st.session_state, so the random number is only chosen once per game session.


- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

Using planning mode before actually allowing it to code is very helpful. I would laso try to look for asnwer rather that trying to figure out by my self because after somepoint it is going to burn a lot of credit.
