## EDA (Explore and Augment)
#### Visualizations
* **descriptive**
  Quick insight into the relationships among numerical variables with scatter plots and display histogram for each variable
  `pd.plotting.scatter_matrix(df, figsize = (10,15))`
   kind = `bar` | `pie` | `scatter` |`box` |`hist` 
  **`hist`**: distribution   `df.hist(figsize= (12,8))` or general plot function  `df[col].plot(kind ='hist')` 
  **`scatter`**: relationship between x and y `df.plot(x = col1, y= col2, kind ='scatter')` 
  **`box`** : `df.col.plot(kind = 'box')` 
> notes:
> using the same indexing technique to keep the order of both results consistent. 
> `ind = df[col].value_counts().index`
> `df[col].value_counts()[ind].plot(kind='pie', figsize = (10,8))`
* **visulization details**
  ```
  import matplotlib.pyplot as plt 
  % matplotlib inline 

  plt.bar([1, 2, 3], [224, 620, 425], tick_label=['a', 'b', 'c'])
  plt.title('Some Title')
  plt.xlabel('Some X Label')
  plt.ylabel('Some Y Label');
  ```
* **Correlation Matrix** 
  ```
  corrMatrix = df.loc[:,['col','col2']].corr()
  sns.heatmap(corrMatrix, annot = True)
  plt.show()
  ``` 
* **Charts selection** 
  ![Chart](Pics/new_chart.jpeg) 