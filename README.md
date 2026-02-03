# Echo Transfer Processor for XChem Echo

A Notebook for generating Echo liquid handler transfer files. 


## Project Structure

```
├── Echo_Transfer_Processor.ipynb       # Main processing notebook
├── sample-prep-file.csv  # Example sample preparation data
├── README.md                           # This file
```

## Input Data Format

The input CSV file should contain the following columns:

| Column | Description |
|--------|-------------|
| `plate_ID` | Unique identifier for the source plate |
| `Source Well` | Well position in source plate (e.g., A05, B12) |
| `ASAP_batch_ID` | Sample batch identifier |
| `Vol from stock nl` | Transfer volume in nanoliters |

## Output Format

Each generated transfer file contains:

| Column | Description |
|--------|-------------|
| `PlateBatch` | Destination plate name (format: `Zika-NS2B-NS3_creoptix_p##`) |
| `SrcWell` | Normalized source well position |
| `Destination well` | Sequential destination well (A1, B1, C1, etc.) |
| `XferVol` | Transfer volume in nanoliters |

## Usage

### Prerequisites

```python
import pandas as pd
import re
from pathlib import Path
```

### Running the Processor

1. **Prepare Input Data**: Ensure your sample preparation data is in CSV format with the required columns
2. **Configure Settings**: Update the configuration variables in the notebook:
   ```python
   PLATENAME = "Zika-NS2B-NS3"
   PLATETYPE = "creoptix"
   INPUT_FILE = "sample-prep-file.csv"
   OUTPUT_DIR = "transfer-files"
   ```
3. **Execute Notebook**: Run all cells in `Echo_Transfer_Processor.ipynb`
4. **Review Outputs**: Check the `transfer-files/` directory for generated files

### Configuration Options

- `PLATENAME`: Base name for destination plates
- `PLATETYPE`: Plate type identifier (e.g., "creoptix")
- `INPUT_FILE`: Path to input CSV file
- `OUTPUT_DIR`: Directory for output files

---

*Last updated: February 2026*