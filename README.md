# Google Data Analytics Course - Capstone Project using Python (January 2025)
# Case study: How does a bike-share navigate speedy success?  🚴🚲👩‍💻📈📊

This project contains a solution using Python for the Capstone of [Google Data Analytics Professional Certificate Program](https://www.coursera.org/professional-certificates/google-data-analytics) from [Google](https://www.coursera.org/google-career-certificates) 

> This project was inspired by a [previous implementation](https://github.com/carlacotas/google-data-analytics-capstone-case-study-trackA-cyclistic) I developed using the R programming language. Although this version using Python is a distinct solution, some phrases and ideas in the presentation of this solution may be similar to the original R project. This is intentional, as the challenge and problem-solving approach remains consistent across both implementations.

## Google Data Analytics Course 📈📊 

- Professional training designed by Google 🟢🔵🔴🟡
- Prepare for a career in Data Analytics
- 8 Course series, including Google Data Analytics Capstone: Complete a Case Study

> This project is my proposed solution using Python on the Cyclistic bike-share analysis case study! 

<br/>

## Introduction 

In this case study, I will take on the role of a junior data analyst performing real-world tasks for a fictional company, Cyclistic, working in the marketing analytics team. To address the business questions, I will follow the steps of the data analysis process: [Ask](#ask), [Prepare](#prepare), [Process](#process), [Analyze](#analyze), [Share](#share), and [Act](#act).

<br/>


## Background and Business Question

### Cyclistic

Cyclistic, a bike-share company in Chicago, launched in 2016 a successful bike-share offering. Since then, has grown to 5,824 geotracked bicycles and locked into a network of 692 stations across Chicago. Cyclistic bikes can be accessed from one station and returned to any other station in the network, anytime. This bike-share program includes traditional bikes and more inclusive options like reclining bikes, hand tricycles, and cargo bikes useful to people with disabilities and riders who can’t use a standard two-wheeled bike. While most users ride for leisure, 30% use the bikes for commuting to work each day.

Cyclistic offers flexible pricing plans: single-ride passes, full-day passes (for casual riders), and annual memberships (for members). Cyclistic’s finance analysts have found that annual members are more profitable, and the director of marketing sees an opportunity to grow by converting casual riders into members, as they are already familiar with the Cyclistic program. Rather than targeting all-new customers, she believes the focus should be on converting casual riders into members, as they are already familiar with Cyclistic and rely on it for their mobility needs.

<br/>

### Characters and teams

- **Cyclistic marketing analytics team:** A team of data analysts who are responsible for collecting, analyzing, and reporting data that helps guide Cyclistic marketing strategy.

- **Cyclistic executive team:** The notoriously detail-oriented executive team.

- **Lily Moreno:** The director of marketing and the manager of my team. Moreno is responsible for the development of campaigns and initiatives to promote the bike-share program. These may include email, social media, and other channels. She believes the company’s future success depends on maximizing the number of annual memberships.

- **Carla Cotas:** A junior data analyst working in the marketing analytics team. My team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve the recommendations, so they must be backed up with compelling data insights and professional data visualizations. 

<br/>

### Scenario 

**Moreno has set a clear goal:** Design marketing strategies aimed at converting casual riders into annual members.

*In order to do that, however, my team needs to better understand how annual members and casual riders differ, why casual riders would buy a membership, and how digital media could affect their marketing tactics. Therefore, Moreno and her team are interested in analyzing the Cyclistic historical bike trip data to identify trends.*

<br/>

## Ask 

### Analysis Questions

Three questions will guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

The first question to answer was assigned to me: **_How do annual members and casual
riders use Cyclistic bikes differently?_**

<br/>

## Prepare

### Folder Structure

The local directory, folders, sub-folders and file-naming conventions follow the structure below:

```
|--20250109_CyclisticBikeShare
  |-- 1.OriginalData
  |-- 2.PreparedData
  |-- 3.UploadedData
    |-- YYYYMMDD
  |-- 4.Analysis
    |-- DataErrors
      |-- AutomaticallyExcludedResults
      |-- ManuallyExcludedResults
    |-- PythonCode
    |-- Figures
  |-- 5.Insights
    |-- MyInsights
    |-- SharedInsights
  |-- 6.Final
    |-- Report
    |-- Presentation
```


### Data Source

Cyclistic’s historical trip data to analyze and identify trends is available [here](https://divvy-tripdata.s3.amazonaws.com/index.html).

This study analyzes and identifies trends from the previous 12 months: January 2024 to December 2024 (‘202401-divvy-tripdata.csv’ → ‘202412-divvy-tripdata.csv’).

*The data has been made available by Motivate International Inc. under this [license](https://divvybikes.com/data-license-agreement). This is public data that can use to explore how different customer types are using Cyclistic bikes. But note that data-privacy issues prohibit from using riders’ personally identifiable information. This means that you won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.*

### Data Preparation

> ⚠️ **Note:** Im my [previous implementation](https://github.com/carlacotas/google-data-analytics-capstone-case-study-trackA-cyclistic) I used Posit’s RStudio and I could only complete this project in R focusing the first previous 6 months: November 2023 to April 2024 (‘202311-divvy-tripdata.csv’ → ‘202404-divvy-tripdata.csv’) because Posit’s RStudio not crashed due to Memory Usage. However, when using Python for this project, I don't have this Memory Usage problem and I was able to do a more complete analysis, completing [further anaysis points](https://github.com/carlacotas/google-data-analytics-capstone-case-study-trackA-cyclistic?tab=readme-ov-file#act) identified in the previous study in R. 

The Cyclistic’s historical trip data is available to download in zip files (‘202401-divvy-tripdata.zip’ to ‘202412-divvy-tripdata.zip’). After downloaded and stored in a folder (1.OriginalData), the zip files were unzipped locally giving the original .CSV data files (‘202401-divvy-tripdata.csv’ to ‘202412-divvy-tripdata.csv’). This study uses Python 3.8 for the analysis because it is a widely used programming language in data analytics, providing extensive data libraries.

The original data files, naming convention of YYYYMM-divvy-tripdata, were loaded into Python and renamed for simplicity and improve readability.
