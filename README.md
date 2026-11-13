## Requirements

The project requires **Python 3** and the following libraries:

- PyTorch
- Transformers
- Accelerate
- Z3
- SymPy
- Pandas
- Datasets
- Hugging Face Hub

## Notebook Overview

The notebook performs the following operations:

1. Downloads the full RuleTaker validation split.
2. Downloads the two CounterBench question files.
3. Downloads the FOLIO validation split.
4. Runs the reasoning system on each dataset.
5. Prints accuracy and execution time for each dataset.
6. Generates the final `submission.csv` file.

## FOLIO Translation

FOLIO translation uses **Qwen2.5-7B-Instruct** in full precision.

**Hardware Requirements:**
- A CUDA-enabled GPU is required.
- The GPU must have sufficient memory to load and run the model.
- The model is automatically downloaded on first use.

## Submission Format

The generated `submission.csv` file contains two columns:

| Column | Description |
|--------|-------------|
| `id` | Unique identifier for each example |
| `label` | Predicted binary label |

### Additional Details

- IDs are prefixed with the dataset name to ensure uniqueness across datasets.
- Predictions are generated using publicly available data.
- Unsupported results are recorded as `False` in the binary output file.