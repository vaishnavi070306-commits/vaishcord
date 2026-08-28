

# PROBATION DIARY

--------------------------------------

## Domain Tasks

## 1)Linkage Mechanism Build

The designed mechanism is a **Whitworth quick-return mechanism** that converts continuous rotary motion into reciprocating linear motion. The mechanism consists of a **fixed base, rotating crank, eccentric crank pin, slotted oscillating lever, and horizontal ram**. The crank rotates about its fixed centre, causing the eccentric pin to follow a circular path while sliding inside the slot of the oscillating lever. This makes the lever oscillate about its lower fixed pivot, which in turn drives the horizontal ram in a reciprocating motion.

The motion conversion is:

$$
\boxed{\text{Rotary Motion} \rightarrow \text{Oscillatory Motion} \rightarrow \text{Reciprocating Motion}}
$$

The main feature is the **quick-return action**. The crank covers unequal angular displacements during the working and return strokes. For constant angular velocity,

$$
t = \frac{\theta}{\omega}
$$

and the quick-return ratio is:

$$
\boxed{QRR = \frac{t_w}{t_r} = \frac{\theta_w}{\theta_r}}
$$

Since the return stroke corresponds to a smaller crank angle, it takes less time than the working stroke. This principle is commonly used in **shaper machines** to reduce non-productive return time.

The mechanism was modelled with defined dimensions for the crank, eccentric pin, slotted lever, pivots, slot, and ram. The individual components will be **FDM 3D printed and assembled** with suitable clearances at the moving interfaces to ensure smooth rotation and sliding. The final assembly will demonstrate the relationship between **linkage geometry, constrained motion, quick-return kinematics and CAD design**.

<img width="400" height="400" alt="withworth" src="https://github.com/user-attachments/assets/7baeba18-a7d7-47a5-9041-f5be19a0b9c4" />



-----

# 2)Compliant Mechanism – 3D Printed Chip/Bags Clip

The designed mechanism is a **single-piece compliant chip/bag clip** based on a **living-hinge flexure**, in which motion is generated through elastic deformation rather than conventional rigid joints. The clip consists of two gripping arms connected by a thin, flexible hinge region. When an external force is applied to the arms, the flexure undergoes bending deformation and stores elastic strain energy; upon release, this energy produces the restoring force required to return the clip towards its closed position. Thus, the mechanism achieves **actuation without pins, bearings, screws, or rigid-link assembly**.

The living hinge is mechanically analysed as a **flexible beam subjected to bending**. The bending stress is given by:

$$
\sigma=\frac{Mc}{I}
$$

For a rectangular flexure:

$$
I=\frac{bt^3}{12}
$$

and the stress-strain relationship is:

$$
\sigma=E\epsilon
$$

where $M$ is the bending moment, $c$ is the distance from the neutral axis, $I$ is the second moment of area, $b$ is the hinge width, $t$ is its thickness, $E$ is Young's modulus, and $\epsilon$ is strain. Since flexure stiffness is strongly dependent on hinge thickness, the geometry must provide sufficient deformation while keeping the maximum stress below the material's elastic limit. This ensures reversible deformation and prevents permanent bending or fracture during repeated actuation.

The mechanism is intended for **reusable food-bag sealing**, providing a practical application of compliant-mechanism design. It will be fabricated as **one continuous component using FDM 3D printing**, with the material selected based on strength, ductility, flexibility, and resistance to repeated bending. Since FDM components are anisotropic due to their layer structure, the **print orientation and layer direction** will be selected to improve the strength and fatigue resistance of the living hinge. The printed component will require no mechanical assembly, with only minor removal of printing artefacts if necessary. The prototype will be evaluated through repeated opening and closing cycles to assess **elastic recovery, gripping force, deformation, and resistance to failure**. The project therefore integrates **compliant mechanism design, Strength of Materials, Material Science, mechanical analysis, CAD modelling, additive manufacturing, and real-world application** into a functional single-piece mechanism.

<img width="500" height="500" alt="compliant" src="https://github.com/user-attachments/assets/d507e5c7-2f13-4939-8970-ef2240be7f3d" />

# 3) Computational Fluid Dynamics (CFD) Resource Article

## CFD Analysis of Airflow Through a Pipe with Sudden Expansion

### 1. Introduction

Computational Fluid Dynamics (CFD) is a numerical method used to study fluid flow using a computer. In CFD, the fluid domain is divided into small cells called a **mesh**, and the governing equations of fluid mechanics are solved to obtain information such as velocity, pressure and turbulence.

CFD is widely used in mechanical engineering for applications such as automotive aerodynamics, HVAC, pumps, turbines, heat exchangers and piping systems.

As a practical example, this article considers air flowing through a pipe that suddenly expands from **20 mm to 40 mm diameter**. The aim is to study the change in velocity, pressure, flow separation and pressure loss.


-----

## 2. CFD Workflow

A typical CFD analysis follows these steps:

**Geometry → Meshing → Material → Boundary Conditions → Solver → Convergence → Post-Processing → Validation**

The geometry represents the fluid region being analysed. The domain is then divided into mesh cells. Fluid properties and boundary conditions are defined, after which the solver calculates the flow field. Finally, the results are visualised and compared with theoretical values.


## 3. Geometry and Parameters

| Parameter                  |                      Value |
| -------------------------- | -------------------------: |
| Fluid                      |                        Air |
| Inlet diameter, \(D_1\)    |                      20 mm |
| Outlet diameter, \(D_2\)   |                      40 mm |
| Inlet velocity, \(V_1\)    |                     10 m/s |
| Outlet pressure            |                 0 Pa gauge |
| Density, \(\rho\)          |                1.225 kg/m³ |
| Dynamic viscosity, \(\mu\) | \(1.81\times10^{-5}\) Pa·s |
| Flow                       |          Steady, turbulent |
| Turbulence model           |           \(k-\omega\) SST |

The sudden increase in diameter creates a sudden increase in flow area, causing the velocity to decrease and creating a region of separated flow downstream of the expansion.


## 4. Governing Equations

### Continuity

For steady incompressible flow:

$$
A_1V_1=A_2V_2
$$

where the pipe area is:

$$
A=\frac{\pi D^2}{4}
$$

### Navier-Stokes Equation

Fluid motion is governed by:

$$
\rho\left(\frac{\partial\vec V}{\partial t}+\vec V\cdot\nabla\vec V\right)
=-\nabla p+\mu\nabla^2\vec V+\vec F
$$

This represents the effects of acceleration, pressure, viscosity and body forces.

### Reynolds Number

$$
Re=\frac{\rho VD}{\mu}
$$

At the inlet:

$$
Re=\frac{(1.225)(10)(0.020)}
{1.81\times10^{-5}}
\approx13536
$$

Since the Reynolds number is above approximately 4000, the inlet flow is treated as turbulent.


## 5. Boundary Conditions

### Inlet

A velocity inlet of:

$$
V_1=10\;m/s
$$

is applied.

The inlet area is:

$$
A_1=3.1416\times10^{-4}\;m^2
$$

Therefore, the volumetric flow rate is:

$$
Q=A_1V_1
$$

$$
\boxed{Q=3.1416\times10^{-3}\;m^3/s}
$$

The mass flow rate is:

$$
\dot m=\rho A_1V_1
$$

$$
\boxed{\dot m\approx3.85\times10^{-3}\;kg/s}
$$

An inlet turbulence intensity of approximately 5% may be assumed.

### Outlet

The outlet is set to:

$$
\boxed{P_{out}=0\;Pa\;gauge}
$$

This represents atmospheric pressure relative to the gauge reference. It does **not** mean that the absolute pressure is zero.

### Walls

A stationary no-slip wall condition is applied:

$$
\boxed{V_{wall}=0\;m/s}
$$

This means the fluid immediately touching the wall has zero velocity relative to it.

## 6. Theoretical Outlet Velocity

The outlet area is:

$$
A_2=\frac{\pi(0.040)^2}{4}
=1.2566\times10^{-3}\;m^2
$$

Using continuity:

$$
A_1V_1=A_2V_2
$$

Therefore:

$$
V_2=\frac{A_1V_1}{A_2}
$$

$$
\boxed{V_2=2.5\;m/s}
$$

The velocity decreases because the outlet area is four times the inlet area.

## 7. Mesh and Simulation Setup

The mesh should be refined near the sudden expansion and pipe walls because these regions contain large velocity gradients and flow separation.

The simulation procedure is:

1. Create the internal fluid geometry.
2. Generate the mesh.
3. Refine the mesh near the expansion and walls.
4. Define air as the fluid.
5. Apply the inlet and outlet conditions.
6. Apply no-slip wall conditions.
7. Use a pressure-based solver.
8. Select the \(k-\omega\) SST turbulence model.
9. Run the simulation until convergence.
10. Examine the results through post-processing.

The \(k-\omega\) SST model is selected because it performs well for flows involving adverse pressure gradients and separation.

## 8. Expected Flow Behaviour

When the air enters the larger section, its average velocity decreases from 10 m/s to approximately 2.5 m/s.

However, the flow does not immediately follow the expanded wall. The sudden change in geometry causes **flow separation and recirculation** near the walls.

The separated region also produces turbulence and permanent energy loss.

Although some pressure recovery occurs because the velocity decreases, the process is not completely reversible.

For an ideal sudden expansion, the Borda-Carnot equation gives the approximate head loss:

$$
h_L=\frac{(V_1-V_2)^2}{2g}
$$

Using \(V_1=10\;m/s\) and \(V_2=2.5\;m/s\):

$$
\boxed{h_L\approx2.87\;m}
$$

The corresponding pressure loss is approximately:

$$
\boxed{\Delta P_L\approx34.4\;Pa}
$$

These theoretical values can be used to check the CFD results.

## 9. Post-Processing

The main CFD results to examine are:

* **Velocity contours** — show the reduction in velocity after expansion.
* **Pressure contours** — show pressure recovery and pressure loss.
* **Streamlines** — show flow separation and recirculation.
* **Turbulence contours** — identify regions of increased turbulent activity.
* **Pressure loss** — indicates the energy loss caused by the sudden expansion.

The CFD outlet velocity and pressure loss can be compared with the theoretical values calculated above.

## 10. CFD Applications and Learning

CFD is used in many engineering fields, including:

* Automotive aerodynamics
* Aerospace
* HVAC and ventilation
* Pumps and turbines
* Heat exchangers
* Piping systems

Students can begin learning CFD using platforms such as **ANSYS Fluent, OpenFOAM, SimScale and STAR-CCM+**. A good approach is to start with simple cases such as pipe flow and sudden expansion before moving to more complex problems.

## 11. Conclusion

The sudden-expansion pipe provides a simple example for understanding the basic CFD workflow and the behaviour of internal turbulent flow.

The theoretical calculation predicts an outlet velocity of approximately **2.5 m/s**. The sudden expansion also causes flow separation, recirculation and pressure loss.

The CFD simulation can visualise these phenomena and provide detailed information about the flow field. Comparing the simulation with theoretical calculations also helps verify whether the results are physically reasonable.

This example demonstrates that CFD is not simply about generating flow contours. It combines **fluid mechanics, numerical analysis, computer simulation and engineering judgement** to study and improve real-world systems.


## Regular Lab Activities & Attendance

As part of my responsibilities in the MARVEL lab, I made it a point to be present in the lab during my free time and not only when a particular task or activity was assigned to me. Regular presence in the lab helped me become familiar with the day-to-day functioning of the workspace, understand how different activities were coordinated, and remain available whenever assistance was required. It also gave me an opportunity to observe and learn from the work being carried out by other students and coordinators.

During batch sessions, I actively assisted students with their presentations and helped them whenever they faced difficulties. I supported students in understanding the requirements of their assigned activities, clarified basic doubts, and guided them whenever they required assistance with the tools, components, or procedures being used. By interacting with different batches, I was also able to improve my communication skills and develop a better understanding of the challenges students face while carrying out practical tasks.

Another important responsibility was assisting with the issue and return of components, kits, tools, and other laboratory resources. Whenever students required components for their assigned activities, I helped in providing the required items and keeping track of their issue and return. After completion of the work, I helped ensure that the components and kits were returned properly. This was important because proper management of laboratory resources helps prevent loss or misplacement of components and ensures that the required equipment remains available for other batches and future activities.

I also understood the importance of maintaining proper records for every visit to the lab. I regularly signed the lab log register whenever I visited the MARVEL lab. Maintaining the register provides a record of lab usage and helps keep track of the participation and presence of coordinators and students.

Overall, regular lab presence allowed me to contribute beyond my individually assigned tasks. It helped me develop responsibility, teamwork, communication, and resource-management skills while also giving me practical exposure to the functioning of a student-driven technical laboratory. By assisting during batch sessions, supporting component and kit management, and maintaining proper attendance records, I contributed to keeping the lab organized, accessible, and supportive for students working on their projects and activities.
Here is my running log of visits  https://docs.google.com/spreadsheets/d/1brApsyCMCcpFy1qJmYbUQTcHdMLXy3yz_7gGkANS4pg/edit?usp=sharing


## SIH Internal Hackathon Support

My contribution to the SIH Internal Hackathon so far has mainly been focused on campaigning and communication. I broadcasted the information related to the hackathon to students through the available communication channels, including details regarding the event, participation, and registration. This helped ensure that the information reached the intended students and created awareness about the hackathon.

### Specific Contribution

- Broadcasted SIH Internal Hackathon announcements and information.
- Shared participation and registration-related details with students.
- Helped spread awareness about the event through the available communication channels.




## Resource Cataloguing

Maintaining accurate documentation of laboratory components, tools, kits, and equipment is essential for keeping the lab organized and ensuring that available resources can be easily identified and accessed. A proper inventory system helps distinguish newly acquired components from existing ones while providing information about their **type, quantity, specifications, condition, and storage location**. Recording the exact storage location, such as a particular box, rack, shelf, or cupboard, also reduces the time required to locate components and helps prevent misplacement or duplication of items. Regularly updating such records ensures that the laboratory maintains a reliable and accessible inventory of its resources.

As part of this task, I worked on identifying and documenting a range of **electronics, EV, and IoT components** available in the laboratory. Each component was inspected and its relevant information was systematically recorded in an **Excel sheet** according to the required cataloguing format. The details included the **component name, quantity, type, technical specifications, storage location, and condition** wherever applicable. Particular attention was given to identifying where each component was physically stored, including the respective **boxes, racks, shelves, and cupboards** assigned to them.

The cataloguing process also involved differentiating between various types of components and understanding their intended applications, particularly in the areas of **electronics, electric vehicles, and IoT systems**. This helped create a more structured inventory and made it easier to associate each component with its corresponding storage location and technical purpose. The completed Excel catalogue can be further updated whenever new components are acquired, existing components are relocated, or their quantities and conditions change, providing the lab with a systematic record for future reference and efficient resource management.
Here goes my excel
https://1drv.ms/x/c/b10fdfa91d172e27/IQAMvyOC31hoQoc6SlrhhNM8AfRXQF6M3VwfnOoWZrXGlYU?e=kYaP3e



## Equipment Documentation  


## 1)HW-130 L293D Motor Driver Shield – User Manual

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/e8dd48b5-e9a5-404e-96e4-1a3ffde2a455" />

### Function
- Used to control the direction and speed of DC motors.
- Can also be used for controlling stepper motors.
- Provides an interface between Arduino and motors.
- Suitable for robotics and automation applications.
- Prevents the Arduino from directly handling high motor current.

### Working Principle
- Uses L293D H-bridge motor driver ICs.
- H-bridges reverse motor polarity to change its direction.
- PWM signals from the Arduino control motor speed.
- External power supplies the motors.
- Control signals are received from the Arduino.

### Specifications
- Driver IC: L293D.
- Motor supply: approximately 4.5–25 V DC.
- Continuous current: approximately 600 mA per channel.
- Peak current: approximately 1.2 A per channel.
- Compatible with Arduino boards.

### Operating Instructions
- Mount the shield onto the Arduino correctly.
- Connect the motor to the appropriate motor terminal.
- Connect a suitable external motor power supply.
- Upload the required motor-control program.
- Set the required motor direction and speed using the Arduino program.

### Safety Instructions
- Do not exceed the rated voltage or current.
- Check power polarity before switching on.
- Do not connect/disconnect motors while powered.
- Avoid short circuits at the output terminals.
- Allow the driver IC to cool if it becomes excessively hot.


## 2) PWM DC Motor Speed Controller – User Manual

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/0a14ec31-dea5-4859-b209-a963c769e84c" />

### Function
- Controls the speed of a brushed DC motor.
- Provides smooth and adjustable speed control.
- Uses a rotary knob for speed adjustment.
- Suitable for small motors, robots and fans.
- Provides efficient motor control compared with simple resistive control.

### Working Principle
- Operates using Pulse Width Modulation (PWM).
- Rapidly switches the motor supply ON and OFF.
- The potentiometer changes the PWM duty cycle.
- Higher duty cycle generally increases motor speed.
- Lower duty cycle reduces motor speed.

### Specifications
- Type: PWM DC motor speed controller.
- Input: DC supply.
- Typical voltage range: approximately 6–28 V DC.
- Typical current rating: up to approximately 3 A.
- Control: Rotary potentiometer.

### Operating Instructions
- Connect the DC supply to the input terminals.
- Connect the motor to the output terminals.
- Keep the speed knob at minimum before powering on.
- Switch on the power supply.
- Slowly rotate the knob to increase or decrease motor speed.

### Safety Instructions
- Use only DC power within the rated range.
- Never connect the module to AC mains.
- Do not exceed its current rating.
- Check polarity before powering the module.
- Disconnect power before changing connections.


## 3)BEETELCH DC Power Supply – User Manual

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/945cbee2-8bb7-48d0-9f74-7a021b1f1617" />

### Function
- Provides adjustable regulated DC voltage.
- Supplies controlled current to electronic circuits.
- Used for laboratory experiments and circuit testing.
- Displays output voltage and current.
- Allows voltage and current limits to be adjusted.

### Working Principle
- Converts input electrical power into regulated DC output.
- Voltage-control circuitry maintains the selected voltage.
- Current-control circuitry limits the maximum output current.
- The display continuously indicates voltage and current.
- The supply can operate in constant-voltage or current-limited operation.

### Specifications
- Type: Regulated DC bench power supply.
- Manufacturer: BEETELCH.
- Controls: Coarse and fine voltage/current adjustment.
- Display: Voltage and current indication.
- Outputs: Positive, negative and ground terminals.

### Operating Instructions
- Connect the power supply to a suitable AC source.
- Keep the voltage and current settings low initially.
- Set the required voltage and current limit.
- Connect the circuit with correct polarity.
- Switch on the output and monitor the displayed readings.

### Safety Instructions
- Check polarity before connecting a circuit.
- Do not exceed the rated output.
- Never intentionally short the output terminals.
- Keep liquids away from the equipment.
- Switch off the output before changing connections.

## 4)Two-Axis Joystick Module – User Manual

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/71826085-c504-401d-bfd7-538f89c78a26" />

### Function
- Provides user input for electronic and robotic systems.
- Detects movement in X and Y directions.
- Provides an additional push-button input.
- Commonly used with Arduino and other microcontrollers.
- Can control robots, robotic arms and games.

### Working Principle
- Contains two potentiometers for X and Y movement.
- Joystick movement changes the resistance of the potentiometers.
- This produces variable analog output voltages.
- The microcontroller reads these voltages to determine position.
- Pressing the joystick activates the built-in push-button switch.

### Specifications
- Type: Two-axis analog joystick.
- Axes: X-axis and Y-axis.
- Outputs: 2 analog + 1 digital switch output.
- Typical supply: 5 V DC.
- Includes a momentary push-button switch.

### Operating Instructions
- Connect VCC to the appropriate supply.
- Connect GND to circuit ground.
- Connect X and Y outputs to analog input pins.
- Connect the switch output to a digital input.
- Move and press the joystick to observe the corresponding readings.

### Safety Instructions
- Use the correct supply voltage.
- Check the pin configuration before connecting.
- Do not short VCC and GND.
- Avoid applying excessive force to the joystick.
- Disconnect power before changing connections.


## 5)16×2 LCD Display – User Manual

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/a0fe1ecd-132a-4cdb-bc44-f808b82a67ff" />

### Function
- Displays alphanumeric information.
- Provides 16 characters in each of two rows.
- Used to display sensor readings and system messages.
- Can be interfaced with Arduino and other microcontrollers.
- Provides a simple visual output for electronic systems.

### Working Principle
- Uses liquid-crystal cells to produce visible characters.
- A controller receives commands and character data.
- RS selects command or data mode.
- E (Enable) latches the transmitted information.
- D4–D7 can be used for 4-bit data communication.

### Specifications
- Display format: 16 × 2 characters.
- Interface: Parallel.
- Data pins: D0–D7.
- Control pins: RS, RW and E.
- Typical supply: 5 V DC.

### Operating Instructions
- Connect VDD to the positive supply and GND to ground.
- Connect RS, RW and E to the microcontroller.
- Connect D4–D7 for 4-bit operation.
- Upload the required LCD program.
- Adjust the contrast using the VO connection.

### Safety Instructions
- Use the specified supply voltage.
- Check pin orientation before powering.
- Do not reverse the power polarity.
- Avoid short-circuiting the pins.
- Handle the LCD glass carefully and avoid excessive pressure.


---

## Financial Documentation

As part of the **Financial Documentation** exercise, under the guidance of the Finance Coordinator **Aashray**, we gained practical knowledge about how financial activities are managed, recorded, and documented within MARVEL. The activity helped us understand the importance of maintaining proper financial records for the purchase of components, equipment, tools, and other resources required for various laboratory activities.

Since this was a **group task**, the work was divided among the members, which helped us organize the documentation efficiently and complete it within the given time. Our main task was to document the purchase bills along with their respective **GST bills**. Two copies of each document were maintained systematically. One file contained the **original bills**, while the second file contained their **photocopies**, ensuring that the records could be referred to easily whenever required.

The components and equipment required by MARVEL are purchased using funds provided by **UVEGA**. Therefore, the coordinators are responsible for ensuring that these funds are utilized appropriately and that the expenses are properly recorded. Whenever a component or equipment is required, the necessary amount is requested along with details such as the **item description, quantity, specifications, purpose, and estimated cost**. After the requirement is approved and the funds are transferred, the required item is purchased and the corresponding bills are collected for documentation.

We also understood the importance of maintaining **GST bills and purchase records** as supporting documents for every transaction. These records provide information about the items purchased, their quantities, costs, and applicable taxes. Proper organization of these documents makes it easier to track expenses and verify the utilization of funds.

The activity highlighted the importance of **financial accountability, transparency, and systematic record keeping** in the functioning of a technical laboratory. Maintaining proper financial records ensures that institutional funds are used responsibly and provides reliable documentation for future verification, auditing, and financial planning.

Overall, the Financial Documentation exercise gave us valuable practical exposure to the administrative and financial procedures involved in the functioning of MARVEL. It helped us understand that financial management is not limited to purchasing the required resources but also involves maintaining accurate records and ensuring accountability for the funds used. Through this activity, we developed a better understanding of **responsibility, coordination, documentation, and financial management** in a technical organization.


-----

## Industry Outreach and Design Domain Research

As part of this task, I reached out on LinkedIn to **Mr. Amar M**, a Mechanical Design Engineer and CAD/CAM/CAE Trainer at **TC_Technocraft**. He referred me to his colleague, **Mr. Shreedhar Mahadev**, who also has experience in mechanical design.

I enquired about the **current industry trends, software requirements, and skills expected in mechanical design and prototyping**. He suggested that we develop strong proficiency in **SolidWorks**, as it is widely used by companies in India for mechanical design and modelling. He also mentioned that higher-end companies may use advanced tools such as **HyperMesh** for more specialized CAE and simulation applications.

Based on this interaction, I understood that learning industry-relevant CAD/CAE software alongside our existing tasks could help us develop skills that are more aligned with current industry requirements.

I would therefore suggest that **SolidWorks or other widely used industry-relevant CAD/CAE software** could be incorporated into some of our future tasks. This would provide practical exposure to tools currently used in the field and help us further improve our design and prototyping skills.

## Cross-Domain Exposure Tasks

### Task 1 – Solar Panel Sun Tracking

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/b1c5555a-cede-40a8-b2ec-bdde82808f28" />


The first task involved designing and implementing a basic **solar panel sun-tracking mechanism using LDRs, an Arduino, and a servo motor**. The main objective was to make the solar panel automatically orient itself toward the direction from which the strongest light was being received. Since the amount of solar energy collected by a panel depends on the intensity and direction of incident sunlight, keeping the panel oriented toward the strongest light source can improve energy collection.
The system used **two LDR (Light Dependent Resistor) sensors** placed on different sides of the panel. The LDRs detect the intensity of light falling on each side and provide corresponding electrical readings to the Arduino. By comparing these two readings, the Arduino can determine which side is receiving more light and accordingly adjust the position of the solar panel.
I first understood the working principle of an LDR and how its resistance changes according to the intensity of incident light. The two LDRs were connected to the Arduino so that their readings could be continuously monitored. The servo motor was then used as the actuator responsible for changing the orientation of the solar panel.
The Arduino program was designed to compare the readings obtained from the two LDRs. If the reading from one LDR indicated a stronger light source than the other, the Arduino would command the servo motor to rotate the panel toward that direction. When the readings from the two sensors became relatively similar, the panel would remain near the position where both sensors received comparable amounts of light.
This created a simple **feedback-based control system**. The LDRs acted as the sensors, the Arduino acted as the controller, and the servo motor acted as the actuator. The sensor readings were continuously evaluated so that the position of the panel could be adjusted according to changes in the direction of the light source.
During the implementation, I also had to consider the practical behaviour of the servo and sensor readings. Small differences in LDR values can occur even when the light source is nearly centered, so the comparison logic needs to avoid unnecessary or continuous movement. This helped us understand that practical control systems require suitable decision-making rather than simply responding to every small change in sensor readings.
Through this task, I learnt how **light sensors can be integrated with a microcontroller to control mechanical movement**. We understood the working principle of LDRs, analog sensor readings, servo motor control, and basic conditional logic in Arduino programming.



# Task 2 – SPI Communication

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/fdf1577f-74a3-4ce4-a74a-fb7d1183b70b" />

The second task involved implementing **SPI (Serial Peripheral Interface) communication** using Arduino boards. The objective was to understand how digital devices communicate using SPI and how a **master device exchanges data with a slave device**. SPI is commonly used for communication between microcontrollers and peripherals such as SD card modules, displays, sensors, and other microcontrollers.

The task specifically focused on understanding the four primary SPI signals: **MOSI, MISO, SCK, and SS**. We also had to understand how these signals work together to provide synchronized and full-duplex communication between the master and slave.

I first studied the purpose of each of the four SPI communication lines. **MOSI (Master Out Slave In)** is used to transmit data from the master to the slave, while **MISO (Master In Slave Out)** carries data from the slave back to the master. **SCK (Serial Clock)** provides the clock signal generated by the master to synchronize the data transfer. **SS (Slave Select)** is used by the master to select the particular slave with which it wants to communicate.

After understanding the individual signals,I implemented the communication using **two Arduino boards**, with one configured as the master and the other as the slave. The required SPI connections were established between the boards, ensuring that the corresponding communication lines were connected correctly. The boards were also given suitable power and common ground connections so that the communication signals had a common reference.

I then programmed the master to transmit a specific value to the slave and configured the slave to receive the transmitted data. The slave was also programmed to respond with data, allowing us to test communication in both directions. This helped us understand the **full-duplex nature of SPI**, where transmission and reception can take place during the same clocked communication process.

During the implementation,I encountered issues while establishing communication and therefore had to troubleshoot the connections and program configuration. I checked the SPI wiring, the roles assigned to the two Arduino boards, and the transmitted and received values. I also monitored the communication behaviour and used the output from the Arduino environment to verify whether the expected values were being exchanged.

After troubleshooting, the communication was successfully verified. The master was able to send a value to the slave and receive the expected response back. This confirmed that the SPI connection and program logic were functioning correctly. We also understood that the labels of **master and slave are based on their programmed communication roles**, rather than simply the physical position of the Arduino boards.

This task gave me practical knowledge of **SPI communication and master-slave data exchange**. I learnt the purpose of MOSI, MISO, SCK, and SS and understood how the clock signal synchronizes the transfer of data between the communicating devices.

I also learnt that SPI communication requires both **correct hardware connections and appropriate software configuration**. Even a small wiring or configuration error can prevent successful communication, making systematic troubleshooting an important part of embedded-system development.

The task also helped me understand the concept of **full-duplex communication**, where the master and slave can exchange data through separate transmission and reception lines. By implementing the communication ourselves, I gained a clearer understanding of how SPI can be used for communication between a microcontroller and external peripherals or another microcontroller.


# Articulation — Sampada Magazine Article 

It was a truly amazing experience to work in such a lab as MARVEL. I had the privilege of becoming a coordinator for one month under probation, where I had to perform duties that were almost equivalent to those of the regular coordinators.

Being around such creative and enthusiastic people made me feel like I was wasting my potential for no reason at all, or maybe that I simply didn't have my friends along with me. But MARVEL became an instrument for building connections, where I met many of my peers and was able to have conversations with them and work on projects together. This truly opened up my horizons. It felt as though I had stepped out of a bubble.

I also had to perform domain-specific tasks. Since I belong to D&P Mechanical, I had to design mechanisms, get them 3D printed and learn other software as well. All the probation coordinators of D&P had to collaborate on the group task of creating a functional toy. We got quite a wonderful output, and the process itself was quite fun and engaging.

I had other general tasks to get done as well. For example, maintaining the lab, helping batch students and peers, broadcasting information from class to class, reaching out to industry professionals for potential workshops or changes in the syllabus, campaigning for the SIH Hackathon and its internal support, resource cataloguing, equipment documentation, financial documentation and cross-domain exposure tasks.

The industry outreach was one of the tasks that gave me a perspective outside the lab. I reached out to professionals on LinkedIn to understand the current trends and requirements in the field of mechanical design and prototyping. I initially contacted Mr Amar M, a Mechanical Design Engineer and CAD, CAM and CAE trainer at TC_Technocraft, who referred me to his colleague, Mr Shreedhar Mahadev, who also had experience in the design field. Speaking to people who are already working in the industry helped me understand what skills I should actually be focusing on as a student. One of the important suggestions I received was to become thorough with SolidWorks, as it is widely used by companies in India.

Financial documentation was another task that gave me an insight into the organisational side of MARVEL. Under the guidance of our Finance Coordinator, Aashray, we had to document bills along with their respective GST bills and maintain two copies in separate files, one containing the originals and the other containing the photocopies. Since the components and resources are purchased using funds provided by UVEGA, the coordinators are held accountable for maintaining proper records. This made me realise that even though documentation may not seem as exciting as designing or building something, it is still an important part of keeping an organisation running properly.

The cross-domain exposure tasks made me realise that I too can take up tasks from other domains if I am patient enough to learn the concepts and apply them like an engineer. Initially, I thought that being from Mechanical meant that I would naturally be limited to mechanical tasks. But getting exposure to other domains showed me that engineering concepts are not confined to one particular field. If I am willing to understand the fundamentals and put them into practice, I can work outside my comfort zone as well.

Engineering is not about memorising or simply following protocols. It is mostly about grasping concepts and having the ability to apply them in real life to solve problems. This is one valuable lesson I learned at MARVEL. I have always heard this as advice from my professors, but here I was able to experience it in real time. Whether it was working on a mechanism, troubleshooting a technical task, or trying to understand something from another domain, I realised that knowing the concept and being able to apply it are two different things.

I am truly grateful for getting selected and posted as a probation coordinator. It provided me with responsibility as well as accountability. I have always been happy to help people around me in general, so it made me glad that I was able to do it officially as a coordinator. I helped out a few of my juniors with their projects, pitched in my suggestions and tried to be of help whenever I could.

Apart from the technical and organisational work, I think the people I met during this period were one of the most valuable parts of the experience. Working with different people, interacting with peers from different domains and being able to contribute to something together made me more comfortable stepping out of my usual circle. MARVEL gave me an environment where I could learn from others while also contributing whatever I knew.

There were definitely moments when I was confused or did not know how to approach a task. But that was also part of the experience. I learned that it is okay not to know something initially, as long as I am willing to learn it, ask questions and work through the problem. In that sense, the probation was not just about completing the tasks assigned to me. It was also about becoming more willing to explore things that were unfamiliar to me.

As a kid, I always wished to build something using electronic components, but I never really got the opportunity to do it. I feel that this childhood wish has finally been fulfilled through MARVEL and its unwavering support for creative minds. Having access to the lab, components, and guidance gave me the opportunity to move beyond just being curious about electronics and actually build and experiment with them. More importantly, MARVEL showed me that even ideas that begin as simple curiosity can turn into something tangible when you have the right environment and support.


Looking back, I feel that the probation gave me much more than just technical exposure. It gave me an opportunity to interact with people, take responsibility, work as part of a team, understand how an organisation functions and explore areas outside my own domain. 

Most importantly, it made me realise that I am capable of more than I initially thought. Being surrounded by people who were constantly learning, building and experimenting made me want to do the same.


I am truly grateful for this opportunity and for everyone who was a part of this journey. My special thanks go to each and every Coordinator and Probation Coordinator at MARVEL for making this experience something I will cherish forever.

