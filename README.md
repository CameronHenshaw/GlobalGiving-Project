# GlobalGiving-Project

 ## Retention
Following the advice of Patrick Campbell, I decided to keep things simple and calculate churn (and its inverse, retention) by dividing the total number of churned organizations in a period by the number of partners we had on the first day of that period.
Campbell also argues that churn should be defined as the moment when a customer’s subscription period ends and they don’t renew. Although we’re not looking at subscriptions, I decided that the period of time that a nonprofit is vetted is a good parallel to a subscription period, given that vetting also requires a monetary investment from the nonprofit. We’ll be looking at the churn and retention rates by month (See section 2 of the code file).
 
While retention is helpful, the average period of vetting is two years; if we only pay attention to this retention rate, we have a significant time gap where we do not have information about the organizations' activity. Campbell also makes the point that we should be working to retain organizations before they churn; hence it is important to track organizations' activity before churning actually happens.

We should therefore also pay attention to the percentage of organizations that have had an active project in the last six months; I’ll call this measurement Project Activity Retention. Unfortunately, this dataset only has the last project deactivation date, as far as data relevant to this measurement. This is a problem because we can't determine the start date of projects with this dataset, which means we can't determine how many projects are active at the start of each month to calculate the Project Activity Retention rate. I tried to figure out a way to work around this by creating an estimation with the vetted dates, but ultimately it wasn't working well and wasn't very accurate. This could likely be calculated with the bulk Project file from the API.

Overall, I would measure retention by the overall retention rate (based on the vetted period), the Project Activity retention rate at six months, as well as the Project Activity retention rate at 12 months. Looking at all three of these rates will give us a good picture of the on-going activity of organizations, as well as the final retention rate.

We should also pay attention to the organizations that start using the platform, but never successfully post a project. It seems likely that these organizations are finding barriers to successfully using the platform, and are influenced by different issues than those who do go on to successfully fundraise. However, I think this rate is better suited to more in depth reporting rather than on a dashboard, as the previous rates paint a better large scale picture of retention. 
 
## Correlation and Dashboard
After exploring retention, I wanted to investigate the correlation between different columns in the dataset. In particular, I looked at the time_frame_int column I created, as this contained the number of days until the organizations churned. With this column, I could see what variables correlated with how long organizations used the GlobalGiving platform.

(See Section 3 of the code file)

There was a weak positive linear relationship between the time_frame_int column and  the number of field visits. There was also a weak positive linear relationship between the time_frame_int column and all time unique donors.

There was also a weak negative linear relationship with the ID number. I would guess that this is due to the fact that organizations with higher ID numbers are newer to using GlobalGiving, and therefore have had less opportunity to spend time on the platform.


For a dashboard, I would include the three retention rates, listed at the end of Part 1, as well as a comparison between these rates and the previous months. For example, “95% Six-month project activity retention: 5% higher than previous month.*” This gives us a good idea of the overall picture of retention, while also giving us a comparison to quickly verify if there are large jumps in rates. 

While I found some correlations, I would want to explore the bulk projects data set further, as well as others, to get a better picture of what most correlates with retention rate. After doing this, I would want to include further visuals on the dashboard to demonstrate if there are any big changes in these variables- for instance, a pie chart that highlights that there are an abnormally large percentage of Superstar organizations that had no project activity in the last six months. I’d like to go into this further, but unfortunately I’ve run up against time. 

*Unless there is a stronger yearly pattern; it may be better to compare to the same month of the previous year

## Further investigation:

I really wanted to do a cohort analysis with the bulk project file from the API, but unfortunately I’m not experienced using APIs and ended up spending too much time trying to troubleshoot my code. 

I’d want to investigate:

Are organizations meeting their fundraising goals? 
Is there a correlation between the % of project funded and retention length of organizations?

Is a language barrier a factor in organization retention?
Are organizations from English speaking countries retained longer? 

Are organizations with more staff able to better succeed at using the GlobalGiving platform (meeting fundraising goals), and does this affect the retention of organizations? 

There are many more questions that I’d like to explore, and more I’d like to write here. Unfortunately, I’ve run out of time!

