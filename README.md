

# Overview

Welcome to my analysis of the data job market, focusing on data analyst roles. This project was created out of a desire to navigate and understand the job market more effectively. It delves into the top-paying and in-demand skills to help find optimal job opportunities for data analysts.

The data sourced from Luke Barousse's Python Course which provides a foundation for my analysis, containing detailed information on job titles, salaries, locations, and essential skills. Through a series of Python scripts, I explore key questions such as the most demanded skills, salary trends, and the intersection of demand and salary in data analytics.


# The Questions

Below are the questions I want to answer in my project:

1.What are the skills most in demand for the top 3 most popular data roles?
2.How are in-demand skills trending for Data Analysts?
3.How well do jobs and skills pay for Data Analysts?
4.What are the optimal skills for data analysts to learn? (High Demand AND High Paying)


## Tools I Used

For my deep dive into the data analyst job market, I harnessed the power of several key tools:

-Python: The backbone of my analysis, allowing me to analyze the data and find critical insights. I also used libraries:
-Pandas Library: This was used to analyze the data.
-Matplotlib Library: I visualized the data.
-Seaborn Library: Helped me create more advanced visuals.
-Jupyter Notebooks: The tool I used to run my Python scripts which let me easily include my notes and ana
-Visual Studio Code: My go-to for executing my Python scripts.
-Git & GitHub: Essential for version control and sharing my Python code and analysis, ensuring collaboration and publish my work.

# The Analysis

Each Jupyter notebook for this project aimed at investigating specific aspects of the data job market. Here's how I approached each question


## Data Preparation and Cleanup

This section outlines the steps taken to prepare the data for analysis, ensuring accuracy and usability.



# The Analysis

 ## 1. What are the most demanded skills for the top 3 most popular data role?

 To find the most demanded skills for the top 3 most popular data roles. I filtered out those positions by which ones were the most popular, and got the top 5 skills for these top 3 roles. This query highlights the most popular job titles and thier top skills , showing which skills I should pay attention to depending on the role I'm targeting.

 View my notebook with detailed steps here: [2_Skill_Demand.ipynb](2_skill_demand.ipynb )   

 ### Visualize Data

```python

   fig,ax = plt.subplots(len(job_titles),1)

    for i,job_title in enumerate(job_titles):
        df_plot = df_skills_perc[df_skills_perc['job_title_short']== job_title].head(5)[::-1]sns.barplot(data= df_plot, x= 'skill_percent', y= 'job_skills', ax=ax[i], hue='skill_count, palette='dark:b_r')
        plt.show()
```

  ### Results

![Visualization of
Top Skills for Data Nerds](Images/skill_demand_all_data_roles.png)
 
### Insights
Here is the exact text from the image:

> ### Insights
-- Python is a versatile skill, highly demanded across all three roles, but most prominently for Data Scientists (72%) and Data Engineers (65%).

-- SQL is the most requested skill for Data Analysts and Data Scientists, with it in over half the job postings for both roles. For Data Engineers, Python is the most sought-after skill, appearing in 68% of job postings.

-- Data Engineers require more specialized technical skills (AWS, Azure, Spark) compared to Data Analysts and Data Scientists who are expected to be proficient in more general data management and analysis tools (Excel, Tableau).


## 2. How are in-demand skills

### Results

![Trending Top skills for Data Analysts in the US](Images\Skills_Trend_DA.png)
*Bar graph visualizing the trending top skills for data analysis in the US in 2023.*

### Insights:
-SQL remains the most consistently demanded skill throughout the year, although it shows a gradual decrease in demand.

-Excel experienced a significant increase in demand starting around September, surpassing both Python and Tableau by the end of the year.

-Both Python and Tableau show relatively stable demand throughout the year with some fluctuations but remain essential skills for data analysts. Power BI, while less demanded compared to the others, shows a slight upward trend towards the year's end.

# The Analysis
## 3. How well do jobs and skills pay for Data Analysts?

### Salary Analysis for Data Nerds

### Visulaize Data

``` python
sns.boxplot(data=df_DA_US_top6, x= 'salary_year_avg', y='job_title_short' order=job_order)

ticks_x=plt.FuncFormatter(lambda y, pos : f'${int(y/1000)}K')
plt.gca().xaxis.set_major_formatter(ticks_x)
plt.show()

```
![Salary Distribution of Data Jobs in the US](Images\Salary_Analysis.png)
*Box plot visualizing the salary distribution for the top 6 data job titles.*

### Salary Analysis for Data Nerds
#### Insights
-There is a significant variation in salary ranges across different job titles. Senior Data Scientist positions tend to have the highest salary potential, with up to $600K, indicating the high value placed on advanced data skills and experience in the industry.

-Senior Data Engineer and Senior Data Scientist roles show a considerable number of outliers on the higher end of the salary spectrum, suggesting that exceptional skills or circumstances can lead to high pay in these roles. In contrast, Data Analyst roles demonstrate more consistency in salary, with fewer outliers.


-The median salaries increase with the seniority and specialization of the roles. Senior roles (Senior Data Scientist, Senior Data Engineer) not only have higher median salaries but also larger differences in typical salaries, reflecting greater variance in compensation as responsibilities increase.




# The  Analysis 
## 4. What is the most optimal skill to learn fro Data Analysts?

### Visualize Data

```python
from adjustText import adjust_text
import matplotlib.pyplot as plt

plt.scatter(df_DA_skills_high_demand['skill_percent'], df_DA_skills_high_demand['median_salary'])
plt.show()
```
### Visualize Data

![Most Optimal Skills for Data Analysts in the US](image-1.png)

#### Insights:

-The scatter plot shows that most of the programming skills (colored blue) tend to cluster at higher salary levels compared to other categories, indicating that programming expertise might offer greater salary benefits within the data analytics field.

-Analyst tools (colored green), including Tableau and Power BI, are prevalent in job postings and offer competitive salaries, showing that visualization and data analysis software are crucial for current data roles. This category not only has good salaries but is also versatile across different types of data tasks.

-The database skills (colored orange), such as Oracle and SQL Server, are associated with some of the highest salaries among data analyst tools. This indicates a significant demand and valuation for data management and manipulation expertise in the industry.



# What I Learned

Throughout this project, I deepened my understanding of the data analyst job market and enhanced my technical skills in Python, especially in data manipulation and visualization. Here are a few specific things I learned:

-Advanced Python Usag: Utilizing libraries such as Pandas for data manipulation, Seaborn and Matplotlib for data visualization, and other libraries helped me perform complex data analysis tasks more efficiently.
-Data Cleaning Importanc: I learned that thorough data cleaning and preparation are crucial before any analysis can be conducted, ensuring the accuracy of insights derived from the data.

-Strategic Skill Analysi: The project emphasized the importance of aligning one's skills with market demand. Understanding the relationship between skill demand, salary, and job availability allows for more strategic career planning in the tech industry.



# Insights

This project provided several general insights into the data job market for analysts:

-Skill Demand and Salary Correlatio: There is a clear correlation between the demand for specific skills and the salaries these skills command. Advanced and specialized skills like Python and Oracle often lead to higher salaries.

-Market Trend: There are changing trends in skill demand, highlighting the dynamic nature of the data job market. Keeping up with these trends is essential for career growth in data analytics.

-Economic Value of Skill: Understanding which skills are both in-demand and well-compensated can guide data analysts in prioritizing learning to maximize their economic returns.



# Challenges I Faced

This project was not without its challenges, but it provided good learning

-Data Inconsistencies
-Complex Data Visualization
-Balancing Breadth and Depth


# Conclusion

This exploration into the data analyst job market has been incredibly informative, highlighting the critical skills and trends that shape this evolving field. The insights I got enhance my understanding and provide actionable guidance for anyone looking to advance their career in data analytics. As the market continues to change, ongoing analysis will be essential to stay ahead in data analytics.This project is a good foundation for future explorations and underscores the importance of continuous learning and adaptation in the data field