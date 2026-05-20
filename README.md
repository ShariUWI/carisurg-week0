# carisurg-week0

# CariSurg MedTech Pathways - Week 0 Portfolio

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
