# training-Freeplane-script-GPT

- What: Training a custom GPT bot to create Freeplane scripts 
  
- How: In order to train the bot, my method will be to create a sequence of tests that need to be passed by the bot. The tests increase in complexity. The idea is that, if the bot doesn't pass a test, I change the prompts and reference material until it does. This way, the prompt engineering focuses on building the foundational skills, first.

- This is the chat bot (Requires ChatGPT Plus): https://chat.openai.com/g/g-GHr7occhP-freeplane-scripts-creator

The bot uses actions to communicate with the Github repositories (see bellow), so it will ask for permissions when creating the script. 

Important: it is necessary that the bot makes the calls (it will show the message "Talked to api.github.com" or "Talked to raw.githubusercontent.com"). If it fails, it will show the message "Error talking to" and the quality of the code will be bad. If that happens, try to regenerate the answer until the calls are made succesfully.

- The prompt that I'm using: [prompt](prompt)

- The actions that I'm using: 
Those 2 from https://github.com/bapo2/gpt-actions

Github File Lister, 

Github File Reader

- The files that I'm using to feed the GPT: none (it seems that actions work better)

---
If you manage to make improvements in the GPT, please share it, so we can collectively work on it.

Please, share with with the Freeplane community any interesting scripts that you create.

⚠️Disclaimer: scripts can change the data in the map, and even another files in the PC (if permissions are given). So, be careful when using it. Before using a script in a map with important information, backup files and test extensively.

# Sequence of Levels
## I'm working here--->⬜ simple single method
The idea here is to make sure that the GPT is able to use every method, individually 
## ⬜ combination of simple methods
This step is very simple, and should not be a problem, once the previous one is achieved.
## ⬜ simple gui
Here, it's relevant to know things that are specific of Freeplane. For example: locationRelativeTo:ui.currentFrame
## ⬜ difficult methods and other special Freeplane conditions
For example:
- node change listeners
- execution modes
- Node at(String path)

## ⬜ complex gui
For example:
- Jumper Add-on
- Map Insight Add-on
- TabbedPanelMod Add-on
- Tutorial-o-Matic Add-on
## ⬜ internal methods
