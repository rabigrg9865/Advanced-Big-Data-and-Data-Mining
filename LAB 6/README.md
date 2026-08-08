# MSCS 634 Lab 6: Association Rule Mining

## Purpose

This lab applies association rule mining to a public bakery transaction dataset. The notebook prepares item-level transaction records, explores product frequency and co-occurrence with Seaborn, mines frequent itemsets with Apriori and FP-Growth, generates association rules, and compares the two algorithms.

The dataset is `BreadBasket_DMS.csv` from the public `prasertcbs/basic-dataset` GitHub repository. After cleaning, the analysis used 9,465 transactions and 94 unique items.

## Key Insights

Coffee was the most common item, appearing in about 47.8% of transactions. Bread followed at about 32.7%, while tea, cake, pastry, sandwich, medialuna, and hot chocolate formed the next group of frequent items.

Both Apriori and FP-Growth found 61 frequent itemsets at a 1% minimum support threshold. The strongest product patterns were centered on coffee. For example, `Toast -> Coffee` had about 70.4% confidence and a lift of 1.47, meaning toast purchases were more likely to include coffee than a random basket. Rules such as `Pastry -> Coffee`, `Medialuna -> Coffee`, and `Sandwich -> Coffee` showed the same pattern.

The highest lift rule was `Coffee, Tea -> Cake`, with a lift of about 1.94. This rule had lower support than the coffee-centered food pairings, but it suggested a stronger-than-random relationship among those three items.

## Algorithm Comparison

Apriori and FP-Growth returned the same frequent itemsets and the same 31 association rules under the selected thresholds. FP-Growth ran faster in the executed notebook, taking about 0.12 seconds compared with about 0.59 seconds for Apriori. This result fits the expected behavior because FP-Growth compresses transactions into an FP-tree instead of repeatedly generating and testing candidate itemsets.

Apriori was still useful for this lab because its candidate-generation process is easy to inspect. FP-Growth was more efficient for the same output.

## Challenges and Decisions

The main decision was the minimum support threshold. A higher threshold returned mostly one-item patterns, while a lower threshold produced many sparse combinations. A 1% support threshold kept the output readable while preserving enough two-item and three-item patterns for rule mining.
