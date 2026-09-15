# Web Server Log Analysis using Hadoop, Hive, and Pig

An end-to-end Big Data analytics pipeline designed to ingest, process, query, and visualize web server logs using the Apache Hadoop ecosystem, Apache Pig, and Apache Hive.

---

## 🛠️ Technology Stack

* **Distributed File System:** Apache Hadoop (HDFS)
* **Data Processing / ETL:** Apache Pig (Pig Latin)
* **Data Warehousing & SQL Querying:** Apache Hive
* **Operating System:** Linux / Unix Shell Environment

---

## 📁 Directory Structure

```text
.
├── hadoop_setup_snaps/                  # Screenshots of HDFS configuration, directory creation, and dataset uploads
├── hive_setup_snaps/                    # Visual proof of Hive metastore initialization, database creation, and table schemas
├── hive_queries_run_output_screenshots/ # Screenshots of executed Hive analytical queries and CLI output logs
├── hive-query-visuals/                  # Graphs and visual analytics generated from Hive query results
├── pig_latin_setup/                     # Verification and setup screenshots for the Apache Pig execution environment
├── pig_latin_scripts_run_output/        # Pig Latin scripts and terminal execution logs for log cleaning and ETL
└── project_related_text_files/          # Raw web server logs, query scripts, schemas, and reference documents
```

---

## 🚀 Execution & Workflow Steps

### 1. Hadoop HDFS Configuration
* Start HDFS and YARN services:
  ```bash
  start-all.sh
  jps
  ```
* Create dedicated directories on HDFS and copy raw log files from `project_related_text_files/`:
  ```bash
  hdfs dfs -mkdir -p /web_log_analysis
  hdfs dfs -put project_related_text_files/raw_logs.txt /web_log_analysis/
  ```

### 2. ETL Processing with Apache Pig
* Run Pig Latin scripts (`pig_latin_scripts_run_output/`) to clean raw web log data.
* Extract IP addresses, timestamps, HTTP status codes, request methods, and user agents using Regex.
* Filter out malformed entries and output structured CSV files directly to HDFS.

### 3. Data Warehousing & Querying with Apache Hive
* Create external or internal Hive tables mapping to the processed Pig output.
* Run analytical SQL queries to evaluate:
  * Traffic volume by hour and day.
  * Frequency of client errors (`4xx`) and server errors (`5xx`).
  * Popular endpoints and browser/device breakdowns.

---

## 📊 Summary of Directory Contents

| Folder Name | Description |
| :--- | :--- |
| `hadoop_setup_snaps` | Screenshots proving HDFS setup, file transfers, and folder management. |
| `hive_setup_snaps` | Proof of database creation and table schema setup in Hive. |
| `hive_queries_run_output_screenshots` | Execution logs and query output screens in Hive. |
| `hive-query-visuals` | Plotted visual charts (traffic peaks, error rate graphs, client distributions). |
| `pig_latin_setup` | Screenshots verifying Apache Pig environment configuration. |
| `pig_latin_scripts_run_output` | Scripts and console outputs for Pig data transformation tasks. |
| `project_related_text_files` | Supporting text documents, raw datasets, and SQL/Pig scripts. |