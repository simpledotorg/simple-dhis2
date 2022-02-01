# Patient Import

This script imports patients from a Simple line list into DHIS2. To use it, follow the steps below.

## 1. Download a line list from Simple

Log into the Simple dashboard and download the desired line list from Reports.

## 2. Enrich the line list with DHIS2 identifiers

Under the human-readable headers, insert a new row. Populate the relevant columns in that row with the DHIS2 UIDs for those fields.

## 3. Place the enriched line list in the `src/` directory

Note that the `src` directory is gitignored.

## 4. Run the script

The script will convert the linelist into a JSON file and place it in the `dist/` directory. This directory is also gitignored.
The JSON file is ready to be uploaded to DHIS2

## 5. Upload the JSON file

The JSON file can be uploaded to DHIS2 through:

1. The dashboard: Navigate to Import/Export --> Tracked Entity Instances --> Upload the JSON file
1. The command line: `curl -d @dist/test.json "https://dhis2-sandbox.simple.org/api/trackedEntityInstances" -X POST -H "Content-type:application/json" -u 'user:pass'`