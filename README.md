# Rearc Cybersecurity Detection Quest

## Q. What is this quest?
The cybersecurity quest is a fun way to assess your hands-on engineering skills. It is also a good representation of the type of work associated with this role.

## Q. What skills are needed?
* Security Data Engineering
* Detection Engineering
* Programming Language (Python and/or SQL)
* Development (Working with Jupyter Notebooks, Python, and Git)

## Q. Challenge Steps
This quest consists of 3 main parts. Putting all 3 of these parts together will mimic our detection development and engineering workflow. If you get stuck see the [FAQ section](#faq).

- Part 1 will showcase your general data skills, this section consists of:
  - Setting up a local spark environment (this part is completed for you but may require environment setup beforehand)
  - Loading a JSON line file into an appropriate format
  - Parsing the JSON data out for use in following analytic steps.

- Part 2 will showcase your analytic skills by applying the threat hypothesis. The expectations here are:
  - Develop an actionable analytic query using preferably either PySpark or SQL
  - Document your design process in either notebook context or code comments

- Part 3 will showcase your knowledge of additional cybersecurity data subjects including:
  - Alert Packaging
  - Data Normalization Frameworks
  - Threat Intelligence Enrichment


### Hypothesis - IMPORTANT

 - Adversaries may send spearphishing emails with a malicious attachment in an attempt to gain access to victim systems. 
 - A threat actor can leverage Microsoft Office applications against users on Windows endpoints through phishing to make potentially malicious web calls. 
 - Windows Endpoints forwarding DNS activity via sysmon logs to a data orchestration platform like Cribl would be utilized to identify this activity.

### Part 1: Load the Sample Dataset

***THIS STEP IS COMPLETED FOR YOU.***
<br />The template Jupyter notebook contains the code for the following actions:

1. Load the JSON line file from the `data/` directory into a Spark dataframe.
2. Create a new dataframe that parses out any necessary fields from the `_raw` column to be used in part 2.
3. Create a view for use with Spark SQL queries

### Part 2: Detection Engineering

1. Preferably using either PySpark or SQL, create a query or queries that will prove the detection hypothesis.
2. Output the result of this query in the notebook with a new dataframe
    - Select columns based on what is applicable to an analyst during triage

### Part 3: Additional Steps

#### Data Normalization
 - Using any relevant cybersecurity data model framework, create a "normalized" view of your original parsed/result dataframe

#### Write the result to a fictitious `alert` table
 - Package the result of the detection as an alert row in a new dataframe that would theoretically be used by an analyst during triage
    - Think about what an analyst would need, what metadata would be useful at a high level, how this might be presented on a dashboard


#### Threat Intel Enrichment on Domain in Query
  - Given that the source data includes domain names, enrich the detection or alert with information from any threat intelligence source

## FAQ

### Q. What do I need to do to setup this environment
A general understanding of Python and Virtual Environments is expected. For the purposes of this challenge the only dependency outside of what is listed in the `requirements.txt` file is Java 17 or Later

### Q. Do I have to complete every step?
Complete the steps that you feel comfortable with.

### Q. What do I have to submit?
Submission should include a copy of the repo with a Jupyter notebook populated with the results of your code as well as a README file that includes a quick explanation of your process.

### Q. Can I share this quest with others?
No.

### Q. What can I do if I've never worked with Jupyter Notebooks, PySpark, or SQL before?
Demonstrate your skills as best you can, if you run into problems we recommend using online documentation and examples. Document whatever process you used to demonstrate your learning and problem solving techniques.

### Q. Can I use AI to assist me?
You ***may*** use AI as a reference tool but there will be a strong expectation to exhibit the same expertise and understanding from your submission in your interview. In addition we encourage you to be open about any usage! Please document what you used, what your prompts were, how it helped, what it got wrong, etc.

### Q. Hints 🤐
<details>
<summary>Hint 1: Loading a dataframe using PySpark</summary>

- Installation: We recommend using a local virtual python environment, use the following link for [setup information](https://spark.apache.org/docs/latest/api/python/getting_started/install.html#)

-  PySpark Initialization & Reading JSON: [See Getting Started Docs](https://spark.apache.org/docs/latest/sql-getting-started.html#running-sql-queries-programmatically)

</details>
<details>
<summary>Hint 2: Parsing a dataframe in PySpark</summary>

- For extractic JSON, [See PySpark docs](https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/api/pyspark.sql.functions.from_json.html)
- The [Ultimate Windows Security Encyclopedia]("https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/") is a good resources for the schema.

</details>
<details>
<summary>Hint 3: Using SQL with a dataframe</summary>
 
- Running SQL Queries Programmatically: [See Getting Started Docs](https://spark.apache.org/docs/latest/sql-getting-started.html#running-sql-queries-programmatically)

</details>
