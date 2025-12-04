---
tags:
  - SUI
  - to_be_finished
aliases:
  - agents
  - agent
  - Agent
  - Agents
---
# Agent System
An agent system is an encapsulation of a decision behaviour (neuron system, automata, etc.) with a pre-set input and output.
## Terminology
Some basic terminology involving agent systems:
### Agent
An agent has several components:
- **Sensors** (input) are ways the agent perceives its environment.
- **Actuators** (output) are actions the agent can do in response to its environment.**
### Agent Function
Agent function is a description of the agent's behaviour in response to its perceived environment. For this it uses:
- **Percept sequence** as input.
- **Action** as output.
### Agent Program
A realization of the agent function. This can take on many forms depending on the needed behaviour such as finite automata, neuron system, etc. This also includes design of the memory, states, etc.
### Agent Realization
Is the combination of **agent program** and the **architecture** (hardware).
## Rational Agent
A rational agent is one that acts the best as it can, depending on:
- Performance measure PM
	- Relation to the objective function
	- Influences the required behaviour
- Prior knowledge
- Available actions and percept sequence
Rationality is not perfection.
## Task Environment
An environment in which the task of the agent is carried out. In this sense this is similar to algorithm [[Task|task]] and [[State Space|state space]].
### Specification of Task Environment
Shortcut for describing the specification of the task environment is **PEAS**, which is comprised of **performance**, **environment**, **actuators**, **sensors**.
	An example of *PEAS* can be:
	- *P* - Resulting points
	- *E* - Exam room
	- *A* - Hand with pen (question selection: A, B, C, D)
	- *S* - Eyes (reading questions)
	This example models a student on a test with selection questions. The exam room can be omitted, the student can make actions by selecting 1 of 4 answers with their actuator hand, the sensors are their eyes by which they read the questions and the resulting performance is the score they get on the score.
### Environment Specifications
There are several specifications the environment can have such as:
- **Visibility** that is relevant to the aspects of task and environment relation (a robot vacuum can ignore the carpet's colour):
	- *Fully observable*
	- *Partially visible*
- How is the **Choice of Action** selected:
	- *Deterministic*
	- *Randomized* (Stochastic)
- **Confidence**:
	- *Confident* (Fully observable and Deterministic)
	- *Unconfident*
- **Amount of Agents** (only relevant if one agent is influenced by another, such as economics):
	- *Single agent*
	- *Multiagent*
		- *Competitive*
		- *Cooperative*
- **Continuity** either in *actions* or *runs* such as in computer games:
	- *Episodic*
	- *Sequential*
- **Time**:
	- *Discrete*
	- *Continuous*
- **Knowledge**:
	- *Known*
	- *Unknown*
### State Representation of an Environment
There are three main ways agents represent the current state of the environment within:
- **Atomic** does not consider the internal structure.
- **Factored** represents the state as attributes (variables with values). 
- **Structured** represents the state as objects and relations between them.
## Types of Agent Systems
Division of agent systems can be done in many ways, for example here it is done through the structure of agent programs:
### Reactive Agent
Also known as a **Simple Reflex Agent**. It does not have a history of perceptions and uses a if-then construction.
### Reactive Agent with Model
Also known as a **Model-Based Reflex Agent**. The model should reflect the reality of either the environment or the world it operates in. It can either simulate memory or it can remember what happened (save perceptions).
### Goal-Based Agent
An agent system that is driven by a single goal that it needs to achieve. A goal-based agent should be capable of moving from any place within the space to any other place within the space. This means it should be capable of more then just moving from any place to one specific concrete space.
An example of such system could be one that is trying to cook dinner. To cook dinner it needs to buy ingredience, but it doesn't have money. It first needs to gain money so it could buy the ingredience.
### Utility-Based Agent
An utility-based agent evaluates multiple ways of achieving the goal and selects the one that satisfies the task.
## Learning Agent
An agent that learns. This does not relate to the structure of the program. It is composed of several components:
- **Performance Element** selects the action based on the *current agent* function it gets from the *Learning Element*.
- **Critic** defines how after from a fixed performance standard the agent is. This is decided by observing the current environment state through sensors and giving *feedback* to the *Learning Element*.
- **Learning Element** learns from the *current agent function* in the *Performance Element* and from the *feedback* it gets from the *Critic*. Designs changes in the *agent function*.
- **Problem Generator** gets *learning goals* from the *Learning Element* and generates problems so the agent does not get stuck within *local solutions*.
---
### Sources:
- [[SUI_02_Agent_Systems.pdf]]