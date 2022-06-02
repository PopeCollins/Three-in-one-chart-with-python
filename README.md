# [Three in one chart with python](https://popecollins.github.io/Three-in-one-chart-with-python/)
A chart that describe the rate of happiness. 
A data titlle world happiness report 2021 was used to 
The data used for this analysis was downoload from Kaggle 
### The Source code for writting the on jupiter notebook will be provide in this repo

### The image:
![image](https://github.com/PopeCollins/Three-in-one-chart-with-python/blob/main/top%2010.png "image")


### The source code Using jupiter notebook
#### Import the usefull library
1. import pandas as pd
2. import numpy as np
3. import seaborn as sns
4. import matplotlib.pyplot as plt
5. %matplotlib inline
6. sns.set_style('darkgrid')
7. plt.rcParams['font.size']=15
8. plt.rcParams['figure.figsize']= (10,7)
9. plt.rcParams['figure.facecolor']= '#FFE5B4'



### Load your data set
data_first= pd.read_csv('....... adjust base on the location on your machine ....world-happiness-report-2021.csv')

### Select some Columns
data_link = ['Country name', 'Regional indicator', 'Ladder score', 'Logged GDP per capita', 'Social support', 'Healthy life expectancy','Freedom to make life choices','Generosity','Perceptions of corruption']
data_first= data_first[data_link].copy()

### Rename your coulumn
happy_df= data_first.rename(columns={'Country name':'country_name', 'Regional indicator':'regional_indicator', 'Ladder score':'happiness_score','Logged GDP per capita':'logged_GDP_per_capita', 'Social support':'social_support', 'Healthy life expectancy':'healthy_life_expectancy', 'Freedom to make life choices':'freedom_to_make_life_choices','Generosity':'generosity','Perceptions of corruption':'perceptions_of_corruption'})

### Select
1. top_10 = happy_df.head(10)
2. bottom_10= happy_df.tail(10)
3. any_10=happy_df.iloc[15:25]

### Finish the coding
1. fig, axes= plt.subplots(1,3, figsize=(16,6))
2. plt.tight_layout(pad=3)
3. xlabels=top_10.country_name
4. axes[0].set_title("Top 10 happy country")
5. axes[0].set_xlabel("The countries")
6. axes[0].set_ylabel('The health life expectancy')
7. axes[0].set_xticklabels(xlabels,rotation = 45, ha='right' )
8. sns.barplot(x=top_10.country_name, y=top_10.healthy_life_expectancy, ax= axes[0])

1. xlabels= bottom_10.country_name
2. axes[1].set_title("Bottom 10 happy country")
3. axes[1].set_xlabel("The countries")
4. axes[1].set_ylabel('The health life expectancy')
5. axes[1].set_xticklabels(xlabels,rotation = 45, ha='right' )
6. sns.barplot(x=bottom_10.country_name, y=bottom_10.healthy_life_expectancy, ax= axes[1])

1. xlabels=any_10.country_name
2. axes[2].set_title("Any 10 happy country")
3. axes[2].set_xlabel("The countries")
4. axes[2].set_ylabel('The health life expectancy')
5. axes[2].set_xticklabels(xlabels,rotation = 45, ha='right' )
6. sns.barplot(x=any_10.country_name, y=any_10.healthy_life_expectancy, ax= axes[2])


Respect to simplilearn on YT (You impact knowldge in me)
