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


### Recommendations
