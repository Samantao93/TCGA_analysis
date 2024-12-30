  # TCGA_analysis

## Setup and Load Libraries:

Load necessary libraries for data acquisition (TCGAbiolinks), data manipulation (dplyr, tidyr), data visualization (ggplot2, plotly), and survival analysis (survival, survminer).

## Data Acquisition:

Use TCGAbiolinks to query and download the clinical data for lung cancer (LUAD) from the Genomic Data Commons (GDC).
Prepare the clinical data into a usable format (variable clinical_data).

## Data Preprocessing:

- Replace unwanted values ([Not Available], [Not Evaluated], [Unknown], [Not Applicable]) with NA across all columns.
- Filter out columns that have only NA values for analysis.
- Convert certain columns (e.g., age_at_initial_pathologic_diagnosis) to numeric format.

## Visualizations:

- Age Distribution of LUAD patients.
- Vital Status Distribution (alive vs dead).
- Gender Distributionof patients by gender.
- Use grid.arrange() to combine these plots into a grid layout.
- Age Distribution by Gender and Vital Status:
  - Create a histogram of age, stratified by both gender and vital status.
  - Use facet_wrap() to separate the plots by gender.
  - Violin Plot for Age by AJCC Tumor Stage:

- Violin plot to show the relationship between age and AJCC pathologic tumor stage, including boxplots, smooth lines, and jittered points.
- Pie Chart for Lung Region Distribution:
  - Create a dynamic pie chart using plotly to visualize the distribution of lung regions (anatomic organ subdivisions).
