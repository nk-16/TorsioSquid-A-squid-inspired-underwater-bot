# TorsioSquid-A-squid-inspired-underwater-bot

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/Picture2.png" alt="Image 1" width="700"/>
</div>

Underwater soft robotics is an emerging field due to the increased need for underwater exploration and surveillance, which requires blending with natural habitats. Although previous work has been done mimicking fishes and octopuses, only a few have tried to imitate the mantle movement of squid. Mimicking the mantle's propulsion mechanism could lead to a compact design, which we have presented through the TorsioSquid, a bio-inspired robotic system. 

* **Working and Design**

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/Screenshot%202024-08-26%20014253.png" alt="Image 1" width="700"/>
</div>

Key to TorsioSquid's actuation is a unique combination of torsional buckling and Bowden cables. Torsional buckling, a form of mechanical imperfection, is induced in the system through carefully engineered
Bowden cables are arranged in a specific helical geometry. We have kept all electronics and mechanisms in a semi-ellipsoidal shell of Ecoflex. At the core of TorsioSquid is a linear actuator housed within the apex of the shell, whose circuit has been isolated from water to prevent damage. All the bowden cables have been arranged in a helix around the shell, one end of which has been connected to the linear actuator while the other end has been fixed to the apex of the shell. As the linear actuator retracts, it pulls on the Bowden cables arranged in a helix around the shell. The helical geometry imparts axial and tangential forces on the shell, inducing a combined axial and torsional movement. By optimising the helix angles and cable configurations, we induce controlled buckling of the shell, which will lead to the volumetric reduction of the shell, mimicking the squid's mantle movement and generating thrust for propulsion.
  
* **Modelling, Simulation and Analysis**

The Finite Element Method (FEM) stands out as our chosen approach for the modelling of Soft Robotics due to its adaptability in handling complexities without intricate analytical models. We have used the Ansys Workbench tool, which works on FEM.

1. Material Assessment - We chose the Yeoh 3rd order model [6] and its parameters for Ecoflex for the material assignment. The Yeoh model is chosen because it only needs a small amount of experimental
data to get reasonable numerical results. It can also describe a wide range of deformation. The reason for choosing Ecoflex material is the abundance of its experimental material data, and it is biocompatible and
flexible.

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/Screenshot%202024-06-10%20025813.png" alt="Image 1" width="700"/>
</div>

<br>

2. Meshing parameters - We choose Nonlinear Mechanical and large deflection while meshing to capture the nonlinearities of a soft robot. The element order was kept linear, and the element size was 3.75 mm. The Automatic meshing method has been used, which generally creates a tetrahedral mesh for 3D models, which balances computational efficiency and accuracy. Thus, we get an average element quality of 0.78 with nodes <50000.

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/Screenshot%202024-06-10%20030331.png" alt="Image 1" width="700"/>
</div>

<br>

3. Boundary conditions - The base of the shell has been kept fixed while all the forces and remote displacement have been provided at the top of the apex. A Force of 1.25 N has been applied at the centre of the apex to consider the weight of the electronics enclosed within the apex of semi ellipsoidal shell.

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/Screenshot%202024-06-10%20030546.png" alt="Image 1" width="400"/>
   <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/Screenshot%202024-06-10%20091051.png" alt="Image 2" width="400"/>
</div>

<br>

4. Nonlinear buckling and Eigenvalue buckling to find  volumetric deformation
   
● Analysis A1: A 1-degree rotation has been applied to give Pre-stress to the shell.
● Analysis A2: Eigen buckling analysis to create geometrical imperfections in the shell.

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/abc1.png" alt="Image 1" width="700"/>
  <div align="center">
Analysis A1 (left) and Analysis A2 (right)
</div>
</div>

<br>

● Analysis A3: Translational and rotational load are applied in steps of t = 10 secs on the geometrically imperfect shell to generate folds in the semi-ellipsoidal shape, replicating the volumetric deformed state.

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/abc2.png" alt="Image 1" width="700"/>
  <div align="center">
Analysis A3 
</div>
</div>

<br>

● Obtaining volumetric reduction - Importing the volumetric deformed state in Analysis A3 of the shell in Solidworks and comparing it with the initial one gives us the volumetric deformation.


5. Usage of nozzle to increase the exit velocity 

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/abc3%20(1).png" alt="Image 1" width="700"/>
  <div align="center">
A semi-ellipsoidal-shaped nozzle with an exit diameter of 50 mm can increase the exit velocity, thus increasing the thrust force.  
</div>
</div>

<br>

* **Performance Metrics and Conclusion** - We calculate the mesh convergence error to verify our simulation results. We get a 0.7 % mesh convergence error, which gives our simulation results reasonable accuracy. The following metrics are comparable with preliminary robots that have tried to mimic squids, but here, we achieved these metrics by using mostly soft components.

<div align="center">
  <img src="https://github.com/nk-16/TorsioSquid-A-squid-inspired-underwater-bot/blob/main/Screenshot%202024-08-28%20175118.png" alt="Image 1" width="700"/>
</div>








