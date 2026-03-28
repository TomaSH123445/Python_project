# The Analysis 

## 1. What are the skills most in demand for the top 3 most popular data roles in UK?

To find the most demanded skills for the top 3 most popular data roles. I filtered out those positions by which ones were the most popular, and got the top 5 skills for these top 3 roles. This query highlights the most popular job titles and their top skills, showing which skills I should pay attention to depending on the role I'm targeting.

View my notebook with detailed steps here: 
[2_Skill_Demand.ipynb](3_Project/2_Skill_Demand.ipynb)

### Visualize Data

```python
fig, ax = plt.subplots(len(job_titles), 1)

sns.set_theme(style='ticks', palette='pastel')


for i, job_title in enumerate(job_titles):
    df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head(5)
    sns.barplot(data=df_plot, x='skill_percentage', y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')
```
### Results

![Visualization of Top Skills in UK](3_Project/images/skill_demand.png)

### Insights

- SQL and Python are the key core skills across all three positions.
- Data Analysts focus more on Excel, Power BI, and reporting.
- Data Engineers need stronger cloud and infrastructure skills, especially Azure and AWS. 
- Data Scientists rely most heavily on Python for advanced analysis and modeling.

## 2. How are in-demand skills trending for Data Analysts?

To find how skills are trending in 2023 for Data Analysts, I filtered data analyst positions and grouped the skills by the month of the job postings. This got me the top 5 skills of data analysts by month, showing how popular skills were throughout 2023.


View my notebook with detailed steps here: 
[3_Skill_Trend.ipynb](3_Project/3_Skill_Trend.ipynb)

### Visualize Data

```python
rom matplotlib.ticker import PercentFormatter

df_plot = df_DA_UK_percent.iloc[:, :5]

sns.set_theme(style='ticks')
sns.lineplot(data=df_plot, dashes=False, palette="tab10")
sns.despine()
```
### Results

![Trending Top Skills for Data Analyst in the UK](3_Project/images/Skill_trend.png)

### Insights

- SQL remains the most consistently demanded skill throughout the year, reaching its peak around September before declining slightly toward the end of the year.
- Excel stays relatively stable as the second most requested skill, despite a few dips, and remains one of the core tools for data analyst roles.
- Python shows moderate fluctuations, with stronger demand in the middle of the year, confirming its continued importance for analytical and technical tasks.
- Power BI and Tableau are less demanded overall, but both show stronger growth in the second half of the year, suggesting increasing interest in BI and data visualization skills.