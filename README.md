# Task-1 : BabySoC Fundamentals


## 🧩 1. Understanding System-on-Chip (SoC)

A **System-on-Chip (SoC)** is essentially a miniature computer built onto a single silicon chip.  
It integrates all the key components required for computation, communication, and control — making it compact, efficient, and highly power-optimized.

For example, in a **traditional computer**, we have a **central CPU core** (from Intel or AMD) mounted on a **motherboard**.  
The motherboard houses all the necessary circuitry and components required for the CPU to function properly — such as timers, counters, interrupt controllers, RAM, code memory, HDD interface, clock generators, frequency dividers, I/O controllers, peripheral interfaces, and various protocol handlers.  

This setup is **modular and repairable**, meaning any faulty part (like RAM or storage) can be replaced independently.  
However, it also **occupies more space** and **consumes more power**, since all components are placed on a large PCB and connected through external buses.

In contrast, an **SoC** (like Apple’s *M-series chips*) integrates all these components — the **CPU core, memory, clocking circuits, I/O interfaces, and peripherals** — onto a **single silicon wafer**.  
This drastically **reduces area and power consumption**, making SoCs ideal for **portable and low-power devices** such as smartphones, tablets, and wearables.  

The trade-off, however, is **repairability** — since everything is fabricated together, replacing or upgrading a single component isn’t possible.  


### ✳️ Key Components of an SoC
- **CPU (Central Processing Unit):**  
  Acts as the brain of the system, executing instructions and managing all operations.  

- **Memory:**  
  - **RAM** for temporary data storage during operation/runtime. 
  - **ROM/Flash** for permanent data storage.  

- **I/O Interfaces:**  
  Enable communication with external peripherals like sensors, displays, or network interfaces.  

- **GPU (Graphics Processing Unit):**  
  Handles image and video rendering.  

- **DSP (Digital Signal Processor):**  
  Specializes in audio, video, and signal processing tasks.  

- **Power Management Unit (PMU):**  
  Controls energy distribution to ensure efficiency and longer battery life.  

- **Connectivity Modules (Wi-Fi, Bluetooth, etc.):**  
  Enable wireless communication and data transfer.  

### 💡 Advantages of SoC
- Compact and space-saving.  
- Lower power consumption.  
- Improved processing speed due to shorter data paths.  
- Cost-effective and reliable with fewer interconnections.  

### 📱 Applications
Used in smartphones, IoT devices, wearables, automotive systems, and embedded applications and nowadays even in laptops. 

---

## 🧱 2. Types of SoCs
1. **Microcontroller-based SoC:**  
   Designed for simple, low-power control applications like home appliances or IoT systems.  

2. **Microprocessor-based SoC:**  
   Designed for higher computational needs — found in smartphones and tablets.  

3. **Application-Specific SoC (ASIC-based):**  
   Custom-built for particular applications like AI accelerators, GPUs, or networking hardware.  

---

## 🧭 3. Introduction to VSDBabySoC  

**VSDBabySoC** is a simplified yet powerful RISC-V based SoC, created for educational and open-source experimentation.  

### 🧠 Core Components  
- **RVMYTH Processor (RISC-V CPU):**  
  The main processing unit that handles instruction execution. Learn more about RVMYTH [here](https://github.com/kunalg123/rvmyth)

- **Phase-Locked Loop (PLL):**  
  Generates a stable and synchronized clock for all modules.  

- **10-bit Digital-to-Analog Converter (DAC):**  
  Converts digital data from RVMYTH into analog signals for external output (e.g., sound/video).  

### ⚡ Internal Operation  
1. **Initialization & Clock Generation:**  
   The PLL locks onto an input reference and produces a stable system clock.  

2. **Data Processing in RVMYTH:**  
   The CPU processes data and writes values to the DAC input register.  

3. **Analog Signal Generation via DAC:**  
   The DAC converts the processed digital values into analog signals, enabling BabySoC to interface with real-world devices such as TVs or speakers.  

---


## 🪄 4. Key Analog IPs in BabySoC  

### 🕒 Phase-Locked Loop (PLL)
- Maintains phase and frequency alignment with a reference clock.  
- Consists of:  
  - **Phase Detector**  
  - **Loop Filter**  
  - **Voltage-Controlled Oscillator (VCO)**  
- Ensures synchronized operation across digital and analog modules.  

**Why internal PLL is preferred over off-chip clocks:**  
- Reduces distribution delay and clock jitter.  
- Provides multiple frequency domains for different SoC blocks.  
- Maintains timing accuracy despite environmental variations.  

### 🎚️ Digital-to-Analog Converter (DAC)
- Converts digital binary values into continuous analog voltages.  
- Two major types:  
  1. **Weighted Resistor DAC**  
  2. **R-2R Ladder DAC**  
- In BabySoC, a **10-bit DAC** produces precise analog output corresponding to the RVMYTH processor’s digital output stream.  

---

## 📘 6. Why BabySoC Matters  
VSDBabySoC serves as an excellent educational and research platform because:  
- It integrates **digital (RISC-V)** and **analog (PLL & DAC)** components.  
- Provides a **complete SoC workflow** — from functional modelling to physical implementation.  
- Encourages learning open-source EDA tools and Sky130 technology.  
- Builds a foundation for **digital-analog interfacing and RISC-V system design**.  

---

- BabySoC architecture  
- Role of functional modelling in design verification  

All results, simulations, and notes should be documented clearly on GitHub under **Week-02: BabySoC Fundamentals & Functional Modelling**.  

---
