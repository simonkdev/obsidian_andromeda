2026-04-13 12:17

Tags: [[agentic AI]] [[computer science]] 

------------------------------------------------

### General:
An LLM-based AI agent expands an LLM's capabilities by leveraging different APIs like webcrawl-utlities to complete complex tasks autonomously. 

### Schematic:
![[Pasted image 20260413122144.png]]


### Components:
##### Long-term memory
- provides capability to retain and store theoretically infinite amounts of information for extended periods of time, often using external vector store

*view [[Long Term Memory]]*

##### Reflection and Self-Criticism
- judging the quality of its own results using prompting techniques, this allows for refinement of the agents' results, mimicking the ability to learn from mistakes

*view [[Reflection and Self-Criticism]]*

##### Chain of Thoughts (CoT)
- prompting technique that encourages an LLM to approach tasks in a step-by-step manner. Often generates the course of action the agent is to take using a separate model response 

*view [[Chain of Thoughts (CoT)]]*

##### Subgoal decomposition
- breaks down complex tasks into smaller sub-tasks, can be achieved using simple prompting techniques. Often generated using an LLM much like the CoT 

*view [[Subgoal Decomposition]]*

##### Tools in practice
- an AI agent may use APIs for specific tools, such as web search, code execution/validation  or similar

*view [[Tool APIs for agentic AI]]*




------------------------------------------------------
### References
https://lilianweng.github.io/posts/2023-06-23-agent/