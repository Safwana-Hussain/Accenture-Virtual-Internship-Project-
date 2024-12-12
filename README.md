# Accenture-Virtual-Internship-Project

This project is based on [Forage](https://www.theforage.com/) job simulation program for [Accenture](https://www.theforage.com/simulations/accenture-nam/data-analytics)

# Problem Statement

Social Buzz is a fast-growing social media company with a huge amount of data to manage, including millions of active users and thousands of pieces of content posted daily. As they prepare for an IPO, they need help with scaling their data management and getting ready for the IPO. They aimed to gain insights into the performance of their content categories in order to identify the top 5 most popular categories. This analysis is intended to help them improve their content strategy and enhance audience engagement by calculating and ranking the categories according to a popularity score based on user reactions.

# Key Questions:

1.	What are the top 5 performing categories?
   
2.	What percentage of the total engagement is contributed by each content type?
   
3.	Do the top-performing categories show consistent engagement across all content types, or are they dominated by specific types?
   
4.	Does content creation follow any seasonal trends, such as higher activity during holidays or specific times of the year?
   
5.	Are there specific time blocks where activity peaks?
    
The answers to these questions would provide the foundation for a more focused and effective content strategy.

# Requirements Gathering

The client provided 7 datasets and a data model illustrating the relationships between them. After analyzing the business question, I indentified 3 essential datasets:

•	Reaction Dataset: Included reaction scores linked to content IDs.

•	Content Dataset: Provided information on content types and categories.

•	Reaction Types Dataset: Mapped reaction types to their scores.


# Data Cleaning and Preprocessing

• I filtered each dataset to identify and remove rows with missing or blank data using the "Sort and Filter" option.

• Removed the "User ID" column as it was not relevant to the analysis.

• Standardized column formats, such as renaming the "Type" column to "Content Type" and “Reaction Type in both dataset for clarity.

• Identified and removed duplicate records to prevent skewed results. For instance, I found discrepancies in the "Category" column where some names had quotation marks and others did not, and I used the "Find and Replace" function to correct this inconsistency.  


![image](https://github.com/user-attachments/assets/18167c84-4e11-4678-bca4-b76f1db73475)
![image](https://github.com/user-attachments/assets/6729f157-a1d1-4e16-b63c-74997b91c621)


**Data Modeling**

The preprocessing step involved combining the datasets using VLOOKUP. 
I started with the Reaction dataset as the base and then added the relevant columns from the Content and Reaction Types datasets. This process resulted in a final Merged dataset that was complete and consistent.


<img width="446" alt="image" src="https://github.com/user-attachments/assets/64bfdc52-5752-4a9a-bf4b-3f0ce08cd311" />


# Data Analysis 
  
**Identifying to 5 categories**
 
•	Extracted the "Category" column and removed duplicates.

•	Calculated the total popularity score for each category using the SUMIF function.

•	Ranked categories by their total scores in descending order.

<img width="353" alt="image" src="https://github.com/user-attachments/assets/1badb5d6-0b33-4b09-96e7-1df719763de3" />


**Analyzing Engagement by content type**

To determine how different content types contributed to engagement:

•	Extracted the "Content Type" column and created a unique list.

•	Used SUMIF to calculate total engagement scores for each type.

•	Ranked content types by their scores to identify high and low performers.


![image](https://github.com/user-attachments/assets/103ac1c6-8ffc-4e9a-91e9-fa448a80e0b5)


**Cross-Analyzing Top Categories and Content Types**

To see if top-performing categories showed consistent engagement across all content types:

•	Created a pivot table with categories as rows and content types as columns.

•	Filtered for the top 5 categories identified earlier.

•	Placed content types in the legend and values sections to analyze their engagement distribution.


<img width="629" alt="image" src="https://github.com/user-attachments/assets/da88b68c-7c15-42fd-8868-d81c5d6aaf41" />


**Seasonal and Hourly Trends**

To explore content trends over time:

•	Extracted "Month" and "Hour" from the datetime column using the TEXT function.

<img width="620" alt="image" src="https://github.com/user-attachments/assets/1d390036-a994-4122-8f77-4e843e586632" />

•	Created pivot tables to:

   =>	Analyze total posts by month, with "Month" in rows and "Content ID" in values.
   
   => Analyze hourly trends with “Hour” in rows and "Content ID" in values.

<img width="464" alt="image" src="https://github.com/user-attachments/assets/0ce5d9fd-336b-40f5-be2e-c0d98310613b" />

   
# Data Visualization

The findings were brought to life using Excel visualizations:

•	**Bar Charts**: Highlighted the top 5 categories by popularity scores.

•	**Pie Charts**: Showed the proportional engagement distribution across all categories.

•	**Stacked Bar Charts**: Illustrated content type contributions within the top 5 categories.

•	**Line Charts**: Displayed monthly and hourly trends in content creation and engagement.


<img width="616" alt="image" src="https://github.com/user-attachments/assets/5565a7d2-fabf-4a9c-b07e-6e134cedad11" />



# Key Insight:

•	Top 5 Categories: Animal, Science, Healthy Eating, Technology and Food emerged as the top-performing categories.
   
•	Content Type Contributions: Photos contributed 27% of total engagement, making them the highest-performing content type, while audio lagged at 23%.
   
•	Category-Content Consistency:

   o	For the animal category, photos and audio dominated engagement.
   
   o	For science, photos and videos were the top contributors.
   
   o	Food showed consistent engagement across all content types.
   
   o	For healthy eating, audio & video were dominating content type
   
   o	For technology audio & gif were in the top.
   
•	Seasonal Trends: Content creation peaked in January, May, and August, with over 2,100 posts in each.

•	Hourly Trends: Activity peaked between 12 AM and 1 AM, then slowed until 3 AM. Afternoon activity dipped before rising again after 7 PM.


# Recommendation

•	Focus on High-Performing Categories: Prioritize content creation and engagement strategies around the top-performing categories: Animal, Science, Healthy Eating, Technology, and Food.

•	Optimize Content Creation for Seasonal Trends: Prepare content strategies in advance to align with peak months (January, May, and August) when content creation spikes, ensuring content is fresh and aligned with trends.

•	Target Engagement During Peak Hours: Increase content posting and user engagement efforts when user activity rises, while adjusting for the drop in the afternoon hours.

•	Diversify Content Types Across Categories: While photos dominate engagement in most categories, experiment with mixing other content types (like GIFs and audio) in categories like Food and Science to see if engagement can be boosted.


# Challenges Faced

•	Managing large datasets with inconsistent formats required additional time for standardization.

•	Understanding and applying data model relationships posed initial complexity.


