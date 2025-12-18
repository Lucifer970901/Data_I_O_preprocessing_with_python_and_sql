# Web Scraping and Text Preprocessing

## Data Sources

**Scenario**: Working on Analysis

* Load Jupyter notebook: The interactive environment used for writing code.

* Load data into DataFrame: The primary structure (like a table) used for data manipulation in Python.

* Use .csv file to read in data: A common method for importing external data.

**Practical Data Sources**

In a professional environment, you will interact with a variety of sources:

* Flat files: Simple files like .csv or .txt.

* Databases: Structured storage systems like SQL.

* APIs: Interfaces used to "talk" to other software or web services.

* Web scraping: Extracting data directly from websites.

**What is a DataFrame?**

Think of a DataFrame as a digital spreadsheet. In Python (specifically using the pandas library), it is a two-dimensional structure where data is aligned in rows and columns. It is the "workhorse" of data science because it allows you to filter, sort, and calculate data very quickly.

**Flat Files vs. Databases**
Flat File (.csv): These are "flat" because they contain no structural relationships between records (other than being in the same list). They are easy to share but difficult to manage when the data becomes massive.

Database: These are designed for scale. They allow multiple users to access data simultaneously and can link different tables together (e.g., linking a "Customers" table to an "Orders" table).

**APIs vs. Web Scraping**
API (Application Programming Interface): The "clean" way to get data. A website (like Twitter or Weather.com) provides a specific "doorway" for your code to request data in a structured format.

Web Scraping: The "manual" way to get data. If a website doesn't have an API, you use code to read the HTML of a webpage and "scrape" the information you need. It is often more fragile because if the website changes its design, your scraper might break.

| Category |	Example | 	Primary Data Source |
| :--- | :--- | :--- |
| Generated |	Sales records |	Database |
| Collected |	Competitor prices, weather |	Web scraping, APIs |
| Historical |	Investment transactions |	Flat file (e.g., .csv) |

Generated data is usually internal (your company’s own sales).

Collected data is usually external (what the rest of the world is doing).

Historical data is used to find trends over time, often stored in "cold storage" (flat files) because it isn't updated frequently.

## Proprocessing

**1. Start with Raw Data**

Raw data is unprocessed information in its original form. This is data exactly as it was collected from a source (like a sensor, a database, or a web scraper) before any cleaning or filtering has occurred. It is often "noisy," containing errors or irrelevant information.

**2. Make Data Suitable for Analysis**
To transform raw data into a usable state, several key tasks are performed:

| Task | Purpose |
|:--- | :--- |
| Removing duplicates |	Ensures each observation is unique so that redundant data doesn't bias the results.|
| Handling missing values |	Deciding whether to delete rows with missing data or fill them in (imputation) with averages or logical guesses. |
| Handling outliers |	Identifying and addressing data points that are significantly different from the rest, which could be errors or important anomalies.|
| Fixing inconsistent formatting |	Standardizing data, such as ensuring all dates are in the same format (e.g., MM/DD/YY) or that "NY" and "New York" are treated as the same value.|
| Selecting a subset of features	| Reducing the number of variables by keeping only those most relevant to the analysis (also known as Feature Selection). |
| Scaling values |	Adjusting numeric data to a common range (like 0 to 1) so that variables with large numbers don't unfairly dominate the model. |
| Encoding categorical variables | Converting text-based data (like "Red" or "Blue") into numbers so a computer can process the information mathematically. |

**Data preprocessing benefits**

* Accuracy: Cleaning data removes errors that would otherwise lead to wrong conclusions.

* Efficiency: Reducing features and scaling values helps models run faster and use less computing power.

* Consistency: Standardizing formats allows you to combine data from different sources into one cohesive dataset.

## Pre-processing for business problems

**Goal #1: Identify testimonials for a website**

To find the best customer quotes, the data is preprocessed by:

* Filtering by language: Ensuring the testimonials are in a specific language (e.g., English).

* Removing PII: Stripping away Personally Identifying Information (like full names or IDs) for privacy.

* Sentiment Analysis: Selecting only messages that express "positive sentiment," filtering out negative reviews like "Not helpful".

**Goal #2: Rank hashtags to promote products online**

To understand social media trends, the data is preprocessed by:

* Removing media: Deleting all images and videos to focus strictly on text.

* Extraction: Pulling only the hashtags (e.g., #DogToys) from the posts.

* Frequency count: Creating a ranked list of the top 5 unique hashtags based on how often they appear.

## Data Preprocessing vs. Data Cleaning

Data preprocessing is the broad umbrella of steps used to prepare raw data for analysis. Data cleaning is considered a subset of that larger process.

| Data Preprocessing |	Data Cleaning |
|:---| :--- |
| Goal: Prepare raw data for analysis. |	Goal: Fix specific problems within the data. |
| Includes: Filtering, transforming, and organizing. |	Includes: Correcting errors and fixing typos.|
| Includes: Aligning data with analysis goals.	| Includes: Fixing inconsistencies. |
| Includes: The entire data cleaning process.	| Includes: Removing duplicates. |

## validating the data

In this step you will make sure if the data matches the expectations and if the preprocessing did not introduce any new problems.

this includes for example,
* Are all products name standardized?
* Have all the missing values been addressed?
* Does the number of sales make sense across all locations?

## ETL vs ELT

Data can be processed at different stages of the pipeline: before storage or after.
![alt text](assets/etl_vs_elt.png)

| Feature	| ETL (Extract, Transform, Load) |	ELT (Extract, Load, Transform) |
| :--- | :--- | :--- |
| Transform Stage |	Happens during Preprocessing before storage. |	Happens during Analysis after storage. |
| Data State |	Saved into analysis-ready formats. |	Data is left "as is" or reserved for later. |
| Best For |	General preprocessing that everyone needs. |	Exploration in Python notebooks for specific analysis. |

### What is ETL

![alt text](assets/etl.png)

### what is ELT

![alt text](assets/elt.png)