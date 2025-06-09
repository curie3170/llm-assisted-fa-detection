# 🧠 llm-verilog-fa-annotator

> Detect and annotate Full Adder (FA) logic in Verilog circuits using AIG-level structural analysis and large language models (LLMs).

---

## 📌 Overview

This project implements an automated pipeline for detecting Full Adder (FA) logic in Verilog designs. It uses:

- **Yosys** for synthesis and AIG (And-Inverter Graph) generation
- **Rule-based pattern matching** to identify FA structures
- **GPT-4.1 (LLM)** to annotate Verilog code with FA detection
- **Statistical comparison** between original and optimized designs

The result is a fully annotated Verilog design with structural FA logic clearly labeled, and resource usage visibly improved.

---
---

## 🚀 How It Works

1. **Verilog Input**  
   Load a Verilog design implementing FA logic using XOR/AND/OR gates.

2. **AIG Generation**  
   Use Yosys to synthesize the circuit and output an AIG (`.aag`) file.

3. **FA Detection (Rule-Based)**  
   Analyze the AIG netlist to detect structural FA patterns (3-inputs → sum/carry).

4. **LLM Annotation**  
   Construct a prompt and send it to GPT-4.1 to annotate the original Verilog code.

5. **Comparison & Optimization**  
   Synthesize both original and modified versions, compare cell counts and logic efficiency.

---

## 📊 Example Result

| Metric    | Original | Modified |
|-----------|----------|----------|
| FA_CELL   | 0        | 1 ✅      |
| AND Gates | 3        | 2 ↓      |
| OR Gates  | 2        | 1 ↓      |
| XOR Gates | 2        | 2        |

---

## 🛠️ Requirements

- Python 3.8+
- [Yosys](https://github.com/YosysHQ/yosys)
- OpenAI API access (for GPT-4.1)

---

## 💡 Future Work

- Detect multiple FAs across larger designs
- Support other arithmetic primitives (HA, CLA)
- Integrate Netlist-to-Verilog rewriting

---

## 📜 License
Credits to Yosys and OpenAI for core technologies.
