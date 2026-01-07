# Analysis of the Four-Lepton Invariant Mass Spectrum Using CERN Open Data

## 1. Introduction

The discovery of the Higgs boson in 2012 by the ATLAS and CMS collaborations marked a major milestone in particle physics. One of the cleanest and most important discovery channels is the decay

\[
H \rightarrow ZZ^* \rightarrow 4\ell \;(\ell = e, \mu)
\]

commonly referred to as the *golden channel*. Despite its very small branching ratio, this channel provides excellent mass resolution and low background contamination, making it ideal for precision studies.

In this project, real CERN Open Data are analyzed to reconstruct the four-lepton invariant mass spectrum. The goal is **not** to rediscover the Higgs boson, but to perform a realistic small-statistics analysis, understand background-dominated data, and demonstrate proper experimental reasoning consistent with LHC analyses.

---

## 2. Dataset Description

The data used in this project come from publicly released CERN Open Data in ROOT format (`lep.root`). The file contains reconstructed lepton-level information for proton–proton collision events recorded at the LHC.

Each event consists of:
- Four reconstructed leptons (electrons or muons)
- Lepton four-momenta \((E, p_x, p_y, p_z)\)
- Event-level information suitable for invariant mass reconstruction

A total of **3424 four-lepton events** pass the basic selection criteria and are used in this analysis.

---

## 3. Physics Observable: Four-Lepton Invariant Mass

The central observable is the four-lepton invariant mass, defined as:

\[
m_{4\ell} = \sqrt{\left(\sum_{i=1}^{4} E_i\right)^2 - \left|\sum_{i=1}^{4} \vec{p}_i\right|^2}
\]

This quantity is Lorentz invariant and directly sensitive to resonant particle decays, such as:
- \(Z \rightarrow \ell\ell\)
- \(H \rightarrow ZZ^* \rightarrow 4\ell\)

---

## 4. Data Processing and Analysis Workflow

The ROOT file is analyzed using a Jupyter Notebook (`Analysis-1.ipynb`) with Python-based HEP tools. The main steps are:

1. Reading the ROOT file using appropriate Python libraries
2. Extracting lepton four-momenta for each event
3. Constructing four-vectors and summing them event-by-event
4. Computing the invariant mass \(m_{4\ell}\)
5. Filling a histogram over the range 70–200 GeV

This workflow closely mirrors the structure of real LHC analyses, albeit at a simplified and educational scale.

---

## 5. Expected Physics Contributions

Two main Standard Model processes contribute to the four-lepton invariant mass spectrum:

### 5.1 Background: Continuum ZZ Production

\[
pp \rightarrow ZZ^{(*)} \rightarrow 4\ell
\]

This process produces a **smooth, falling invariant mass distribution** and dominates the event yield across the full mass range.

### 5.2 Signal: Higgs Boson

\[
pp \rightarrow H \rightarrow ZZ^* \rightarrow 4\ell
\]

The Higgs signal would appear as a **narrow resonance** around:

\[
m_H \approx 125 \, \text{GeV}
\]

However, due to the extremely small branching ratio and limited dataset size, only a very small number of Higgs events are expected.

---

## 6. Results: Invariant Mass Spectrum

The reconstructed four-lepton invariant mass distribution is shown in Figure 1. The histogram exhibits:

- A smoothly falling spectrum
- No statistically significant excess near 125 GeV
- Behavior consistent with Standard Model ZZ background expectations

Vertical reference lines are drawn at:
- 91 GeV (Z boson mass)
- 125 GeV (Higgs boson mass)

The absence of a visible Higgs peak is expected given the dataset size and does not contradict the Standard Model.

---


---

## 10. Conclusion

A complete four-lepton invariant mass analysis was performed using real CERN Open Data. The observed spectrum is dominated by Standard Model background processes, and no statistically significant Higgs signal is observed. This outcome is expected and reflects realistic experimental conditions.

This project demonstrates:
- Correct reconstruction of a key LHC observable
- Sound physical interpretation
- Proper use of statistical reasoning


---

## 11. Future Improvements

Possible extensions of this work include:
- Signal and background fitting
- Optimization of event selection criteria
- Combination with simulated datasets
- Extension to other decay channels

These steps would improve sensitivity and more closely resemble full-scale LHC analyses.

