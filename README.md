# Invoice-Data-Normalisation-with-Python
This project demonstrates a practical data cleaning and transformation workflow using Python and Pandas to convert a compressed invoice dataset into a structured, analysis-ready format.
The main challenge in the raw dataset was that multiple transaction values were stored within a single row. Categories and their corresponding amounts were combined using the pipe (|) delimiter, making the dataset unsuitable for straightforward analysis.

## Project Overview
The original dataset contained:
- 4 rows
- 3 columns
<img width="886" height="496" alt="Image" src="https://github.com/user-attachments/assets/11b943bc-d709-4b5a-abb4-fd76761b11bb" />

A single record could contain multiple categories and multiple corresponding amounts.Several transactions were compressed into one row.
## Data Cleaning and Transformation Steps
1. Load and Inspect the Dataset
The raw invoice dataset was imported into Pandas and inspected to understand its initial dimensions and structure.
The dataset initially contained 4 rows and 3 columns.
2. Identify the Structural Data Issue
Inspection of the raw dataset revealed that the Category and Amount columns contained multiple values separated by the pipe (|) character.
3. Validate Category and Amount Pairing
Before expanding the rows, the number of category values was compared with the number of amount values for each Order ID.
This validation ensured that every category had a corresponding amount.
This confirmed that the records could be safely expanded without losing the relationship between categories and amounts.
4. Split the Combined Values
The Category and Amount columns were split using the pipe (|) delimiter.
Each column was transformed from a single string containing multiple values into a list of individual values.
5. Expand Transactions into Individual Rows
Pandas' explode() function was used to transform the lists into separate rows while preserving the relationship between:
- Order ID
- Category
- Amount
The Order ID was repeated for each corresponding transaction, preserving the original invoice relationship.
## Final Dataset
The transformation successfully converted the dataset from:
4 compressed invoice records
to individual transaction records
<img width="802" height="474" alt="image" src="https://github.com/user-attachments/assets/3dfb0cc5-9093-4093-a7cc-4987223e69f0" />

## Tools Used
Python
Pandas
