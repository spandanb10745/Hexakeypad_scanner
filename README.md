# 🔢 Hexadecimal Keyboard Scanner (Verilog)

**Author:** Spandan Bharadwaj  
**ID:** 230102108  
**Tool:** Vivado (Xilinx FPGA)  
**Language:** Verilog HDL  

---

## 📌 Project Overview

This project implements a **Hexadecimal Keypad Scanner** using **Verilog HDL**, designed for a 4x4 matrix keyboard (16 keys: 0–9, A–F). The design is modular, with separate components for scanning, synchronization, row signal generation, and output encoding. The project is built and simulated using **Vivado**.

---

## 🧩 Functional Highlights

- 🔄 **Row scanning logic** for 4x4 keypad  
- 📥 **Column reading and hex encoding**  
- 🧼 **Input synchronization** to avoid glitches and metastability  
- 🧪 **Testbench** for simulation and verification  
- 📝 **Hand-drawn architectural block diagram** included  

---

## 🗂️ Repository Structure

| File/Folder Name                    | Description                                                                 |
|------------------------------------|-----------------------------------------------------------------------------|
| `Hexa_keypad_asm_diagram.pdf`      | Hand-drawn architecture and block-level diagram                            |
| `Signal_Row_Verilog.v`             | Module to generate scanning signal for keypad rows                         |
| `hex_keyboard_Verilog.v`           | Main controller to process keypress and determine hex value                |
| `synchronizer_Verilog.v`          | Synchronizer module to stabilize input signal transitions                  |
| `Hexadecimal_Keyboard_scanner.v`   | Top-level wrapper module that integrates all submodules                    |
| `testbench_hex_keyboard.v`         | Testbench for simulating key presses and validating output behavior        |
| `README.md`                        | Project documentation (this file)                                          |

---

## 🧠 How It Works

1. **Row Activation:**  
   A row signal generator (`Signal_Row_Verilog`) sequentially drives each row low, enabling row-wise scanning.

2. **Column Detection:**  
   When a key is pressed, the corresponding column goes low, indicating the position of the key in the matrix.

3. **Synchronization:**  
   The `synchronizer_Verilog` module filters the input signals to avoid glitches and metastability due to key bounce.

4. **Hex Decoder:**  
   `hex_keyboard_Verilog` interprets the (row, column) combination and outputs a 4-bit hex code (0–F).

5. **Integration:**  
   The `Hexadecimal_Keyboard_scanner` module brings all components together into a unified design for synthesis/simulation.

---

## 🧪 Simulation

To run simulation in **Vivado**:

1. Add all Verilog files to your Vivado project.  
2. Set `testbench_hex_keyboard.v` as your simulation top.  
3. Run behavioral simulation and observe outputs using Vivado waveform viewer.

---

## 🖼️ Architecture Diagram

![ASM Diagram](Hexa_keypad_asm_diagram.pdf)

This PDF provides a visual overview of module interconnections and control logic.

---

## 📊 Example Output

| Pressed Key | Output (Binary) | Output (Hex) |
|-------------|------------------|---------------|
| 5           | `0101`           | 5             |
| A           | `1010`           | A             |
| F           | `1111`           | F             |

---

## 🔧 Tools & Technology

- **Vivado Design Suite** (Xilinx FPGA Simulation/Synthesis)  
- **Verilog HDL**  
- **4x4 Membrane Hex Keypad (Target)**  
- Optional future support for 7-segment displays or LCD  

---

## 📚 References

- Course: EE206 – Digital & Analog Circuits  
- Datasheet for 4x4 Matrix Keypad  
- Xilinx Vivado Documentation  
- *Verilog HDL* – Samir Palnitkar  

---

## 🚀 Future Enhancements

- Add debouncing using counters or FSMs  
- Interface output with 7-segment or LCD display  
- Extend support to detect simultaneous keypresses (N-key rollover)  
- Synthesize and deploy on FPGA development board
