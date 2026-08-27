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









