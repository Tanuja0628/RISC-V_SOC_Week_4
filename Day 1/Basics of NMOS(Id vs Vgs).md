# Basics of Nmos (Id vs Vgs)
## Experiment 1: NMOS Transistor – DC Characteristics
The goal of this experiment is to replicate and analyze the Id versus Vds characteristics of an NMOS transistor utilizing the Sky130 technology models. This will assist in understanding how the MOSFET behaves in each of the three operational regions — cutoff, linear (ohmic), and saturation — as well as how Vgs will affect the Id. Analyzing these characteristics sets the stage for understanding transistor-level behavior; device modeling; and circuity design considerations such as mobility, channel length modulation, and threshold voltage.

## Model Description
```spice
.param temp=27

* Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

* Netlist Description
XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=5 l=2
R1 n1 in 55

Vdd vdd 0 1.8V
Vin in 0 1.8V

* Simulation commands
.op
.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2

.control
run
display
setplot dc1
.endc

.end
```
## Simulation Setup
- Tool used: Ngspice
- Technology: SkyWater 130nm PDK
- Device type: NMOS (sky130_fd_pr__nfet_01v8)
- Bias range:𝑉𝐷𝐷: 0V → 1.8V
             Vin: 0V → 1.8V
## Observation
- We observe that there is a minute current at Vgs=0.6V (cut off region)
- There is no plot observed for Vgs=0.2V and 0.4V , because for the transistor to be on, Vgs shd be atleast Vth=0.56V.

### Results

The table below summarizes the observed drain current (\(I_D\)) behavior for different gate voltages (\(V_{GS}\)):

| Vgs (V) | Id vs Vds Observation | Region of Operation |
|----------------|----------------------------------|------------------|
| 0.6            | Id increases almost linearly with Vds; no clear saturation. | Linear (Ohmic) region |
| 0.8            | Id increases linearly at first, then starts to saturate around Vds \approx 0.4V. | Transition region |
| 1.0            | Higher Id; clear saturation beyond Vds approx 0.55V. | Saturation region |
| 1.2            | Id increases further; saturation current significantly higher. | Saturation region |
| 1.4            | Id reaches maximum slope; channel fully inverted. | Deep saturation |

**Extracted Parameters:**

| Parameter              | Symbol        | Value / Relation             | Observation |
|------------------------|---------------|-----------------------------|-------------|
| Threshold Voltage       | Vth    | ≈ 0.45 V                   | From Id–Vgs curve (model value) |
| Saturation Voltage      | Vds(sat)| ≈ Vgs-Vth      | Marks transition from linear to saturation |
| Channel Length Modulation | lambda  | Small slope in saturation region | Indicates slight increase of \(I_D\) with \(V_{DS}\) |

### Plot
![Id-Vds_Curve](Day_1/Id_vs_Vds.jpg)
