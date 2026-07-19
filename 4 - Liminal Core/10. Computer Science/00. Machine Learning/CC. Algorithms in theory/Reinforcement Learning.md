2026-07-19 18:44

Tags: [[machine learning]]

------------------------------------------------

### Abstract:



### Agent and Environment
When trying to solve a problem using RL, the agent refers to the medium you want to leverage to control the environment. You could also say the agent is what you can directly influence, while the environment is what you ultimately want to change. 

For example, if I want to teach a robot how to drive, I could define the problem as the robot's limbs being the agent: I can directly influence their movement, position and other actions like rotation, opening/closing etc. What I want to change is the car's movement, direction and speed. This requires the robot to actually know how to move its limbs correctly. If this is not given, I must define my problem differentlly. I could also define my problem in multiple, smaller programs. 

For the given example: 
![[Pasted image 20260719185336.png]]


### Markov Decision Process (MDP)
The MDP describes a series of state, action and reward. An AI is presented with the state, which refers to the impressions it gets about the environment. This is similar to senses: It can be e.g. visual, tactile or audial. Now it has to decide on an action. This can be anything that the agent can fulfill, e.g. limb movements if the agent is the body of our robot. The action the robot decides to take determines what reward it gets, be it positive or negative, big or small. 

Expanding on the example of teaching a robot to drive in multiple steps:
![[Pasted image 20260719185741.png]]



------------------------------------------------------
### References
https://www.youtube.com/watch?v=VnpRp7ZglfA