---
title: CS-430 - Machine Learning
parent:
  - "[[Class]]"
aliases: 
tags:
  - cs-class
  - dense-note
---
### CS-430 - Machine Learning
## Class Overview
**Instructor** - Sayani Sarkar, Ph.D.
- ssarkar@bellarmine.edu
- 502-272-7984
- Office Hours - M/W 10:00 AM-11:30 PM
**Location** - Pasteur 104
**Time** - M/W/F 9:00-9:50 AM
## Lecture 1
### Machine Learning Paradigms
**Types of Machine Learning**
1. **Supervised Learning** - The dataset is labeled, the machine has guidance.
	1. Classification - Recognizing input data based on labeled learning data.
	2. Regression - Outputting continuous real values based on learning data.
2. **Unsupervised Learning** - The dataset is not labeled, the machine is given no specific instructions. The goal of unsupervised learning is to find an underlying structure in the data to learn more about it.
	1. Clustering - Grouping items based on similarities.
	2. Assosiation Rules Mining - A technique used to find similarities between different categories of data. For example, motorcycle helmets are associated with motorcycles.
3. **Reinforcement Learning** - An agent learns based on its actions. Each time the agent performs an action (gives output), it will be told if that was good or bad. It learns by maximizing the rewards it gets.
4. **Batch/Offline Learning** - Learning using data that is not changing in real time. It can be downloaded and worked on offline.
5. **Online Learning** - Learning using live data, where the model may change moment to moment based on its varying input data.
**Challenges of Machine Learning**
1. **Not Enough Training Data**
2. **Nonrepresentative Trining Data** - The training data is not representative of the population.
3. **Low Quailyt Training Data**
4. **Irrelevant Features**
5. **Overfitting the Training Data** - The model is too complex relative to the amount and quality of the training data.
6. **Underfitting the Data** - The model is too simple relative to the amount and quality of the training data.
**No Free Lunch Theorem**
	There is no model that is guranteed to work better on a given set of data. The only way to know for sure is to evaluate them all.
## Lecture 2 - Data Gathering and Pandas Series/CSV
### Data Gathering
**Data Gathering Methods**
1. **Surveys and Questionnaires**
2. **Web Scraping**
3. **APIs** - Access data from web services.
4. **Sensor Data**
5. **Observational Studies**
6. **Public Databases** 
**Common Filetypes**
1. **CSV** - (.csv) Comma Separated Values - Plain text with data separated by commas.
2. **TSV** - (.tsv) Tab Separated Values - Plain text with data separated by tabs.
3. **JSON** - (.json) JavaScript Object Notation - Lightweight, key-value-pair-based plain text data.
4. **Excel** - (.xlsx) Microsoft spreadsheet files.
5. **SQL Databases** - Files associated with relational database management.
6. **HDF5** - Heirerchical Data Format v5 - A file formate and toolset for managing complex data.
7. **Feather** - Fast, lightweight, language-agnostic columnar data storage. Used for interchanging data between languages.
8. **Pickle** - Python-specific serialization format used to serialize and deserialize Python objects.
9. **Log Files** - (.log) - Plain text files recording events or activities.
10. **Text Files** - (.txt) - Plain text files.
11. **Markdown** - (.md) - Formatted text files.
12. **Images** - (.jpg, .png, ect) - Visual files.
13. **Audio** - (.mp3, .wav, etc) - Audio files.
14. **Video** - (.mp4, .avi, etc) - Video files.
### Pandas
**Series** - A pandas Series is a one-dimensional labeled array that can hold any data type. Series are...
- One-dimensional - A single column of data.
- Homogenous - All elements are the same data type.
- Labeled - Each index is labeled.
**DataFrame** - A pandas DataFrame is a two-dimentional, tabular data structure with labeled axes. DataFrames are...
- Two-dimensional - Columns and rows, like a table.
- Size-mutable - Elements can be added and removed.
- Heterogeneous - Can have multiple different data types.
- Labeled Axes - Rows and columns have labels.
## Lecture 3 - Web APIs
### Types of APIs
**Web APIs**
- APIs that use web protocols (HTTP/HTTPS).
- Used to enable communication between web services and applications.
**Library APIs**
- APIs provided by programming libraries allowing developers to use pre-built functions and modules.
**Operating System APIs**
- APIs providing functions to interact with an operating system.
**RESTful APIs** - Based on the RESTful principle.
- **R**epresentational **S**tate **T**ransfer - An architectural style for designing networked applications.
- Use standard HTTP methods (GET, POST, PUT, DELETE) to operate on URL-identified resources.
### Web Status Codes
- **200** - Everything worked properly.
- **301** - The server is redirecting you to a different endpoint.
- **400** - The server thinks you made a bad request.
- **401** - The server thinks you're not authenticated.
- **403** - You don't have the right permission to view the requested resource.
- **404** - The server didn't find the requested resource.