# Well Log Panel Construction, Curve Merging, and Double Difference Parameter Calculation

## Project Overview

This project focuses on the processing and visualization of well log data (geophysical well surveys). The key objectives include:

- constructing well log panels (log plots);
- merging multiple curves of the same method (e.g., repeated runs or different tools);
- calculating the double difference gamma ray parameter (ΔGR) for lithological analysis.

## Libraries Used

- `pandas` — for working with tabular data
- `matplotlib` — for data visualization
- `numpy` — for numerical calculations
- `lasio` — for reading `.las` log data files

## Workflow

### 1. Well Log Panel Construction

Well log curves are plotted using `matplotlib`, with a consistent depth scale across tracks. Each curve is color-coded and styled according to standard geophysical log panel conventions.

### 2. Curve Merging

For each geophysical method, multiple curves were merged using:

- `combine_first()` — to prioritize one curve over the other;
- mean-based offset correction — to align overlapping intervals;
- interpolation — when curves had different depth intervals.

### 3. Double Difference Parameter (ΔGR) Calculation

The ΔGR parameter is calculated using the formula:

\[
\Delta GR = \frac{GR - GR_{min}}{GR_{max} - GR_{min}}
\]

Where:
- `GR_min` and `GR_max` are the average values of the gamma ray curve within manually selected reference intervals;
- the final result is normalized between 0 and 1 and can be used to distinguish lithological units.

