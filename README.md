# MSCS 634 Lab 6: Association Rule Mining

**Rohail Shaikh**

## Purpose
Use Apriori and FP-Growth to find frequent products and association rules in the UCI Online Retail data. Seaborn charts show product frequency, co-occurrence, itemsets, rules, and mining time.

## Files
- `MSCS_634_Lab_6_Rohail_Shaikh.ipynb`: Complete, executed notebook.
- `online_retail_france.csv`: France item-level records from the [UCI Online Retail dataset](https://doi.org/10.24432/C5BW33), with customer IDs and dates omitted. The original dataset is licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Run
1. Install Python/Jupyter and the packages: `python -m pip install notebook pandas matplotlib seaborn mlxtend`.
2. Keep the notebook and CSV together in the same folder.
3. Open the notebook with `jupyter notebook` and select **Run > Run All Cells**.

## Key results
After removing returns, invalid sales, postage, and duplicate invoice-product rows, the analysis uses **387 invoices**. With minimum support **5%** and confidence **60%**, each algorithm finds **113 frequent itemsets** and **38 rules**, with identical results. For example, **PACK OF 6 SKULL PAPER PLATES → PACK OF 6 SKULL PAPER CUPS** has support **5.2%**, confidence **90.9%**, and lift **14.07**. This is an association within the France subset, not proof that one purchase causes the other.

## Decisions and challenge
The full retail dataset has many products, and `POSTAGE` is a frequent service charge. Selecting France and excluding postage kept the notebook simple and focused on products. Both algorithms use the same basket and thresholds. The notebook compares the median of five mining runs on the running computer; on this small, sparse subset Apriori was faster during verification, although timing varies by run.

## Data credit
Chen, D. (2015). *Online Retail* [Data set]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33
