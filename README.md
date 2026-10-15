# Data Cleaning Exercise

This repository contains teaching materials for a practical classroom exercise on **data quality, data cleaning, validation, and the effect of data quality on analysis and visualization**.

The exercise is designed for use in **Google Colab**. No prior Python knowledge is required: the code is already provided, and students mainly need to inspect data, make cleaning decisions, run notebook cells, and interpret the results.

## Learning objectives

After completing the exercise, students should be able to:

- identify common data quality problems in a spreadsheet;
- distinguish between issues that can be corrected safely and automatically and issues that require human review;
- standardize categorical, date, and numeric values;
- understand why original values should sometimes be preserved separately;
- understand the role of validation statuses such as `OK`, `CHECK`, and `MISSING`;
- evaluate how data cleaning affects analysis and visualization.

## Repository contents

- `Sintetisko-datu-kopa.xlsx` — the original synthetic Excel dataset containing intentionally introduced data quality problems.
- `Uzdevuma_nosacijumi.docx` — student instructions in Latvian.
- `Data_cleaning_visualization.ipynb` — a notebook for examining the effects of data quality problems before cleaning and comparing the results before and after cleaning.
- `Data_cleaning_task.ipynb` — the main notebook for the data-cleaning exercise.

## Classroom workflow

The materials are intended to be used in a specific order.

### 1. Initial inspection

Students first receive only:

- `Sintetisko-datu-kopa.xlsx`
- `Uzdevuma_nosacijumi.docx`

They inspect the dataset in groups and identify at least five types of data quality problems. For each problem, they should find a concrete example and decide whether it can be corrected automatically or requires human review.

### 2. Group discussion

The identified problems are discussed together before the notebooks are opened.

> **Important:** during the classroom activity, students should not open `Data_cleaning_visualization.ipynb` or `Data_cleaning_task.ipynb` before this discussion, because the notebooks reveal several of the data quality issues included in the dataset.

### 3. Visualization before cleaning

Students open `Data_cleaning_visualization.ipynb` in Google Colab and run the **PIRMS TĪRĪŠANAS** (“Before cleaning”) section.

This demonstrates how inconsistent or invalid values can affect:

- category counts;
- date interpretation;
- numeric analysis;
- charts and summaries.

Students stop at the section **“Tagad iztīrām datu kopu”** (“Now we clean the dataset”).

### 4. Data cleaning

Students open `Data_cleaning_task.ipynb` and follow the instructions step by step.

The notebook covers examples such as:

- fully empty rows;
- unnecessary whitespace;
- standardization of `Jā / Nē` values;
- date standardization and validation;
- satisfaction values on a 1–5 scale;
- numeric income values containing additional text.

Some transformations are applied automatically, while ambiguous values are preserved or flagged for review.

The notebook produces:

`Sintetisko-datu-kopa_CLEANED.xlsx`

### 5. Before/after comparison

Students return to `Data_cleaning_visualization.ipynb`, continue from the cleaned-data section, upload `Sintetisko-datu-kopa_CLEANED.xlsx`, and compare the results before and after cleaning.

### 6. Final discussion

The exercise ends with questions about:

- why data cleaning is necessary;
- what other parts of the dataset could still be cleaned;
- which problems can be automated and which require human judgment;
- why original values may need to be preserved;
- whether data always need to be cleaned before analysis.

## Main principle

Not every suspicious value should be automatically “fixed”.

Some problems can be handled through safe syntactic standardization, such as removing unnecessary whitespace. In other cases, changing a value automatically could alter its meaning or introduce information that was not present in the original data.

For this reason, the cleaning notebook uses additional columns such as:

- `_original` — preserves the original value;
- `_check` — records validation status;
- `_note` — stores additional information about the transformation or problem.

The objective is not to make every value look correct at any cost, but to create a **transparent and reproducible cleaning process**.

## Dataset

The dataset is **synthetic** and was created specifically for teaching purposes. It intentionally contains a range of data quality problems so that students can identify, discuss, clean, and validate them in a controlled setting.

No real student data are included.

## Technical note

The notebooks are intended to be opened in **Google Colab**. Code cells are collapsed by default, so students can focus on the task and outputs while still being able to inspect the Python code using **Show code / Hide code**.
