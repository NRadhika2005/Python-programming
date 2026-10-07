# Data Processing Pipeline

A beginner-friendly Python data processing pipeline that reads raw CSV data, cleans and transforms it, handles missing values and invalid records, removes duplicates, writes structured output, and records execution details through logging.

## Task Objective

Build a Python data processing pipeline that:

- Reads raw data from a file
- Cleans and transforms the data
- Handles missing values
- Performs type conversions
- Handles edge cases such as duplicates and invalid values
- Implements logging
- Uses configuration management
- Produces structured output

## Project Structure

```text
data-processing-pipeline/
│
├── data/
│   ├── input.csv
│   └── output/
│       └── processed_data.csv
│
├── logs/
│   └── pipeline.log
│
├── config.json
├── pipeline.py
└── README.md
```

## Technologies Used

- Python 3
- CSV module
- JSON module
- Logging module
- Datetime module
- pathlib

No external Python packages are required.

## Data Processing Steps

1. Read records from `data/input.csv`.
2. Remove unnecessary whitespace from text fields.
3. Fill missing email values with `Not Provided`.
4. Fill missing city values with `Unknown`.
5. Convert age to an integer.
6. Convert salary to a numeric value.
7. Replace invalid salary values with `0`.
8. Validate joining dates.
9. Remove duplicate employee IDs.
10. Create a `salary_band` field.
11. Save the processed data to `data/output/processed_data.csv`.
12. Record pipeline activity in `logs/pipeline.log`.

## Configuration

The `config.json` file keeps input, output, logging, and missing-value settings outside the Python source code.

Example:

```json
{
    "input_file": "data/input.csv",
    "output_file": "data/output/processed_data.csv",
    "log_file": "logs/pipeline.log"
}
```

This makes it easier to change file locations without editing the main program.

## How to Run

### 1. Install Python

Install Python 3 from the official Python website.

### 2. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd data-processing-pipeline
```

### 3. Run the pipeline

```bash
python pipeline.py
```

On some systems, use:

```bash
python3 pipeline.py
```

### 4. Check the results

After successful execution:

- Processed data: `data/output/processed_data.csv`
- Execution log: `logs/pipeline.log`

## Sample Transformations

| Raw Value | Processed Value |
|---|---|
| `  Ravi Kumar ` | `Ravi Kumar` |
| Empty email | `Not Provided` |
| Empty city | `Unknown` |
| Empty age | `0` |
| `invalid` salary | `0` |
| Duplicate employee ID | Duplicate record skipped |
| Invalid joining date | `Unknown` |

## Edge Cases Handled

- Missing employee ID
- Missing text values
- Missing numeric values
- Invalid numeric values
- Invalid dates
- Duplicate employee IDs
- Missing input file
- Unexpected processing errors

## Expected Output

The processed CSV contains:

- `employee_id`
- `name`
- `email`
- `age`
- `city`
- `salary`
- `joining_date`
- `salary_band`

## Logging

The pipeline logs:

- Pipeline start
- Number of input records
- Duplicate records skipped
- Records with missing identifiers
- Output file creation
- Successful completion
- Errors and exceptions

## Project Outcome

This project demonstrates a simple ETL-style workflow using Python:

**Extract → Clean → Transform → Validate → Load**

It provides practical experience with file handling, data cleaning, type conversion, error handling, logging, configuration management, and structured output generation.

## Author

Akhila
