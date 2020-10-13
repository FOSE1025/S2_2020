# Week 10 SGTA (External Offering)
# PRAC_01 

## Activity 1 - Line charts with trends

The following CSV file has been downloaded from https://people.sc.fsu.edu/~jburkardt/data/csv/csv.html and contains records of floods of the Nile river over 570 years.

* [nile.csv](nile.csv)

Using MATLAB, conduct the following activities:

1. Load the CSV file nile.csv.
2. Plot the data as a line plot.
2. Add a linear trend line.
3. Does the trend line show an increase or a decrease of severity of floods by the Nile river?

## Activity 2 - Correlation matrix

The following CSV file has been downloaded from https://people.sc.fsu.edu/~jburkardt/data/csv/csv.html and contains 1034 records with various information from baseball players.

* [mlb_players.csv](mlb_players.csv)

Using MATLAB, write a live script that implements the follow:

1. Load the CSV file mlb_players.csv.
2. Compute the correlation matrix between the columns "Heightinches" and "Weightlbs". To compute the correlation matrix, use MATLAB's `corrcoef` function. Remember that this function needs a matrix as input, so you need to extract the columns from your table using the notation `{ ... }`.

## Participation task

Submit the MATLAB live script that you produced in activity 2.

## OPTIONAL Activity 3 - Pivot tables for summaries

For this exercise, use the same CSV file `mlb_players.csv` as in activity 2. Create Excel pivot tables that can be used to answer the following questions:

1. What is the average height of the players in each position in each team?
2. Which position of which team has the heaviest player? To make it easier to find this information, feel free to use **conditional formatting** so that cells are coloured based on their value.

For each pivot table, describe what fields were used in each of the components of the pivot table: "filter", "column", "row", "value", and what parts of the pivot table have each answer.

# PRAC_02

## Activity 1 - MATLAB's groupsummary

MATLAB's `groupsummary` allows to combine multiple rows of a table into one by grouping all rows that have the same value in a specific column. 

Look at the first examples of the documentation: https://www.mathworks.com/help/matlab/ref/double.groupsummary.html

You will see that all of the first examples use `groupsummary` to group rows based on columns with **categorical** data such as  "Gender" or "Smoker". But they do not show examples that group rows based on **numerical** data such as "Weight" or "Height".

Explain why it is a bad idea to group the rows based on numerical data. Discuss what you can do if you want to group based on numerical data.

## Activity 2 - Pivot Tables in MATLAB

Something similar Excel's pivot tables can be achieved in MATLAB through the correct sequence of `unstack` and, sometimes, with the addition of `groupsummary` before or after applying `unstack`. Suppose you have a table of expenses for home bookkeeping with the following columns:

* `Date`: The date of the bank transaction. There may be several transactions with the same date. When that happens, each transaction will be stored in a row of the table, and all of the transactions happening during the same day will have the same date.
* `Concept`: Some text about the bank transaction
* `Type`: One of "cash", "credit", "savings"
* `Category`: The type of bank transaction from a limited list, such as: "Car", "Groceries", etc.
* `Amount`: The expense amount.

The first rows of the table might look like this:

| Date | Concept | Type | Category | Amount |
| --- | --- | --- | --- | --- |
| 2020/10/12 | Petrol | Credit | Car | 55 |
| 2020/10/12 | Woolworths | Savings | Groceries | 63 |
| 2020/10/12 | ALDI | Cash | Groceries | 15 |
| 2020/10/15 | Opal Card | Credit | Transportation | 20 |

The table is stored in a MATLAB table with name `expenses`.

Write the sequence of MATLAB instructions that would be needed to generate the following tables:

1. Each row shows one date. Each column shows one category. Each cell in the table displays the total expenses on that day for the specified category. For example:

| Date | Car | Transport | Groceries |
| --- | --- | --- | --- |
| 2020/10/12 | 55 | NaN | 78 |
| 2020/10/15 | NaN | 20 | NaN | 

2. Each row shows one month (January, February, etc.) Each column shows one expense type. Each cell displays the total expenses on that month for the expense type. For example:

| Month | Cash | Credit | Savings |
| --- | --- | --- | --- |
| October | 532 | 611 | 800 |
| November | 492 | 312 | 1250 |

## Participation Task

Submit the answer to the two questions of activity 2. 

## OPTIONAL Activity 3 - Filtering Pivot Tables in MATLAB

Excel's pivot tables allows one to filter by row, by column, and even to specify a separate filter by another column. Can you explain how you would be able to replicate the same behaviour in MATLAB? In particular, assuming that you have the same table `expenses` from activity 2, explain how you would achieve the following using MATLAB:

1. Specify only a subset of the categories, for example:

| Month | Cash | Savings |
| --- | --- | --- | 
| October | 532  | 800 |
| November | 492 | 1250 |

2. Specify the expenses of one month only, for example November.

3. Produce a table with the monthly expenses per category ("Car", "Transport" etc) but only for credit card expenses.