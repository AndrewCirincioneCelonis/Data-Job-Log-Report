# Data Job Log Report

## Overview

This notebook retrieves recent Celonis data job execution logs and creates reports that help analyze schedule runs, transformation runtimes, and runtime variability across executions.

## What it does

- Connects to a Celonis team, data pool, and data job.
- Pulls recent execution logs for the selected data job.
- Calculates run and transformation runtimes.
- Creates summary reports for schedules, transformations, and selected long/short runs.
- Exports report CSV files.

## Requirements

- Celonis access and API key.
- A data pool ID and data job ID.

## Setup

Fill in the user input variables:

```python
team_url = ''
api_key = ''
key_type = 'USER_KEY'
data_pool_id = ''
data_job_id = ''
```

## Outputs

The notebook can generate the following files:

```text
transformation_log_report.csv
schedule_log_report.csv
long_run_log.csv
short_run_log.csv
```

## Important notes

- The execution log request currently uses `limit=25`, so it only analyzes the most recent set of runs returned by that API call.
- Timezone conversion is set to `America/New_York`.
- The example `run_key` values are hardcoded and should be replaced with run keys from your own `execution_dict`.
