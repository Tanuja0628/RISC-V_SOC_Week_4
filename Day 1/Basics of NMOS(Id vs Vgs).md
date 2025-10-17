# Basics of Nmos (Id vs Vgs)

It is necessary to understand the transister level behaviour of our circuit to study and analyse its variations and finally fabricate a fairly  good System on Chip

---

## Why do we need spice?
- SPICE (Simulation Program and Integrated Circuit Emphasis) helps to predict the circuit behaviours before fabrication
- it shows IV charcteristics, threshold shifts and region boundaries (linear/saturation).
- Enables us to tune W/L ratio, bias volteges and other technological parameters
"SPICE simulations allow accurate prediction of device and circuit behavior, saving cost and time by verifying the design before fabrication"
### In genral these are the questions for which Spice is the answer!!
- " where does the delay of a cell actually comes from?"
- " Are the delay models accurate?"
- "How to verify, if our static timing analysis, is correct?"

---

## Introduction to NMOS
An NMOS is a four-terminal device consisting of a P-substrate with n+ diffusion regions for the source and drain, and a gate made of polysilicon or metal separated by a gate oxide. The four terminals are the gate (G), source (S), drain (D), and body (B).
Threshold voltage is the minimum gate-source voltage (\(V_{gs}\)) that needs to be applied to a device, such as a MOSFET, to turn it on. When the gate-source voltage is zero, the p-n junctions are off, and the source-drain resistance is high. Applying a positive \(V_{gs}\) voltage is the first step to turning the device on.

---

## Strong Inversion and Threshold Voltage
Threshold Voltage

The threshold voltage is defined as the minimum gate-to-source voltage required to form a conducting path (the channel) between the source and drain terminals. In the case of an n-channel MOSFET, the substrate is made of p-type silicon. Once a positive voltage is applied to the gate, electrons are attracted from the p-type substrate to the semiconductor-oxide interface, and holes are repelled.

Initially, at small positive gate voltages, the holes are merely pushed away from the oxide interface and a depletion region (a region with no majority carriers) exists near the oxide interface. The threshold voltage is the gated voltage level when the gate voltage can push away a significant amount of holes and also attract enough electrons to the interface to make the surface behave as an n-type material.

The image illustrates the body effect in an n-channel MOSFET by showing two scenarios with different source-to-bulk voltages ($V_{sb}$).

### Case 1: $V_{sb} = 0$
In this scenario, the source (S) and the bulk (B) are connected, meaning they are at the same potential.  
The voltage between the source and bulk is zero ($V_{sb} = 0$).  
The p-n junction between the source and the p-substrate is not reverse-biased.  
The threshold voltage ($V_{th}$) is at its minimum value for the device, as there is no body effect.  
The channel is formed by the electric field from the gate voltage, which attracts electrons from the source and drain regions to the surface of the p-substrate, creating an n-type channel.

### Case 2: $V_{sb} > 0$

In this scenario, a positive voltage is applied between the source (S) and the bulk (B), meaning the source is at a higher potential than the bulk.  
The voltage between the source and bulk is positive ($V_{sb} > 0$).  

This positive voltage reverse-biases the p-n junction between the source and the p-substrate.  
The reverse bias widens the depletion region under the channel, pushing the channel further away from the gate oxide.  

To form the channel, a larger gate-to-source voltage ($V_{gs}$) is required to overcome the increased depletion region width.  
This effect causes the threshold voltage ($V_{th}$) to increase.  

This phenomenon is known as the **body effect** or **substrate-bias effect**.  

The increase in threshold voltage is given by:

$$
V_{th} = V_{th0} + \gamma \left(\sqrt{2\phi_F + V_{SB}} - \sqrt{2\phi_F}\right)
$$

where:  
- $V_{th0}$ is the threshold voltage for $V_{SB} = 0$  
- $\gamma$ is the **body effect coefficient**  
- $\phi_F$ is the **Fermi potential**
