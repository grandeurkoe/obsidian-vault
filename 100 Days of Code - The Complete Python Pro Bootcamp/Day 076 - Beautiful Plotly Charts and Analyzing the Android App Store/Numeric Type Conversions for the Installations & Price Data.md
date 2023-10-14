# Numeric Type Conversions for the Installations & Price Data

#### Challenge

How many apps had over 1 billion (that's right - BILLION) installations? How many apps just had a single install?

1. Check the datatype of the Installs column.
2. Count the number of apps at each level of installations.
3. Convert the number of installations (the Installs column) to a numeric data type. Hint: this is a 2-step process. You'll have to make sure you remove non-numeric characters first.

## Data Cleaning & Converting Data to Numeric Types

To check the data types you can either use `.describe()` on the column or `.info()` on the DataFrame.

![[2020-10-11_12-24-39-fb2db75e5e71a3e89c859e35ad516032.png|500]]