# LIC_EXP_REPORT
Linear Integrated Circuits, Experiment 1 - Report                                                                                                                     *_pavanracharya_*

# Experiment-1

**Objective:** Investigate DC, transient, and AC characteristics of two MOSFET circuit designs, and analyze the impact of MOSFET width variations on circuit performance.  Target power dissipation is 100µW.

# Design-1

![Design 1 Circuit](https://github.com/user-attachments/assets/0b661ae7-5761-4b9b-bd75-93c0fc60eabb)

**Aim:** Determine the DC operating point, and measure the gain using transient and AC analyses.

**Components:** MOSFET, resistors, DC power supply.

**Procedure:**

1. Assemble the circuit as shown.
2. Connect the drain resistor (RD) and DC power supply (VDD) as indicated.
3. Ground the source terminal.
4. Set the input voltage (Vin) to 0.9V and VDD to 1.8V.

**Calculations:**

Using P = V*I, the target drain current (Id) is calculated as 5.56 * 10^-5 A.  MOSFET dimensions (L and W) were adjusted to achieve this current.

![Design 1 L and W](https://github.com/user-attachments/assets/109d353f-a954-4e08-b8d1-603ea40ea67c)

**Analyses:**

**1) DC Analysis:**

*   Procedure: Select "DC op pnt" in the simulation settings and run the simulation.

![DC Analysis Setup](https://github.com/user-attachments/assets/8dbd733e-f0a2-4165-8a8e-ebee3b28ace2)

*   Results:

![DC Analysis Results](https://github.com/user-attachments/assets/22bca609-a67e-4459-aa60-e584eb189442)

**2) Transient Analysis:**

*   Procedure: Select "Transient Analysis," set stop time to 1ms, and run the simulation.

![Transient Analysis Setup](https://github.com/user-attachments/assets/e43f0303-c135-4a82-bc71-12e6ae6000b9)

*   Results:

![Transient Response](https://github.com/user-attachments/assets/87da114b-e8f6-4981-823f-d8a504316454)

**3) AC Analysis:**

*   Procedure: Select "AC Analysis," configure parameters as shown, and run the simulation.

![AC Analysis Setup](https://github.com/user-attachments/assets/f67f362a-312c-45c6-869a-bd410a0e133a)

*   Results:

![AC Response](https://github.com/user-attachments/assets/b4141a4f-8031-4fb8-b5a9-40fe35f9c590)

**Results (Design-1):**

1.  **DC Analysis:** The measured Id matched the calculated value (5.56*10^-5 A).  L=175nm and W=178nm were used.
2.  **Transient Analysis:**  Stable and predictable response observed.
3.  **AC Analysis:**  Gain of -9.94 dB and approximately 180-degree phase shift were observed, consistent with expectations.

**Inference (Design-1):**

1.  Precise control of Id is achievable through MOSFET dimension adjustments.
2.  Width variations of M1 directly influence Id. Increasing W increases Id, and vice-versa.
3.  Design-1 demonstrated reliable performance across all analyses.

# Design-2

![Design 2 Circuit](https://github.com/user-attachments/assets/59e297de-ed5d-426c-8e40-92aee8d3e793)

**Aim:**  Determine the DC operating point, and measure the gain using transient and AC analyses.

**Components:** MOSFETs (M1 and M2), DC power supply.

**Procedure:**

1.  Assemble the circuit.
2.  Connect VDD to the gate terminals.
3.  Ground the source terminals.
4.  Determine Vin for saturation using a VTC curve and set VDD to 1.8V.

**Calculations:**

Target Id remains 5.56 * 10^-5 A.  MOSFET dimensions were adjusted accordingly.

**VTC Curve and Vin Selection:**

A DC sweep analysis was performed to obtain the VTC curve.

![VTC Curve Setup](https://github.com/user-attachments/assets/b26e13fb-57be-4522-8e21-9b4730448512)

![VTC Curve](https://github.com/user-attachments/assets/abddb50e-8287-42ad-9dcc-fc4e29b37ff7)

Vin was chosen as 0.8V, within the saturation region.

![Input Voltage Parameters](https://github.com/user-attachments/assets/f60a3923-74f3-4b7b-8bd2-f000b36797cf)

**MOSFET Dimensions:**

![Design 2 M1 L and W](https://github.com/user-attachments/assets/2197048a-07ff-4819-ae53-b6f496449d35)
![Design 2 M2 L and W](https://github.com/user-attachments/assets/a2eae298-1edc-49bc-a925-278ec1eee622)

**Analyses:** (Similar setup as Design 1)

**1) DC Analysis:**

![DC Analysis Setup Design 2](https://github.com/user-attachments/assets/fe699e4e-be59-4a89-a524-8d88a54555c4)

![DC Analysis Results Design 2](https://github.com/user-attachments/assets/dded314a-ede4-45dd-aa51-d8a5251a6ec2)

**2) Transient Analysis:**

![Transient Analysis Setup Design 2](https://github.com/user-attachments/assets/c3faea32-8fd7-4cdb-9d7b-0b454f8d626b)

![Transient Response Design 2](https://github.com/user-attachments/assets/7d25b588-1dd1-406c-98cd-8fa4fc5c6163)

**3) AC Analysis:**

![AC Analysis Setup Design 2](https://github.com/user-attachments/assets/80e2d1d3-f2f6-4ce8-b26e-0a803006303a)

![AC Response Design 2](https://github.com/user-attachments/assets/e24ddc06-ca3f-41da-b214-6e012222aa04)

**Results (Design-2):**

1.  **DC Analysis:**  Target Id achieved. M1: L=500nm, W=950nm. M2: L=300nm, W=1020nm.
2.  **Transient Analysis:** Stable transient behavior observed.
3.  **AC Analysis:** Gain of 3.8 dB and ~180-degree phase shift.

**Inference (Design-2):**

1.  MOSFET dimensions effectively control Id.
2.  VTC curve facilitated appropriate Vin selection (0.8V).
3.  M2 width has a more significant impact on Id compared to M1.
4.  Design-2 performed as expected.
