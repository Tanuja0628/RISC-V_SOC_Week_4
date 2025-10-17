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


The image illustrates the body effect in an n-channel MOSFET by showing two scenarios with different source-to-bulk voltages (\(V_{sb}\)).     .rPeykc.rWIipd{font-size:var(--m3t5);font-weight:500;line-height:var(--m3t6);margin:24px 0 10px 0;}.f5cPye .WaaZC:first-of-type .rPeykc.uP58nb:first-child{font-size:var(--m3t3);line-height:var(--m3t4);font-weight:400 !important;letter-spacing:normal;margin:0 0 10px 0}.rPeykc.uP58nb{font-size:var(--m3t5);font-weight:500;line-height:var(--m3t6);margin:20px 0 10px 0}.rPeykc.uP58nb.MNX06c{font-size:var(--m3t1);font-weight:normal;letter-spacing:normal;line-height:var(--m3t2);margin:10px 0 10px 0}.f5cPye ul{font-size:var(--m3t7);line-height:var(--m3t8);margin:10px 0 20px 0;padding-inline-start:24px}.f5cPye .WaaZC:first-of-type ul:first-child{margin-top:0}.f5cPye ul.qh1nvc{font-size:var(--m3t7);line-height:var(--m3t8)}.f5cPye li{padding-inline-start:4px;margin-bottom:8px;list-style:inherit}.f5cPye li.K3KsMc{list-style-type:none}.f5cPye ul>li:last-child,.f5cPye ol>li:last-child,.f5cPye ul>.bsmXxe:last-child>li,.f5cPye ol>.bsmXxe:last-child>li{margin-bottom:0}          \(V_{sb}=0\)               In this scenario, the source (S) and the bulk (B) are connected, meaning they are at the same potential.     The voltage between the source and bulk is zero (\(V_{sb}=0\)). The p-n junction between the source and the p-substrate is not reverse-biased. The threshold voltage (\(V_{th}\)) is at its minimum value for the device, as there is no body effect. The channel is formed by the electric field from the gate voltage, which attracts electrons from the source and drain regions to the surface of the p-substrate, creating an n-type channel.
