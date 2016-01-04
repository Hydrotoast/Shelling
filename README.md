**ShellingSegregation** is a Julia implementation for simulating Shelling's
Segregation Model.

Usage
=====

```julia
> Shelling.simulate_random([50, 50])
INFO: Simulating Shelling's segregation model
INFO:   50 agents of kind 1
INFO:   50 agents of kind 2
INFO:   10 neighborhood size
INFO:   0.6 similarity threshold
INFO: Starting simulation
INFO: Iteration 1: 61 unhappy agents
INFO: Iteration 2: 14 unhappy agents
INFO: Iteration 3: 1 unhappy agents
INFO: Iteration 4: 2 unhappy agents
INFO: Iteration 5: 1 unhappy agents
INFO: Iteration 6: 1 unhappy agents
INFO: Iteration 7: 0 unhappy agents
INFO: Converged at 7 iterations
```

Model
=====

As an agent-based model, we model each agent with two properties: a kind and a
position. Each agent decides whether or not they want to move from their
current position based on their nearest neighbors and their preference for
agents of a similar kind. An agent is unhappy if their preference for agents of
a similar kind in their neighborhood is unsatisfied.

The model itself has a few global properties. These properties include a
neighborhood size and a similarity threshold. The neighborhood size defines the
number of closest neighbors that an individual agent with base their decision
to move against. The similarity threshold defines the proportion of neighbors
that must be of the same kind for the agent to decide to stay.

Simulation
==========

We simulate the model by discrete iterations. Each iteration, proceed as follows:

1. Find all unhappy agents
2. For each unhappy agent, find a position where the agent is happy (but do not move them yet)
3. Move all unhappy agents to their new positions
4. Repeat until all agents are happy
