# XRD Analysis and Mineral Phase Identification

This project focuses on processing X-ray diffraction (XRD) data, including reading binary diffractogram files, detecting diffraction peaks, removing background using a sliding segment method, and determining peak positions using a correlation-based approach.

---

## Project Description

X-ray diffraction (XRD) is used to study the crystalline structure of minerals.  
The goals of this project are:

- To read binary diffractogram files;
- To plot diffractograms;
- To determine peak positions using two methods:
  - By local maxima;
  - By template matching (reference impulse);
- To remove background noise using a sliding segment technique;
- To apply a correlation-based method for accurate peak positioning.

---

## Data Structure

- XRD data is stored in binary files (`.DAT`);
- The first 8 values (32-bit unsigned integers) contain technical metadata and are skipped;
- The remaining data consists of diffraction intensity values;
- Diffraction angles (2θ) are computed starting from 1.5° with a step of 0.025°.

---

## Libraries Used

- `numpy` — array manipulation and vectorized operations;
- `matplotlib` — plotting and data visualization;
- `scipy.signal` — peak detection and signal correlation;
- `struct` — reading binary data.
