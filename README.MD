# ESEP Grade Calculator

This library is a simple utility to calculate your grades. 

### go.mod

Lists the requirements of the project and the module path

### grade_calculator.go

Defines the functions and types for the Grade Calculator (see below for more detail)

### grade_calculator_test.go

Tests grade_calculator.go

## How to Run

Runtime requirements:
Golang 1.24+

Run unit tests:
```
cd grade_calculator/
go test ./...
```

Run unit tests with code coverage:
```
cd grade_calculator/
go test -coverprofile=coverage.txt ./...
```

## GradeCalculator

The GradeCalculator stores lists of grades for three categories: assignments, exams, and essays.

### GradeType

Can be one of {Assignment (default), Exam, Essay}

### Grade

Stores a Name (string), Grade (integer), and Type (GradeType) for each Grade. 

### computeAverage ()

Accepts a non-empty array of Grades and returns the average of the scores in the list.

### calculateNumericalGrade Function

Calls the **computeAverage** function for each array of Grades (assigmnents, exams, and essays) and returns a weighted combination of the computed averages. This is equal to

0.5(assignment average) + 0.35(exam average) + 0.15(essay average)

### GetFinalGrade Function

Calls the **calculateNumericalGrade** function and returns a letter grade based on the range which the output falls into.

### AddGrade Function

Appends a Grade (Name, Numerical Grade, Type of Grade) to the array within the GradeCalculator corresponding to the Type of Grade.