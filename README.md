# Twitter-Data-Analytics


# Twitter_Analytics_Dashboard

### Dashboard Link : https://app.powerbi.com/view?r=eyJrIjoiZTM5OWZkMjAtYjE5MS00MDYzLTlmOWMtNGQwZGY4OTVmYzc0IiwidCI6Ijg2YTg3NTRlLTg3ZGUtNGMwZC1hOTVhLTZmMGQzZjA0YjRhMCJ9

# Introduction

This project aims to explore Twitter data and create visualizations to answer key questions about user engagement, content performance, and timing. Specifically, we will focus on three tasks:

#### Task 1: Click Distribution

 Analyze the distribution of clicks (URL clicks, user profile clicks, and hashtag clicks) for tweets with over 500 impressions, using a pie chart with drill-down capabilities.

#### Task 2: Top-Performing Tweets

 Identify the top 10 tweets by retweets and likes, filtering out weekend tweets, and visualize the results in a chart that displays user profiles, while considering specific time, even impression, odd date, and word count constraints.

#### Task 3: Media Engagement Comparison

 Compare the number of replies, retweets, and likes for tweets with media engagements above the median value, using a visualization that filters tweets by date range, time, odd date and even media views and word count.

By completing these tasks, we will gain a deeper understanding of Twitter user behavior, identify optimal posting times and content strategies, and develop data-driven insights to inform future social media marketing efforts.

# Background

Twitter is a popular social media platform with millions of active users. Analyzing Twitter data can provide valuable insights into user behavior, preferences, and engagement patterns. This project uses Twitter data to create visualizations that inform marketing strategies and improve engagement.

# Learning Objectives

#### Technical Skills

1. Data visualization using pie charts, bar charts and other visuals.
2. Data filtering and sorting using Power BI.
3. Data manipulation using DAX.
4. Using conditional statements and logical operators (e.g., IF, AND, OR)
5. Working with date and time data (e.g., weekday, hour, day)
6. Creating drill-down capabilities for interactive visualizations
7. Developing filters for specific date ranges and times.

#### Data Analysis Skills

1. Identifying and selecting relevant data for analysis
2. Applying filters to narrow down data
3. Ranking and sorting data to identify trends
4. Interpreting data visualizations to draw insights
5. Using data to tell a story or support a hypothesis
6. Analyzing engagement metrics (e.g., clicks, retweets, likes)
7. Understanding the importance of median values in data analysis

#### Critical Thinking Skills

1. Breaking down complex problems into manageable tasks
2. Identifying patterns and relationships in data
3. Evaluating data quality and potential biases
4. Considering multiple perspectives when interpreting data
5. Drawing meaningful conclusions from data analysis
6. Recognizing the importance of filtering and sorting data
7. Understanding the impact of time and date on engagement metrics

#### Business Acumen Skills

1. Understanding the importance of social media analytics.
2. Using data to inform business decisions.
3. Recognizing the value of data-driven insights.
4. Analyzing engagement metrics to optimize social media strategy.
5. Understanding the impact of timing on social media engagement.

#### Soft Skills

1. Attention to detail
2. Organizational skills
3. Time management
4. Problem-solving
5. Ability to work with complex data sets
6. Ability to interpret and communicate insights effectively



# Activities and Tasks 

### Task 1

Step 1: Data Preparation

- Load tweet data into Power BI.

- Create calculated column:

        Impression Filter: SocialMedia[impressions] > 500
   
Step 2: Filtering

- Apply filter: Impression Filter = TRUE

Step 3: Pie Chart Creation

- Create a Pie Chart.

- Add fields:

      Sum of Url clicks(value)
      Sum of User profile clicks(value)
      Sum of Hashtag clicks(value)

Step 4: Formatting

- Set chart title: "Proportion of Url clicks, User profile clicks and Hashtag Clicks (Impressions > 500)".

- Adjust colors, fonts, and layout.

#### Final Visualization

A pie chart representing the proportion of Url clicks, User profile clicks and Hashtag clicks for tweets with Impressions > 500

## Task 2

Step 1: Data Preparation

- Load tweet data into Power BI.

- Create calculated columns:

      Weekday Filter: WEEKDAY('SocialMedia'[Date]) <> 1&& WEEKDAY('SocialMedia'[Date]) <> 7 (excludes weekends)

      Time Filter: HOUR('SocialMedia'[Time]) >= 15 && HOUR('SocialMedia'[Time]) <= 18 (3 PM - 6 PM)

      Impression Filter:MOD('SocialMedia'[impressions],2) = 0 (even impressions)

      Date Filter: MOD(DAY('SocialMedia'[Date]), 2) = 1 (odd date)

      Word Count Filter: LEN('SocialMedia'[Tweet]) < 30 (word count < 30)

      Retweets & Likes: ('SocialMedia'[retweets]) + ('SocialMedia'[likes]) (sum of retweets and likes)

Step 2: Filtering

- Apply filters:

      Weekday Filter = TRUE
      Time Filter = TRUE
      Impression Filter = TRUE
      Date Filter = TRUE
      Word Count Filter = TRUE

Step 3: Chart Creation

- Create a Top N Bar chart

- Add fields:

      Sum of Retweets & Likes (value)
      Tweet (legend)
      id (tooltip)
      Date (tooltip)

Step 4: Sorting and Top 10

- Sort by Sum of Retweets & Likes in descending order.

- Set Top N to 10.

Step 5: Formatting

- Set chart title: "Top 10 Tweets by Sum of Retweets and Likes".

- Adjust colors, fonts, and layout.

#### Final Chart

A bar chart showing the top 10 tweets by Retweets & Likes (retweets + likes), filtered by:

- Weekdays (excluding weekends)
- 3 PM - 6 PM time frame
- Even tweet impressions
- Odd tweet dates
- Tweet word count < 30

Each bar represents a tweet, with:

- Sum of Retweets & Likes (value)
- Tweet (legend)
- id (tooltip)
- Date (tooltip)

## Task 3

Step 1: Data Preparation

- Load tweet data into Power BI.
- Create calculated columns:

      Mediafilter = ('SocialMedia'[media engagements]) > MEDIAN('SocialMedia'[engagements])
      Datefilter = MONTH('SocialMedia'[Date]) >= 6 && MONTH('SocialMedia'[Date]) <= 8 && YEAR('SocialMedia'[Date]) = 2020
      Timefilter = HOUR('SocialMedia'[Time]) >= 15 && HOUR('SocialMedia'[Time]) <= 18
      Odd Date = MOD(DAY('SocialMedia'[Date]), 2) = 1
      Even Media views = MOD('SocialMedia'[media views], 2) = 0
      Wordcount = LEN('SocialMedia'[Tweet]) < 50

Step 2: Filtering

- Apply filters:

      Mediailter = TRUE
      Datefilter = TRUE
      Timefilter = TRUE
      Odd Date = TRUE
      Even Media Views = TRUE
      Word Count = TRUE

Step 3: Visualization

- Create a Bar Chart.

- Add fields:

      Sum of replies (value)
      Sum of retweets (value)
      Sum of likes (value)
      Date (tooltip)

Step 4: Formatting

- Set chart title: "Replies, Retweets and Likes Comparision".
- Adjust colors, fonts, and layout.


#### Final Visualization

A bar chart comparing the number of:

- Replies
- Retweets
- Likes

For tweets with:

- Media engagements > median value
- Posted between June-August 2020
- 3 PM-6 PM time frame
- Odd tweet dates
- Even media views
- Tweet word count < 50

# Skills and Competencies

#### Task 1: Pie Chart with Drill-Down

1. Data Visualization: Create interactive and dynamic visualizations using pie charts.
2. Data Filtering: Filter data based on specific conditions (e.g., impressions > 500).
3. Data Analysis: Analyze click data and calculate proportions.
4. Drill-Down Capability: Create interactive drill-down features to view specific click types.
5. Attention to Detail: Ensure accurate data representation and visualization.

#### Task 2: Top 10 Tweets Chart

1. Data Analysis: Analyze engagement metrics (retweets, likes) and calculate sums.
2. Data Filtering: Filter data based on specific conditions (e.g., weekdays, 3 PM-6 PM, even impressions, odd dates, < 30 words).
3. Ranking and Sorting: Rank tweets by engagement sum and sort by user profile.
4. Data Visualization: Create interactive and dynamic visualizations using bar charts.
5. Critical Thinking: Identify top-performing tweets and understand engagement patterns.

#### Task 3: Media Engagements Visualization

1. Data Analysis: Analyze media engagement metrics (replies, retweets, likes) and calculate comparisons.
2. Data Filtering: Filter data based on specific conditions (e.g., June-August 2020, 3 PM-6 PM, odd dates, even media views, < 50 words).
3. Data Visualization: Create interactive and dynamic visualizations using bar chart.
4. Median Value Calculation: Calculate median media engagement values.
5. Critical Thinking: Identify engagement patterns and trends in media engagements.

# Feedback and Evidence

Task 1: Click Distribution Pie Chart
- Effective use of colors and labels in the pie chart.
- Drill-down capability allows for detailed analysis of each tweet's click distribution.
- Adding a tooltip to display exact click numbers.
- Ensure the chart is responsive and adjustable for various screen sizes.
- Screenshot of the pie chart with drill-down functionality.
![Task_1](https://github.com/user-attachments/assets/ef72a477-ca03-444b-8704-44361407ca98)

Task 2: Top-Performing Tweets Chart
- Clear visualization of top-performing tweets and their engagement metrics.
- Effective filtering and sorting of tweets based on specific criteria.
- Ensure the chart is interactive, allowing users to hover over or click on bars for more information.
- Screenshot of the top-performing tweets chart.
![Task_2](https://github.com/user-attachments/assets/b669b187-cc75-42dc-a633-2874f38d4e65)
Task 3: Media Engagement Comparison Visualization
- Effective comparison of engagement metrics for tweets with high media engagement.
- Clear filtering and sorting of tweets based on specific criteria.
- Screenshot of the media engagement comparison visualization.
![Task_3](https://github.com/user-attachments/assets/3b4cf149-09eb-4100-8d69-d49cde55af39)


- Ensuring all visualizations are interactive and allow for user exploration.
- Using clear and concise labels, titles, and legends.

# Challenges and Solutions

#### Challenges
1. Data quality issues (e.g., missing or incorrect click data)
2. Difficulty in designing an effective drill-down functionality
3. Ensuring the pie chart is interactive and responsive
4. Filtering and sorting large datasets efficiently
5. Ensuring the chart is interactive and allows for user exploration
6. Handling tweets with multiple profiles
7. Calculating median media engagement values accurately
8. Ensuring the visualization effectively compares engagement metrics
9. Handling tweets with missing or incorrect media engagement data

#### Solutions
1. Data cleaning and preprocessing to ensure accurate click data
2. Using interactive visualization to create drill-down functionality
3. Implementing responsive design principles to ensure the chart adapts to different screen sizes
4. Using data filtering and sorting to efficiently process data.
5. Implementing interactive visualization to create interactive charts.
6. Developing a clear methodology for handling tweets with multiple authors or profiles
7. Using DAX query to calculate median values accurately
8. Implementing visualization best practices (e.g., using clear labels, colors) to effectively compare engagement metrics
9. Developing a data cleaning and preprocessing pipeline to handle missing or incorrect media engagement data

# Outcomes and Impact


1. Improved understanding of user engagement: The pie chart provides insights into the types of clicks (URL, user profile, hashtag) that occur on tweets with high impressions.
2. Identified areas for optimization: By analyzing the click distribution, we can identify areas where tweets can be optimized to increase engagement (e.g., using relevant hashtags).
3. Enhanced social media strategy: The visualization informs our social media strategy by highlighting the importance of including engaging elements (e.g., links, hashtags) in tweets.
4. Identified top-performing content: The chart highlights the most engaging tweets, allowing us to understand what content resonates with our audience.
5. Informed content creation: By analyzing the top-performing tweets, we can create more effective content that resonates with our audience.
6. Increased engagement: By promoting top-performing tweets, we can increase engagement and reach a wider audience.
7. Understanding of media engagement patterns: The visualization reveals patterns in media engagement (replies, retweets, likes) for tweets with high media engagement.
8. Identified opportunities for improvement: By comparing engagement metrics, we can identify areas where tweets can be improved to increase media engagement.
9. Enhanced media strategy: The visualization informs our media strategy by highlighting the importance of creating engaging multimedia content.

# Conclusion

This project demonstrates the power of data visualization in understanding social media engagement and informing marketing strategies. By analyzing Twitter data, we gained valuable insights into user behavior, content performance, and media engagement patterns. These insights can be used to optimize social media content, increase engagement, and improve overall marketing effectiveness.

The project's outcomes and impact highlight the importance of data-driven decision-making in social media marketing. By leveraging data visualization tools and techniques, businesses can unlock the full potential of their social media data and drive meaningful engagement with their audience.
