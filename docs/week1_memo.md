# Memorandum

**To:** Dr. De Freitas, Clinical AI & Innovation Unit, Mercer Trust
**From:** Chioma (CariSurg Trainee, 2026 Cohort)
**Date:** June 2026
**Re:** Week 1 — Scoping Review: AI-Assisted Backend Interface for the Magnetic Vine Robot

---

## 1. Purpose

This memo summarises the Week 1 scoping work undertaken to define the research and development direction for the Magnetic Vine Robot (MVR) Backend Interface project. It outlines the clinical problem, the proposed role of AI within the system, key literature reviewed, and the immediate next steps.

---

## 2. Background

Minimally invasive surgery (MIS) has become the preferred approach for a growing range of diagnostic and therapeutic procedures, offering reduced patient trauma, shorter recovery times, and lower rates of post-operative complication compared to open surgery. However, conventional MIS instruments are constrained by their rigidity: they follow fixed insertion trajectories and offer limited manoeuvrability within body cavities, particularly in anatomically complex or obstructed regions.

The **Magnetic Vine Robot (MVR)** is a prototype soft robotic system under development at the Clinical AI & Innovation Unit. It draws inspiration from the growth mechanics of climbing vine plants — extending, steering, and retracting through tissue via magnetic actuation rather than mechanical linkages. This approach enables single-entry navigation to target sites that would otherwise require multiple incisions or open access, making it particularly suited to **tissue biopsy** and **small lesion removal** in minimally invasive contexts.

The **Backend Interface** is the software layer that connects MVR hardware to the clinical operator. It is responsible for:
- Receiving and processing real-time positional and sensor data from the robot
- Translating operator commands into hardware actuation signals
- Enforcing safety interlocks and logging procedural data
- Providing a data pipeline for AI-assisted decision support during procedures

---

## 3. Clinical Problem

Current biopsy and tissue removal procedures in MIS settings face several limitations:

- **Access constraints** — rigid instruments cannot reach lesions behind anatomical structures without additional incisions
- **Operator dependence** — procedure outcomes are heavily influenced by surgeon experience and real-time judgement
- **Limited intraoperative feedback** — surgeons often lack real-time confirmation that the instrument tip is correctly positioned relative to the target tissue
- **Data loss** — procedural data is rarely captured in structured form, limiting opportunities for post-hoc learning and AI training

The MVR backend interface is designed to address the last two points directly, while the robot hardware addresses the first.

---

## 4. Proposed AI Role

Based on the Week 1 literature review, the following AI functions are proposed for integration into the backend interface:

| Function | Description | Priority |
|---|---|---|
| Positional anomaly detection | Flag unexpected deviations in robot trajectory in real time | High |
| Tissue classification support | Assist operator in distinguishing target from surrounding tissue using sensor data | Medium |
| Procedural data logging | Structured capture of all intraoperative events for audit and AI training | High |
| Operator decision support | Surface relevant reference data and prior case outcomes during procedure | Low (Phase 2) |

---

## 5. Literature Summary

Five papers were reviewed this week covering soft robotics in surgery, magnetic actuation systems, AI-assisted MIS, and intraoperative decision support. Key findings:

- Soft robotic systems demonstrate significantly improved access in confined anatomical spaces compared to rigid instruments, with vine-inspired robots showing particular promise for single-entry navigation
- Magnetic actuation provides precise, wireless control without the mechanical complexity of tendon-driven systems, though it introduces challenges around field interference in theatre environments
- AI-assisted intraoperative systems have shown measurable reductions in procedural error rates in early-stage trials, particularly for target localisation tasks
- Structured procedural data capture is identified as a prerequisite for training reliable AI models in surgical contexts; most existing systems do not capture this data in usable form

---

## 6. Gaps Identified

- Limited published work exists on backend software architecture for soft surgical robots specifically
- No standardised data schema exists for logging MVR-type procedural data
- Theatre electromagnetic compatibility for magnetic actuation systems requires further investigation before clinical trials

---

## 7. Next Steps

- Week 2: Establish version-controlled repository; commit literature and scoping documents
- Week 3: Define backend data schema and API structure
- Week 4: Begin prototype backend implementation in Python (FastAPI)
- Ongoing: Expand literature review to cover regulatory requirements for AI-assisted surgical devices (MDR 2017/745)

---

## 8. References

*(To be auto-generated from Zotero — see Week 1 proposal for full bibliography)*

---

*Prepared as part of the CariSurg Healthcare AI Virtual Programme, 2026 Cohort.*
