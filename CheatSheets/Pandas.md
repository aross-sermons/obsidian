---
title: Pandas
parent:
  - "[[Cheat Sheet]]"
aliases: 
tags:
  - python
---
## Classes
### pandas.DataFrame
**Parameters**
- **data :** *ndarray (structured or homogenous), Iterable, dict, or DataFrame*
	- 
- **index :** *Index or array-like*
## Functions
### Importing Data from Files
###### `read_csv()`
**Sources**
- File - `list = pd.read_csv("path/to/list.csv")`
- URL - `list = pd.read_csv("https://myurl")`
**Parameters**
- `index_col` - Used to specify which column should be used as the index.
	- Ex: `list = pd.read_csv("people.csv", index_col = "name")`
- `usecols` - Specifies which columns to import.
	- Ex: `list = pd.read_csv("people.csv", usecols = ["name", "age"])`
- `skiprows` - Skips `n` rowns from the top.
	- Ex: `list = pd.read_csv("people.csv", skiprows = 1)`
- **`header`** - Sets the header to `n` rows from the top.
	- Ex: `list = pd.read_csv("people.csv", header = 1)`
- `delimiter` - Specifies the delimeter used in the file.
	- Ex: `list = pd.read_csv("people.csv", delimiter = '\t')`
- `sep` - Specifies the character or regex pattern to treat as the delimiter.
	- Ex: `list = pd.read_csv("people.csv", sep = '\t'`
- `names` - Specifies header names as a list.
	- Ex: `list = pd.read_csv("people.csv", names = ["first", "last"])`
###### `read_excel()`
**Sources**
- File - `excel = pd.read_excel("path/to/excel.xlsx")`
###### `read_json()`
**Sources**
- File - `json = pd.read_json("path/to/json.json")`