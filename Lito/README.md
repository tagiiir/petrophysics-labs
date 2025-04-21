
# Lithological Core Description and Well Correlation

This project focuses on lithological description of core samples, correlating geological layers between two wells using the Levenshtein distance algorithm, and visualizing results with detailed lithology columns and layer matching lines.

---

## Project Description

Lithological core description is based on depth-marked photographs and includes:

- Identification of rock types;
- Description of sedimentary structures and textures;
- Indication of post-sedimentary changes (fracturing, bitumen, oil saturation, etc.);
- Marking of layer boundaries.

The goal of this project is:

- To compute the optimal correlation between two lithological sequences using the Levenshtein algorithm;
- To detect full, partial, and missing matches between layers;
- To visualize lithology columns and draw correlation lines between matching intervals.

---

## Data Structure

- Each well is represented as a table with the following columns:
  - `Depth`: Top depth of the layer (m);
  - `H`: Layer thickness (m);
  - `Rock`: Rock type and additional lithological features.

---

## Methods

- **Levenshtein Distance (Wagner–Fischer algorithm)**:
  - Calculates the minimum number of edits needed to transform one well’s lithology sequence into another;
  - A traceback function retrieves the optimal correlation path;
  - Each layer is marked as fully correlated, partially matched, or pinched out.

- **Visualization**:
  - Lithology columns are plotted vertically using colored rectangles;
  - Colors reflect lithological type;
  - Correlation lines connect matching layer boundaries between wells;
  - Depth increases downward (geological standard).

---

## Libraries Used

- `numpy` — array processing and matrix operations;
- `pandas` — tabular data manipulation;
- `matplotlib` — plotting lithology columns and correlations.

---

## Example Features

- Core-to-core correlation between Taezhnaya 102 and Taezhnaya 103;
- Background lithology colored based on rock type (e.g. sandstone, clay, coal);
- Depth labels and correlation lines on both top and bottom of matching intervals.
