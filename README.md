# Student LLM Usage and Learning Survey

This repository contains code and data for an assignment in the **Tools for Research** course, part of the **M.Sc. Computer Science** program (2026). It uses a Microsoft Forms survey to explore students’ use of large language models (LLMs) and learning, with Python workflows for preprocessing and analysis.

## Project files

| File | Description |
| --- | --- |
| `Survey_ Studying impact of LLM usage on student's learning.xlsx` | Original survey export. Keep this as the source copy. |
| `preprocess_survey_colab.ipynb` | Google Colab notebook that uploads the original workbook, cleans it, and downloads `cleaned_survey_data.xlsx`. |
| `survey_analysis_colab.ipynb` | Google Colab notebook with descriptive statistics, Matplotlib charts, and a Spearman correlation analysis. |

## Dataset

The dataset contains Microsoft Forms responses about AI/LLM use, study habits, perceived effects on learning, and related concerns. The original export includes response metadata and survey answers. Some questions use ordered response scales, such as frequency or perceived impact.

The current cleaned workbook contains 10 responses. Results from this small sample are exploratory and may not represent a larger student population.

## Preprocessing

The preprocessing notebook:

- Trim spaces from column names and text responses.
- Treat common text markers such as `N/A` and `-` as missing values.
- Remove completely empty rows and exact duplicate rows.
- Fill missing numeric values with the column median.
- Leave missing text responses blank, including respondent names, so anonymous responses are not assigned another respondent’s identity.

The Colab notebook saves and downloads the result as `cleaned_survey_data.xlsx`.

## Analysis

The analysis notebook uses the cleaned workbook to:

- Summarize AI-use frequency and perceived impact on conceptual understanding.
- Display response counts and basic descriptive statistics.
- Create bar charts and a scatter plot with Matplotlib.
- Calculate a Spearman correlation between AI-use frequency and perceived impact.

The correlation describes an association. It does not establish that AI use caused a change in learning. Interpret statistical results cautiously because the dataset is small.

## Run in Google Colab

1. Open `preprocess_survey_colab.ipynb` in Google Colab.
2. Run the cells in order and upload the original Excel workbook when prompted.
3. Download the generated `cleaned_survey_data.xlsx` file.
4. Open `survey_analysis_colab.ipynb` in Google Colab.
5. Run the cells in order and upload the cleaned workbook when prompted.

Colab stores uploaded files in its temporary runtime. Download the cleaned workbook to keep a copy, or save it to Google Drive separately. If the runtime resets, upload the required workbook again.

## Run the preprocessing script locally

Install the required packages:

```bash
python -m pip install pandas openpyxl
```

Place the source workbook in the project folder using the filename shown in the project files table, then run:

```bash
python preprocess_survey.py
```

The script writes `cleaned_survey_data.xlsx` in the project folder.

## Privacy

Identifying details were removed from Survey_ Studying impact of LLM usage on student's learning.xlsx before the workbook was added to this repository. Please follow the survey's consent terms when sharing or reusing its responses.
