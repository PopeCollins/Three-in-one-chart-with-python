# [Three in one chart with python](https://popecollins.github.io/Three-in-one-chart-with-python/)
A chart that describe the rate of happiness. 
A data titlle world happiness report 2021 was used to 
The data used for this analysis was downoload from Kaggle 
### The Source code for writting the on jupiter notebook will be provide in this repo

### The image:
![alt text](https://github.com/PopeCollins/Three-in-one-chart-with-python/blob/main/top%2010.png)


### The source code Using jupiter notebook
#### Import the usefull library
```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
%matplotlib inline
sns.set_style('darkgrid')
plt.rcParams['font.size']=15
plt.rcParams['figure.figsize']= (10,7)
plt.rcParams['figure.facecolor']= '#FFE5B4'
```


### Load your data set
```python
data_first= pd.read_csv('....... adjust base on the location on your machine ....world-happiness-report-2021.csv')
```
### Select some Columns
```python
data_link = ['Country name', 'Regional indicator', 'Ladder score', 'Logged GDP per capita', 'Social support', 'Healthy life expectancy','Freedom to make life choices','Generosity','Perceptions of corruption']
data_first= data_first[data_link].copy()
```

### Rename your coulumn
```pyhton
happy_df= data_first.rename(columns={'Country name':'country_name', 'Regional indicator':'regional_indicator', 'Ladder score':'happiness_score','Logged GDP per capita':'logged_GDP_per_capita', 'Social support':'social_support', 'Healthy life expectancy':'healthy_life_expectancy', 'Freedom to make life choices':'freedom_to_make_life_choices','Generosity':'generosity','Perceptions of corruption':'perceptions_of_corruption'})
```
### Select
```python
top_10 = happy_df.head(10)
bottom_10= happy_df.tail(10)
any_10=happy_df.iloc[15:25]
```
### Finish the coding
```pyhton
fig, axes= plt.subplots(1,3, figsize=(16,6))
plt.tight_layout(pad=3)
xlabels=top_10.country_name
axes[0].set_title("Top 10 happy country")
axes[0].set_xlabel("The countries")
axes[0].set_ylabel('The health life expectancy')
axes[0].set_xticklabels(xlabels,rotation = 45, ha='right' )
sns.barplot(x=top_10.country_name, y=top_10.healthy_life_expectancy, ax= axes[0])

xlabels= bottom_10.country_name
axes[1].set_title("Bottom 10 happy country")
axes[1].set_xlabel("The countries")
axes[1].set_ylabel('The health life expectancy')
axes[1].set_xticklabels(xlabels,rotation = 45, ha='right' )
sns.barplot(x=bottom_10.country_name, y=bottom_10.healthy_life_expectancy, ax= axes[1])

xlabels=any_10.country_name
axes[2].set_title("Any 10 happy country")
axes[2].set_xlabel("The countries")
axes[2].set_ylabel('The health life expectancy')
axes[2].set_xticklabels(xlabels,rotation = 45, ha='right' )
sns.barplot(x=any_10.country_name, y=any_10.healthy_life_expectancy, ax= axes[2])
```


