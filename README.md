# Module04-Challenge-Pandas
Data Analytics Boot Camp - Module 04 - Data Analysis with Python \
Pandas Challenge

---

# Results

Refer to the Jupyter Notebook, file: *PyCitySchools/PyCitySchools.ipynb*.

# Implementation notes

Local Government Area (LGA) Summary:
- Combined multiple filter conditions (i.e. combined filters on multiple columns at once), to determine the number of students who passed both maths and reading.

School Summary:
- Used .set_index() to help return various per-school statistics as Pandas Series, for example:
```
    # Calculate the total student count per school from school_data
    per_school_counts = school_data.set_index(["school_name"])["size"]
```
- Applied .groupby() and .mean() to calculate 'the average test scores per school'.
- Created separate filtered DataFrames to determine the individual students passing maths, reading, and both maths and reading.
- Applied .groupby() and .count() on those filtered DataFrames, to create a new DataFrame containing subtotals of the students passing maths, reading, and both maths and reading, together with the total number of students, per school.
- Used that DataFrame to calculate the Percentage Pass Rates for Maths, Reading, and Overall.

Top and Bottom performing schools:
- Applied .sort_values() with parameter ascending=False/True for Descending (Top peforming first) and Ascending (Bottom performing first) sorts, respectively.

Maths scores / Reading scores by Year level:
- Applied .groupby() and .mean() to calculate 'mean scores per year level per school', for example:
```
    # Create data series of scores by year levels using conditionals
    year_nine = school_data_complete[(school_data_complete["year"] == 9)]
    ...
    # Maths scores by Year; Group each by school name
    year_nine_scores = year_nine.groupby("school_name")["maths_score"].mean()
    ...
```

Scores by School Spending:
- Conversion from string-based 'currency' values (e.g. "$3.45") to float via a combination of 'str.replace' and '.astype(float)':

# References

The following references were used in the development of the solution for this Challenge.

## Pandas - filter on multiple conditions
- https://saturncloud.io/blog/how-to-use-pandas-to-check-multiple-columns-for-a-condition/

## Pandas - using .groupby()
- https://stackoverflow.com/questions/39922986/how-do-i-pandas-group-by-to-get-sum
- https://pandas.pydata.org/pandas-docs/stable/user_guide/groupby.html#aggregation
- https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.groupby.html (re: set parameter 'observed = False' to avoid warning messages regarding deprecated / default value will change to True in a future version of Pandas)

## Pandas - using .cut()
- https://pandas.pydata.org/docs/reference/api/pandas.cut.html

## Pandas - convert string-based 'currency' values to float
- https://stackoverflow.com/questions/32464280/how-to-convert-currency-column-with-and-to-numbers

## Pandas - rounding values to specified number of decimal places
- https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.round.html

## Python - options for breaking code across multiple lines
- https://note.nkmk.me/en/python-long-string/

## Markdown - showing code blocks
- https://www.markdownguide.org/extended-syntax/#fenced-code-blocks
