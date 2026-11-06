# formal-error-bound-gmu
# Compiler Error Bound Verification (Task 3 Solution)

This project checks the mathematical error and numerical differences between a normal PyTorch model and its compiled version using `torch.compile`.

## What it does
- Loads `bert-base-uncased` from Hugging Face.
- Runs a forward pass on a sample text to get the baseline output.
- Compiles the model via `torch.compile` and gets the optimized output.
- Calculates the maximum absolute error and mean error between both outputs to ensure the compiler didn't break anything.

## Repository Setup
The code is organized as a clean python package:
- `src/formal_error_bound/`: Contains the core analyzer logic and config schema.
- `tests/`: Basic unit testing using pytest.
- `examples/quickstart.py`: End-to-end script to run the Hugging Face model and compile it.
- `pyproject.toml`: Package installation settings.

## Actual Test Results
When running the verification script on the BERT model, it successfully passed the error bound check:
- **Maximum Absolute Error:** 2.3841e-06
- **Mean Absolute Error:** 2.9280e-07
- **Status:** PASS (The error is well within the acceptable threshold)

## How to run
1. Install the package locally:
   ```bash
   pip install -e .
   ```
2. Run the full Hugging Face compilation test:
   ```bash
   python examples/quickstart.py
   ```
3. Run unit tests:
   ```bash
   pytest
   ```
