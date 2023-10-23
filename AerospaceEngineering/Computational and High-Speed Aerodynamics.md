---
layout: post
title:  "Computational and High-Speed Aerodynamics"
toc: true
---

# Review of Aerodynamic Concepts

## Physical Quantities

* Every physical quantity can be expressed in terms of 4 fundamental properties
	* Mass (m)
	* Length (L)
	* Time (t)
	* Temperature (T)
	

## Properties of a Fluid
* Density
* Viscosity
	* No-Slip Condition
	* Gives rise to most important aerodynamic concepts
* Pressure
	* Normal force

## Dimensional Analysis
* We often have to rely on experiments to determine the answers
* We use dimensional analysis to reduce the number of variables we need to experimentally consider.


# The boundary layer concept (prandtl)

- In the flow past an airfoil, vicsous effecrts are mainly confined to a thin layer close to the surface of the airfoil (the boundary layer) and its wake.
- The BL is dominated by viscocity while the outer region can be considered inviscid

## Origin of boundary layer

### No-slip condition

- At a solid boundary, the fluid will have zeo velocity relative to the boundary. Molecules of fluid right at the surface stick to the surface as flow moves past.

- The flow around a body is determiedn by the action of viscosity in a thing later in th eimmediate vicinity of the body surface. 

- In this thin layer, fluid velocity increases from zero at the wall to the external flow value, where viscosity may be ignored.

- Even thought viscosity may be small, the shear stress will still be large near the wall, because of the large velocity gradient.

## Definition of boundary layer profile

- A boundary layer profile is a plot of streamwise velocity, U, against perpendicular wall distance, y. The boundary layer charecteristics are very sensistive to the shape of the profile.

- A comparison between two profile shapes is best made by using nondimensional profiles. In these profiles $U_1$ is the freestream velocity and $\delta_{99}$ is the 99% boundary layer thickness (defined as the point where the velocity reaches 99% of the freestream value).

## Boundary layer thickness

- The boundary layert thickness grows as the flow proceeds over the body, as more flow is affected by fluid friction as the flow proceeds over a body.
- There are different ways to define a boundary layer
	- **Physical Thickness:** 99% thickness, $\delta_{99}$, is the wall distance where velocity reaches 99% of the freestream value.
	- **Displacment Thickness:** Displacment thickness, $\delta^{star}$ is the distance that the external streamlines of the outer potential flow are shifted due to presence of the boundary layer.
		- Same mass flow rate would occur for frictionless flow if boundary was moved out by $\delta^*$
	- **Momentum thickness:** Thickness of freestream fluid with same momentum as the momentum defect due to the boundary layer

## Some definitions

- Viscosity is responsible for the formation of shear stress $\tau = {\mu \partial u /\partial y}$
- $\mu$ is the coefficient of **dynamic** viscosity and v is the coefficient of **kinematic** viscosity: $v = \mu/\rho$
- Viscosity is a physical property of a fluid and it varies differently for gases and fluids
	- Variation with T 
		- Liquids $\mu$ decreases as T increases
		- Gases $\mu$ increases as T increases.
		- For air at sea level conditions: $\mu = 1.7894 \times 10^{-5} kg/(m\cdot s)$ and $v = 1.4607 \times 10^{-5} m^2/s$
- Reynolds number is a measure of the ratio of inertial forces to viscous forces

$$
Re = {
	{\rho_{\infty} V_{\infty} L} 
\over 
\mu_{\infty}
} 
= 
{
{V_{\infty} L} 
\over 
v_\infty
}
$$

- Exact similtude will only exist between a wind tunnel model, CFD analysis and a real aircraft at the same Re.

# CFD

## What is CFD?

- Computational fluid dynamics
- How to define it.
	- Simulating fluid flow, heat transfer, mass transfer, and related phenomena by solving governing equations numnerically.
- Technically even a computer solution of potential flow is CFD although we usually reserve the term for more complex Navier-Stokes based simulations.

## Why is it useful?

- Avoids experimental costs and issues
- Unfortuantly the full Navier-Stokes equations cant be solved so we need to model and validate it with real-life testing at some point in the design cycle.

## What are the steps in performing CFD?

1. Choose the mathematical model
2. Make an other simplifying assumptions
3. Define the region of fluid you want to simulate
4. Mesh (discretize) the fluid region
5. Define the fluid properties 
6. Run the solver
7. Examine the results

## Naiver Stokes Equations

- Most complete mathematical model describing the flow of a fluid.
### Typical version of the equation:
$$
\nabla \cdot u = 0 \quad \textrm{Conservation of Mass}
$$

$$
\rho {du \over dt} = {- \nabla p + \mu \nabla ^2 u + F} \quad \textrm{Newtons Second Law}
$$

### Continuity equation

$$
{\partial p \over \partial t} + {\partial (pu) \over \partial x} + {\partial(pv) \over \partial y} + {\partial (pw) \over \partial z} = 0
$$

- Rate of change of mass within a control volume is equal to the sum of the $\dot m$ flow in - $\dot m$ flow out

#### Derivation

- Mass of fluid in the control volume, density time volume:
$$
\rho \cdot dx \cdot dy \cdot dz
$$

- where: dx, dy, dz are the sides of the control volume.

- Rate of change of the mass is:

$$
\partial (\rho \cdot dx \cdot dy \cdot dz) \over \partial t
$$

- Of course dx, dy, dz are not changing with time, so:

$$
{\partial \rho \over \partial t} dx \cdot dy \cdot dz
$$

- Now we consider the flow in and out of the control volume. At every point in the control volume the fluid will have a velocity vector. Denoted:

$$
\vec V = ui + vj + wk
$$

- Consider the opposite sides of the cube, only the flow in that direction will move fluid across the boundary, the other flow vectors are tangental. So for the horizontal direction the only component of importance for flow rate is u. So the volume flow rate is:

$$
u \cdot dy \cdot dz
$$

- To turn that into a mass flow rate we multiply by the density.

$$
\rho \cdot u \cdot dy \cdot dz
$$

- Now we turn this into a net mass flow equation, so mass flow in minus mass flow out.

$$
\rho \cdot u \cdot dy \cdot dz - \rho (u + {du \over dx} dy \cdot dz)
$$

- Expanding gives:

$$
\rho u \cdot dy \cdot dz - \rho u \cdot dy \cdot dz - \rho {du \over dx} \cdot dx \cdot dy \cdot dz
$$

- Canceling the front terms leaves us with:

$$
 - \rho {du \over dx} \cdot dx \cdot dy \cdot dz
$$

- This is the net mass flow rate into the box through the two horizontal sides. Considering this for all the other sides:

$$
 - \rho {dv \over dy} \cdot dx \cdot dy \cdot dz
$$

$$
 - \rho {dw \over dz} \cdot dx \cdot dy \cdot dz
$$

- We substitute these into the orignial stated equation, $\dot m = \dot m_{in} - \dot m_{out}$

$$
{\partial \rho \over \partial t} dx \cdot dy \cdot dz =   - \rho {du \over dx} \cdot dx \cdot dy \cdot dz - \rho {dv \over dy} \cdot dx \cdot dy \cdot dz  - \rho {dw \over dz} \cdot dx \cdot dy \cdot dz
$$

- Divide by $ dx \cdot dy \cdot dz$:

$$
{\partial \rho \over \partial t} + \rho ({du \over dx} +  {dv \over dy} +  {dw \over dz})  =  0
$$

- So term one is the mass flow, term two is the net flow in the x direction, term two is the net flow in the y direction and term 3 is the net flow in the z direction. We know all these need to sum to 0 because the need to balance for mass conservation.
- This assumes incompressability so constant density $\rho$, the equation as first stated above considered compressible flow effects.


# Supersonic Wind Tunnel Lab

## In Report

- Optical Path
- Describe the aparatus
- Uses Nitrogen
    - Can be considered similar to the air
    - Similar heat ratio to air (1.4)
- Uses a convergent-divergent nozzle


# Shock Theory

## Mach Waves

- A generator moving faster than or equal to the speed of sound will create a Mach Cone and Zone of silence.
- The air in the zone of silence has no way of reacting to the supersonic flow.
- The angle of the mach cone can be determined through simple geometry. The equation is outlined below:

$$
\sin {(\mu)} = {1 \over M}
$$

Where, $\mu$ is the angle and M is the Mach number

## Shock Waves

- The above is true if the generator is infintesimally small, however in many situation the generator could be a large bluff body, such as an aircraft. For these cases the true angel $\beta$ is greater that $\mu$.

- In these cases we refer to it as a shock wave. These waves are much stronger than a Mach wave. 

## Sonic Boom

- A sonic boom is a common name for the sound created by shock and mach waves. 
- It takes time to travel from the generator to an observer.

## Normal Shock Waves
- Shock line is perpendicular to the flow direction.
- Normal shocks are very thin and so can be considered as a discontinuity.

### Traits
- Adiabatic
- Not isentropic
- The flow is always supersonic upstream of a shock and subsonic downstream of a shock.
- $u_2 < u_1$
- $P_2 > P_1$
- $T_2 > T_1$
- $\rho_2 > \rho_1$
- $T_{02} = T_{01}$, as it's adiabatic
- $P_{02} > P_{01}$, as it's not isentropic

### Equations for Normal Shock Waves

$$
M_{2}^{2} = {{1 + ({{\gamma - 1} \over 2}) M_{1}^{2}} \over {\gamma M_{1}^{2} - ({{\gamma - 1} \over {2}})}}
$$

$$
{\rho_2 \over \rho_1} = {u_1 \over u_2} = {{(\gamma + 1) M_{1}^{2}} \over {2 + (\gamma -1) M_{1}^{2}}}
$$

$$
{P_2 \over P_1} = {1 + {{2 \gamma} \over {\gamma + 1}} (M^2_1 - 1)}
$$

$$
{T_2 \over T_1} = {h_2 \over h_1} = {[{1 + {{2 \gamma} \over {\gamma + 1}} (M^2_1 - 1)}][{{{2 + (\gamma -1) M_{1}^{2}}}\over  {{(\gamma + 1) M_{1}^{2}}}} ]}
$$

## Expansion Waves/Fans

- Occur when a supersonic flow is turned.

### Traits
- Adiabatic
- Isentropic
- $M_2 > M_1$
- $P_2 < P_1$
- $T_2 < T_1$
- $\rho_2 > \rho_1$
- $T_{02} = T_{01}$, as it's adiabatic
- $P_{02} = P_{01}$, as it's isentropic

An expansion fan is composed of an infinite number of Mach waves, bounded by:

- The Mach angle of the upstream incoming flow: $\mu_1 = \sin^{-1} ({1 \over M_1})$
- The Mach angle of the downstream flow: $\mu_2 = \sin^{-1} ({1 \over M_2})$

### Equations for Expansion Waves



