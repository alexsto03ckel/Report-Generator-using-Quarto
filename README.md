# 🎬 Top Movies Report Generator

This project generates **PDF reports** for the top-rated movies by genre using data from the TMDB (The Movie Database) and Python scripting with **Quarto (`.qmd`)**.

## 📄 Description

Using a parameterized [Quarto Markdown](https://quarto.org/) document (`.qmd`), this tool:
- Filters movies by selected genre.
- Sorts them based on average votes.
- Displays ratings distribution charts.
- Shows posters, titles, and descriptions of the top movies.

Each report is rendered as a **standalone PDF**, making it ideal for presentations or sharing insights.

---

## 📊 Example Report Contents

Each report includes:
- **Histogram** of rating distributions for the selected genre.
- A list of **top N movies**, including:
  - Title
  - Poster image
  - Short description

---

## 🧠 Technologies Used

- 🐍 Python (with `pandas` and `matplotlib`)
- 📄 Quarto (`.qmd`)
- 📦 TMDB Movie Dataset (`TMDB-Small.csv`)
- 💻 Command-line automation with `os.system`

---

## 📁 File Structure
---
.
├── data/
│   └── TMDB-Small.csv               # Movie dataset
├── parameterized-report.qmd         # Quarto template for generating reports
├── generate_reports.py              # Python script to batch generate reports
├── genre_X_Y.pdf                    # Sample generated reports
└── README.md                        # This file

---

## ⚙️ How to Use

### 1. Requirements

- Python 3.7+
- Quarto installed → [https://quarto.org/docs/get-started/](https://quarto.org/docs/get-started/)
- Python packages:
  ```bash
  pip install pandas matplotlib
``
  ## 📊 Parameters

The report is parameterized with:

- `genre`: The movie genre (e.g., `"comedy"`, `"action"`, `"drama"`)
- `num_movies`: Number of top movies to include in the report

These parameters can be set at the top of the `.qmd` file or passed directly via command line when using Quarto.

## 🖥️ Usage

### 1. Run a single report manually

You can generate a report using Quarto with specific parameters:

```bash
quarto render parameterized-report.qmd -P genre:comedy -P num_movies:10 --output comedy_10.pdf
```

This will create a file named `comedy_10.pdf` with the top 10 comedy movies.

### 2. Generate reports in batch

Use the provided Python script to automatically generate multiple reports across genres and different `num_movies` values:

```bash
python generate_reports.py

