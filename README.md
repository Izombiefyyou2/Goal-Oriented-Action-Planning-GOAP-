# Goal Oriented Action Planning
It has always intruiged me how a games AI does its decision making. From deciding where to walk around to choosing between attacking or holding their ground.
So for this project I decided to research one of the many ways it can be handled, namely Goal Oriented Action Planning. <br />
Next to that there's also others I'd like to compare GOAP to, like Hierarchical Task Network Planning A.K.A HTN, to see what the pros and cons between them are. <br />
## What is G.O.A.P?
Now what exactly is G.O.A.P really? It's a way to create decision making in your AI of course. The title actually sort of explains it already, change up the words and you have a pretty easy and straightforward explanation.<br />
You give your AI a goal to achieve and then give it all sorts of different actions (every action has prerequisites and effects) it can take to eventually reach that goal, it then plans the best possible way to get to that goal. In other words the AI checks the world state and tries to change it to achieve it's goal<br />
I'll try to explain it more with an example
![alt text](https://www.aiandgames.com/wp-content/uploads/2020/05/vlcsnap-2020-05-04-10h22m05s673-1024x576.png "Example GOAP")
Say in this case your AI has a goal in another room and needs a way to reach that room. He is given the action to be able to open a door, in the example you see the prerequisites are that: <br />
* The door has to be closed.
* The door must be in the room the NPC is in.
* The door must lead to room B.<br/>
Once all the prerequisites are there, the action can take place and the effects then will occur.
## Existing Games
### F.E.A.R
A very known game that uses G.O.A.P is F.E.A.R, a first person action horror game from 2005.<br />
This isn't the only implementation of G.O.A.P used in games but it's one that's very easy to access as you can simply download the public source code and open it up in visual studio, plus it's the first very popular game to use this type of decision making for AI.
### Horizon Zero Dawn
An also very known game that's more recent is Horizon Zero Dawn.<br/>
This implementation can't be accessed quite as easy but it shows that even in more recent games this type of decision making is still a valid option.<br/>
In the next part of this document I'll explain why games like these 2 can use this type of decision making without many issues compared to how other games might have big issues with it.
## G.O.A.P vs H.T.N
Now that we know what G.O.A.P is and how it works, I thought it would be a good idea to see what another valid option is.<br/>
One of the biggest issues G.O.A.P faces is that it's very heavy to run, as every NPC has to constantly replan their approach whenever the world state changes.<br/>
H.T.N works more like a tree, in this tree there are 3 types of tasks you can have: <br />
* primitive tasks, which are simpler tasks.
* compound tasks, which can be seen as composed of a set of simpler tasks.
* goal tasks , which roughly corresponds to the goal, but are more general.<br/>
![alt text](https://www.researchgate.net/profile/Piper-Jackson/publication/225115074/figure/fig3/AS:667774657515531@1536221293427/Hierarchical-Task-Network-HTN-Example.png "Example HTN")
The problem H.T.N can face is that it is really expressive, which in general cases makes it so it's indecidable and thus can't function properly.
## Conclusion
G.O.A.P is a very interesting and good way of going through decision making for your AI, the problems it gives make it so not many NPC's can have it running at the same time. But with a bit of a smart workaround you can use it to create highly intelligent AI.<br />
Sadly i wasn't able to create my own implementation, my idea to make an implementation would be around a simple text based decision maker that is given a few problems and actions and seeing how to make it realise the best course of action.
