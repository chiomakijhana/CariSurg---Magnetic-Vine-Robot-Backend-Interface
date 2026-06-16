# CariSurg — Magnetic Vine Robot Backend Interface

> **CariSurg Healthcare AI Programme — 2026 Cohort**
> Trainee portfolio for the Clinical AI & Innovation Unit, Mercer Trust.

---

## What is this?

This repository contains the backend interface software developed as part of the **CariSurg Healthcare AI Virtual Programme (2026)**, supporting the **Magnetic Vine Robot (MVR)** — a prototype surgical robot designed for minimally invasive procedures including tissue removal and biopsy.

The MVR is a soft, flexible robotic system that navigates through the body using magnetic guidance, mimicking the growth behaviour of a vine plant. This backend interface handles the communication layer between the physical robot hardware and the clinical operator interface, enabling real-time control, data logging, and AI-assisted decision support during procedures.

This repository is intended for review by clinical and technical supervisors, including the Trust's Clinical IT Lead.

---

## Who is it for?

| Audience | What to look at |
|---|---|
| Clinical reviewer (non-technical) | `docs/` — memos and proposals in plain English |
| Technical reviewer | `notebooks/` — Jupyter notebooks with methodology and prototyping |
| Supervisor / auditor | This README, then the pull request history |

---

## Clinical Context

The Magnetic Vine Robot addresses a key limitation of conventional minimally invasive surgical tools: rigidity. Standard laparoscopic instruments follow fixed trajectories and require multiple incisions for complex procedures. The MVR navigates soft tissue via magnetic actuation, allowing a single-entry, steerable approach for:

- **Tissue biopsy** — targeted sampling from difficult-to-reach anatomical locations
- **Tissue removal** — excision of small lesions or masses with minimal trauma
- **Intraoperative imaging support** — real-time positional feedback to the surgical team

The backend interface developed in this repo sits between the MVR hardware and the surgeon's control station, processing positional data, managing safety interlocks, and logging procedural data for audit and AI training purposes.

> ⚠️ The MVR is currently at **research / prototype stage**. This software is not approved for clinical use. All testing is conducted in controlled laboratory environments.

---

## Repository Structure

```
CariSurg---Magnetic-Vine-Robot-Backend-Interface/
│
├── notebooks/          # Jupyter notebooks (EDA, prototyping, modelling)
│   └── week0_triage_eda.ipynb
│
├── docs/               # Written deliverables
│   ├── week1_memo.md
│   └── week1_proposal.md
│
├── data/               # Data lives here — see data/README.md
│   └── README.md
│
├── requirements.txt    # Python dependencies
├── .gitignore
├── LICENSE
└── README.md           # You are here
```

---

## How to Run the Notebooks

1. **Clone the repo**
   ```bash
   git clone https://github.com/chiomakijhana/CariSurg---Magnetic-Vine-Robot-Backend-Interface.git
   cd "CariSurg---Magnetic-Vine-Robot-Backend-Interface"
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   venv\Scripts\activate        # Windows
   source venv/bin/activate     # macOS/Linux
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter**
   ```bash
   jupyter notebook notebooks/
   ```

> ℹ️ Notebooks can also be opened in **Google Colab** — upload the `.ipynb` file and attach the relevant dataset from `data/`.

---

## Data Notice

No real patient data is stored in this repository. All data used during the research phase is anonymised and synthetic. See `data/README.md` for details.

---

## Programme Context

- **Programme:** CariSurg Healthcare AI Virtual Programme
- **Project:** Magnetic Vine Robot — Backend Interface
- **Unit:** Clinical AI & Innovation Unit, Mercer Trust
- **Supervisor:** Dr. De Freitas
- **Clinical IT Lead:** Martina Griffith
- **Cohort year:** 2026
- **Status:** Research / Prototype

---

## Licence

[MIT](LICENSE) — free to reuse with attribution.
