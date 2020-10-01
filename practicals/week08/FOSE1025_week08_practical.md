# Week 8 SGTA (Internal offering)
# PRAC_01

## Activity 1 - Parse addresses (10 minutes + 10 minutes discussion)
The following CSV file contains personal information from fictitious people:

* [sample_addresses.csv](sample_addresses.csv)

Conduct the following activities:

1. Create the columns **Street**, **City**, **Postcode**, **State**
2. Use the "text to columns" feature to parse the address column into the different components. For example, the address `171 E 24th St, Leith, 7315 TAS` would fill the following data:

    - **Street**: `171 E 24th St`
    - **City**: `Leith`
    - **Postcode**: `7315`
    - **State**: `TAS`

*Hint: In order to fill the columns, you will need to use "text to columns" twice. The first time, use the comma "," as a separator. The second time, use the blank space " " as a separator.*


## Activity 2 - From Excel Dates to Text (10 minutes + 5 minutes discussion)

The following CSV file contains weather data from the US (FYI, the original file is from https://figshare.com/articles/weather_data_csv/5012747).

* [weather_data.csv](weather_data.csv)

1. Import the CSV file into an Excel spreadsheet.
2. Create the columns `Day`, `Month`, `Year`.
3. Use EXCEL formulas (`DAY`, `MONTH`, `YEAR`) to populate the columns.
4. Use the EXCEL formula (`TEXT`) to generate dates in US format using the `Day`, `Month`, and `Year` columns. In the US format, the month is written before the day. For example, if the date is `23/11/2014`, in US format it will be `11/23/2014`.

You can find documentation about the TEXT function here:
* https://support.office.com/en-us/article/combine-text-with-a-date-or-time-cef6a66c-8176-470c-ba85-4b030405dfbf
* https://support.office.com/en-us/article/text-function-20d5ac4d-7b94-49fd-bb38-93d29371225c

## Participation task

Submit an excel file with your solution to activity 2 to the week 8 practical 1 participation task submission box.

## Activity 3 - Excel: Is this a date or a string? (5 minutes + 5 minutes discussion)

A problem that you may encounter with Excel is that what looks a date is actually a string. Can you tell which is which in the following spreadsheet?

* [date_or_string.xlsx](date_or_string.xlsx)

To determine whether a cell contains a date or a string, conduct the following tests:

1. Click on the cell and observe what format it is in. If the cell is in date or text format, you know the answer.
2. Change the cell format to string. If the contents changes to a number, then you had a date.
3. Try to use a function that requires a date. For example, apply the function `DAY` to the cell. If the output looks like the day of the date, then it was a date.


## OPTIONAL Activity 4 - Filtering Data in MATLAB (10 minutes + 10 minutes discussion)

This activity is optional for those who have completed the previous activities.

Use the same file as in activity 2.

* [weather_data.csv](weather_data.csv)

Conduct the following tasks using MATLAB.

1. Read the CSV data file in MATLAB.
2. Find all records that measure **precipitation** in any location and save them in a variable named `precipitation_all`.
3. Find all records that measure **precipitation** in **Brookings** and save them in a variable named `precipitation_brookings`.
4. Now, find all records that measure the **maximum** and **minimum temperatures** in **Brookings** and save them in a variable named `temperatures_brookings`.

# PRAC_02

## Activity 1 - Concatenating text in Excel (10 minutes + 10 minutes discussion)

Consider the reverse problem to activity 2 in practical 1: you have an Excel table with the following columns: **Street**, **City**, **Postcode**, **State**. You want to add a new column **Address** that contains the full address using the format `Street, City, State Postcode`. Note that sometimes we use a comma, and sometimes we use a blank space to separate the different parts of the address.

For example, if a row has the following data in each column:

- **Street**: `171 E 24th St`
- **City**: `Leith`
- **Postcode**: `7315`
- **State**: `TAS`

The cell in the new column **Address** must have this contents: `171 E 24th St, Leith, TAS 7315`

Write the instructions of how you could use Excel to achieve this. Make sure that the "Address" column has the commas and blank space as shown in the example above.

## Activity 2 - Access Data in Tables (15 minutes + 10 minutes discussion)

MATLAB uses three different notations to access data from tables. Review the information here: https://au.mathworks.com/help/matlab/matlab_prog/access-data-in-a-table.html

Suppose that you have used `readtable` to read the CSV file `weather_data.csv` that you used in practical 1. This reads the CSV file and stores the result as a table. Answer now the following questions:

1. How would you find a **table** that contains all the rows of the original table but only the columns `param` and `siteid`?
2. What if now you want to obtain a **matrix** with the same information? What would you do?
3. Can you explain what is the difference between a **table** and a **matrix**?

## Participation task

Submit your solution to activity 2 to the week 8 practical 2 participation task submission box. Question 1 should be easy. Question 2 requires knowledge not covered in the lectures but it is explained in the link from Activity 2.


## OPTIONAL Activity 3 - Treating Missing Data (10 minutes + 10 minutes discussion)

This activity is optional for those who have completed the previous activities.

The lecture notes of week 7 describe how one can use MATLAB to handle rows with missing data. Write the instructions that one can follow to detect rows containing missing data and remove these rows.
