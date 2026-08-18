# Amazon Bestsellers — Data Analysis

A short pandas exercise exploring Amazon's Top 50 bestselling books dataset (2009–2019): cleaning the raw data, then pulling out the most prolific authors and the average rating per genre.

## Dataset

`bestsellers.csv` — 550 rows, one row per bestselling book/year, with columns:

| Column | Description |
|---|---|
| `Name` | Book title |
| `Author` | Author name |
| `User Rating` | Average user rating |
| `Reviews` | Number of reviews |
| `Price` | Price (USD) |
| `Year` | Year it appeared in the bestseller list |
| `Genre` | Fiction / Non Fiction |

## What the notebook does (`main.ipynb`)

1. **Load** `bestsellers.csv` into a DataFrame and do a first pass (`head`, `shape`, `describe`, `columns`).
2. **Clean**:
   - drop duplicate rows;
   - rename columns to clearer names (`Name` → `Title`, `Year` → `Publication Year`, `User Rating` → `Rating`);
   - cast `Price` from `int` to `float`.
3. **Analyze**:
   - author popularity — count of bestseller appearances per author (`value_counts`);
   - average rating by genre (`groupby("Genre")["Rating"].mean()`).
4. **Export** the two results to CSV.

## Outputs

- **`top_authors.csv`** — top 10 authors by number of bestseller appearances (Jeff Kinney leads with 12, followed by Gary Chapman, Rick Riordan and Suzanne Collins with 11 each).
- **`avg_rating_by_genre.csv`** — average rating per genre: Fiction (≈4.65) edges out Non Fiction (≈4.60).

## Tech stack

- Python 3.10, [pandas](https://pandas.pydata.org/) (2.2.3)
- Jupyter Notebook

## Running it

```bash
pip install pandas
jupyter notebook main.ipynb
```
Make sure `bestsellers.csv` sits in the same folder as the notebook before running all cells.

## Possible next steps

- Visualize the results (bar charts for top authors / avg rating by genre) instead of just exporting to CSV.
- Look at rating and price trends over time (`Publication Year`).
- Check for a correlation between `Price`, `Reviews` and `Rating`.

## Author

Mathias Chane-Waye
