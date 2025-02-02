# Power BI Data Project: Global Quality of Life Index

# Overview

I chose this project as my second project due to my passion for travel and plans to relocate in the future. The project involves data exploration, cleaning, transformation, and manipulation, along data visualization that demonstrates my skills in using Power Query and visualization tools within Power BI. The dashboard aims to help travelers, expats, institutions, and organizations analyze and assess quality of life across countries. Sourced from Kaggle, the dataset includes quality-of-life metrics such as purchasing power, safety, healthcare, cost of living, traffic, pollution, and overall quality of life, offering both numerical scores and descriptive categories for a comprehensive analysis.


# Table of Contents

- [Objective](#objective)
- [Data Source](#data-source)
- [Stages](#stages)
- [Design](#design)
- [Development](#development)
  - [Process Outline](#process-outline)
  - [Data Extraction](#data-extraction)
  - [Data Exploration and Cleaning](#data-exploration-and-cleaning)
  - [Data Transformation and Manipulation](#data-transformation-and-manipulation)
- [Visualization](#visualization)
  - [Dashboard](#dashboard)
- [Analysis & Findings](#analysis-and-findings)
- [Recommendations](#recommendations)



# Objective

To provide a comprehensive, data-driven analysis of quality of life across different countries and help travelers, expats, government institutions, and organizations make informed decisions about relocation, policy-making, and investment opportunities by visualizing global trends and rankings.


# Data Source

The [data](https://www.kaggle.com/datasets/ahmedmohamed2003/quality-of-life-for-each-country) is sourced from Kaggle (an Excel extract). The dataset consists of columns such as but not limited to:

| Column_Name | Description |
| --- | --- |
| country | Name of the country. |
| Purchasing Power Value | Numeric score for purchasing power |
| Purchasing Power Category | Qualitative category for purchasing power |
| Quality of Life Value | Numeric score for overall quality of life |
| Quality of Life Category | Qualitative quality of life category. | 
| Cost of Living Value | Numeric score for cost of living |
| Cost of Living Category | Qualitative cost of living category |
| Safety Value |  Numeric safety index score |
| Safety Category | Qualitative safety category |


# Stages

- Design
- Development
- Visualization
- Analysis
- Recommendation


# Design

## Design Considerations

- Below are the design considerations and key questions that guided the creation of the initial visualization:

    - How can we effectively display key quality-of-life metrics for different countries at a glance?
    - What visualizations best highlight the top and bottom-ranked countries in each category?
    - How can we visualize the relationships between multiple quality-of-life factors (e.g., cost of living, safety, healthcare) across countries?

## Dashboard Mockups

- Below dashboard was created using Mokkup AI. 

![Dashboard mockup](assets/images/Dashboard_Mockup.png)
 



# Development


## Process Outline

What was the step-by-step approach to executing this project from start to finish?

1.	Extract data and load it to Power Query in Power BI
2.	Explore, clean and transform the data through Power Query Editor
3.	Create visualizations in Power BI
4.	Provide the analysis and recommendation based on the findings
5.	Write the documentation process in GitHub
6.	Publish the data to GitHub Pages


## Data Extraction

This was the first stage, where the dataset was extracted and loaded using Power Query Editor in PowerBI. 

![data_extraction](assets/images/data_extraction.png)


## Data Exploration and Cleaning

This was the stage where data was scanned for any errors, inconsistencies, blanks, duplicates, and unusual characters. 

1. First, column profiling was changed to based on entire data set.

![column_profiling](assets/images/column_profiling.png)

2. Dataset was examined for any duplicates. No duplicates were found.
   
3. Data types were then checked through column header types, as well as if there are no blanks, NULL values using the column quality, distribution and profile features of power query. 

- The snapshot below shows that the data types for both the property price-to-income value and the quality of life value are incorrectly set to "Text" and should be changed to "Decimal Number."

![datatype_change](assets/images/datatype_change.png)

4. Extracted the value for the “Quality of Life Value” column in between delimiters and replaced NULL values with 0.

![QOL_zero](assets/images/QOL_zero.png)

5. Extracted the text between the delimiters in each category column.

![between_delimiter](assets/images/between_delimiter.png)

6. Filtered out zero and “None” values as they represent missing or incomplete information that could lead to inaccurate analysis and visualizations if included.



## Data Transformation and Manipulation

This was the stage where additional queries were created using the dataset. These queries would be used as additional data and support for the data visuals.

1. Created an additional query "Average per Metric" by duplicating the original query. This query is to get the total average value per quality of life metric.

![averagepermetric](assets/images/averagepermetric.png)

  - Removed columns other than those containing the numeric values.
    
    ![removedcolumns](assets/images/removedcolumns.png)
    
  - Unpivoted the columns

    ![unpivot](assets/images/unpivot.png)
    
  - Aggregated the columns using the GROUP BY function to get the total average per key metric

    ![groupby](assets/images/groupby.png)
    ![groupby2](assets/images/groupby2.png)
    
  - Pivoted back the columns
    
    ![pivoted](assets/images/pivoted.png)
    

2. Created multiple set of additional queries to get the ranking of countries per key metric and to sort the categories for the visuals.

![multiplequeries](assets/images/multiplequeries.png)

Rank: 
  - Duplicated the original query and left the country column and a specific key metric numeric column, which is then sorted in ascending order. 
  - Created an index column starting from 1
  - Using the index column, created a new custom column to create a rank for each country.

    ![rank_query](assets/images/rank_query.png)

Sort:
  - Duplicated the rank query and left a specific key metric category column.
  - Removed duplicate rows.
  - Created an index column starting from 1, then renamed to "Sort"

    ![sortquery](assets/images/sortquery.png)



# Visualization

## Dashboard

What does the dashboard looks like?

The dashboard offers an interactive experience with key quality-of-life metrics on the left, a dynamic filled map in the center that lets users filter by country and category, and bar charts on the right showing the top and bottom 10 countries per category. Navigation buttons at the top make it easy for users to explore detailed dashboards for each key metric.

- Dashboard on Default under the Overall Quality Metric

![Global_Quality_of_Life_Index_-_Dashboard](assets/images/Global_Quality_of_Life_Index_-_Dashboard.png)

- Dashboard under the Overall Quality Metric filtered on a specific country

![Global_Quality_of_Life_Index_-_Dashboard_2](assets/images/Global_Quality_of_Life_Index_-_Dashboard_2.png)

- Filled Map with Hover functionality

![Map_Hover_1](assets/images/Map_Hover_1.png)

- Buttons with Hover functionality

![Buttons_Hover_1](assets/images/Buttons_Hover_1.png)

- GIF displaying all of the dashboard's functionalities

![GlobalQualityofLifeIndex_gif](assets/images/GlobalQualityofLifeIndex_gif.gif)



# Analysis & Findings

1. The primary factors that significantly contribute to the Quality-of-Life score in each country include cost of living, safety, purchasing power, and healthcare. Countries classified within the "very high" and "high" categories consistently demonstrated strong performance across these metrics.

2. Countries with higher safety ratings and better healthcare systems tend to experience a more positive quality-of-life assessment, as these factors are essential to the overall stability and well-being of residents.

3. The top 10 countries in terms of overall quality of life are predominantly European, whereas the bottom 10 are primarily comprised of nations from Africa and South Asia.

4. Higher living costs are often associated with greater purchasing power, as individuals in these regions typically earn more, allowing them to afford a higher standard of living despite the increased expenses. This relationship shows how wages and the cost of goods and services affect financial stability and quality of life.


# Recommendations

For Travelers & Expats

1. Countries like Luxembourg, Oman, and the Netherlands offer excellent living conditions, high safety, and strong healthcare systems, making them ideal for relocation.
2. Travelers should exercise caution in countries with low safety scores and weaker healthcare systems, particularly in some African and South Asian regions.

For Business Leaders & Investors

1. Companies should target countries with strong purchasing power for high-value product and service offerings.
2. While some countries rank lower, they offer cost-effective labor and investment opportunities, particularly in growing economies with rising middle-class populations.

For Governments & Other Organizations

1. Countries with low safety scores should prioritize crime reduction, emergency response systems, and public safety reforms. Additionally, nations with high pollution levels should implement stricter environmental policies and invest in cleaner energy solutions to enhance air quality and overall well-being.
2. Organizations should focus on improving healthcare access in lower-ranking countries where healthcare scores are below average. 







