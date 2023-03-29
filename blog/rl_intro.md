# A Basic Intro to Reinforment Learning

Reinforment Learning (RL) has recieved a lot of attention within the NLP field. Partly because of
ChatGPT and other works that have succefully used human feedback to training large language models (LLM).

In the middle of all this exitement, I decided to take a closer look at the basic components of RL
and jot notes down. This document is more of a summary highlighting some the important fundational
concepts needed to communicate and understand the ideas and concepts in RL. This by no means is a
complete thing, but its the things I found useful and important to understand to start getting my
hands dirty with RL.

## An agent and its enviroment

In RL you have an **agent** and **enviroment**. The agent lives within this enviroment and interacts
with  this enviroment by taking **actions**. At every step, an agent asks itself the question:
**What action should I take?**

For every **action** that the agent take within the enviroment, its recieves a **reward**. This
reward tells the agent how good or bad that action was. If its a good action, then its a high reward.
If its a bad its a low reward. Ultimately, the agent wants to maximize the cumulitive reward.
This is known as the **return**.  

## States and Observations

An enviroment contains **states** which describe the state of the world. In a state, $s$ , all the
information is available and nothings is hidden. An obeservation, $o$, is a partial description of
the state. An observation may omit information from the state.

**fully observed**: The agent can obeserve the complete state of the enviroment.
**partially observed**: An agent can only see an observation.  

## Action Spaces

When an agent is in an enviroment, it can take different types of actions. If we take a LLM as an
agent, then at each decoding step the model has the option to choose a single token or subword within
the vocabulary. This will be considered as a **discrete action space** because there are a finte
amount of actions that the agent can take. On the hand, a robot can take real life actions (e.g move
forward, move left, etc).  This would qualify as a **continous action space** because the actions are
real valued vectors defined everywhere in the space.

## Policies

A policy defines how the agent decides to take an action. In an LLM, you can define the policy
to be $\pi$:

$$ a_t \sim \pi_{\theta}(\cdot | s_t) $$

Here, an action, $a_t$ is sampled from the policy $\pi_{\theta}$ given the state, $s_t$.
The policy, $\pi_{\theta}$ has parameters $\theta$. You can think of this as an LLM where $a_t$ is
the next word.

**Note**: It seems like in the literaty the word "agent" and "policy" are used interchangibly.

There are different types of policies:

**Categorical**:
