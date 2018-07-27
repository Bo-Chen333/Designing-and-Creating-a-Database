Designing-and-Creating-a-Database
===========================================================

Getting to Know the Data(Step 1)
-----------------------------------------------------------
1. Using pandas, read in each of the four CSV files: `game_log.csv`, `park_codes.csv`, `person_codes.csv`, `team_codes.csv`. For each:<br>
* Use methods and attributes like `DataFrame.shape`, `DataFrame.head()`, and `DataFrame.tail()` to explore the data.<br>
* Write a brief paragraph to describe each file, including for the helper files how the data intersects with the main log file.<br>
2. Research any fields you are not familiar with, using both the text file and Google as needed. In particular, you should explore and write a short paragraph on:<br>
* What each defensive position number represents.
* The values in the various league fields, and which leagues they represent.

Importing Data into SQLite(Step 2)
------------------------------------------------------------
1. Recreate the `run_command()` and `run_query()` functions from the previous guided project, which you can use<br>
2. Use `DataFrame.to_sql()` to create tables for each of our dataframes in a new SQLite database, `mlb.db`:
* The table name should be the same as each of the CSV filename without the extension, eg `game_log.csv` should be imported to a table called game_log.
3. Using `run_command()`, create a new column in the `game_log` table called `game_id`:
* Use SQL string concatenation to update the new columns with a unique ID using the Retrosheet format outlined above.

Looking for Normalization Opportunities(Step 3)
------------------------------------------------------------
1. Looking at the various files, look for opportunities to normalize the data and record your observations in a markdown cell.

Planning a Normalized Schema(Step 4)
-------------------------------------------------------------
1. Using whichever design tool you feel most comfortable with, plan a schema for our baseball database.
2. When you are happy with your schema, insert a screenshot or photo into a markdown cell.

Creating Tables Without Foreign Key Relations(Step 5)
-------------------------------------------------------------
1. Create the `person` table with columns and primary key as shown in the schema diagram.
* Select the appropriate type based on the data.
* Insert the data from the `person_codes` table.
* Write a query to display the first few rows of the table.
2. Create the `park` table with columns and primary key as shown in the schema diagram.
* Select the appropriate type based on the data
* Insert the data from the `park_codes` table.
* Write a query to display the first few rows of the table.
3. Create the `league` table with columns and primary key as shown in the schema diagram.
* Select the appropriate type based on the data.
* Insert the data manually based on your research on the names of the six league IDs.
* Write a query to display the table.
4. Create the `appearance_type` table with columns and primary key as shown in the schema diagram.
* Select the appropriate type based on the data.
* Import and insert the data from `appearance_type.csv`.
* Write a query to display the table.

Adding The Team and Game Tables(Step 6)
--------------------------------------------------------------
1. Create the `team` table with columns, primary key, and foreign key as shown in the schema diagram.
* Select the appropriate type based on the data.
* Insert the data from the `team_codes` table.
* Write a query to display the first few rows of the table.
2. Create the `game` table with columns, primary key, and foreign key as shown in the schema diagram.
* Select the appropriate type based on the data.
* Insert the data from the `game_log` table.
* Write a query to display the first few rows of the table.

Adding the Team Appearance Table(Step 7)
---------------------------------------------------------------
1. Create the `team_appearance` table with columns, primary key, and foreign keys as shown in the schema diagram.
* Select the appropriate type based on the data.
* Insert the data from the `game_log` table, using a `UNION` clause to combine the data from the column sets for the home and away teams.

Adding the Person Appearance Table(Step 8)
---------------------------------------------------------------
1. Create the `person_appearance` table with columns, primary key, and foreign keys as shown in the schema diagram.
* Select the appropriate type based on the data.
* Insert the data from the `game_log` table, using `UNION` clauses to combine the data from the columns for managers, umpires, pitchers, and awards.
* Use a loop with string formatting to insert the data for offensive and defensive positions from the `game_log` table.
Write a query to verify that your data was inserted correctly.
* Write a query to verify that your data was inserted correctly.

Removing the Original Tables(Step 9)
-----------------------------------------------------------------
1. Drop the tables we created to hold our unnormalized data:
* `game_log`.
* `park_codes`.
* `team_codes`.
* `person_codes`.
