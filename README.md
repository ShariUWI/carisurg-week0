# carisurg-week0

# CariSurg MedTech Pathways: Week 0 Portfolio

This repository contains my Week 0 submissions for the **CariSurg MedTech Pathways Programme**.

Week 0 focuses on onboarding, environment setup, Python readiness, basic data cleaning, exploratory data analysis, and clinical context development using a de-identified emergency triage dataset.

## Programme Context

The CariSurg MedTech Pathways Programme is a 13-week intensive designed to develop Caribbean talent in clinical AI, health technology, data analytics, and healthcare innovation.

Week 0 introduces the tools and workflow that will be used throughout the programme, including Google Colab, Google Drive, Python, pandas, GitHub, and basic clinical data analysis.

## Week 0 Objectives

The main objectives for Week 0 are to:

- Set up Google Drive and Google Colab
- Confirm that Python 3.10+ is available
- Create and use a public GitHub repository
- Load and inspect the Week 0 emergency triage dataset
- Clean selected dataset columns
- Perform basic exploratory data analysis
- Create simple data visualizations
- Explain a clinical vital sign in plain language
- Develop simple rule-based logic to identify at-risk patients
- Submit a final documented notebook

---

## Day 1 Submission: Gender Column Cleaning

The Day 1 task focused on cleaning the `Gender` column in the Week 0 emergency triage dataset.

The completed notebook includes:

- Loading the dataset into pandas
- Inspecting the original `Gender` column
- Identifying inconsistent values such as `0`, `1`, `Male`, `MALE`, `Female`, and `FEMALE`
- Encoding gender values using:
  - `1 = Male`
  - `0 = Female`
  - `2 = Non-binary/Other`
  - `-1 = Unknown/Unspecified`
- Handling missing, unclear, and unexpected entries
- Verifying the cleaned column using value counts
- Saving the cleaned dataset for future Week 0 tasks

Notebook: `S_Oliver_Week0_Day1_Gender_Cleaning.ipynb`

---

## Day 2 Submission: Advanced MAP Cleaning

The Day 2 task focused on cleaning the assigned `MAP` column. Since MAP is calculated from systolic and diastolic blood pressure, we first prepared `SBP` and `DBP`, then recalculated MAP using:

`MAP = (SBP + 2 × DBP) / 3`

The submission includes:

- Completed Colab/Jupyter notebook
- MAP cleaning justification report
- Screenshots showing environment setup and final cleaning outputs
- Evidence of DBP, SBP, and MAP validation checks

### Files

- `S_Oliver_Week0_Tutorial2_Advanced_Cleaning.ipynb`
- `MAP_Cleaning_Report_Extra_Justifications.pdf`

### Evidence Screenshots

Screenshots are stored in the `screenshots/` folder and show the notebook outputs used to verify the cleaning process.

## Cleaning Considerations

Several considerations were made during the MAP cleaning process:

1. **Clinical dependency of MAP**  
   MAP is not an independent value. It is calculated from systolic blood pressure (`SBP`) and diastolic blood pressure (`DBP`) using:

   `MAP = (SBP + 2 × DBP) / 3`

   Because of this, we prepared `SBP` and `DBP` before recalculating `MAP`.

2. **Valid clinical ranges**  
   We used the following ranges to identify invalid values:

   - `SBP`: 50-250 mmHg
   - `DBP`: 30-150 mmHg
   - `MAP`: 40-180 mmHg

3. **Invalid values were not deleted immediately**  
   Values outside the valid range were converted to `NaN` instead of deleting patient rows. This preserved other useful patient information.

4. **Median imputation was used where appropriate**  
   Median imputation was selected because blood pressure values may contain outliers, and the median is less affected by extreme values than the mean.

## Submission Evidence

The repository includes:

- Completed Day 2 notebook
- MAP cleaning justification report
- Screenshots showing the cleaning outputs
    - `screenshots/tut2_environment_setup.png`
    - `screenshots/dbp_cleaning.png`
    - `screenshots/sbp_cleaning.png`
    - `screenshots/map_cleaning1.png`
    - `screenshots/map_nan_output.png`
- Evidence of the considerations used to clean SBP, DBP, and MAP

6. **MAP was recalculated from cleaned SBP and DBP**  
   After preparing `SBP` and `DBP`, we recalculated `MAP` using the clinical formula. This was more appropriate than only filtering or imputing the original MAP column.

7. **Clinically significant values were preserved**  
   One MAP value was slightly below the expected range. Since it was calculated from valid SBP and DBP values, it was preserved and flagged as a possible critically low MAP rather than treated as a data error.
