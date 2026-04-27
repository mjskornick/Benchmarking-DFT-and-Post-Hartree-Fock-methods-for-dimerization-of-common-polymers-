# Benchmarking-DFT-and-Post-Hartree-Fock-methods-for-dimerization-of-common-polymers
This is a repository to store data collected for a project from my Physical Chemistry II class, where we created 6 week long computational chemistry research projects based on a topic that interested us. Mine is about polymers and i used monomers and dimers of common polymers for my project.


# **Benchmarking DFT and Post–Hartree–Fock Methods for Dimerization of Common Polymers**

**Author:** Matthew Skornick  
**Date:** 04/27/26  
**Course:** CH‑374 — Physical Chemistry II  

---

## **📘 Table of Contents**
- [Project Overview](#project-overview)
- [Polymer Systems Studied](#polymer-systems-studied)
- [Computational Methods](#computational-methods)
- [Key Findings](#key-findings)
- [File Structure](#file-structure)
- [Navigation & Usage Instructions](#navigation--usage-instructions)
- [Prerequisites & Dependencies](#prerequisites--dependencies)
- [Citation](#citation)

---

## **📄 Project Overview**

This project investigates the **computational efficiency and accuracy** of several widely used electronic structure methods for modeling **early‑stage polymerization**, with a focus on the **dimerization step**. Although polymer chemistry is central to industrial and academic research, there is limited benchmarking data evaluating **low‑cost quantum chemical methods** for predicting monomer–dimer interaction energetics.

This study compares the performance of:

- **PBE**
- **MP2** (reference method)
- **B3LYP**
- **M06‑L**
- **HF**

across six representative polymer systems. The goal is to determine which method provides the best balance of **accuracy**, **runtime**, and **computational cost** for modeling polymer dimerization.

Monomer and dimer structures were constructed in **Avogadro**, optimized at the **PBE** level, and then used for **single‑point energy calculations** with all other methods. No further geometry optimization was performed to ensure consistent structural baselines and reduce computational overhead.

---

## **🧪 Polymer Systems Studied**

The following polymer classes were included:

- **PA** — Polyamide  
- **PE** — Polyethylene  
- **PP** — Polypropylene  
- **PS** — Polystyrene  
- **PTFE** — Polytetrafluoroethylene  
- **PVC** — Polyvinyl chloride  

Each system includes both **monomer** and **dimer** structures.

---

## **⚙️ Computational Methods**

All calculations were performed using **ORCA**, with:

- PBE‑optimized geometries as the structural baseline  
- Single‑point energy calculations for all other methods  
- No additional geometry optimization  
- Consistent basis sets and settings across methods (see input files)

This ensures that differences in computed energies reflect **methodological performance**, not structural artifacts.

---

## **📊 Key Findings**

- All methods produced **remarkably consistent total energies**, with values falling within **one standard deviation** of their method averages.
- **MP2** provided the most reliable high‑accuracy reference but required **significantly longer runtimes**.
- **PBE** demonstrated:
  - The **shortest runtimes**
  - Energies **closest to MP2**
  - The best overall balance of **speed** and **accuracy**
- **B3LYP**, **M06‑L**, and **HF** showed acceptable accuracy but did not match PBE’s combined performance.
- **CCSD(T)** was not feasible due to extreme memory demands, highlighting the need for practical alternatives like PBE.

**Conclusion:**  
**PBE** is the most effective low‑cost method for modeling early polymer growth mechanisms and is well‑suited for large‑scale or high‑throughput computational studies.

---

## **📁 File Structure**
project-root/
│
├── log-files-from-calculations-and-data-extraction-code/
│   ├── ORCA output/log files
│   └── Jupyter notebook for data extraction
│
├── xyz-files-of-monomers-and-dimers/
│   └── Original (pre‑optimization) XYZ structures
│
├── optimized-structure-xyz-files/
│   └── PBE‑optimized structures used for all benchmarking calculations
│
└── polymer_inputs/
└── ORCA input files for each monomer and dimer

---

## **🧭 Navigation & Usage Instructions**

If you are exploring the project files:

1. **Start with the structure files**  
   - Use the **optimized structure XYZ files** to see the geometries used for all calculations.  
   - Alternatively, view the **pre‑optimized XYZ files** to compare initial vs. optimized structures.

2. **Review the input files**  
   - The `polymer_inputs/` folder contains all ORCA input files used for each calculation.

3. **Examine the log files and data extraction code**  
   - The `log-files-from-calculations-and-data-extraction-code/` folder includes:
     - Raw ORCA output files  
     - A Jupyter notebook showing how energies were extracted and processed  

This workflow allows you to trace the entire computational pipeline from structure generation → optimization → benchmarking → data analysis.

---

## **📦 Prerequisites & Dependencies**

To reproduce or extend this project, you may need:

- **ORCA** (quantum chemistry software)
- **Avogadro** (structure building and visualization)
- **Python 3.x** with:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `jupyter`
- A machine capable of running moderate‑scale quantum chemical calculations

---

## **📚 Citation**

If you use or reference this repository, please cite:

> Skornick, M. *Benchmarking DFT and Post Hartree–Fock Methods for Dimerization of Common Polymers.* CH‑374 Physical Chemistry II, 2026.
