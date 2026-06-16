# Research Proposal

**Title:** AI-Assisted Backend Interface for the Magnetic Vine Robot: Architecture, Data Pipeline, and Intraoperative Decision Support

**Author:** Chioma (CariSurg Trainee, 2026 Cohort)
**Supervisor:** Dr. De Freitas
**Unit:** Clinical AI & Innovation Unit, Mercer Trust
**Date:** June 2026
**Status:** Week 1 Draft

---

## 1. Introduction

Minimally invasive surgery (MIS) has transformed modern surgical practice, offering patients reduced operative trauma, shorter hospital stays, and faster recovery compared to conventional open procedures [1]. Despite these advantages, existing MIS instruments remain fundamentally constrained by their rigid construction, limiting access to anatomically complex target sites and placing significant demands on operator skill [2].

Soft robotic systems represent a new generation of surgical tools capable of navigating confined and curved anatomical pathways that rigid instruments cannot reach [3]. Among these, vine-inspired robots — which extend through body cavities by growing at the tip rather than pushing from the base — offer a particularly promising approach for single-entry biopsy and tissue removal [4].

The **Magnetic Vine Robot (MVR)**, currently under development at the Clinical AI & Innovation Unit, Mercer Trust, applies magnetic actuation to a vine-inspired soft robotic platform, enabling wireless, steerable navigation through soft tissue without mechanical linkages. This proposal outlines the design and development of the **MVR Backend Interface**: the software layer connecting the robot hardware to the clinical operator, with integrated AI-assisted decision support.

---

## 2. Problem Statement

Current approaches to biopsy and minimally invasive tissue removal face four interrelated limitations:

**2.1 Access constraints**
Rigid laparoscopic instruments follow fixed insertion trajectories. Lesions located behind anatomical structures or within narrow body cavities often require either multiple port sites or conversion to open surgery, increasing procedural risk and recovery time [2].

**2.2 Operator dependence**
Procedural outcomes in MIS are heavily influenced by surgeon experience. Intraoperative decision-making — particularly target localisation and instrument positioning — relies on tacit knowledge that is difficult to transfer and inconsistently applied [5].

**2.3 Limited intraoperative feedback**
Surgeons currently lack real-time, quantitative confirmation that the instrument tip is correctly positioned relative to the target tissue. Feedback is primarily visual (endoscopic camera) and does not integrate sensor data from the instrument itself [3].

**2.4 Unstructured procedural data**
Intraoperative events are rarely captured in structured, machine-readable form. This limits opportunities for post-hoc analysis, quality improvement, and the development of AI models trained on real procedural data [6].

The MVR hardware addresses limitation 2.1 directly. This proposal addresses limitations 2.2–2.4 through the design of an intelligent backend interface.

---

## 3. Proposed System

### 3.1 Overview

The MVR Backend Interface is a Python-based software system that sits between the MVR hardware and the surgeon's control station. It performs four primary functions:

1. **Real-time data ingestion** — receives positional, sensor, and actuation data from the MVR hardware via a serial/wireless communication layer
2. **Safety interlock enforcement** — monitors data streams for out-of-bounds conditions and triggers hardware stops where necessary
3. **Structured data logging** — captures all intraoperative events in a standardised schema for audit and AI training
4. **AI-assisted decision support** — processes sensor data to provide real-time operator guidance on instrument position and tissue classification

### 3.2 Architecture

```
MVR Hardware
     │
     ▼
Communication Layer (serial / BLE)
     │
     ▼
Backend Interface (Python / FastAPI)
  ├── Data Ingestion Module
  ├── Safety Interlock Module
  ├── Logging Module  ──────────► Procedural Database
  └── AI Decision Support Module
     │
     ▼
Operator Control Station (frontend)
```

### 3.3 AI Components

| Component | Method | Input | Output |
|---|---|---|---|
| Positional anomaly detection | Statistical process control / lightweight ML | Robot positional data stream | Alert flag + trajectory deviation magnitude |
| Tissue classification support | CNN on sensor signal data | Force / impedance sensor readings | Tissue type probability distribution |
| Procedural logging | Rule-based structured capture | All intraoperative events | Timestamped JSON log |

---

## 4. Clinical Significance

If successfully developed, the MVR Backend Interface will:

- Reduce operator cognitive load during procedures by surfacing AI-derived guidance in real time
- Generate structured procedural datasets that can be used to train and validate future AI models
- Provide an auditable record of every procedure for clinical governance purposes
- Establish a reusable software architecture applicable to future soft robotic platforms developed by the unit

---

## 5. Methodology

**Phase 1 (Weeks 1–4):** Literature review, system architecture design, backend scaffolding in Python
**Phase 2 (Weeks 5–8):** Data schema definition, API development (FastAPI), integration with MVR hardware simulator
**Phase 3 (Weeks 9–12):** AI module prototyping, bench testing, documentation and handover

All development will follow version-controlled, audit-ready practices in line with Mercer Trust Clinical IT standards.

---

## 6. Ethical Considerations

- No real patient data will be used during the research and prototype phase
- All testing will use synthetic or anonymised procedural data
- The system will be clearly labelled as a research prototype and will not be used in clinical settings without appropriate regulatory approval
- AI outputs will be presented as decision support only; final clinical decisions remain with the operating surgeon

---

## 7. References

[1] Litynski, G. S. (1999). Highlights in the history of laparoscopy. Frankfurt: Barbara Bernert Verlag.

[2] Bergeles, C., & Yang, G. Z. (2014). From passive tool holders to microsurgeons: safer, smaller, smarter surgical robots. *IEEE Transactions on Biomedical Engineering*, 61(5), 1565–1576. https://doi.org/10.1109/TBME.2014.2309294

[3] Russo, S., Ranzani, T., Walsh, C. J., & Wood, R. J. (2019). An additive millimeter-scale fabrication method for soft biocompatible actuators and sensors. *Advanced Materials Technologies*, 4(10), 1900375. https://doi.org/10.1002/admt.201900375

[4] Hawkes, E. W., Blumenschein, L. H., Greer, J. D., & Okamura, A. M. (2017). A soft robot that navigates its environment through growth. *Science Robotics*, 2(8), eaan3028. https://doi.org/10.1126/scirobotics.aan3028

[5] Vedula, S. S., Malpani, A., Tao, L., Chen, G., Gao, Y., Poddar, P., ... & Hager, G. D. (2016). Analysis of the structure of surgical activity for a suturing and knot-tying task. *PLOS ONE*, 11(3), e0149174. https://doi.org/10.1371/journal.pone.0149174

[6] Maier-Hein, L., Vedula, S. S., Speidel, S., Navab, N., Kikinis, R., Park, A., ... & Jannin, P. (2017). Surgical data science for next-generation interventions. *Nature Biomedical Engineering*, 1(9), 691–696. https://doi.org/10.1038/s41551-017-0132-7

[7] De Freitas, L., Goodacre, S., O'Hara, R., Thokala, P., & Hariharan, S. (2020). Qualitative exploration of patient flow in a Caribbean emergency department. *BMJ Open*, 10(12), e041422. https://doi.org/10.1136/bmjopen-2020-041422

---

*Prepared as part of the CariSurg Healthcare AI Virtual Programme, 2026 Cohort.*
