# Research Proposal

**Title:** Magnetic Vine Robot Deployment Interface Design

**Author:** Chioma Okafor
**Supervisor:** Andrea Trujillo
**Date:** June 2026
**Status:** Week 1 Draft

---

## 1. Statement of the Problem

     Physicians performing minimally invasive procedures within narrow and branching endoluminal pathways require surgical tools that can navigate these complex environments while minimizing tissue trauma. Existing vine robots have demonstrated autonomous tip growth, magnetic steering, as well as integrated imaging and biopsy tools. However, current designs face challenges in miniaturization and require increased pressure tolerances at smaller diameters. This project proposes a compact, modular magnetic vine robot capable of integrating steering, imaging and tool delivery with smaller, interchangeable vine diameters to improve access to deep highly branched anatomical regions for endoscopic procedures.
---

## 2. Previous Work:

     Yanez et al. (2026) addressed the clinical challenge of steering soft vine robots used in minimally invasive surgery, whose continuously everting tips can be difficult to control when equipped with tools or sensors. The authors implemented an internal-external ring magnet design to accommodate a permanent magnetic tip equipped with a camera and LED, mounted at the distal end of the everting structure. In doing so, 34 mm bending radius and an average of 35 s per bifurcation was achieved in simulated testing in the upper bronchial tree. However, further miniaturization of the current design is required in order to access deeper regions of the lungs.
     Hawkes et al. (2017) examined the open challenge of controlled tip based growth of thousands of percent while maintaining directional control at speeds comparable to animal locomotion. The authors developed a soft growing robot that extends through pressure driven eversion of a thin walled vessel and steers through controlled asymmetric tip growth, using onboard camera feedback for autonomous navigation. The robot extended from 28 cm to 72 m, operated across diameters from 1.8 mm to 36 cm, reached speeds exceeding 10 m/s, exhibited extensibility seven orders of magnitude greater than plants, and changed direction in less than 1 s. Although the robot achieved rapid tip growth and steering, it was unable to perform real time branching, a capability observed in natural systems such as fungal hyphae.
     Glick et al. (2022) investigated branching vine robots for navigation in unmapped environments using eversion based growth. The authors simulated robot growth in known environments and applied particle swarm optimization to improve branching. Optimized designs were then tested in unseen environments and fabricated for validation. These demonstrated 25% greater coverage, 12.55x higher anchoring forces, capacity to hold over 100× their own mass and successfully anchored a load exceeding 66.7 N at 50 kPa internal pressure. Although branching increased exploratory and anchoring abilities, it also increased robot complexity and made sensor integration difficult. The authors also noted that similar performance could be achieved on pre-mapped environments using open or closed loops with less complexity.
     Davy et al. (2025) addressed the challenge of achieving precise vine robot steering and force transmission during biopsy procedures while maintaining a fully soft structure. The authors developed a magnetic fluid driven vine robot in which the magnetic fluid enables both pressurized tip growth and external steering via magnetic field. It was demonstrated at 4-7 mm diameters, achieved 100% navigation success in bronchial tree phantoms, traversed constrictions as small as 2.5 mm, generated up to 1.26 N of tip insertion force and enabled camera guided needle placement. However, the robot's miniaturization was constrained by burst pressure failures in the 3 mm diameter design; reducing the vine diameter substantially increased the pressure required for growth and necessitates resistance to higher pressures. 
     Girerd et al. (2024) focused on the challenge of miniaturizing vine robots while maintaining a functional working channel for tool delivery. Reducing vine diameter leads to a significant increase in required eversion pressure within the working channel. The authors implemented a ‘scrunched’ design at the robot tip to reduce friction during growth. This design enabled vine extension at smaller diameters down to approximately 2.3 mm while maintaining structural integrity. However, the approach adds mechanical complexity at the tip and requires careful tuning to ensure consistent performance.
     Kalibala et al. (2025) addressed the challenge of non linear force and position control in soft growing robots. The authors trained and integrated a deep neural network into a Model Predictive Control (MPC) framework to perform live force and position control. The DNN-MPC controller improved force and position tracking performance while reducing computation time by 11x. However, the authors did not demonstrate its ability to generalize across different vine robot designs or operating environments. 

---

## 3. Proposed Solution:
     This project proposes a compact modular backend platform for a magnetic vine robot capable of integrating steering, imaging and tool delivery with smaller, interchangeable vine diameters to improve access to deep highly branched anatomical regions for endoscopic procedures. The system backend interface will allow the use of different tip diameters depending on the clinical task. It will incorporate a simple mechanical docking system for securely attaching and exchanging tools. The design will build on prior approaches such as internal-external ring magnet tips for external magnetic steering, and pressure driven eversion of the vessel (Yanez et al., 2026; Hawkes et al., 2026) In addition, concepts such as friction reduction through “scrunched” material design will also be considered to support improved miniaturisation and deployment (Girerd et al., 2024). A simple interface will be used to display sensor output and confirm that the module is functioning correctly during testing.



## 4. References

Yanez Trujillo A, Davy J, Chandler JH, Avery J, Valdastri P. Miniaturized Magnetic Tip Design for Endoluminal Vine Robot Navigation. Advanced Robotics Research. 2026. doi:10.1002/adrr.202500188
Hawkes EW, Blumenschein LH, Greer JD, Okamura AM. A soft robot that navigates its environment through growth. Science Robotics. 2017. Available from: https://www.science.org 
Glick PE, Adibnazari I, Drotman D, Ruffatto D, Tolley MT. Branching Vine Robots for Unmapped Environments. Front Robot AI. 2022. doi:10.3389/frobt.2022.838913
Davy J, Dean TP, Greenidge NJ, Calmé B, Lloyd P, Chandler JH, et al. Magnetic Fluid-Driven Vine Robots for Minimally Invasive Tissue Biopsy Sampling. Advanced Intelligent Systems. 2025. doi:10.1002/aisy.202400827
Kalibala A, Nada AA, Ishii H, El-Hussieny H. Real-time force/position control of soft growing robots: A data-driven model predictive approach. Nonlinear Engineering. 2025;14(1). doi:10.1515/nleng-2025-0099
Girerd C, Alvarez A, Hawkes EW, Morimoto TK. Material Scrunching Enables Working Channels in Miniaturized Vine-Inspired Robots. IEEE Transactions on Robotics. 2024. doi:10.1109/TRO.2024.3370088


*Prepared as part of the CariSurg Healthcare AI Virtual Programme, 2026 Cohort.*
