# The Analysis

## 1. What are the most demanded skills for the   top 3 most popular data roles?

The objective here is to determine the skills that are in most demand for the top three (3) most popular data roles. The combination of each skill for each data role was counted before been filtered for the three most popular data roles. The popular data roles were obtained from counting how often they occur in the dataset used. 
Results from this assessment can aid in knowing what skills rank uppermost for any data role so that anyone aspiring for such roles will know what skills to concentrate on (and pay attention to).


View my notebook with detailed steps here:
[2_Skills_Demand.ipynb](3_Project\2_Skills_Demand.ipynb)

## Visualize Data

    
    fig, ax = plt.subplots(len(job_titles), 1)

    sns.set_theme(style = 'ticks')

    for i, job_title in enumerate(job_titles):
        df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head(5)
        sns.barplot(data = df_plot, x = 'skills_percent', y = 'job_skills',  ax = ax[i], hue = 'skills_count', 
        palette = 'dark:b_r')

    plt.show()




### Results
![Visualize the top skills for Data Roles](3_Project\skills_requested_in_US_JobPosts.png)