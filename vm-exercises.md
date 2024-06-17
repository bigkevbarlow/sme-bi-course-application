a# Virtual Machine (VM) Exercises

## :information_source: Read this before getting started
- The two exercises should not replicate the exact actions shown in your screencast. The goal of exercises is for learners to apply what was learned in the screencasts to new problems or situations. This is best pedagogical practice for retaining and building skills. For example, this can be done by using another dataset between screencasts and exercises or focusing on a different portion of the dataset.
- Power BI / Tableau specific: We can only run free versions of BI software in our virtual machine exercises. In the case of Power BI, make sure the exercises can run on [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) without any additional paid products. 
- Unsure what the scope of an exercise should be? Here's an [example](https://campus.datacamp.com/courses/introduction-to-power-bi/getting-started-with-power-bi?ex=14) from Introduction to Power BI. The first chapter of most DataCamp courses are free, so take a look at our [BI courses](https://learn.datacamp.com/courses?technologies=Tableau&technologies=Power%20BI) to get a feel for how we assess and guide learners.

## 1st VM Exercise

#### Dataset

- [X] Add datasets used to the `datasets/` folder

#### Files

- Not relevant for Databricks (code is stored in the Databricks UI)

#### Learning Objective

Learner will know how to `INSERT` new rows of data into an existing table in Unity Catalog using SQL.

#### Context

You are an insurance adjustor for Brickie Insurance. Part of your job is to ensure that the quality of your insurance claim data is reliable. You have just received a new set of claims from your different customers, and you must upload them to the centralized `claims` table for reference. You decide to use Databricks SQL to accomplish this task.

#### Steps to be executed by the student (max 6)

- If not already, login to the Databricks environment using the credentials at the start of this exercise.
- Click on the `SQL Editor` section of the Databricks environment. On the left of your screen, locate the `claims` table under the `<catalog_name>` catalog and `<schema_name>` schema.
- Find the total number of rows in the dataset, doing a simple count aggregation on the table. This will be your current state of the table.
- You have identified a few new claims to insert into the database. Using the `[INSERT](https://docs.databricks.com/en/sql/language-manual/sql-ref-syntax-dml-insert-into.html)` command, add this data to your table.
- Find the total number of rows within the table again.

#### Exercise question:
After inserting the new claims information, how many rows of data are there in the `claims` table now?

#### End goal:

User will have inserted x rows of new data and increased the table size by x. The end visualization will be a simple count.

## 2nd VM Exercise

#### Dataset

- [X] Add datasets used to the `datasets/` folder

#### Files

-  Not relevant for Databricks (code is stored in the Databricks UI)

#### Learning Objective

Learner will learn how to use the `MERGE` command and understand the differences between that and `INSERT`.

#### Context

As a claims adjustor, you do not only receive new claim information. Sometimes, you receive updates to existing claims in the same batch of information as new claims. You know that Databricks SQL allows you to update your table with one command, and choose to use the `MERGE` function to accomplish your task.

#### Steps to be executed by the student (max 6)

- If not already, login to the Databricks environment using the credentials at the start of this exercise.
- Click on the `SQL Editor` section of the Databricks environment. On the left of your screen, locate the `claims` table under the `<catalog_name>` catalog and `<schema_name>` schema.
- Based on your previous data load, you know that you have uploaded some new rows of data. Find the current total number of rows that you have in the table. This will be your baseline number.
- Below is a table with the latest batch of claims updates. This table has both new rows of data, as well as updates to existing claims in the table. Use the `MERGE` command to make sure this new data is populated into the table. Use the `TRANSACTION_ID` and `CUSTOMER_ID` fields are your merge keys.
- To ensure that your transaction processed, find another total count on your `claims` table.

#### Exercise question:
Based on the new total row count for your `claims` table, what would best describe the behavior of this data transaction?

#### End goal:

Student would be able to identify the behavior of a `MERGE` command. Something like this:

> The `MERGE` command inserted new rows of data and updated existing rows of data from my new dataset into the existing `claims` table.
