# Call Query Report Generator

This repository contains a Jupyter notebook that connects to Google Sheets, filters call records by date, joins branch metadata, and generates summary outputs.

## What it does

- Connects to a Google Sheets spreadsheet using a local service account JSON file.
- Loads retail call records from the `testing` worksheet.
- Loads staff-to-branch mapping from the `Staff-Branch` worksheet.
- Filters records by date and produces cleaned data extracts.
- Generates a PDF report with staff and branch summaries.

## Repository Layout

- `Data.ipynb` - main notebook with the data loading, transformation, and PDF generation logic.
- `output/` - generated PDF reports.
- `retail_filtered.xlsx` and `retail_filtered_20.05.2026.xlsx` - exported filtered data files.
- `khemra_account.json` - local Google service account credentials. Keep this file private.

## Requirements

- Python 3.10 or newer.
- Jupyter Notebook or VS Code notebooks.
- Python packages:
  - `pandas`
  - `gspread`
  - `google-auth`
  - `matplotlib`
  - `openpyxl`

## Setup

1. Install the Python packages listed above.
2. Place your Google service account JSON file at `khemra_account.json`.
3. Open `Data.ipynb` in VS Code or Jupyter.
4. Update the spreadsheet key in the notebook if you want to point to a different sheet.

## Usage

Run the notebook cells in order. The notebook will:

1. Connect to Google Sheets.
2. Load the `testing` worksheet.
3. Filter the call data for the target date range.
4. Join staff branch information.
5. Export the filtered data and generate a PDF report in `output/`.

## Security Note

The service account file is ignored by Git on purpose. Do not commit real credentials to the repository. If you need to share the project, share a template file or setup instructions instead of the live JSON key.