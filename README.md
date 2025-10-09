# The Analysis

## 1. What are the most demanded skills for the   top 3 most popular data roles?

The objective here is to determine the skills that are in most demand for the top three (3) most popular data roles. The combination of each skill for each data role was counted before been filtered for the three most popular data roles. The popular data roles were obtained from counting how often they occur in the dataset used. This dataset was merged with that derived from counting the job postings for each of the top three roles of choice-to facilitate the derivation of the percentage occurrence of each skill. 

Results from this assessment can aid in knowing what skills rank uppermost for any data role so that anyone aspiring for such roles will know what skills to concentrate on (and pay attention to).


View my notebook with detailed steps here:
[2_Skills_Demand.ipynb](3_Project\2_Skills_Demand.ipynb)


### Visualize Data
    
    fig, ax = plt.subplots(len(job_titles), 1)

    sns.set_theme(style = 'ticks')

    for i, job_title in enumerate(job_titles):
        df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head(5)
        sns.barplot(data = df_plot, x = 'skills_percent', y = 'job_skills',  ax = ax[i], hue = 'skills_count', 
        palette = 'dark:b_r')

    plt.show()


### Results
![Visualize the top skills for Data Roles](3_Project\skills_requested_in_US_JobPosts.png)


### Insights
SQL and PYTHON are needed in all three data roles. For a data Scientist, Python features prominently (72%) – meaning almost 3 out of every 4 Data Scientist postings require Python, while for a Data Engineer, it (Python) features significantly (65%), almost as much as SQL (68%). Slightly above half (i.e., 51%) of every Data Analyst job posting requires SQL as a skill.

TABLEAU seems to be the most mentioned and requested DATA VISUALIZATION SKILL for Data Analysts; 28% of all Data Analyst postings require TABLEAU.

Data Engineers require knowledge in CLOUD Technologies like Azure and AWS, with AWS (at 44% mention) being highly sought after.



# The Analysis
## 2. How are in-demand skills trending for Data Analysts?

Analyzing the skills of Data Analysts in the United States within a given year to ascertain if and how they vary monthly. To arrive at this, the data was filtered for only job postings of Data Analysts located in the United States. A count of each skill listed in the job postings was performed and presented with respect to each month using a pivot table. Through the implementation of a group-by function, with respect to the months, the number of job postings per month was also determined. This was used, through the div function, to calculate the likelihood of a job skill appearing in a job posting in a particular month.

The results of this assessment will serve as a guide to any aspiring Data Analyst in the United States in terms of which skills to focus on-and which skills are still important. 

View my notebook with detailed steps here:
[3_Skills_Trend.ipynb](3_Project\3_Skills_Trend.ipynb)


### Visualize Data


    fig, ax = plt.subplots(len(job_titles), 1)

    sns.set_theme(style = 'ticks')

    for i, job_title in enumerate(job_titles):
        df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head(5)
        sns.barplot(data = df_plot, x = 'skills_percent', y = 'job_skills',  ax = ax[i], hue = 'skills_count', 
                                palette = 'dark:b_r')

    plt.show()



### Results
![View graph of trending skills for Data Analysts](3_Project\Trending_Top_Data_Analyst_Skills_in_US.png)


### Insights

SQL is still the most sought-after skill for Data Analysts, as it facilitates querying of databases to pull data needed for analysis. An Indication that virtually all companies have a form of database.

SQL and EXCEL are still highly regarded for a Data Analyst role in the United States, with SQL appearing in more than 45% (on average) of the job postings throughout the year, peaking at almost 51%. EXCEL appears in more than 35% (on average) of the monthly job postings.

All the skills showed a dip in likelihood in November and a rise in December.

Python seems to be needed as much as Tableau especially in the month of December

# The Analysis
## 3. How well do jobs and skills pay for Data Roles?

### Salary Analysis for top roles.
This section involves determining the distribution of average yearly salary for the top job roles, comparing how the pay for the senior cadres compare to the respective non-senior ones.

Answering this first part involved obtaining the data for the jobs in a particular country, by filtering the main dataset for that country (in this case the United States). The most occurring data roles were determined by performing a value counts (in descending order) on the necessary column (job_title_short column) after which it was filtered for the top 6 data roles only.

The order of the median salaries of the data roles was obtained using the dataset filtered for the top roles, performing a group-by on the job titles with a median aggregation on the average yearly salary field. This was then sorted in descending order.

The outcome from this assessment gives an idea of the range of salaries earned by professionals in various cadre for the top roles of the jobs in a country; a good guide in negotiations and financial aspirations. In addition, if one is desirous of a career change, the result can also serve to guide such decisions.

#### Visualize the Data

    sns.boxplot(data = df_US_top6, x = 'salary_year_avg', y = 'job_title_short', order = job_order)

    sns.set_theme(style = 'ticks')

#### Results
![Salary Distribution for Top Data Roles](3_Project\Salary_Distribution_Data_Jobs_in_United_States.png)*Salary Distribution for Top 6 Data Roles in the United States


#### Insights
All Senior cadres of job roles have a higher median salary than their Junior / Non-Senior roles. In-fact all Senior cadres earn more that their Junior roles.

A Data Analyst who desires to earn more money should transition to either Data Engineering or Data Scientist roles.

Data Scientist role has a much higher salary distribution than all the other roles within the salary range of 0k to 600k.

It pays more to be a Data Scientist than a Data Engineer or Data Analyst

### Highest Paid and In-Demand Skills







