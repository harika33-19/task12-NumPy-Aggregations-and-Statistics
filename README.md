# task12-NumPy-Aggregations-and-Statistics
## Task Overview
Use NumPy functions to calculate common statistical measures on a numerical dataset. This task helps build basic numerical analysis skills using Python and NumPy.

## Objectives
- Calculate sum, mean, median, minimum, maximum, standard deviation, and variance.
- Practice using aggregation functions along `axis=0` and `axis=1`.
- Compare statistical results across different columns.
- Write a short interpretation of the results.

## Tools Required
- Python
- NumPy
- Jupyter Notebook or Google Colab

## Dataset
For this example, we use a small student-performance dataset. The values are illustrative and can be replaced with a Student Performance Dataset or Iris Dataset.

```python
import numpy as np

# Rows represent students; columns represent subjects
marks = np.array([
    [85, 78, 92],
    [76, 88, 80],
    [90, 95, 89],
    [68, 72, 75],
    [82, 84, 87]
])

subjects = ["Maths", "Science", "English"]

print("Student marks:")
print(marks)
```

## Step 1: Calculate Aggregation Functions

```python
print("Total of all marks:", np.sum(marks))
print("Mean of all marks:", np.mean(marks))
print("Median of all marks:", np.median(marks))
print("Minimum mark:", np.min(marks))
print("Maximum mark:", np.max(marks))
print("Standard deviation:", np.std(marks))
print("Variance:", np.var(marks))
```

These are seven aggregation/statistical functions: `sum`, `mean`, `median`, `min`, `max`, `std`, and `var`.

## Step 2: Analyze Each Subject (`axis=0`)

`axis=0` calculates a result down each column, so it gives statistics for each subject.

```python
print("Mean by subject:", np.mean(marks, axis=0))
print("Median by subject:", np.median(marks, axis=0))
print("Minimum by subject:", np.min(marks, axis=0))
print("Maximum by subject:", np.max(marks, axis=0))
print("Standard deviation by subject:", np.std(marks, axis=0))
print("Variance by subject:", np.var(marks, axis=0))
```

## Step 3: Analyze Each Student (`axis=1`)

`axis=1` calculates across each row, so it gives statistics for each student's marks.

```python
print("Total marks per student:", np.sum(marks, axis=1))
print("Average marks per student:", np.mean(marks, axis=1))
print("Median marks per student:", np.median(marks, axis=1))
print("Minimum mark per student:", np.min(marks, axis=1))
print("Maximum mark per student:", np.max(marks, axis=1))
```

## Step 4: Compare Subjects

```python
subject_means = np.mean(marks, axis=0)

for subject, average in zip(subjects, subject_means):
    print(f"{subject} average: {average:.2f}")

best_subject_index = np.argmax(subject_means)
print("Highest average subject:", subjects[best_subject_index])
```

## Step 5: Short Interpretation of Results

Using the sample dataset:
- The overall mean is the average of all marks.
- The median is the middle value after sorting the marks.
- The minimum and maximum show the lowest and highest marks.
- Standard deviation describes how spread out the marks are around the mean.
- Variance is the square of the standard deviation.
- Subject averages help compare performance across subjects.
- `axis=0` summarizes each subject (column); `axis=1` summarizes each student (row).

The sample dataset has subject averages of 80.2 in Maths, 83.4 in Science, and 84.6 in English. English has the highest average in this example.

## Conclusion
This task demonstrates how NumPy makes statistical analysis concise and efficient. The results can help identify overall performance, compare subjects, and understand variation in student marks.

## How to Run
1. Open Google Colab or Jupyter Notebook.
2. Create a new notebook.
3. Copy the code sections into separate cells, in order.
4. Run each cell from top to bottom.
5. Review the output and write your interpretation.

## Repository Suggestion
`numpy-aggregations-statistics`
