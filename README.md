# Rearc Cybersecurity Detection Quest

## Q. What is this quest?
The cybersecurity quest is a fun way to assess your hands-on engineering skills. It is also a good representation of the type of work associated with this role.

## Q. What skills are needed?
* Security Data Engineering
* Detection Engineering Concepts
* Programming Language (Python and/or SQL)
* Development (Working with Jupyter Notebooks, Git, and virtual environments)

## Q. Challenge Steps
This quest consists of 3 parts. Putting all 3 of these parts together will mimic our detection development and engineering workflow. If you get stuck see the [FAQ section](#faq).

- Part 1 will showcase your skills with basic data engineering using PySpark.
- Part 2 will showcase your analytic skills by applying the threat hypothesis below to an actionable analytic query using SQL (preferably).
- Part 3 will showcase your knowledge of additional subjects such as data normalization frameworks, alert packaging, and threat intel enrichment.


### Hypothesis

 - A threat actor can leverage Microsoft Office applications against users on Windows endpoints through phishing to make potentially malicious web calls. 
 - Windows Endpoints forwarding DNS activity via sysmon logs to a data orchestration platform like Cribl would be utilized to identify this activity.

### Part 1: Load the Sample Dataset

1. Using a Jupyter notebook load the JSON line file from the data/ directory into a Spark dataframe.
2. Create a new dataframe that parses out any necessary fields from the `_raw` column to be used in part 2.

### Part 2: Detection Engineering

1. Preferably using either PySpark or SQL create a query or queries that will prove the detection hypothesis.
2. Output the result in the notebook
    - Select columns based on what is applicable to an analyst during triage

### Part 3: Additional Steps

#### Data Normalization
 - Using any open cybersecurity data model framework create a "normalized" view of your original parsed dataframe

#### Write the result to a fictitious `alert` table
 - Package the result of the detection as an alert row in a new dataframe that would theoretically be used by an analyst during triage
    - Think about what an analyst would need, what metadata would be useful at a high level, how this would be presented on a dashboard


#### Threat Intel Enrichment on Domain in Query
  - Given that the source data includes domain names, enrich the detection or alert with information from any threat intelligence source

## FAQ

### Q. Do I have to complete every step?
Complete the steps that you feel comfortable with.

### Q. What do I have to submit?
Submission should include a copy of the repo with a Jupyter notebook populated with the results of your code as well as a README file that includes a quick explanation of your process.

### Q. Can I share this quest with others?
No.

### Q. What can I do if I've never worked with notebooks, pyspark, or sql before?
We would still like you to demonstrate your existing skills, feel free to accomplish the hypothesis goal in whatever you way you do have experience with or use the hints to do as much as you can.

### Q. Can I use AI to assist me?
You can use AI as a reference, but we encourage you to be open about it! Please document what you used, what your prompts where, how it helped, what it got wrong, etc.

### Q. Hints 🤐
<details>
<summary>Hint 1: Loading a dataframe using PySpark</summary>

- Installation: We reccomend using a local virtual python environment, use the following link for [setup information](https://spark.apache.org/docs/latest/api/python/getting_started/install.html#)

-  PySpark Initialization & Reading JSON: [See Getting Started Docs](https://spark.apache.org/docs/latest/sql-getting-started.html#running-sql-queries-programmatically)

</details>
<details>
<summary>Hint 2: Parsing a dataframe in PySpark</summary>

- For extractic JSON see [PySpark docs](https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/api/pyspark.sql.functions.from_json.html)
- The [Ultimate Windows Security Encyclopedia]("https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/") is a good resources for the schema.

</details>
<details>
<summary>Hint 3: Using SQL with a dataframe</summary>
 
- Running SQL Queries Programmatically: [See Getting Started Docs](https://spark.apache.org/docs/latest/sql-getting-started.html#running-sql-queries-programmatically)

</details>
