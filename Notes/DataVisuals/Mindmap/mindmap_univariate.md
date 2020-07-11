# univariate 
## countplot
### `sns.countplot(data = df, x = 'cat_var')`

### `color = `
- `sns.color_palette()[i]`

### `order = `
- `[]` to sort the chart 
- e.g. `df.col.value_counts().index`

### `plt.xticks()`
- overlapped tickes 
  `(rotation = 90)`

- location and name 
  loc:  `np.arange(0, maxvalue, step)`
  name: `np.arnge(0, maxvalue, step)`
  
### limit 
- `plt.xlim([lower, upper])`
### annotate
- `plt.text(x, y, string_print, va/ha )` 

## barplot

### `sns.barplot(index, val,color)`
###  Missing data 
  ```
  sns.barplot(
  	df.isna().sum().index.values, 
   	df.isna().sum())
  ```
 
## pie plot
### into small slices 
### `sns.pie()` 
- `labels` 
- `startangle` =90 
- `counterclock` 
- `widgeprops` ={'width':0.4} 


## historgram 
### `plt.hist(data =, x ='')`
- `bins` 
### `sns.distplot(df[col])`
- `bins`
- `kde` (True/False)
- `hist_kws` {'alpha':1}

# techniques 
## Absolute vs relative frequency
## axis limit
## scales and transformations