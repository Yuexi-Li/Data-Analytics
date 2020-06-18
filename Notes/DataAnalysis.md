# Data Analysis Process

### Data Analysis Process Overview
<details> 
<summary> Data Analysis Process </summary>
<bold> 
Step 1: Ask questions   

Either you're given data and ask questions based on it, or you ask questions first and gather data based on that later. In both cases, great questions help you focus on relevant parts of your data and direct your analysis towards meaningful insights.

Step 2: Wrangle data
You get the data you need in a form you can work with in three steps: gather, assess, clean. You gather the data you need to answer your questions, assess your data to identify any problems in your data’s quality or structure, and clean your data by modifying, replacing, or removing data to ensure that your dataset is of the highest quality and as well-structured as possible.

Step 3: Perform EDA (Exploratory Data Analysis)
You explore and then augment your data to maximize the potential of your analyses, visualizations, and models. Exploring involves finding patterns in your data, visualizing relationships in your data, and building intuition about what you’re working with. After exploring, you can do things like remove outliers and create better features from your data, also known as feature engineering.

Step 4: Draw conclusions (or even make predictions)
This step is typically approached with machine learning or inferential statistics that are beyond the scope of this course, which will focus on drawing conclusions with descriptive statistics.

Step 5: Communicate your results
You often need to justify and convey meaning in the insights you’ve found. Or, if your end goal is to build a system, you usually need to share what you’ve built, explain how you reached design decisions, and report how well it performs. There are many ways to communicate your results: reports, slide decks, blog posts, emails, presentations, or even conversations. Data visualization will always be very valuable.
</details>

## Categlog 
### Data Wrangling: 
#### 1. Gather Data
`label`  to change the column name 
`header` if 0 then the frist line of the data; None then nothing; 1 is the second line of the data
`index` False to ingnore the index
```
labels = ['col1', 'col2', 'col3']  
df = pd.read_csv('data.csv', names=labels, index = False)   
```
#### 2.  Access and Build Intuition
  &emsp;   `shape` | `dtypes` | `describe` | `info` | `unique`
#### 3. Clean Data
**incorrect data types**
`df['timestamp'] = pd.to_datetime(df['timestamp']) `
**missing value** 
   ```
   # example impute by mean
   mean = df.col.mean()   
   df.col = df.col.fillna(mean, inplace = True)
   ```
**duplicates** 
`df.duplicated()` gives boolean result 
`sum(df.duplicates())` gives the number of duplicates records 
`df.drop_duplicates()`



### EDA (Explore and Augment)
#### Visualizations
* **descriptive**
  Quick insight into the relationships among numerical variables with scatter plots and display histogram for each variable
  `pd.plotting.scatter_matrix(df, figsize = (10,15))`
   kind = `bar` | `pie` | `scatter` |`box` |`hist` 
  `hist`: distribution   `df.hist(figsize= (12,8))` or general plot function  `df[col].plot(kind ='hist')` 
  `scatter`:relationship between x and y `df.plot(x = col1, y= col2, kind ='scatter')` 
  `box` :`df.col.plot(kind = 'box')` 
> notes:
> using the same indexing technique to keep the order of both results consistent. 
> `ind = df[col].value_counts().index`
> `df[col].value_counts()[ind].plot(kind='pie', figsize = (10,8))`