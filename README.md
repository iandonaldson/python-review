# python-review
a review of python basics as a md document

## Notebook setup in VS Code

Open this folder in VS Code, then install the Microsoft `Python` and `Jupyter` extensions.

Create and activate a virtual environment from the repository root:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

Install the notebook kernel and the project dependencies:

```bash
python -m pip install ipykernel pandas scikit-learn numpy plotly dash nbformat matplotlib
```

Register the environment as a Jupyter kernel:

```bash
python -m ipykernel install --user --name python-review --display-name "Python Review (.venv)"
```

Then in VS Code:

1. Open `codily.ipynb` or `python-review.ipynb`.
2. Click `Select Kernel` in the top right.
3. Choose `Python Review (.venv)`.
4. Run the first cell.

If you want to reinstall everything later from the same environment, use:

```bash
source .venv/bin/activate
python -m pip install --upgrade pip ipykernel pandas scikit-learn numpy plotly dash nbformat matplotlib
```
