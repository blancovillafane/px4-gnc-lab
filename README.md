# px4-gnc-lab

Guidance, navigation and control algorithms implemented in C++ and validated against PX4 flight simulation.

---

## 🎯 Why this exists

Flight control algorithms are usually developed in MATLAB/Simulink and stay there. This repository takes them the rest of the way: into tested C++ running against an open-source autopilot.

The target algorithm is an **INDI controller with a minimum-power control allocator** for an over-actuated VTOL quadplane — the subject of my MSc thesis.

---

## 📍 Status

**Phase 0 — environment setup.** Nothing flies yet. Roadmap below is live and updated as work lands.

---

## ✅ How correctness is checked

Every algorithm here is verified against a MATLAB reference model I trust:

1. Run the MATLAB model, export inputs and expected outputs.
2. The C++ reads the same inputs and must reproduce the same numbers.
3. Tests run automatically on every push.

This means "is the C++ correct?" always has a yes/no answer, never an opinion.

---

## 🗺️ Roadmap

| Phase | Goal | Target | Done |
|---|---|---|---|
| 0 | Headless Linux box + PX4 SITL flying, ground station connected | Sep 2026 | ☐ |
| 1 | Scripted autonomous mission + flight-log analysis | Oct 2026 | ☐ |
| 2 | Control effectiveness matrix in C++, tested vs MATLAB, CI green | Nov 2026 | ☐ |
| 3 | Full allocation: pseudo-inverse → saturation redistribution → minimum-power step | Dec 2026 | ☐ |
| 4 | C++ controller flying the simulator end-to-end | Q1 2027 | ☐ |
| 5 | Monte Carlo campaign: wind, sensor noise, dispersions | Q2 2027 | ☐ |
| 6 | Allocator as an in-tree PX4 module, quadplane airframe | Q3 2027 | ☐ |

---

## 🧰 Stack

- **Autopilot:** PX4 (SITL) · QGroundControl
- **Language:** C++17 with Eigen · Python for analysis and plotting
- **Build & test:** CMake · GoogleTest · GitHub Actions
- **Machines:** Raspberry Pi 5 (Ubuntu Server 24.04 LTS, headless) · macOS ground station

---

## ⚙️ Setup

*Instructions land at the end of Phase 0.*

---

## 📄 Reference

Pfeifle, O. and Fichter, W., "Minimum Power Control Allocation for Incremental Control of Over-Actuated Transition Aircraft," *Journal of Guidance, Control, and Dynamics*, Vol. 46, No. 2, 2023. [doi:10.2514/1.G006929](https://doi.org/10.2514/1.G006929)

---

## 👤 About

Aerospace engineer, ~3 years in GNC (missiles and UAVs), including 1+ years as GNC technical lead. Background in guidance laws, state estimation, nonlinear control, and flight-test validation.

📫 [LinkedIn](https://linkedin.com/in/blancovillafane) · blancovillafane@gmail.com
