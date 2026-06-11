# Exam Mark Merger

A web-based utility to automatically merge assessment marks from multiple sources into a final mark template.

## Website

https://arunpradeep-sec.github.io/mark-merger/

---

## Features

* Merge Part A and Part B&C marks into a single output file.
* Automatic student matching using Register Number.
* Supports bulk processing of entire class records.
* Preserves the uploaded output template structure.
* Runs completely in the browser.
* No installation required.

---

## Input Files Required

### 1. PART A File

Requirements:

* CSV format.
* Contains student ID numbers.
* Contains Question 1 to Question 5 marks.

Mapping:

| Question | Output Column |
| -------- | ------------- |
| Q1       | G             |
| Q2       | H             |
| Q3       | I             |
| Q4       | J             |
| Q5       | K             |

All imported marks are multiplied by 2 before being entered into the output file.

---

### 2. PART B&C File

Requirements:

* Excel format (.xlsx/.xls).
* Student data starts from Row 7.
* Register Number / Student ID must be in Column D.

Mapping:

| Input Column | Question | Output Column |
| ------------ | -------- | ------------- |
| F            | Q6       | L             |
| I            | Q7       | N             |
| L            | Q8       | P             |

All imported marks are multiplied by 2 before being entered into the output file.

---

### 3. Output Template

Requirements:

* Excel format (.xlsx/.xls).
* Register Number should be present in Column A.
* Student records start from Row 5.

---

## Matching Criteria

Student records are matched using:

PART A → ID Number

=

PART B&C → Student ID (Column D)

=

Output Template → Register Number (Column A)

---

## Total Calculation

After populating the marks:

Column F is automatically calculated as:

F = SUM(G:Q)

for every student record.

The calculation starts from Row 5 and continues until the last valid Register Number.

---

## Output

The application generates:

Final_Merged_Output.xlsx

containing:

* Part A marks
* Part B&C marks
* Automatically calculated total
* Original template structure

---

## Disclaimer

This application is intended for educational and academic use only.

While every effort has been made to ensure the accuracy of the generated outputs, users are responsible for verifying all results before use.

Errors and Omissions Excepted (E&OE).
