# Gold Extraction Process

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

