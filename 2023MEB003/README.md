# Manufacturing Cell Unit — Discrete-Event Digital Twin

A baseline discrete-event simulation model of an automated manufacturing cell pipeline developed in **MATLAB SimEvents (R2026a)**.

---

## 📌 Project Overview

This model simulates the flow of workpieces across a linear manufacturing cell:
Raw Material Inflow ➔ Buffer Queue ➔ CNC Machining ➔ Conveyor Belt ➔ Inspection Station ➔ Finished Goods Sink

---

## ⚙️ Configured Parameters

* **Raw Material Inflow (`Entity Generator`):** Generates 1 raw workpiece blank every **15 s**.
* **Part Buffer (`Entity Queue`):** Capacity of **10 parts**, FIFO order.
* **CNC Machining (`Entity Server`):** Machining service time of **10 s** (Capacity = 1).
* **Conveyor Belt (`Entity Transport Delay`):** Transit delay time of **5 s** (driven via a `Constant` block).
* **Quality Inspection (`Entity Server`):** Inspection service time of **8 s** (Capacity = 1).
* **Finished Goods Sink (`Entity Terminator`):** Outputs total completed workpiece count.

---

## 📊 Instrumentation

* **Display Block:** Connected to the `a` (arrived) port of the Terminator to monitor total finished parts.
* **Scope Block:** Connected to the `n` (entities in block) port of the Queue to plot buffer buildup and depletion in real time.

---

## 🚀 How to Run

1. Open **MATLAB R2026a**.
2. Open the file `manufacturing_cell_pipeline.slx`.
3. Set **Stop Time** to `100`.
4. Click **Run**.
5. View total completed parts on the **Display** block and real-time buffer history on the **Scope** block.
