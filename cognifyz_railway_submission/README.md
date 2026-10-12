# Cognifyz Solutions — Railway Data Engineering Task

## Contents
- `Railway_info.csv`: original input dataset supplied for this task.
- `src/railway_analysis.py`: reusable Python analysis pipeline.
- `outputs/cleaned_railway_data.csv`: cleaned data with normalized day and category fields.
- `outputs/saturday_trains.csv`: Saturday records (including values with the raw `d` suffix normalized to Saturday).
- `outputs/trains_from_selected_station.csv`: records starting from `CST-MUMBAI`.
- `outputs/railway_analysis.xlsx`: analysis workbook with summary and aggregation sheets.
- `outputs/charts/`: charts generated from the dataset.
- `outputs/screenshots/`: chart/profile previews suitable for inserting into the report.
- `report/railway_analysis_report.html` and `.pdf`: findings and recommendations.

## Run locally
Install dependencies:
```bash
pip install -r requirements.txt
```
Run from the project root:
```bash
python src/railway_analysis.py --input Railway_info.csv --output outputs
```

## Important data interpretation note
The source `days` column contains weekday values and variants ending in `d` (for example, `Saturdayd`). The analysis preserves the original value in `days_raw`, flags the suffix, and normalizes the weekday for day-wise analysis. The business meaning of the suffix has not been assumed and should be confirmed with the data owner.

## Metric caveat
`Average_Trains_Per_Operating_Day` is a simple source-station record count divided by seven. It is a normalized comparison, not a validated estimate of actual daily services. The source data has no dates or explicit daily service calendar.

## Tools
Python, pandas, NumPy, Matplotlib, openpyxl, ReportLab.
