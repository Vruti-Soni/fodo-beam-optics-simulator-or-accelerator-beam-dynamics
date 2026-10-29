# fodo-beam-optics-simulator-or-accelerator-beam-dynamics
Markdown
# ⚛️ 3D Interactive Particle Beam Accelerator & FODO Optics Simulator
An interactive, web-based 3D physics simulation and numerical solver that models charged particle beam transport through a periodic **FODO (Focusing-Defocusing)** magnet lattice in circular synchrotrons and beamlines.

---

## 🔬 Physics & Mathematical Framework

In modern particle accelerators (such as the Large Hadron Collider at CERN), charged particle beams are focused and contained using alternating magnetic quadrupole lenses. This project implements **Linear Beam Dynamics (Matrix Optics)** to compute transverse particle motion and evaluate beam stability.

### 1. Matrix Optics & Transfer Matrices
The transverse state of a particle is represented by its phase space vector $\vec{x} = \begin{pmatrix} x \\ x' \end{pmatrix}$, where $x$ is transverse displacement and $x' = \frac{dx}{ds}$ is trajectory divergence angle.

* **Drift Space ($L$):**
  $$M_{\text{drift}} = \begin{pmatrix} 1 & L \\ 0 & 1 \end{pmatrix}$$

* **Focusing Quadrupole ($f$):**
  $$M_{\text{focusing}} = \begin{pmatrix} 1 & 0 \\ -\frac{1}{f} & 1 \end{pmatrix}$$

* **Defocusing Quadrupole ($-f$):**
  $$M_{\text{defocusing}} = \begin{pmatrix} 1 & 0 \\ \frac{1}{f} & 1 \end{pmatrix}$$

### 2. Symmetric FODO Cell Transfer Matrix
The total transport matrix $M_{\text{cell}}$ for a full symmetric FODO cell ($F/2 - \text{Drift} - D - \text{Drift} - F/2$) is given by matrix multiplication:

$$M_{\text{cell}} = M_{F/2} \cdot M_{\text{drift}} \cdot M_{D} \cdot M_{\text{drift}} \cdot M_{F/2}$$

### 3. Stability Condition
For transverse **Betatron Oscillations** to remain bounded (preventing beam loss against the vacuum pipe walls), the trace of the total cell transfer matrix must satisfy:

$$|\text{Tr}(M_{\text{cell}})| < 2$$

---

## ✨ Key Features

* **Real-Time 3D Rendering Engine:** Built with Three.js to dynamically render quadrupole magnets, drift tubes, particle trajectories, and transverse magnetic field vectors.
* **Interactive Control Dashboard:** Adjust focal length ($f$), drift length ($L$), beam momentum ($p$), and emittance in real time using interactive sliders.
* **Phase Space Analysis:** Toggle between the 3D accelerator beamline view and a 2D Phase Space phase portrait ($x$ vs $x'$).
* **Live Stability Evaluation:** Automated matrix trace computation providing real-time feedback on beam stability status.
* **Camera Controls & Presets:** Orbit controls with top, side, front, and perspective camera angles.

---

## 🛠️ Tech Stack

* **Frontend / 3D Graphics:** HTML5, JavaScript (ES6+), Three.js (WebGL), Tailwind CSS
* **Numerical Analysis & Prototyping:** Python, NumPy, Matplotlib, `ipywidgets` (Google Colab)
* **Deployment & Hosting:** GitHub Pages

---

Result(https://vruti-soni.github.io/fodo-beam-optics-simulator-or-accelerator-beam-dynamics/)

## 🚀 How to Run Locally
