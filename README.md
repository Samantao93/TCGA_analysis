  # TCGA analysis

## Setup and Load Libraries:

Load necessary libraries for data acquisition (TCGAbiolinks), data manipulation (dplyr, tidyr), data visualization (ggplot2, plotly), and survival analysis (survival, survminer).

### Packages version:

- TCGAbiolinks: 2.34.0
- dplyr: 1.1.4
- ggplot2: 3.5.1
- gridExtra: 2.3
- ggplotify: 0.1.2
- plotly: 4.10.4
- survival: 3.8-3
- survminer: 0.5.0

## Data Acquisition:

Use TCGAbiolinks to query and download the clinical data for lung cancer (LUAD) from the Genomic Data Commons (GDC).
Prepare the clinical data into a usable format (variable clinical_data).

## Data Preprocessing:

- Search for duplicated records.
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

## Survival Analysis:

- The death_days_to and last_contact_days_to columns are converted to numeric format.
- The vital_status change "Dead" to 1 and "Alive" to 0.
- A new column, survival_time, is created to represent the time until death or last contact.

### Kaplan-Meier Survival Curves:

- Plot survival curves stratified by AJCC Pathologic Tumor Stage to see if there are significant differences between stages.
- Check if EGFR mutation status has any significant impact on survival.
- Analyze survival differences based on KRAS mutation status.
  
### Cox Proportional Hazards Model:

The Cox regression model is used to assess the impact of variables such as age at diagnosis, AJCC tumor stage, and tobacco smoking history on survival.
Hazard ratios (HR) are calculated for each predictor, and a forest plot is created to visualize the significance and effect size of each variable.
