# Copilot Instructions for Python Learning Project

## Project Overview
This is a Python learning project focused on foundational programming concepts and data analysis. The main work happens in Jupyter notebooks that combine executable Python code with learning exercises.

**Key Resources:**
- `Lesson2.ipynb` - Interactive notebook covering Python fundamentals (functions, strings, lists, dictionaries, loops)
- `data/assignment_2_data/` - CSV datasets for inflammation data analysis
- `data/slides_data/` - Real-world datasets (transportation, housing, municipal data) for practice

## Architecture & Data Flows

### Notebook Structure
Jupyter notebooks serve as the primary learning environment. Cells contain:
- **Function definitions** (e.g., `calc_total_bill()`, `divide()`) to teach function concepts, default parameters, and error handling
- **Exploratory code cells** testing functions with various inputs, including intentional error cases
- **Data structure manipulation** (lists, dictionaries) with transformative operations
- **String processing & formatting** using `.format()` and f-strings
- **File processing patterns** (see cell with `input_files` list comprehension)

### Data Organization
```
data/
├── assignment_2_data/       # Structured inflammation datasets (CSV)
│   ├── inflammation_01.csv  # 12 patient files for time-series analysis
│   └── small_*.csv          # Minimal test datasets
└── slides_data/             # Real-world datasets for learning
    ├── *delay*.csv          # Transportation delay data
    ├── bike_thefts*.csv     # Crime/safety datasets
    └── *.xlsx               # Structured lookup tables
```

## Key Patterns & Conventions

### Python Fundamentals Approach
1. **Function Definition Pattern**: Parameters with sensible defaults
   ```python
   def calc_total_bill(price, tax_rate=0.13, tip_rate=0.15):
       # Learn: default parameters, required vs optional args
   ```

2. **String Operations**: Both `.format()` and f-string approaches shown
   ```python
   # Traditional
   'Ada Lovelace\'s initials are {}.{}.'.format(first_name[0], last_name[0])
   # Modern (f-string)
   f'Ada Lovelace\'s initials are {first_name[0]}.{last_name[0]}.'
   ```

3. **List Comprehension Pattern**: File name transformation
   ```python
   input_files = ['data_01.csv', 'data_02.csv']
   output_files = []
   for i in input_files:
       temp_file_name = 'processed_' + i.replace('.csv', '.xlsx')
       output_files.append(temp_file_name)
   ```

4. **Data Structure Nesting**: Dictionaries with nested structures (Olympic cities example)

### Error Handling
Notebooks include intentional error cells to demonstrate:
- Division by zero (ZeroDivisionError)
- Type mismatches (string to numeric operations)
- Syntax errors (e.g., `calc_total_bill(200,,0.18)`)
- Missing positional arguments after keyword arguments

These error cells aid learning—do NOT attempt to "fix" them unless explicitly requested.

## Development Workflow

### Running Notebook Cells
- Execute cells individually using the Run button or keyboard shortcut
- Cells maintain kernel state—output depends on execution order
- Use `help(function_name)` to display docstrings (e.g., cell with `help(calc_total_bill)`)

### Loading Data
Notebooks should use relative paths from the notebook location:
```python
import pandas as pd
df = pd.read_csv('../data/assignment_2_data/inflammation_01.csv')
```

### Testing Pattern
Many cells function as unit tests for function definitions. When adding new functions:
- Define in one cell
- Test with multiple calls in subsequent cells (success cases + edge cases)
- Follow the convention of showing expected errors for learning

## Common AI Agent Tasks

### Adding Analysis Code
When extending lessons with data analysis:
1. Keep function definitions isolated in single cells
2. Use cells below for exploratory analysis and visualization
3. Reference datasets using `data/assignment_2_data/` or `data/slides_data/` paths
4. Include both `.format()` and f-string examples for consistency with learning goals

### Debugging
- Most error outputs in existing cells are intentional learning examples
- Check execution count to determine cell execution order
- Verify imports at notebook start (currently only `import numpy as np`)

### Documentation
- Add docstrings to functions explaining parameters and return values
- Use cell-level markdown comments to explain teaching concepts
- Keep docstrings brief but clear for learning purposes

## External Dependencies
- `numpy` - Currently imported but not actively used; extend with numerical operations
- `pandas` - Not yet imported; use for CSV data loading in data analysis lessons
- Jupyter/IPython - Runtime environment for notebooks

---

*Last Updated: Learning project baseline state with Python fundamentals in Lesson2.ipynb*
