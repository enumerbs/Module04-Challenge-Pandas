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

# References

The following references were used in the development of the solution for this Challenge.

## Pandas - filter on multiple conditions
- https://saturncloud.io/blog/how-to-use-pandas-to-check-multiple-columns-for-a-condition/

## Pandas - using .groupby()
- https://stackoverflow.com/questions/39922986/how-do-i-pandas-group-by-to-get-sum
- https://pandas.pydata.org/pandas-docs/stable/user_guide/groupby.html#aggregation
