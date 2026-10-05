## Video 0: spreadsheets and flat file database

Databases are used to store and organize data.

The way people store data has developed over time, from writing information on physical materials to using digital tools and modern database systems.

---

## Evolution of Data Storage

In the past, information was stored physically, such as on:

- Walls
- Paper
- Other written records

Today, data is mainly stored digitally.

As the amount of information increased, better ways of organizing and managing data became necessary.

---

## Spreadsheets

Spreadsheets such as Google Sheets organize data using:

- Rows
- Columns

Each row usually represents a record, while columns represent different pieces of information about that record.

Spreadsheets are useful for organizing data, but they become less practical when working with very large amounts of data.

---

## Flat File Databases

A simple way to store data digitally is by using a flat file.

One common example is a CSV file.

CSV stands for:

```text
Comma-Separated Values
```

A CSV file stores data in rows, with values separated by commas.

Example:

```csv
name,house
Harry,Gryffindor
Draco,Slytherin
```

CSV files provide a simple way to store structured data that can also be processed using programs.

---

# Working with CSV Files in Python

Python provides the `csv` library for working with CSV files.

```python
import csv
```

---

## csv.reader

`csv.reader` reads each row from a CSV file as a list.

Example:

```python
import csv

with open("students.csv") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

Each row is accessed using its position inside the list.

---

## csv.DictReader

Instead of treating each row as a list, `DictReader` treats each row as a dictionary.

```python
import csv

with open("students.csv") as file:
    reader = csv.DictReader(file)

    for row in reader:
        print(row)
```

The column names become keys, which makes it easier to access specific values.

For example:

```python
row["name"]
```

instead of accessing the value using its numerical position.

---

## Video 1: Data Analysis in Python

## Counting Data

The lesson uses a CSV file containing CS50 students' favorite programming languages.

The file is opened using `csv.DictReader()`:

```python
import csv

with open("favorites.csv", "r") as file:
    reader = csv.DictReader(file)
```

A dictionary called `counts` is used to count how many times each language appears:

```python
counts = {}

for row in reader:
    favorite = row["language"]

    if favorite in counts:
        counts[favorite] += 1
    else:
        counts[favorite] = 1
```

The language is stored as the key, and its count is stored as the value.

## Cleaning the Data

Before analyzing data, it may need to be cleaned so that similar values are not treated as different values because of formatting.

For example, values can be standardized before counting them.

This helps make the results more accurate.

## Sorting the Results

Python's `sorted()` function can be used to sort the values:

```python
for favorite in sorted(counts):
    print(f"{favorite}: {counts[favorite]}")
```

This sorts the dictionary by its keys.

To sort according to the count instead, a function can be provided using `key`:

```python
def get_value(language):
    return counts[language]
```

Then:

```python
for favorite in sorted(counts, key=get_value, reverse=True):
    print(f"{favorite}: {counts[favorite]}")
```

`reverse=True` sorts the results from the largest count to the smallest.

## Lambda Function

Instead of creating a separate function such as:

```python
def get_value(language):
    return counts[language]
```

Python allows us to use a `lambda` function:

```python
for favorite in sorted(
    counts,
    key=lambda language: counts[language],
    reverse=True
):
    print(f"{favorite}: {counts[favorite]}")
```

A `lambda` is an anonymous function that can be written directly where it is needed.

## Searching the Data

The program can also ask the user which value they want to search for:

```python
favorite = input("Favorite: ")
```

Then it checks whether that value exists in `counts`:

```python
if favorite in counts:
    print(f"{favorite}: {counts[favorite]}")
```

This allows the user to search for a specific language and see how many times it appears in the data.

## Video 2: Relational Database

## Flat File vs Relational Database

A **flat file** stores data in a single file, such as a CSV file.

A **relational database** stores data in tables that can be related to each other.

Instead of keeping all information together in one file, the data can be divided into multiple related tables.

## Online Store Example

The lesson uses an online store as an example.

An online store may contain different types of data, such as:

- Customers
- Products
- Orders

Instead of putting all of this information in one file, a relational database can organize it into separate tables.

## RDBMS

**RDBMS** stands for:

```text
Relational Database Management System
```

It is the system used to manage relational databases.

## SQL

**SQL** stands for:

```text
Structured Query Language
```

SQL is the language used to communicate with relational databases.

It allows us to perform operations on the data stored inside the database.

## SQLite

SQLite is a relational database management system.

It allows us to create and work with SQL databases.

## SQLite3

`sqlite3` can be used from the terminal to work with SQLite databases.

Example:

```bash
sqlite3 store.db
```

This opens or creates a database called:

```text
store.db
```

## Creating a Database

A database can be created using SQLite3:

```bash
sqlite3 store.db
```

After entering SQLite, SQL commands can be used to work with the database.

## CRUD

CRUD represents four basic database operations:

```text
Create
Read
Update
Delete
```

These operations are used to create, retrieve, modify, and delete data.

## Creating a Table

A table can be created using the SQL command:

```sql
CREATE TABLE
```

Example:

```sql
CREATE TABLE products (
    id INTEGER,
    name TEXT,
    price NUMERIC
);
```

The table contains columns such as:

```text
id
name
price
```

Each column can have a specific data type.


## Video 3: SQLite Dot Commands

SQLite provides special commands that start with a dot `.`.

These commands are used inside the SQLite terminal.

## `.mode csv`

Before importing a CSV file, the mode can be changed to CSV:

```sql
.mode csv
```

This tells SQLite that the data being used is in CSV format.

## `.import`

The `.import` command is used to import data from a CSV file into a table.

```sql
.import FILE TABLE
```

Example:

```sql
.import favorites.csv favorites
```

Here:

- `favorites.csv` is the CSV file.
- `favorites` is the table name.

The data from the CSV file is imported into the SQLite database.

## `.schema`

The `.schema` command shows the structure of the database table:

```sql
.schema
```

It can be used to see the table and its columns after importing the data.

## Example

```sql
sqlite3 favorites.db
.mode csv
.import favorites.csv favorites
.schema
```

This:

1. Opens or creates `favorites.db`.
2. Sets the mode to CSV.
3. Imports the CSV file into a table called `favorites`.
4. Shows the structure of the table.

## Video 4: CRUD: Read Data

## CRUD

CRUD stands for:

```text
Create
Read
Update
Delete
```

In this lesson, the focus is on:

```text
Read
```

Reading data from a database is done using `SELECT`.

## `SELECT`

The basic syntax is:

```sql
SELECT column
FROM table;
```

For example:

```sql
SELECT language
FROM favorites;
```

This returns the values stored in the `language` column from the `favorites` table.

## Selecting More Than One Column

More than one column can be selected:

```sql
SELECT language, problem
FROM favorites;
```

## Selecting All Columns

The `*` symbol can be used to select all columns:

```sql
SELECT *
FROM favorites;
```

## SQL Functions

SQL provides functions that can be used while reading data.

### `COUNT`

`COUNT` counts the number of rows:

```sql
SELECT COUNT(*)
FROM favorites;
```

### `DISTINCT`

`DISTINCT` returns unique values without duplicates:

```sql
SELECT DISTINCT language
FROM favorites;
```

It can also be used with `COUNT`:

```sql
SELECT COUNT(DISTINCT language)
FROM favorites;
```

## Other Functions

Other SQL functions mentioned include:

```text
AVG
MAX
MIN
LOWER
UPPER
```

They can be used when reading and working with data in a database.

## Video 5: Filtering Data in SQL

## `WHERE`

`WHERE` is used to filter rows based on a condition.

Example:

```sql
SELECT *
FROM favorites
WHERE language = 'Python';
```

This returns only the rows where the language is Python.

## Combining Conditions

Conditions can be combined using operators such as:

```sql
AND
OR
```

Example:

```sql
SELECT *
FROM favorites
WHERE language = 'Python'
AND problem = 'Mario';
```

## `ORDER BY`

`ORDER BY` is used to sort the results.

```sql
SELECT *
FROM favorites
ORDER BY language;
```

The results can also be sorted in descending order:

```sql
SELECT *
FROM favorites
ORDER BY language DESC;
```

## `GROUP BY`

`GROUP BY` groups rows that have the same value.

For example:

```sql
SELECT language, COUNT(*)
FROM favorites
GROUP BY language;
```

This groups the rows by language and counts how many times each language appears.

## Combining `GROUP BY` and `ORDER BY`

The grouped results can also be sorted:

```sql
SELECT language, COUNT(*)
FROM favorites
GROUP BY language
ORDER BY COUNT(*) DESC;
```

This displays the languages starting with the one that appears the most.

## `LIMIT`

`LIMIT` controls how many rows are returned.

```sql
SELECT language, COUNT(*)
FROM favorites
GROUP BY language
ORDER BY COUNT(*) DESC
LIMIT 1;
```

This returns only the first result.

## Combining SQL Clauses

Several SQL clauses can be used together:

```sql
SELECT language, COUNT(*)
FROM favorites
WHERE language IS NOT NULL
GROUP BY language
ORDER BY COUNT(*) DESC
LIMIT 3;
```

