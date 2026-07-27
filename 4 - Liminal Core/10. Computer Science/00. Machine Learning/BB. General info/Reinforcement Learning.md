2026-07-19 18:44

Tags: [[machine learning]]

------------------------------------------------

### Abstract:
The goal of reinforcement learning (RL) is to learn a policy $\pi$ that enables an agent to maximize the expected cumulative return $G_t$​. A policy maps each state to an action (or, more generally, a probability distribution over actions) that the agent executes while interacting with its environment. RL is particularly well suited to robotics and other sequential decision-making problems, as it allows an agent to improve its behavior through trial-and-error interactions guided by reward signals.

### Agent and Environment
When trying to solve a problem using RL, the agent refers to the medium you want to leverage to control the environment. You could also say the agent is what you can directly influence, while the environment is what you ultimately want to change. 

For example, if I want to teach a robot how to drive, I could define the problem as the robot's limbs being the agent: I can directly influence their movement, position and other actions like rotation, opening/closing etc. What I want to change is the car's movement, direction and speed. This requires the robot to actually know how to move its limbs correctly. If this is not given, I must define my problem differentlly. I could also define my problem in multiple, smaller programs. 

For the given example: 
![[Pasted image 20260719185336.png]]


### Markov Decision Process (MDP)
The MDP describes a series of state, action and reward. An AI is presented with the state, which refers to the impressions it gets about the environment. This is similar to senses: It can be e.g. visual, tactile or audial. Now it has to decide on an action. This can be anything that the agent can fulfill, e.g. limb movements if the agent is the body of our robot. The action the robot decides to take determines what reward it gets, be it positive or negative, big or small. 

Expanding on the example of teaching a robot to drive in multiple steps:
![[Pasted image 20260719185741.png]]

The MDP itself is the series of state, action, reward that defines the learning process. The series can either go on forever or terminate, the latter would be the end of an "episode" (e.g. failing a level in a videogame). Most of the time a series starts with a state, and the rewards mark the beginning of one step. So basically:
![[Pasted image 20260726140234.png]]
Since my primary learning source is denotes it differently (the reward ending a step instead of starting one), formulas from other sources might differ in the timesteps a bit.

### Markov Property
The Markov Property requires that each state is a sufficient summary of everything in the past that is relevant for predicting the future. For example, when training a robot to catch a ball, you need to give it the balls movement vector (as well) and not just the balls position, since it would have to examine multiple timesteps to determine the speed and direction that it is going, which are both relevant for the learning process. 

Not every single problem fulfills this property, therefore they need an RL method designed around the fact that they have multi-step dependencies. Most methods assume the markov property to keep it simple.

### Decision-making
The goal of the agent is to, for any timestep, use the given state (input) to decide on an action (output) to maximise the subsequent rewards over time.
The mathematical function that maps a state to an action is called the policy. It is denoted as $\pi$, and there are two types of policies:

#### Deterministic policy:
When the agent is in a specific state, it always chooses the same action. Denoted as $$\pi(s)$$

#### Stochastic policy:
The policy assigns a probability to each possible action given a specific state. For example, at an intersection, a robot has multiple actions to choose from, none of which are inherently wrong (left, right, straight). This is denoted as:
$$\pi(a | s)$$
and resolves to a probability (read as "probability of action a given the state $s$").


### Rewards
The reward for any timestep $t$ is defined as follows:
$$G_t = r_t + yr_{t+1} + y²r_{t+2} + y³r_{t+3}...$$
With $y$ being the "discount factor", defined as  $0 <= y <= 1$ 
A smaller value for this discount would result in distant future rewards being less relevant, while a discount of 1 would make all equal (only works for terminating episodes, else it would add up to infinity).


## Further concepts:










------------------------------------------------------
### References
https://www.youtube.com/watch?v=VnpRp7ZglfA