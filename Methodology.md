# Data Source(s)
- The dataset was loaded from a local file named **`elements-by-episode.csv`**.
- The file was referenced multiple times in the notebook using both Python’s built-in `open()` function and `pandas.read_csv()`.
- Because the CSV was not bundled with the notebook, the original download location is unknown.

# Data Preparation/Cleaning
- **Manual line parsing:**  
  - The notebook opens `elements-by-episode.csv` using `open()` and reads it line by line.  
  - Each line is processed with `strip()` to remove trailing newline characters.  
  - Lines are split with `.split(",")` to create a list of column values.
- **Column extraction by index:**  
  - The code checks `len(clean_parts) > 60` and then extracts `clean_parts[60]`.  
  - This implies the CSV has **at least 61 columns**, and only the value at index 60 is used for frequency counting.
- **String-based counting:**  
  - Values from column index 60 are added to a dictionary (`index_60_counts`) to compute counts for each unique entry.
- **DataFrame loading:**  
  - The CSV is loaded using `pandas.read_csv()` into a DataFrame (`elements`).  
  - No additional type conversions, missing-value handling, or column renaming were performed in the notebook.
- **Text processing for word frequencies:**  
  - Episode titles are split into words, collected into a list, and converted into a `pandas.Series` for frequency counts.  
  - No stop-word filtering or text normalization (e.g., case-folding, punctuation removal) appears in the code.

# Assumptions
- It is assumed that **comma separation** is sufficient to correctly parse the CSV file, even though some CSVs require quoting or special handling.
- It is assumed that the **61st column (index 60)** is meaningful and consistently populated across rows.
- When splitting episode titles into words, it is implicitly assumed that:
  - Words are separated by spaces.
  - Case differences (`Tree` vs. `tree`) do not need normalization.
- It is assumed that missing or malformed rows (e.g., rows with fewer than 61 columns) can simply be **skipped**.

# Limitations
- Because rows with fewer than 61 columns are ignored, this may introduce bias if those rows contain relevant information.
- Parsing the CSV manually with `.split(",")` may incorrectly split fields containing commas inside quotes.
- The CSV file folder/location is unknown, so reproducibility of the workflow is limited.
- Word frequency analysis does not remove punctuation or enforce lowercase, so counts may be inflated or fragmented (e.g., `"tree"` vs `"tree,"`).
- No documentation is available describing what each column represents, making it difficult to confirm the meaning of index-60 values.
- Repeated `read_csv()` calls suggest that no persistent cleaned dataset was created during the workflow.