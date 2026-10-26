# Lab 1 — SENSE: Giving a System Senses

- Team name:f26-cecs1011-team1515-labs
- GitHub usernames:ngquann3007-rgb

Complete the tasks below in the same order as the lab handout. Replace prompts with your results and keep units visible.

## How to insert your photos

1. Save your own measurement photos as JPG or PNG. Use clear filenames, such as `fixed-resistor.jpg` or `ldr-covered.png`.
2. Upload them to `labs/lab-01/evidence/` in this private Labs repository using **Add file → Upload files**, then commit the upload. If the folder is missing, follow [Lab 1, Step 5](https://vinuni-cecs1011.github.io/labs/lab-01.html#upload-photos) to create it.
3. Edit this report. Replace each **Insert your photo here** prompt with an image line using your actual filename, for example: `![Fixed-resistor measurement showing the reading and unit](evidence/fixed-resistor.jpg)`. Paste the line without surrounding backticks. The `!` displays the photo inside the report.
4. Add a short caption below the image. Select **Preview** and check that the photo is visible, the reading/unit can be read, and the caption explains the result. Check filename spelling, extension and letter case if the image does not appear.
5. Commit the report update using your own account. Keep the photos in the repository so the submitted version contains both the report and evidence.

This starter contains no example photos. Insert your team's own evidence. Remove these setup instructions when your report is complete. Follow [the handout](https://vinuni-cecs1011.github.io/labs/lab-01.html) for the experiment and final submission checklist.

## Part 1: Meet the tools and the sensor

### Task 1. Measure a fixed resistor

- **Nominal resistance and marked tolerance:** The measured resistance was 9.8845 kΩ. The nominal value and marked tolerance of the resistor must be confirmed from the component markings or lab materials.
- **Measured resistance:** 9.8845 kΩ.
- **Acceptable range and comparison:** If the resistor is rated at 10 kΩ ±5%, its acceptable range is:

  Minimum = 10 × (1 − 0.05) = 9.5 kΩ

  Maximum = 10 × (1 + 0.05) = 10.5 kΩ

  The measured value of 9.8845 kΩ is within this range, provided that the nominal value is 10 kΩ and the tolerance is ±5%.

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/bde99774-d2e7-411e-9fca-726a75f80d1e" />


### Task 2. Investigate the photoresistor

- **How we reproduced the exposed and covered conditions:** The LDR was measured under exposed-light conditions and then covered by a hand to reduce the light reaching its surface.
- **Exposed LDR resistance:** 15.14 kΩ.
- **Covered LDR resistance:** 82.019 kΩ.
- **How resistance changes with light:** The LDR resistance increased when the sensor was covered, indicating that its resistance increased as the incident light intensity decreased.
- **Our prediction for Vout when covering the LDR:** We predicted that Vout would increase because the LDR was connected between Vout and GND, while the fixed resistor was connected between the supply and Vout.
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/20d527af-c0ba-4486-8cb1-63b7c07baad6" />
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/ce4796de-349d-4ffa-ba94-de8e4350001a" />


## Part 2: Build the sensor circuit

### Task 3. Set up the power supply

- Supply setting: 5 V; current limit: 0.01 A (10 mA).
- Measured supply voltage, Vs (V):

### Task 4. Build a voltage divider

The voltage divider consists of a fixed resistor connected between the positive supply and Vout, and an LDR connected between Vout and GND.
The output voltage is measured at the junction between the two resistors relative to GND.

### Task 5. Measure the output voltage
The voltage-divider equation is:

Vout = Vs × Rphoto / (Rs + Rphoto)

For the calculations below, the nominal supply setting of 5.00 V is used as a calculation assumption, not as a confirmed measured supply voltage. The fixed resistance used is 9.8845 kΩ.

**Exposed condition:**

Vout = 5.00 × 15.14 / (9.8845 + 15.14)

Vout ≈ 3.03 V

**Covered condition:**

Vout = 5.00 × 82.019 / (9.845 + 82.019)

Vout ≈ 4.46 V

| Condition and method | LDR resistance (kΩ) | Calculated output (V) |       Measured output (V) |
| -------------------- | ------------------: | --------------------: | ------------------------: |
| Exposed to light     |               15.14 |                3.03\* | 2.1151 or 2.1551 — verify |
| Covered by hand      |              82.019 |                4.46\* |                      4.45 |

*Calculated using an assumed supply voltage of 5.00 V. Recalculate using the measured supply voltage if it differs from 5.00 V.*

- **Explanation of the observed change in Vout:** Covering the LDR increased its resistance. This increased the fraction of the supply voltage across the LDR and raised Vout.
- **Comparison of calculated and measured output:** The covered-condition calculated value of approximately 4.46 V is close to the reported measurement of 4.45 V. For the exposed condition, the measured voltage is lower than the calculated value. The discrepancy should be checked against the original multimeter reading, actual supply voltage, resistor identification, and circuit connections.
- **One limitation:** The calculations assume a fixed supply voltage and use resistance measurements taken separately from the voltage measurements. Changes in illumination, measurement conditions, component tolerances, and connection resistance may contribute to differences between calculated and measured values.

## Part 3: Observe the signal over time

### Task 6. Connect the oscilloscope

- Probe tip and ground-reference connections:
- Probe attenuation and matching oscilloscope setting:

### Task 7. Observe the live signal

**Insert your photo here:** oscilloscope capture showing the signal change, with voltage and time scales visible. Add a caption describing what the trace shows. If you use a short recording instead, insert an accessible recording link here and explain the same result.

- Voltage scale and time scale:
- What changed when we covered/uncovered the LDR: The voltage-divider model predicts that Vout increases when the LDR is covered and decreases when it is exposed to more light. The actual oscilloscope trace must be checked to confirm this behavior over time.

- Comparison with the multimeter readings: The multimeter provides individual voltage readings, whereas an oscilloscope trace can show how the voltage changes over time, including the response when the light condition changes. No direct comparison with an oscilloscope trace can be reported until the trace is available.

## Project connection

Our project is different from the LDR experiment, so the relevant measured quantity should be selected according to the project's actual purpose.

A sensor-based system could measure a physical quantity such as temperature, distance, or gas concentration. The measurement could support a decision such as triggering a warning when a predefined threshold is reached.

An important assumption to test is whether the sensor readings are sufficiently accurate and reliable under the conditions in which the system will operate. The actual project-specific quantity, decision, and assumption should be updated to match our team's project.

## Contributions

| GitHub username | Work completed and result I can explain | Evidence or report section |
|---|---|---|
| `tdph08` | Measured the LDR resistance under exposed and covered conditions, recorded the readings, and analyzed how light intensity affects resistance. | Task 2; LDR measurements and observations |
| `minhduc108` | Helped assemble the sensor circuit and monitored the team's progress to keep the lab work on schedule. | Task 4; circuit assembly |
| `mixaobo0312` | Configured the power supply settings and helped check the voltage and current limit before circuit testing. | Task 3; power supply setup |
| `ngquann3007-rgb` | Coordinated team tasks, organized the submission, and helped compile the measurement results and report. | Report organization; submission coordination |
| `minh tri` | Helped measure and record circuit output voltages under exposed and covered LDR conditions and compare the measured values with the calculated results. | Task 5; output-voltage measurements and calculations |


## Sources and AI use
**Source:** [CECS1011 Lab 1 — SENSE: Giving a System Senses](https://vinuni-cecs1011.github.io/labs/lab-01.html).
**AI use disclosure:** ChatGPT was used to help organize the report, improve English wording, explain the voltage-divider equation, and check calculations based on the measurements provided by the team. Numerical values were taken from the supplied measurement photos and results table. Missing measurements were marked as unavailable rather than invented. The team should verify all values against the original lab evidence and confirm that this disclosure complies with the course's AI-use guidelines.and results table. Missing measurements were marked as unavailable rather than invented. The team should verify all values against the original lab evidence and confirm that this disclosure complies with the course's AI-use guidelines.
