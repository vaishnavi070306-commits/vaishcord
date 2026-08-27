# Whitworth Quick-Return Mechanism

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

The mechanism was modelled with defined dimensions for the crank, eccentric pin, slotted lever, pivots, slot, and ram. The individual components will be **FDM 3D printed and assembled** with suitable clearances at the moving interfaces to ensure smooth rotation and sliding. The final assembly will demonstrate the relationship between **linkage geometry, constrained motion, quick-return kinematics, CAD design, and additive manufacturing**.

# Compliant Mechanism – 3D Printed Chip/Bags Clip

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

## Financial Documentation

As part of the **Financial Documentation** exercise, under the guidance of the Finance Coordinator **Aashray**, we gained practical knowledge about how financial activities are managed, recorded, and documented within MARVEL. The activity helped us understand the importance of maintaining proper financial records for the purchase of components, equipment, tools, and other resources required for various laboratory activities.

Since this was a **group task**, the work was divided among the members, which helped us organize the documentation efficiently and complete it within the given time. Our main task was to document the purchase bills along with their respective **GST bills**. Two copies of each document were maintained systematically. One file contained the **original bills**, while the second file contained their **photocopies**, ensuring that the records could be referred to easily whenever required.

The components and equipment required by MARVEL are purchased using funds provided by **UVEGA**. Therefore, the coordinators are responsible for ensuring that these funds are utilized appropriately and that the expenses are properly recorded. Whenever a component or equipment is required, the necessary amount is requested along with details such as the **item description, quantity, specifications, purpose, and estimated cost**. After the requirement is approved and the funds are transferred, the required item is purchased and the corresponding bills are collected for documentation.

We also understood the importance of maintaining **GST bills and purchase records** as supporting documents for every transaction. These records provide information about the items purchased, their quantities, costs, and applicable taxes. Proper organization of these documents makes it easier to track expenses and verify the utilization of funds.

The activity highlighted the importance of **financial accountability, transparency, and systematic record keeping** in the functioning of a technical laboratory. Maintaining proper financial records ensures that institutional funds are used responsibly and provides reliable documentation for future verification, auditing, and financial planning.

Overall, the Financial Documentation exercise gave us valuable practical exposure to the administrative and financial procedures involved in the functioning of MARVEL. It helped us understand that financial management is not limited to purchasing the required resources but also involves maintaining accurate records and ensuring accountability for the funds used. Through this activity, we developed a better understanding of **responsibility, coordination, documentation, and financial management** in a technical organization.

# Task 1 – Solar Panel Sun Tracking

## What the Task Was

The first task involved designing and implementing a basic **solar panel sun-tracking mechanism using LDRs, an Arduino, and a servo motor**. The main objective was to make the solar panel automatically orient itself toward the direction from which the strongest light was being received. Since the amount of solar energy collected by a panel depends on the intensity and direction of incident sunlight, keeping the panel oriented toward the strongest light source can improve energy collection.

The system used **two LDR (Light Dependent Resistor) sensors** placed on different sides of the panel. The LDRs detect the intensity of light falling on each side and provide corresponding electrical readings to the Arduino. By comparing these two readings, the Arduino can determine which side is receiving more light and accordingly adjust the position of the solar panel.

## How We Approached the Task

We first understood the working principle of an LDR and how its resistance changes according to the intensity of incident light. The two LDRs were connected to the Arduino so that their readings could be continuously monitored. The servo motor was then used as the actuator responsible for changing the orientation of the solar panel.

The Arduino program was designed to compare the readings obtained from the two LDRs. If the reading from one LDR indicated a stronger light source than the other, the Arduino would command the servo motor to rotate the panel toward that direction. When the readings from the two sensors became relatively similar, the panel would remain near the position where both sensors received comparable amounts of light.

This created a simple **feedback-based control system**. The LDRs acted as the sensors, the Arduino acted as the controller, and the servo motor acted as the actuator. The sensor readings were continuously evaluated so that the position of the panel could be adjusted according to changes in the direction of the light source.

During the implementation, we also had to consider the practical behaviour of the servo and sensor readings. Small differences in LDR values can occur even when the light source is nearly centered, so the comparison logic needs to avoid unnecessary or continuous movement. This helped us understand that practical control systems require suitable decision-making rather than simply responding to every small change in sensor readings.

## What We Learned

Through this task, we learned how **light sensors can be integrated with a microcontroller to control mechanical movement**. We understood the working principle of LDRs, analog sensor readings, servo motor control, and basic conditional logic in Arduino programming.

The task also helped us understand the basic concept of a **solar tracking mechanism**. Instead of keeping the solar panel fixed in one direction, the tracking system attempts to maintain a favourable orientation with respect to the strongest available light source. We learned how a simple combination of sensors, a controller, and an actuator can be used to create an automatic mechanical system.

Overall, the task gave us practical experience in combining **electronics, programming, sensing, and mechanical actuation** to solve a real-world engineering problem. It also demonstrated how automation can be used to improve the efficiency of energy-collection systems.


# Task 2 – SPI Communication

## What the Task Was

The second task involved implementing **SPI (Serial Peripheral Interface) communication** using Arduino boards. The objective was to understand how digital devices communicate using SPI and how a **master device exchanges data with a slave device**. SPI is commonly used for communication between microcontrollers and peripherals such as SD card modules, displays, sensors, and other microcontrollers.

The task specifically focused on understanding the four primary SPI signals: **MOSI, MISO, SCK, and SS**. We also had to understand how these signals work together to provide synchronized and full-duplex communication between the master and slave.

## How We Approached the Task

We first studied the purpose of each of the four SPI communication lines. **MOSI (Master Out Slave In)** is used to transmit data from the master to the slave, while **MISO (Master In Slave Out)** carries data from the slave back to the master. **SCK (Serial Clock)** provides the clock signal generated by the master to synchronize the data transfer. **SS (Slave Select)** is used by the master to select the particular slave with which it wants to communicate.

After understanding the individual signals, we implemented the communication using **two Arduino boards**, with one configured as the master and the other as the slave. The required SPI connections were established between the boards, ensuring that the corresponding communication lines were connected correctly. The boards were also given suitable power and common ground connections so that the communication signals had a common reference.

We then programmed the master to transmit a specific value to the slave and configured the slave to receive the transmitted data. The slave was also programmed to respond with data, allowing us to test communication in both directions. This helped us understand the **full-duplex nature of SPI**, where transmission and reception can take place during the same clocked communication process.

During the implementation, we encountered issues while establishing communication and therefore had to troubleshoot the connections and program configuration. We checked the SPI wiring, the roles assigned to the two Arduino boards, and the transmitted and received values. We also monitored the communication behaviour and used the output from the Arduino environment to verify whether the expected values were being exchanged.

After troubleshooting, the communication was successfully verified. The master was able to send a value to the slave and receive the expected response back. This confirmed that the SPI connection and program logic were functioning correctly. We also understood that the labels of **master and slave are based on their programmed communication roles**, rather than simply the physical position of the Arduino boards.

## What We Learned

This task gave us practical knowledge of **SPI communication and master-slave data exchange**. We learned the purpose of MOSI, MISO, SCK, and SS and understood how the clock signal synchronizes the transfer of data between the communicating devices.

We also learned that SPI communication requires both **correct hardware connections and appropriate software configuration**. Even a small wiring or configuration error can prevent successful communication, making systematic troubleshooting an important part of embedded-system development.

The task also helped us understand the concept of **full-duplex communication**, where the master and slave can exchange data through separate transmission and reception lines. By implementing the communication ourselves, we gained a clearer understanding of how SPI can be used for communication between a microcontroller and external peripherals or another microcontroller.

Overall, the SPI task provided practical exposure to **embedded communication protocols, Arduino programming, digital data transfer, hardware interfacing, and debugging**. It helped bridge the gap between the theoretical concept of SPI and its actual implementation using hardware.


## Component and Equipment Cataloguing

Maintaining accurate documentation of laboratory components, tools, kits, and equipment is essential for keeping the lab organized and ensuring that available resources can be easily identified and accessed. A proper inventory system helps distinguish newly acquired components from existing ones while providing information about their **type, quantity, specifications, condition, and storage location**. Recording the exact storage location, such as a particular box, rack, shelf, or cupboard, also reduces the time required to locate components and helps prevent misplacement or duplication of items. Regularly updating such records ensures that the laboratory maintains a reliable and accessible inventory of its resources.

As part of this task, I worked on identifying and documenting a range of **electronics, EV, and IoT components** available in the laboratory. Each component was inspected and its relevant information was systematically recorded in an **Excel sheet** according to the required cataloguing format. The details included the **component name, quantity, type, technical specifications, storage location, and condition** wherever applicable. Particular attention was given to identifying where each component was physically stored, including the respective **boxes, racks, shelves, and cupboards** assigned to them.

The cataloguing process also involved differentiating between various types of components and understanding their intended applications, particularly in the areas of **electronics, electric vehicles, and IoT systems**. This helped create a more structured inventory and made it easier to associate each component with its corresponding storage location and technical purpose. The completed Excel catalogue can be further updated whenever new components are acquired, existing components are relocated, or their quantities and conditions change, providing the lab with a systematic record for future reference and efficient resource management.

