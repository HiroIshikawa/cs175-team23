---
layout: default
title:  Status
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/tdBFFRMu1i0" frameborder="0" allowfullscreen></iframe>

# Project Status
Our project's goal is to implement a speech-to-command application for Minecraft that allows the user to be able to play the game using just voice commands. The goals that the current iteration of our project can accomplish are the speech recognition portion, where we are able to convert a recorded speech into text format. Then we are able to take this text format and parse it using natural language processing, which is the focus of our project, in order for it to be interpreted by the Malmo command framework. Using Malmo, we are able to take these parsed commands and move the agent according to the vocal command.

### Approach
Speech Recognition
- Our approach is pretty straight forward here - we use Python speech recognition through Google Speech API in order to extract text from a recorded audio file to be used by our next step

Natural Language Processing
- After extracting text from user speech, we parse the speech using open-source NLP library, spaCy
- Using spaCy's dependency and part-of-speech parsing, we are able to navigate the parse tree, make sense of the user's commands, and translate them into valid Malmo commands

Malmo Commands
- After parsing the necessary text to be read as commands, we use the Malmo environment in order to process these commands
- Using "<ObservationFromNearbyEntities>" as our main method of accessing the state of the environment, we are able to analyze the environment and perform the necessary actions that reflect the voice command
- The agent also has algorithms implemented that take advantage of the Malmo environment to follow objects (like Mobs) and avoid certain obstacles while reaching an objective, such as jumping over a block in the way
- We also created a tkinter simulation window in order to visualize the simulation as a skyview like in mob_fun.py from the Python_Examples folder for Malmo

### Evaluation
Our project is currently performing well under the expectations placed on this project for this stage in development. We are able to perform basic speech commands and have the agent reflect those commands accurately. In addition, we accomplished the 'go to (object)' command in time for this stage of our project development. We still have many more ideas and commands that we would like to implement in order to make it work cleaner and be more user-friendly, but we are confident in our progress so far, and some features are currently in testing, but not yet ready for a demo.

Usage examples:

Chase a target with object avoidance:

![alt text](https://raw.githubusercontent.com/HiroIshikawa/speech2craft/master/docs/imgs/jump_and_chase1.png "Jump and chase target 1"){:height="50%" width="50%"}
![alt text](https://raw.githubusercontent.com/HiroIshikawa/speech2craft/master/docs/imgs/jump_and_chase2.png "Jump and chase target 2"){:height="50%" width="50%"}
![alt text](https://raw.githubusercontent.com/HiroIshikawa/speech2craft/master/docs/imgs/jump_and_chase3.png "Jump and chase target 3"){:height="50%" width="50%"}

Use tool and smoothly dig ground:

![alt text](https://raw.githubusercontent.com/HiroIshikawa/speech2craft/master/docs/imgs/use1.png "Use 1"){:height="50%" width="50%"}
![alt text](https://raw.githubusercontent.com/HiroIshikawa/speech2craft/master/docs/imgs/use2.png "Use 2"){:height="50%" width="50%"}
![alt text](https://raw.githubusercontent.com/HiroIshikawa/speech2craft/master/docs/imgs/use3.png "Use 3"){:height="50%" width="50%"}

### Remaining Goals and Challenges
Our project prototype is currently limited by the number of commands that it is currently able to interpret, as well as the ability for the agent to perform like a human. For improving what we have currently, certain features, like the obstacle avoidance feature, can be improved and further tested, but is working relatively well in our customized testing environment.

For the final report, we would like to implement many more commands, such as "move until hitting a wall" or "attack the zombie". We would also like to implement more AI algorithms in order to make the agent's movement and actions more fluid in a "real-world" Minecraft environment. One last thing we would like to add is word-vector similarity scoring, in order to incorporate a larger span of possible user inputted commands. 

Given our experience so far, some of the challenges we face for completing our goals for the final report include: adequately parsing more advanced sentences, accurately reflecting some of these more advanced actions in Malmo, implementing any AI qualities in the agent for more advanced movements ("attack the zombie and come back"), and properly executing user-friendly functions (queueing up commands or overriding current commands).


