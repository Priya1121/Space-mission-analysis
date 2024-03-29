# Space-mission-analysis

# Airlines-Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/7f2cfeae-416d-4d4b-ae6e-9d85e3057e80?ctid=75c6a54f-cdc9-4ed2-941c-7096cf7dbda0&pbi_source=linkShare

## Introduction

This interactive platform provides a comprehensive overview of space missions conducted over the years, offering valuable insights into the exploration of outer space.

In the dataset we the following columns:
1) Company
2) Location
3) Date
4) Time
5) Rocket
6) Mission
7) Price
8) Mission_status
### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present except column named "Price".
- Step 5 : In Power BI Query Editor,we convert the datatype of the Price in whole number type from the text type.
- Step 6 : Now we multiple the price column with 1000000 
- Step 7 : Now we create a new table for the date.
- Step 8 :for that we wrote the following query 
Date_table = ADDCOLUMNS(CALENDAR(MIN(space_missions[Date]),MAX(space_missions[Date])),"Year",YEAR( [Date] ),"Month",format([Date],"mmm"),"Month-num",FORMAT([Date],"mm"))
- Step 9 : Now in the model view we create a many to one relation between the table of date and space mission. 
         
- Step 10 : Now we created the measure to calculate the total number of mission by each company.
For that we use the following query:

total mission = Count(space_missions[Mission])
- Step 11 : Then we created another measure that is no. of successful missions per company using the following query:

successful_mission = CALCULATE(COUNT(space_missions[Mission]),space_missions[MissionStatus]="Success")

- Step 12 : Similarly we find the other measures like Failed, Partially failed, Prelaunch failure, Active rocket using the following query:

Failed_mission = CALCULATE(COUNT('space_missions (2)'[Mission]),'space_missions (2)'[MissionStatus]="Failure")

Partially_failed = CALCULATE(COUNT('space_missions (2)'[Mission]),'space_missions (2)'[MissionStatus]="Partial Failure")

Prelaunch_failure = CALCULATE(COUNT('space_missions (2)'[Mission]),'space_missions (2)'[MissionStatus]="PreLaunch Failure")

Active_Rockets = CALCULATE(COUNT('space_missions (2)'[Rocket]),'space_missions (2)'[RocketStatus]="Active")
- Step 13 : Now we first set a black background of the dashboard then start making KPIs.

- Step 14 : select the text box then drag the value of total mission in it,
Similiary we will make the KPIs for the successful missions, sum of price, count of company, active rockets

        
- Step 15 : Then we create a bar chart to show the total number of successful missions of the top 15 companies.for this we use the filter pane where we selected the top N filter over the company. 
        
 - Step 16 : Another bar chart with the values company at y axis and successful_mission,Failed_mission,Prelaunch_failure,Partially_failed values in the x axis.
 
 - Step 17 : A donut chart to show the distribution of price by top 10 company. 
 
- Step 18 : A line chart to show the distribution of total number of mission per year.
