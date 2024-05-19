# Pandas Challenge: PyCitySchools

<img src="https://media.licdn.com/dms/image/D5612AQFbpgGAr5mqqw/article-cover_image-shrink_600_2000/0/1704477591953?e=2147483647&v=beta&t=PjRe1TshkF9dGu9aoNgnga6ivZmWouJRBXWokuBAB_4" alt="Crowdfunding Project Analysis" style="width: 100%; height: auto;">

***
## Background
As the new Chief Data Scientist for the city's school district, you are tasked with analyzing district-wide standardized test results. The goal is to aggregate the data and showcase trends in school performance to help the school board and mayor make informed decisions regarding future school budgets and priorities.

***

## Instructions
Using Pandas and Jupyter Notebook, a report is created to include the following data:

### District Summary
Perform calculations to create a high-level snapshot of the district's key metrics:
- Total number of unique schools
- Total students
- Total budget
- Average math score
- Average reading score
- % passing math (the percentage of students who passed math)
- % passing reading (the percentage of students who passed reading)
- % overall passing (the percentage of students who passed both math and reading)

### School Summary
Calculate key metrics about each school:
- School name
- School type
- Total students
- Total school budget
- Per student budget
- Average math score
- Average reading score
- % passing math
- % passing reading
- % overall passing

### Highest-Performing Schools
Sort the schools by % overall passing in descending order and display the top 5 rows.

### Lowest-Performing Schools
Sort the schools by % overall passing in ascending order and display the top 5 rows.

### Math Scores by Grade
List the average math score for students of each grade level (9th, 10th, 11th, 12th) at each school.

### Reading Scores by Grade
List the average reading score for students of each grade level (9th, 10th, 11th, 12th) at each school.

### Scores by School Spending

``` python

spending_bins = [0, 585, 630, 645, 680]
labels = ["<$585", "$585-630", "$630-645", "$645-680"]
```
*Use pd.cut to categorize spending based on the bins.*

*Use the following code to then calculate mean scores per spending range.*

```python

spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Math Score"].mean()
spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Math"].mean()
spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()
overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()

```

Break down school performance based on average spending ranges (per student):
- Average math score
- Average reading score
- % passing math
- % passing reading
- % overall passing

### Scores by School Size

```python

size_bins = [0, 1000, 2000, 5000]
labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]
```

Break down school performance based on school size:
- Average math score
- Average reading score
- % passing math
- % passing reading
- % overall passing

### Scores by School Type
Show school performance based on the school type:
- Average math score
- Average reading score
- % passing math
- % passing reading
- % overall passing

***

## Results
### District Summary
- **Total Schools:** 15
- **Total Students:** 39,170
- **Total Budget:** $24,649,428.00
- **Average Math Score:** 79.0
- **Average Reading Score:** 81.9
- **% Passing Math:** 74.98%
- **% Passing Reading:** 85.81%
- **% Overall Passing:** 65.17%

### School Summary
(Example for one school)
- **School Name:** Huang High School
- **School Type:** District
- **Total Students:** 2917
- **Total School Budget:** $1,910,000.00
- **Per Student Budget:** $655.0
- **Average Math Score:** 76.6
- **Average Reading Score:** 81.2
- **% Passing Math:** 65.7%
- **% Passing Reading:** 81.3%
- **% Overall Passing:** 53.5%

### Highest-Performing Schools
Top 5 schools by % Overall Passing:
1. Cabrera High School
2. Thomas High School
3. Griffin High School
4. Wilson High School
5. Pena High School

### Lowest-Performing Schools
Bottom 5 schools by % Overall Passing:
1. Rodriguez High School
2. Figueroa High School
3. Huang High School
4. Hernandez High School
5. Johnson High School

### Math Scores by Grade
A DataFrame listing average math scores by grade level for each school.

### Reading Scores by Grade
A DataFrame listing average reading scores by grade level for each school.

### Scores by School Spending
A DataFrame showing average scores and passing percentages based on school spending per student.

### Scores by School Size
A DataFrame showing average scores and passing percentages based on school size.

### Scores by School Type
A DataFrame showing average scores and passing percentages based on school type.

***

## Observable Trends
1. **School Type and Performance:**
   - Charter schools generally outperform district schools in terms of both math and reading scores.
   - Charter schools also show higher percentages of students passing math and reading compared to district schools.

2. **Impact of Budget:**
   - Schools with higher per-student spending do not necessarily achieve higher average scores or higher passing percentages.
   - Moderate spending seems to correlate with better performance, indicating that beyond a certain threshold, increased spending does not yield proportional academic improvements.

*** 

## Usage
To run the analysis, open the `PyCitySchools.ipynb` notebook in Jupyter and execute the cells sequentially. Ensure the dataset (`schools_complete.csv`) is present in the `Resources` folder.

***

## Requirements
- Python 3.x
- Pandas library
- Jupyter Notebook

***

## Acknowledgments
This project is part of a data analytics bootcamp and uses data generated by edX Boot Camps LLC for educational purposes.
