---
layout: post
title:  "Engineering Capstone Project Part A"
---

# Building a System for Managing Satellite Trajectories

To build a system for managing satellite trajectories, you need to consider several important components.

1. **Establish Communication Between Satellites:** This can be achieved by using existing satellite communication infrastructure, which allows most existing satellites to immediately become part of the network. It also prevents the need for modifications.

2. **Manage and Store Satellite Data:** This involves processing data and outputting a control maneuver that optimizes the trajectory of each satellite. To achieve this, you need to use machine learning algorithms. These algorithms should be trained to prioritize actions that minimize fuel usage, increase useful mission time, maintain power levels, decrease chances of catastrophic failure, and optimize overall efficiency. The algorithms should also account for the benefit of individual satellites as well as the overall collective satellite system.

3. **Flexibility:** The system should be flexible and allow for independent configuration of priorities for each satellite. For example, some satellites might prioritize minimizing fuel usage, while others might prioritize time over a particular area or maintaining a particular distance from other satellites.

4. **Account for Orbital Hazards:** The system should account for not only connected satellites but also space junk and other orbital hazards. Ground tracking systems can provide up-to-date information on these hazards, which can be used to adjust satellite trajectories as needed.
Use an Open Standard: Use an open standard that can be incrementally improved and built upon. This will allow the system to adapt to changing needs over time.

5. **To implement this system,** you will need to develop machine learning algorithms that can account for the specific priorities and requirements of your satellite network. These algorithms should be supported by other physics software that performs pre and post-work on the data to account for the actual physics or maneuver calculations.

Overall, building a system for managing satellite trajectories requires careful consideration of communication, data management, machine learning algorithms, and system flexibility. By following these guidelines, you can develop a system that optimizes the trajectory of each satellite and ensures overall efficiency and safety for the entire satellite network.

---

# Initial Thoughts

- So it seems the most important components here would be:

    - Communication between satelites
    - Managment and storage of other satelite data
    - Processing the data and outputting a control manouver

- This assumes the satelites only need to manage trajectorys once already placed in orbit.
- The ML Algorith will have to be trained to reward and condone certain actions as well as prioritising these actions in order of benefit or severity.
    - Rewards could be:
        - Minimising fuel usage
        - Moving satelites to create long term stability and optimisation for the whole collective
        - Increaing the useful mission time
        - Decreasing chances of catestophic failure should a collision occur
        - Maintaining power levels
    - Condonements could be:
        - Using two much fuel
        - Causing a collision
        - Reducing collective optimisation and efficiency

    - Having the system be flexible would be valuable.
        - The system can allow for indepentant configuration of the priorities for each satellite.
            - Minimising fuel usage
            - Time over a particular area
            - Distance from other satelites or maintaining swarm structures
        - Should integrate existing data and act autonomously if required.

    - The system should be able to account for the benefit of individual satelites as well as the overall collective satelite system.
        - This way overall efficiency can be considered

- The system will need to account for not just connected satelites but also space junk and other orbital hazards.
    - Ground tracking systems could still uplink to satelites to keep this data updated.

- The system should use existing satelite communication infrastructure
    - This way most existing satelites can immediatly be brought on to the network
    - Prevents the need for modification

- Satelites can share data directly with each other
    - Will take pressure and the onus off ground based systems
    - Allows for a graph theory based system where each satellite is considered as a node in the network
        - Data from two satelites seperated geograpically but connected by a shared link or links should be communicatable
    - Provents tampering and removes ground based systems as a point of failure.
        - Should one satelite get information to move but other satelites don't adjust to account for this a catastopic result could occur

- Should promote and use an open standard that can be incrementally improved and built upon

- A ML alogithm or several could be trained to account for these requirments
    - The inputs and outputs are relativly simple in that all the movements are based on physics and really this is an optimisation problem
    - The ML should be supported by other physics software to perform pre and post work on the data so that the ML does not need to account for the actuall physics or manouver calulations
        - Give this the ML should be trained to output set manouvers and input organised trajectory data