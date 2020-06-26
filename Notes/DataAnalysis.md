# Data Analysis Process
### Outline 
<ul>
<li><a href="#L2">Data Analysis Process Overview</a></li>
<li><a href="#L3">Data Wrangling</a></li>
<ul><li><a href="#L2.1">Gathering Data</a></li>
    <li><a href="#L2.2">Access Data</a></li>
    <li><a href="#L2.3">Clean Data</a></li>
</ul>
<li><a href="#L4">Additional</a></li>
</ul>

****
<a id='L2'></a>
## Data Analysis Process Overview

- **Step 1: Ask questions**   

  Ask questions based on data or before gather data to help to focus on relevant parts of data and direct analysis towards meaniful insights.  

- **Step 2: Wrangle data**
  - gather: retrieve and read data  
  - assess: identify problems in data's quality or structure 
  - clean : by modifying, replacing, or removing data 


- **Step 3: Perform EDA (Exploratory Data Analysis)**
   Explore and augment data to maximize the potential of analysis, visualizations, and models including
  - finding pattern 
  - visulizing relationship 
  - building intuition about the data 
  - feature engineering (remove outliers and create better features)

- **Step 4: Draw conclusions (or even make predictions)**
Typically approached with machine learning or inferential statistics.

- **Step 5: Communicate your results**
  - Justify and convey meaning in the insights found. 
  - Or, if the end goal is to build a system, then need to share what been built, explain how we reached design decisions, and report how well it performs. 

**** 

<a id='L3'></a>

## Data Wrangling: 

<a id='L2.1'></a>
### 1. Gather Data

#### Raw File
* **HTML**
  - workbook with bs4 ([link](GatherData_bs4.html))
  



#### Prepared Files
* **unzip**
  ```
  import zipfile  
  with ZipFile('file.zip', 'r') as myzip:    
        myzip.extractall()
  ```

* **Read**
`label`  to change the column name 
`header` if 0 then the frist line of the data; None then nothing; 1 is the second line of the data
`index` False to ingnore the index
`sep` sepecify the delimiter
  ```
  labels = ['col1', 'col2', 'col3']  
  df = pd.read_csv('data.csv', names=labels, index = False)   
  ```


<a id='L2.2'></a>
### 2.  Access and Build Intuition
* **basic funtions**  &emsp;   `shape` | `dtypes` | `describe` | `info` | `unique`
* **reassign column name** 
  ```
  # Work from df 
  df.rename(columns ={'A' :'A1'}, inplace = True)
  df.rename(INDEX ={0:'A1'})
  ```
  - replace space with underscores and lowercase label 
  `df.rename(columns=lambda x: x.strip().lower().replace(" ", "_"), inplace=True)`
  - check two dataframe's columns if identical 
  `(df.columns == df2.columns).all()`



<a id='L2.3'></a>
### 3. Clean Data

**Stpes** 
1. Define: convert assessment into defined cleaning tasks 
2. Code: convert definition to code
3. Test: test the dataset (like using assert statement)
    * **assert**
   check if every text in a `asap_list` is in `df.startDate.values`
   ```
   for phrase in asap_list:
      assert phrase not in df.startDate.values
   ```
* **incorrect data types**
`df['timestamp'] = pd.to_datetime(df['timestamp']) `
`df[col] = df[col].astype(str/int/float)`
string in col `df[df.col.str.contains('?')]`
* **missing value** 
  **check**
number of rows have missing value `df.isnull().any(axis = 1).sum()`
number of col have missing value `df.isnull().any(axis = 0).sum()`
   ```
   # example impute by mean
   mean = df.col.mean()   
   df.col = df.col.fillna(mean, inplace = True)
   ```
    - drop missing records
      `df.drop(['col','col'], axis = 1, inplace = True)`  
      **drop rows** with NA `df.dropna(axis = 0, inplace = True)`  
      or drop row with idx `df.drop((df.query('age == -1')).index[0])`
      **drop cols** with NA `df.dropna(axis = 1, inplace = True)` 
    
* **duplicates** 
`df.duplicated()` gives boolean result 
`sum(df.duplicates())` gives the number of duplicates records 
`df.drop_duplicates()`

* **`query`**: 
  - selected rows by indexing with a mask
    `df.query('col == "Y"')`
  - easy to subset
  `low = df.query('alcohol < {}'.format(df['alcohol'].median()))`
  - select condition 
  `df.query('col in ["val1", "vla2"]')`


**** 
<a id='L4'></a>
## Additional