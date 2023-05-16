---
layout: post
title:  "Engineering Journal"
---

# Thoughts

- Currently looking at refining and expaning my knowledge of ai models, differential equations and orbital mechanics.
    - Reading through the book Fundamentals of Astrodynamics.
    - Generating vector field simulations for differential equations
    - Writing a 2 dimensional GA and NN based Satellite avoidence system in p5.js

- Investigating the use of a Deep Q-Network (DQN)
- Considering whether or not its simpler to model each orbit as a plane so that the software is only considering a 2D subset.
    - Would need to workout how to incorporate overlaps.

# Work Completed
- Finished creating a 2D environment for the orbits
    - First going to attempt to have satellites reorganise themselves so they are equidistant along a single orbit. 
        - They will start at random points, altitudes and perhaps orbital shapes.

- Re-wrote the 2D environment in Python it was previously javascript. This allows for better access to ML Librarys like Tensorflow
- Ran a Deep Q-Learning model after hours of trial and error to train an agent to solve the OpenAI Cartpole problem.
- Started formatting the 2D environment in a way that would be viable when applying the q-learning algorithm.
- Finished the formatting after many hours.
- Integrating with the q-learning model was easier than expected. 
- Setup saving and loading for the model weights.
- Note: changed the previous idea from equidistant satellites to a simpler first problem. Now I initialise a satellite with a random position and velocity. This agent is then rewarded for how circular it can keep the orbit.
    - The rewards are as follows:
        - 5 Points for managing to reduce the change in altitude when compared to the last step.
        - Negative 100 points for hitting the planet or straying to far (500 distance units).
        - Negative 10 Points for large deviations in altitude (greater than 10 distance units).
        - Negative 0.1 Points for any fuel usage tracked as use of the thrusters. Satellite starts with 100 units. (This is likely contributing little to the training as is)
    - The idea is this is a good first attempt at running these ai models and will help as a foundation for scalling to 3 Dimensions, considering more parameters (such as pertubations) and including other satellites to represent a DSS.

All this progress can be tracked on my GitHub.

# Sources

- OpenAI Gym Tutorials
- Coding train for NN Background
- Code Bullet for Q-Learning Examples
- ChatGPT for code explanation, debugging and q-learning information

# Tools and Dependancies

- Tensorflow
- Python
- ChatGPT
- P5.js
- Javascript

