# Lab 01 — Spectrometric Gamma Method (Natural Radioactive Elements)

This lab focuses on determining the concentrations of naturally radioactive elements (NREs) — potassium (K), thorium (Th), and uranium (U) — from gamma spectrometry data. The work is based on mathematical decomposition of measured gamma spectra using reference (standard) spectra.

## Background

Most rocks contain natural radioactive elements such as U, Th, and K. Their concentrations can provide important geological insights, including clay mineral content, lithology, and historical hydrodynamic processes. 

Spectrometric gamma logging allows the determination of these concentrations by analyzing the energy spectrum of gamma radiation detected from rock samples. The spectrum of an unknown sample is assumed to be a linear combination of the spectra from the three standard elements (K, Th, U). Mathematically, this is solved using the **least squares method**.

## Objective

- Load standard gamma spectra for potassium, thorium, and uranium.
- Load the measured spectra along a core profile.
- Solve an overdetermined system of linear equations (one per energy channel) for each depth point to estimate NRE concentrations.
- Analyze and interpret the sequence of rock samples based on NRE concentrations.

## Methodology

Gamma spectrum of a sample \( S \) is modeled as a linear combination:

\[
S = a \cdot S_K + b \cdot S_{Th} + c \cdot S_U
\]

Where:
- \( S_K, S_{Th}, S_U \): standard spectra of K, Th, U
- \( a, b, c \): concentrations of respective elements

To solve for \( a, b, c \), we use the **least squares solution**:

\[
\mathbf{x} = (\mathbf{A}^T \cdot \mathbf{A})^{-1} \cdot \mathbf{A}^T \cdot \mathbf{S}
\]

## Data

- `K.csv`, `Th.csv`, `U.csv`: Standard spectra (one column each, no headers)
- `quest.csv`: 52 measured spectra (columns; rows represent energy channels; includes a header with depth in cm)

## Output

- Plot of element concentrations versus depth.
- Interpretation of the sample sequence (e.g., `K Th Th U K …`).
- Insight into the spatial layout and boundaries between zones dominated by different NREs.

## Tools

- Python 3.x
- NumPy
- Pandas
- Matplotlib

## References

- A.N. Pegoev. *Practical Methods of Data Processing in Applied Gamma Spectrometry*, Hydrometeoizdat, 1980.
- Technical documentation for the MKS-01A "Multirad" gamma spectrometer.