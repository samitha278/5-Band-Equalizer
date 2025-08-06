# 🎚️ 5-Band Analog Audio Equalizer - Hertz Labs

A robust, fully analog 5-band audio equalizer designed and built by undergraduate students of the Department of Electronic and Telecommunication Engineering, University of Moratuwa. The project features selective gain control across five standard audio frequency bands, with a real-time LED bar display for audio levels — all using only fundamental analog components like op-amps, resistors, capacitors, and transistors.

> 📡 Designed for: EN2091 Laboratory Practice and Projects  
> 🧪 Built by: Team Hertz Labs  
> 🎓 University of Moratuwa

---

## 📷 Project Overview

This 5-band equalizer allows users to independently adjust the gain across the following audio frequency bands:

- **20 Hz – 300 Hz** (Sub-bass)
- **300 Hz – 1 kHz** (Bass/Mid)
- **1 kHz – 4 kHz** (Midrange)
- **4 kHz – 10 kHz** (Upper midrange)
- **10 kHz – 20 kHz** (Treble)

The design ensures minimal distortion when idle, accurate band separation, and robust gain control without digital processing — preserving the integrity of the original analog signal.

---

## 🧩 System Architecture

The system is divided into two main blocks:

### 1. 🎛️ Filter & Control Section
- **Input/Buffer Stage:** Inverting amplifier with a gain of -2 and DC shift to mid-voltage.
- **Filter Bank:** Five fourth-order bandpass filters, each built using two cascaded Sallen-Key second-order filters.
- **Adder Stage:** Inverting summing amplifier that combines the filtered signals, each weighted by a volume potentiometer.
- **Mid-Voltage Generator:** Provides a virtual ground reference for single-supply operation.

### 2. 💡 Display Section
- **Differential Amplifiers:** Monitor current flow to the adder circuit without affecting audio fidelity.
- **LED Display Driver:** LM3914 IC used to drive 10-segment LED bar graphs for each frequency band.

---

## 🧠 Key Design Choices

- **Single-Supply Design:** Operates at 18V with mid-voltage reference, avoiding complex dual supply requirements.
- **High-Order Filters:** Fourth-order filtering for each band ensures steep roll-off and minimal overlap.
- **Current-Limiting Resistors:** Prevents saturation at the adder stage and ensures smooth audio performance.
- **Component Compactness:** Utilized SMD op-amps (TL072) for filters and through-hole components where needed for durability and signal integrity.

---

## 📐 Hardware and PCB

- **Design Software:** Altium Designer (2-layer PCB)
- **Main PCB Size:** 100 mm × 84 mm
- **Display PCB Size:** 100 mm × 100 mm
- **Enclosure:** Custom-designed with SolidWorks. PLA+ 3D printed main body + laser-cut plywood front panel.
- **Inputs/Outputs:** 3.5 mm audio jacks and barrel jack for power input.

---

## 🔬 Simulation & Testing

- **Simulation Software:** LTSpice
- **Verification:** Individual filter responses and system-level flat gain tested in simulation.
- **Prototyping:** Breadboard implementation before final PCB.
- **Final Testing:** Oscilloscope and audio output testing verified each band’s control and system integrity.

---

## 🛠️ Components Used

| Component       | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| TL072 Op-Amp   | Low noise, low distortion, wide bandwidth — ideal for audio applications.  |
| LM3914         | Bar graph LED driver with linear scale, built-in reference voltage.         |
| Potentiometers | Sliding potentiometers used for precise gain control of each band.          |
| Passive Parts  | Standard 0.25W resistors, film capacitors selected for precision and stability. |

---

## 🚧 Future Improvements

- 🔋 **Custom Power Supply**: Develop an in-house 18V power supply for standalone operation.
- 💡 **Display Enhancement**: Refine LED driver circuit for more accurate real-time response.
- 🔊 **More Bands**: Extend to a 7-band or 10-band equalizer for finer audio tuning.

---

## 👥 Team Members

-Jayakody J.A.K
-Pelagewatta H.P
-Jayarathne H.A.C.N
-Bandara M.A.G.S

---

## 🔗 References

- [LM3914 Datasheet](https://www.ti.com/lit/ds/symlink/lm3914.pdf)
- [Sallen-Key Filter Design Guide - TI](https://www.ti.com/lit/pdf/sloa096)
- [Medium Blog Inspiration](https://medium.com/@vgr0876/5-band-audio-equalizer-8df9b991d8ea)

---

## 📂 Repository Structure

```bash
5-Band-Equalizer-HertzLabs/
├── Schematics/           # LTSpice and Altium design files
├── PCB_Design/           # PCB layout files (Main + Display)
├── Enclosure/            # SolidWorks and Laser-cut designs
├── Media/                # Photos and demo videos
├── Report/               # Final PDF report and documentation
└── README.md             # This file
