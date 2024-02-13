# training-Freeplane-script-GPT

- What: Training a custom GPT bot to create Freeplane scripts This is the chat bot:

  
- How: My method will be to create a sequence of tests that need to be passed by the bot. The tests increase in complexity. The idea is that, if the bot doesn't pass a test, I change the prompts and reference material until it does. This way, the prompt engineering focuses on building the foundational skills, first.

The prompt that I'm using:

The files that I'm using to feed the GPT:

If you manage to make improvements in the GPT, please share it, so we can collectively work on it.

Please, share with with the Freeplane community anything interesting that you create.

⚠️Disclaimer: scripts can change the information in the map, and even another files in the PC (if permissions are given). So, be careful when using it. Before using a script in a map with important information, backup files and test extensively.

# Sequence of Levels
## ⬜ simple single method
The idea here is to make sure that the GPT is able to use every method, individually 
## ⬜ combination of simple methods
This step is very simple, and should not be a problem, once the previous one is achieved.
## ⬜ simple gui
Here, it's relevant to know things that are specific of Freeplane. For example: locationRelativeTo:ui.currentFrame
## ⬜ difficult methods and other special Freeplane conditions
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
