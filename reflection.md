# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

--- The game looked simple enough when I first ran it. When I played the game, I noticed that the hints were backwards, ie giving a number higher than the secret number produced a hint that says Go Higher and vice versa. Another issue I encountered is that clicking on New Game once I guessed the secret answer does not restart the game. Finally, the difficulty settings are kind of mixed up in the sense that Easy setting is harder than Normal and Hard setting.

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

--- I used Claude Code to help me with this project. The AI was very helpful in fixing the errors I pointed out and also showed me other logical flaws in the code. An example of its suggestion is to fix the logic for the difficulty wherein Hard should have more potential outcomes and less attempts. An incorrect suggestion it had was to set st.session_state.attempts to 1. Upon checking it, I asked it to double check this suggestion and it agreed that it was incorrect.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

--- I decided that a bug was truly fixed when I ran multiple possible scenarios with it in the game interface. For example, on the attempts input, I tried putting in a higher number, lower number, the correct number, letters, and symbols to see if potential error states are acounted for. I did both manual and pytest to ensure that everything was working perfectly. Running pytest only generated the results for me and the AI did not explain it. Only after reading this portion of the reflections file did I ask Claude to explain how it works.

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---Streamlit "reruns" is basically Python running the entire code from top to bottom whenever any interaction is made in the app. This prevents certain variable values to be saved. Session state is how we fix this problem. This can be thought about as memory and anything that is present in it will persist between reruns.

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

---One habit that I will reuse for future labs or projects is to seek help from the AI regarding logical choices or design choices I make in my code. Its a good way for me to know if there are possibilites I didn't account for and also error checking pieces of code instead of dealing with it when the entire program is written. One thing I would do differently is to tell Claude to not check for all bugs/fixes when I ask it to read a file for me. This project helped me understand how to use AI as an assistant rather than a tool to generate code. It also helped me realize that AI generated code may sometimes have flaws and you can converse with the AI to discuss how/why it generated a piece of code.