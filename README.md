# Emirates Auction — Website Data Analysis

Academic data-mining project exploring vehicle-auction listing data using **Python, Selenium, Beautiful Soup, pandas, scikit-learn, and WEKA**.

## Project overview

The original Jupyter notebook contains a web-scraping workflow for vehicle listings from [Emirates Auction](https://www.emiratesauction.com/ar/motors), followed by data preparation and exploratory machine-learning experiments.

**Scope and evidence:** The notebook's saved execution output reports **100 extracted records** and exports the semicolon-delimited `emirates_auction_data.csv` dataset. This is a historical run, not a claim that the live scraper still works today.

## Dataset

The published CSV includes the following fields:

| Column | Meaning |
| --- | --- |
| `title` | Vehicle title / model |
| `sequence` | Listing sequence identifier |
| `time_left` | Remaining time as displayed on the site |
| `bids` | Number of bids |
| `price` | Displayed price |

**Dataset size:** 100 records in the original notebook run. The recorded cleaning step kept 100 after missing-value removal, and 98 after outlier removal.

## Workflow covered in the original notebook

1. Extract vehicle listing information with Selenium and Beautiful Soup.
2. Load and clean CSV data with pandas.
3. Encode a vehicle-brand feature from listing titles.
4. Scale numeric features and handle outliers using Z-scores.
5. Explore Random Forest, Logistic Regression, and SVM classifiers.
6. Explore correlation-based feature selection and PCA.
7. Compare experiments with preprocessing variations.

## Repository files

- `Data mining project.ipynb` — original notebook with Python code and saved outputs.
- `emirates_auction_data.csv` — collected vehicle listings (100 rows).
- `emirates_auction_data.arff` — **five-row example ARFF**, not a full export of the 100-row CSV.
- `WEKA_vs_Python_Report.pdf` — accompanying project report (its contents should be reviewed independently).

## Critical interpretation notes

- The original notebook defines a class based on whether `price` exceeds the dataset median, but also includes **`price` as a model feature**. This creates **target leakage**. Therefore, the notebook's saved classification accuracies are **not valid evidence of predictive performance**.
- Some notebook cells may have been executed out of order; the PCA section needs a clean rerun after aligning feature and target rows.
- The ARFF file contains only five data rows. It does not demonstrate a full WEKA analysis of the CSV.
- The scraper depends on website selectors and a local ChromeDriver path and may need maintenance.
- Public notebook output should be checked for personal student information and local machine paths before being shared broadly.

## Portfolio status

**Original academic coursework, published for reproducibility and transparency.** The original scraping and preparation steps are evidenced by saved outputs. Machine-learning metrics require correcting leakage, rerunning the pipeline, and validating results before being reported as portfolio findings.

The later [Emirates Auction Python/WEKA reconstruction](https://github.com/omarshaeban/emirates-auction-weka-analysis) is a separate educational reconstruction and should not be confused with this original submission.
