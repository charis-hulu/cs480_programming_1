# Programming Assignment 1: SQL

## Deadline: *XX*-th October, midnight (CST).

### Assignment guideline
- This folder contains **3 SQL** files
- Your task is to complete the SQL queries in each file. Look for patterns like `-- Task X.Y`, for example:
```shell
-- Task 1.1
-- Task 1.2
...
```
You have to implement *15 SQL queries** across the 3 SQL files.
- Each query is worth *XX* points, totaling *YY* points. 
- **DO NOT MODIFY ANY DATA, DATABASE NAME OR TABLE STRUCTURES**
- **COLUMN NAMES SHOULD EXACTLY MATCH THE `Output columns` MENTIONED IN EACH QUERY**
- (Optional) You can import each SQL file to your local MySQL server:
```shell
mysql -u root -p < task1.sql
mysql -u root -p < task2.sql
mysql -u root -p < task3.sql
```

## Gradescope submission instructions
- Submit the SQL files on Gradescope.
- There are 15 test cases. For each test case, you will see `test_case_task_<TASK_NUMBER>_<PROBLEM_NUMBER> (test_SQL_Queries.TestFunctions) (XX/XX)` if it passes the testcase.   
- If you have Gradescope access issue, send a message with your First name, Last name, and UIC email address. We will add you manually.

For any questions, feel free to reach out.

## Task 1

#### Task 1.1 – Create Tables
Create two tables: **`projects`** and **`researchers`**.

- **`projects`** table should include:
  - `project_id` (Primary Key, Auto Increment)
  - `project_title`
  - `department`

- **`researchers`** table should include:
  - `researcher_id` (Primary Key, Auto Increment)
  - `name`
  - `position`
  - `project_id` (Foreign Key referencing `projects.project_id`)
    - Use **`ON DELETE SET NULL`**
    - Use **`ON UPDATE CASCADE`**

---

#### Task 1.2: Insert Data
Insert the following data into the tables:

**`projects` table:**

| project_id | project_title  | department   |
|------------|----------------|-------------|
| 1          | Brain Scan     | Neuroscience|
| 2          | Cryptography   | CS          |
| 3          | AI Project     | AI Lab      |
| 4          | Bio Signal     | Biomedical  |

**`researchers` table:**

| researcher_id | name  | position   | project_id |
|---------------|-------|-----------|------------|
| 1             | Alice | PhD       | 1          |
| 2             | Ben   | Postdoc   | 1          |
| 3             | Cara  | Assistant | 2          |
| 4             | David | PhD       | 3          |
| 5             | Eva   | Postdoc   | 3          |
| 6             | Frank | Assistant | 4          |


#### Task 1.3: Update Operations

Perform the following updates in the database:

- Change the `department` of project `Bio Signal` from `Biomedical` to `Bio Eng` in the `projects` table.
   
- Change the `position` of researcher `Cara` from `Assistant` to `Senior Assistant` in the `researchers` table.


#### Task 1.4: Delete Operations
- Remove researcher `Alice` (`researcher_id = 1`) from the `researchers` table.

- Remove project `Cryptography` (`project_id = 2`) from the `projects` table.

#### Task 1.5: Show all projects from the `AI Lab` department

- Output columns: `project_id`, `project_title`, `department`.

#### Task 1.6: Show all researchers who are `Postdoc`

- Output columns: `researcher_id`, `name` `position`, `project_id`.

#### Task 1.7: Display each researcher’s `name` along with the `project_title` they are working on.

- Output columns: `researcher_name`, `project_title`.

## Task 2


#### Task 2.1. Show the total number of citations for each venue.

Output columns: `venue_name`, `total_citations`.


#### Task 2.2. Show the average citations for each author.

Output columns: `venue_name`, `total_citations`.


#### Task 2.3. Show the sum of citations for all conference publications.
Output columns: `conference_citations`.

#### Task 2.4. Show the average citations for each venue type (Journal vs Conference).
Output columns : `type`, `avg_citations`.


#### Task 2.5. Show all authors whose total citations are greater than 150.
Output columns: `author`, `total_citations`.


## Task 3

#### Task 3.1. Find all subordinates of Bo.

- Write a recursive query to find all employees who report to Bob.
- Include both direct and indirect reports.
- Output columns: `emp_id`, `name`, `manager_id`, `position`.


#### Task 3.2 Find the chain of managers above Grace
- Write a recursive query to list all managers above Grace, up to the CEO.
- Output columns: `emp_id`, `name`, `manager_id`, `position`.

#### Task 3.3 Assign levels relative to CEO
- Write a recursive query to assign a level number to all employees relative to the CEO.
- CEO should have `level = 0`.
- Direct reports of CEO `level = 1`, and so on.
- Output columns: `emp_id`, `name`, `manager_id`, `position`, `level`.
