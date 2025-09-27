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
