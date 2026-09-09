# ECON 4720, Econometric Methods; Fall 2025

Homework solutions and empirical analyses by Rahul Sunilkumar. Assignments combine mathematical derivations, written explanations, and Python code in Quarto documents, with PDF versions included for reading.

## Assignments

| Assignment | Source | PDF |
| --- | --- | --- |
| HA03 | [Quarto](ha03/ha03.qmd) | [PDF](ha03/ha03.pdf) |
| HA06 | [Quarto](ha06/ha06.qmd) | [PDF](ha06/ha06.pdf) |
| HA07 | [Quarto](ha07/ha07.qmd) | [PDF](ha07/ha07.pdf) |
| HA09 | [Quarto](ha09/ha09.qmd) | [PDF](ha09/ha09.pdf) |
| HA10 | [Quarto](ha10/ha10.qmd) | [PDF](ha10/ha10.pdf) |
| HA11 | [Quarto](ha11/ha11.qmd) | [PDF](ha11/ha11.pdf) |

Topics include probability and statistical inference, linear algebra, ordinary least squares, multiple regression, nonlinear specifications, instrumental variables, panel data, and time series.

## Repository layout

- `haXX/`: each assignment's Quarto source and existing PDF output.
- `data/`: shared datasets and accompanying descriptions, including Stata, Excel, and CSV files. Assignment code uses paths relative to its own folder (`../data/`).
- `ECON4720.code-workspace`: VS Code workspace configuration.
- `.gitignore`: excludes local Python environments, Python caches, and macOS metadata from new tracking.

## Working with the assignments

Read the included PDFs directly, or edit the `.qmd` files to change the analysis. To execute the Python code and render PDFs, install Quarto, Python, and a LaTeX distribution with `pdflatex` and the `erewhon` font package.

From the repository root, create and activate a local environment and install the packages used by the assignments:

```sh
python3 -m venv venv
source venv/bin/activate
python -m pip install jupyter numpy pandas scipy matplotlib
export QUARTO_PYTHON="$PWD/venv/bin/python"
quarto render ha11/ha11.qmd
```

Replace `ha11` with the assignment you want to render. The checked-in PDFs are existing outputs; edits to a source require rendering again to update its PDF.

## Keeping the virtual environment off GitHub

`venv/` and `.venv/` are listed in `.gitignore`. Because `venv/` was already tracked, run this once from the repository root:

```sh
git rm -r --cached venv
```

This removes the environment from Git's index while keeping the local files. Commit that removal together with `.gitignore`, then push to remove it from the current branch on GitHub. Earlier commits will still contain the previously tracked environment.
