# Bike Sharing Analysis

### Project Overview

This data analysis project aims to analyze Divvy bike-sharing data to understand user behavior, identify trends, and provide actionable insights to improve service efficiency and user experience. The analysis focuses on various dimensions such as rider types, bicycle types, and start locations over a specified period (April 2023 to March 2024).

### Data Sources

The primary dataset used for this analysis is the Bike Share Data file by Damion from kaggle [Download here](https://www.kaggle.com/datasets/derescio/bike-share-data)

### Tools
- Power Query - data manipulation and calculations
- PowerBI - Creating reports

### Data Cleaning/Preparation
In the initial data preparation phase, we performed the following tasks:
1. Load All Monthly CSV Files                                                                                         
   Begin by loading all 12 CSV files, each representing a month of data, into Power BI.
2. Combine All Monthly Data into One Table                              
   Use the Union function to combine the data from all 12 CSV files into a single table.
3. Create New Columns and Measures           
   Define new calculated columns and measures to enhance the dataset. These will help in performing detailed analysis and creating insightful visuals.
4. Create a New Column for Distance in Kilometers        
   Add a new calculated column to represent the distance in kilometers.
5. Create a New Column for Ride Duration in Minutes:        
   Add another calculated column to calculate the ride duration in minutes. Example DAX formula
   ```sql
   RideDurationMinutes = DATEDIFF([StartTime], [EndTime], MINUTE)```
6. Create New Columns for Date Parts:     
   Add two new columns to break down the start time into days and months
7. Create Metrics and KPIs:  
   Define metrics and Key Performance Indicators (KPIs) to track important performance measures. Example metrics might include total rides, average distance, and average ride duration.
8. Create a New Column to Change Rider Type   
   Add a new calculated column to categorize rider types into "Subscriber" and "One Time Users." Example DAX formula
   ```sql
   RiderType = SWITCH('divvy-tripdata-all-monthes'[member_casual], "member", "Subscriber", "casual", "One Time Users","unknown") ```
9. Design the Report:
    - Move on to the design phase, creating a visually appealing and informative report.
    - Utilize Power BI's visualization tools to create charts, graphs, and other visual elements.
    - Arrange the visuals in a coherent layout, ensuring that the report tells a clear and compelling story.

### Data Scope
  - Total Rides: 5.75 million
  - Rider Types: Subscribers and One-Time Users
  - Bicycle Types: Electric Bike, Classic Bike, Docked Bike
  - Geographical Scope: 1533 starting stations and 1708 ending stations
  - Time Frame: April 1, 2023, to March 31, 2024

### Key Metrics
  - Number of rides by rider type and bicycle type .
  - Average ride duration by rider type and bicycle type .
  - Ride distribution over time .
  - Ride start locations .

### Insights
#### Rider Type Insights
- **Subscribers** dominate in terms of the number of rides with 3.7 million rides compared to 2.1 million rides by **One-Time Users**.
- **One-Time Users** have a significantly higher average ride duration (28.36 minutes) compared to **Subscribers** (12.81 minutes). This could suggest that One-Time Users may be using the service for leisure or longer trips,while Subscribers might be using it more for daily commuting.
#### Bicycle Type Insights
- **Electric Bikes** are the most popular with 2.9 million rides, followed closely by **Classic Bikes** with 2.8 million rides. **Docked Bikes** have the least usage with 0.1 million rides.
- **Docked Bikes** have the highest average ride duration (185.22 minutes), indicating they are used for fewer but longer trips. This anomaly might warrant a deeper investigation.
#### Temporal Insights
- There is a noticeable fluctuation in ride numbers and duration across months. For instance, August 2023 had the highest number of rides (0.46M for Subscribers and 0.31M for One-Time Users).
- The average ride duration also varies, with peaks in different months, indicating possible seasonal effects or special events influencing bike usage.
#### Geospatial Insights
- The map visualization indicates high bike usage around central areas and popular locations like **Streeter Dr & Grand Ave**, **DuSable Lake Shore Dr & Monroe St**, and **Michigan Ave & Oak St**.
- The stations with the highest ride numbers correlate with areas known for high pedestrian traffic and tourist attractions.

### Recommendations
#### 1. Operational Recommendations
- **Increase Bike Availability in High-Demand Areas:** Ensure a higher availability of bikes, especially Electric and Classic Bikes, in central and high-demand areas identified through geospatial analysis.
- **Monitor and Optimize Docked Bike Usage:** Investigate the reasons behind the high average ride duration for Docked Bikes. Consider optimizing docking station locations or introducing more flexible usage policies.
##### 2. Marketing Recommendations
- **Targeted Promotions for One-Time Users:** Since One-Time Users have longer ride durations, targeted promotions or incentives could convert them into Subscribers, potentially increasing overall subscription rates.
- **Seasonal Campaigns:** Utilize the temporal data to create seasonal marketing campaigns that align with peak usage periods, such as summer months and special events.
#### 3. Service Improvement Recommendations
- **Expand Infrastructure:** Based on the data, consider expanding bike lanes and docking stations in high-usage areas to cater to increasing demand and improve user convenience.
#### 4. Analytical Recommendations
- **Integrate Predictive Analytics:** Develop predictive models to forecast demand and optimize bike distribution and maintenance schedules. This can help in proactively managing resources and improving service reliability.
- **Incorporate User Feedback:** Regularly gather and analyze user feedback to identify pain points and areas for improvement. This can lead to more user-centric service enhancements.
