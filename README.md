# <ins>Analyzing the Top 2000 Companies: A Data-Driven Approach</ins>

## About Project 👨‍💻

- Analyzed company metrics to gain business insights. 
- Cleaned data using Excel.
- Created visualizations in Power BI.
- Integrated Python for advanced visuals.

## Technologies used ⚙️
    
- Statistics
- Excel
- Python
- PowerBI

## Problem statements and questions ❓
 ### Answer the following questions:
- Descriptive Statistics:
   - What is the overall distribution of key financial metrics (sales, profit, assets, market value)?
    - What is the average, median, and range for each of the financial metrics (sales, profit, assets, and market value)?
    - Are there any extreme outliers that may need further investigation or clarification?
- Top Companies Analysis:
  - What are the top 10 companies in terms of sales, profit, assets, and market value?
  - Are the top companies in these categories consistent, or do the rankings shift when you consider different metrics (e.g., a company might be top in sales but not in profit)?
- Geographic Insights:
  - What countries are most represented in the dataset? Which countries have the highest performing companies in terms of market value, sales, and profit?
  - Do any countries show significant disparities in their representation or performance (e.g., some countries have only a few high-performing companies, while others have a wide range)?
  - Are there any trends or patterns in global company performance (e.g., are North American companies predominantly performing better in sales, while Asian companies are leading in market value)?
- Profitability vs. Size (correlation):
  - How does profit relate to sales, assets, and market value? Are companies with higher sales always more profitable, or are there exceptions?
  - Is there a strong correlation between company size (assets or market value) and profitability, or are smaller companies often more profitable in relation to their size?

 ## Data Analysis
- In this part of the page there will be a resume of the overall process like screenshots or python code that I have used in order to make the visualizations
- <a href='https://www.kaggle.com/datasets/soumyodippal000/top-2000-companies-financial-data-2024-dataset'>Dataset from Kaggle</a> 

### Python Code:
  - Histogram:
```
# dataset = pandas.DataFrame(Market Value)
# dataset = dataset.drop_duplicates()
# Paste or type your script code here:
import matplotlib.pyplot as plt
plt.hist(dataset, bins=40, edgecolor = "#FFFFFF", color="red")
plt.xlabel("Market Value (Billon)")
plt.show()
```
  - Heatmap:
```
#dataset = pandas.DataFrame(Assets, Market Values, Profit, Sales)
#dataset = dataset.drop_duplicates()
# Paste or type your script code here:
import seaborn as sns
import matplotlib.pyplot as plt
dataset = pandas.get_dummies(dataset)
correlation = dataset.corr(numeric_only = False)
heatmap = sns.heatmap(correlation, annot = True, cmap = 'Reds')
plt.show(heatmap)
```
### Visualizations and insights
![heatmap](images/screenshot/heatmap.png?raw=true "Title")
- The heatmap displays correlation coefficients between four financial metrics: Market Value, Profit, Sales, and Assets. The color intensity represents the correlation strength, with deeper red indicating a stronger positive correlation. The numbers within each cell denote the actual correlation coefficient.
Key insights from the graph:
Profits are strongly correlated with both Sales and Market Value and moderately correlated with Assets.
The strong correlation between Sales and Profit suggests that higher sales generally lead to higher profitability. However, the correlation is not perfect (1.0), indicating exceptions—some companies may have high sales but lower profit margins, and vice versa.
Market Value and Profitability also show a strong correlation, reinforcing the idea that more profitable companies tend to have higher market values.
The moderate correlation between Assets and Profitability suggests that factors beyond asset size influence profitability. Some smaller companies may achieve higher profit margins relative to their size.

![histogram](images/screenshot/histogramdistributionv2.png?raw=true "Title")
-  Examining the graph of all four metrics we can see that they exhibit a positive skew (right skew). This means that for each metric, most companies have values concentrated toward the lower end, with a smaller number of companies having much larger values that pull the mean upward.
The histograms, combined with the large differences between the average and median, strongly suggest the presence of outliers, especially in Profit and Market Value.

![t10companies](images/screenshot/top10companies.png?raw=true "Title")
- If we see it, there is some overlap in the top companies across different metrics, but the rankings and even the presence of certain companies change significantly. This tells us that leadership in one area doesn't guarantee leadership in others, this means that the rankings are not consistent. As noted above, companies like Walmart and the Chinese banks demonstrate significant shifts in ranking depending on the metric. This indicates that different factors drive each of these metrics, and companies can choose to prioritize different areas of focus.
![top10countries](images/screenshot/top10countries.png?raw=true "Title")
- The graph highlights which countries are most represented in the dataset, with the United States, China, and Japan leading across all previously analyzed metrics. Another key observation is the limited representation of Middle Eastern countries—while Saudi Arabia appears in some charts, likely due to Saudi Aramco, broader regional representation remains scarce. Additionally, the data suggests a notable European presence; several European countries appear consistently, though not always at the top, indicating a strong yet more diversified economic base

### Conclusions of analisis 


