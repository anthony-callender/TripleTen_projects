# Gold Extraction Process

## Business Statement

**Introduction:** This project aims to transform gold extraction for Zyfra by building an accurate recovery prediction model using historical data and advanced techniques, seeking to optimize operational efficiency in gold extraction processes.

**Business Problem Statement:** The absence of a dependable predictive model hinders accurate forecasting of gold concentrate recovery, impacting resource allocation and the economic viability of extraction operations.

**Business Value:** Accurate recovery predictions hold strategic importance, enabling optimized resource utilization, enhanced operational efficiency, and informed decision-making, thereby improving resource management and financial performance in gold extraction.

## Overview
This README outlines the technological process of extracting gold from ore. It provides an insight into the stages involved, the data description, feature naming conventions, recovery calculation, and evaluation metric.

### Technological Process Stages
Gold extraction involves several stages:

1. **Primary Processing and Flotation**
   - Mined ore undergoes primary processing to create the rougher feed, which is used in the flotation process.
   - Flotation separates the gold ore mixture into rougher Au concentrate and rougher tails.
   
2. **Purification**
   - The rougher concentrate undergoes two stages of purification to obtain the final concentrate and new tails.

### Process Breakdown
#### Flotation
The flotation process involves:
- Feeding the gold ore mixture into float banks to obtain rougher Au concentrate and rougher tails.
- Factors affecting stability: volatile and non-optimal physicochemical state of the flotation pulp.

#### Purification
The rougher concentrate goes through two stages of purification, resulting in the final concentrate and new tails.

### Here is a visual of the process:

![Gold_Recovery_Process](https://github.com/anthony-callender/TripleTen_projects/assets/129457454/88953d04-535e-413e-8a8d-83f77e8d6293)

### Data Description
- **Technological Process**
  - **Rougher Feed:** Raw material
  - **Rougher Additions:** Flotation reagents (Xanthate, Sulphate, Depressant)
    - Xanthate: Promoter or flotation activator
    - Sulphate: Sodium sulphide for this particular process
    - Depressant: Sodium silicate
  - **Rougher Process:** Flotation
  - **Rougher Tails:** Product residues
  - **Float Banks:** Flotation unit
  - **Cleaner Process:** Purification
  - **Rougher Au:** Rougher gold concentrate
  - **Final Au:** Final gold concentrate

- **Parameters of Stages**
  - Air amount: Volume of air
  - Fluid levels
  - Feed size: Particle size of the feed
  - Feed rate

### Feature Naming
Features are named in the following format:
`[stage].[parameter_type].[parameter_name]`
Example: `rougher.input.feed_ag`
- `[stage]` Values: rougher, primary_cleaner, secondary_cleaner, final
- `[parameter_type]` Values: input, output, state, calculation

### Recovery Calculation
To simulate gold recovery from ore, use the following formula:

![Recovery](https://github.com/anthony-callender/TripleTen_projects/assets/129457454/ac4d3910-c202-4f2f-bcdb-c8d13a771207)

- **C:** Share of gold in the concentrate after flotation/purification.
- **F:** Share of gold in the feed before flotation/in the concentrate after flotation.
- **T:** Share of gold in the rougher tails after flotation/after purification.

### Evaluation Metric - sMAPE
sMAPE (symmetric Mean Absolute Percentage Error) is used as the evaluation metric.
It is calculated as:

![sMAPE](https://github.com/anthony-callender/TripleTen_projects/assets/129457454/1bbc23e0-d03e-4256-a3de-4b4365022183)

- **Denotations:**
  - `y` = Value of target or prediction for the observation
  - `N` = Number of observations in the sample

### Prediction Values
Predict the following values:
- `rougher.output.recovery` - Rougher concentrate recovery
- `final.output.recovery` - Final concentrate recovery

The final metric comprises both values:

![Final_sMAPE](https://github.com/anthony-callender/TripleTen_projects/assets/129457454/2f7a0b55-dbbe-4a24-a95b-d9ead3c14561)


### Conclusion
The model's performance on the test set, as measured by a custom sMAPE of 5.332169162564367, demonstrates a 5.25% improvement over the baseline sMAPE of 5.609281705374244. This indicates that the model's predictions exhibit a notable enhancement compared to the expected baseline, validating its success in outperforming the initial expectations set by the baseline performance.
