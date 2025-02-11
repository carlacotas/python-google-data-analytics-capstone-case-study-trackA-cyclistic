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

The Cyclistic’s historical trip data is available to download in zip files (‘202401-divvy-tripdata.zip’ to ‘202412-divvy-tripdata.zip’). After downloaded and stored in a folder (1.OriginalData), the zip files were unzipped locally giving the original .CSV data files (‘202401-divvy-tripdata.csv’ to ‘202412-divvy-tripdata.csv’). This study uses Python 3.11 for the analysis because it is a widely used programming language in data analytics, providing extensive data libraries.

The original data files, naming convention of YYYYMM-divvy-tripdata, were imported into Python.

```
CyclisticTripData_2024_01 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202401-divvy-tripdata.csv')
CyclisticTripData_2024_02 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202402-divvy-tripdata.csv')
CyclisticTripData_2024_03 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202403-divvy-tripdata.csv')
CyclisticTripData_2024_04 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202404-divvy-tripdata.csv')
CyclisticTripData_2024_05 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202405-divvy-tripdata.csv')
CyclisticTripData_2024_06 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202406-divvy-tripdata.csv')
CyclisticTripData_2024_07 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202407-divvy-tripdata.csv')
CyclisticTripData_2024_08 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202408-divvy-tripdata.csv')
CyclisticTripData_2024_09 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202409-divvy-tripdata.csv')
CyclisticTripData_2024_10 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202410-divvy-tripdata.csv')
CyclisticTripData_2024_11 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202411-divvy-tripdata.csv')
CyclisticTripData_2024_12 = pd.read_csv('~/projects/20250109_CyclisticBikeShare/1.OriginalData/202412-divvy-tripdata.csv')

print('Importing original data files completed!')

```

A check summary data of each dataframe about structure and information was performed for exploring consistency in the column numbers to ensure the same number of columns and the same column names before moving to the next step and merge them in only one data set.

```
CyclisticTripData_2024_01.info()
```
![image](https://github.com/user-attachments/assets/72df52a0-64ff-4c0e-998c-e03eda92bae2)

```
CyclisticTripData_2024_02.info()
```
![image](https://github.com/user-attachments/assets/1d191b46-2565-402f-a4e7-8d82dc42e0af)

```
CyclisticTripData_2024_03.info()
```
![image](https://github.com/user-attachments/assets/e84d9242-8975-4bce-b640-77eea9295f09)

```
CyclisticTripData_2024_04.info()
```
![image](https://github.com/user-attachments/assets/4e793338-1578-410b-94cb-bc9042a21637)

```
CyclisticTripData_2024_05.info()
```
![image](https://github.com/user-attachments/assets/a69c1c18-d917-4d1f-8e1f-350ce9ef1e85)

```
CyclisticTripData_2024_06.info()
```
![image](https://github.com/user-attachments/assets/4f206865-8eb0-4325-bdcb-9b0698a24e64)

```
CyclisticTripData_2024_07.info()
```
![image](https://github.com/user-attachments/assets/37cf9752-6710-49b0-9684-891389472913)

```
CyclisticTripData_2024_08.info()
```
![image](https://github.com/user-attachments/assets/71be4d6e-0ea9-41d3-a9e0-afd981e4c33b)

```
CyclisticTripData_2024_09.info()
```
![image](https://github.com/user-attachments/assets/012c873a-723e-4e56-8154-7fdbe06424ab)

```
CyclisticTripData_2024_10.info()
```
![image](https://github.com/user-attachments/assets/49ccf8a0-15d4-4b8b-8343-8e69f4b9e1a1)

```
CyclisticTripData_2024_11.info()
```
![image](https://github.com/user-attachments/assets/6e33e011-d5c7-461d-9ecc-51dc1864a5d0)

```
CyclisticTripData_2024_01.info()
```
![image](https://github.com/user-attachments/assets/8c32c633-58d1-4b8d-ad04-e466750c83a5)


Key findings:
- the data is organized in CSV (comma-separated values) format
- there are consistency in the column numbers and column names
- there are consistency on the column types, 4 columns has data type _‘float64’_ and 9 columns has data type _‘object’_
- the column labels include ride id, rideable type, started and ended time, start and end station - name, id, latitude and longitude - and member type
- the number of observations is different every month


The data can be trusted, it is published in a trustworthiness source and it is aligned with the question that was assigned to me. However, all ride ids are unique and due to data privacy prohibiting using rider's personally identifiable information, it will not be possible to determine if riders have purchased multiple single passes and, also, determine if riders live in the Cyclistic service area. Now that a description of all data sources used has been explored, the data is ready to be processed and cleaned for analysis.

<br/>

## Process

In this step, the 12 dataframes are combined into one dataframe, clean it and manipulate it.

### Data cleaning

The consistency in column names, column types and number of columns in each dataframe makes it possible that the 12 dataframes can be combined into only one dataframe for analyzing 12 months of data.

```
dataframes = [CyclisticTripData_2024_01, CyclisticTripData_2024_02, CyclisticTripData_2024_03, 
              CyclisticTripData_2024_04, CyclisticTripData_2024_05, CyclisticTripData_2024_06,
              CyclisticTripData_2024_07, CyclisticTripData_2024_08, CyclisticTripData_2024_09,
              CyclisticTripData_2024_10, CyclisticTripData_2024_11, CyclisticTripData_2024_12]
CyclisticTripData = pd.concat(dataframes, ignore_index=True)
```

Then the large dataframe can be verified to check very quickly uniformities and to get a better data sensitivity.

```
CyclisticTripData.info()
CyclisticTripData.shape
CyclisticTripData.columns
CyclisticTripData.head()
CyclisticTripData.tail()
```

And, the CyclisticTripData dataframe looks like

| ride_id |	rideable_type |	started_at	| ended_at | start_station_name	| start_station_id |	end_station_name	| end_station_id	| start_lat |	start_lng |	end_lat |	end_lng |	member_casual |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|**0** |	C1D650626C8C899A |	electric_bike	| 2024-01-12 15:30:27	| 2024-01-12 15:37:59 |	Wells St & Elm St	| KA1504000135 |	Kingsbury St & Kinzie St |	KA1503000043	| 41.903267 |	-87.634737 |	41.889177 |	-87.638506	| member |
|**1** |	EECD38BDB25BFCB0 |	electric_bike	| 2024-01-08 15:45:46	| 2024-01-08 15:52:59	| Wells St & Elm St	| KA1504000135 |	Kingsbury St & Kinzie St |	KA1503000043	| 41.902937 |	-87.634440 |	41.889177	| -87.638506	| member |
|**2** |	F4A9CE78061F17F7 |	electric_bike	| 2024-01-27 12:27:19	| 2024-01-27 12:35:19	| Wells St & Elm St	| KA1504000135 |	Kingsbury St & Kinzie St |	KA1503000043	| 41.902951 |	-87.634470 |	41.889177	| -87.638506	| member |
|**3** |	0A0D9E15EE50B171 |	classic_bike	| 2024-01-29 16:26:17	| 2024-01-29 16:56:06	| Wells St & Randolph St	| TA1305000030	| Larrabee St & Webster Ave |	13193	| 41.884295	| -87.633963	| 41.921822	| -87.644140	| member |
|**4** |	33FFC9805E3EFF9A |	classic_bike	| 2024-01-31 05:43:23	| 2024-01-31 06:09:35	| Lincoln Ave & Waveland Ave |	13253 |	Kingsbury St & Kinzie St	| KA1503000043	| 41.948797 |	-87.675278	| 41.889177	| -87.638506	| member |


| ride_id |	rideable_type |	started_at	| ended_at | start_station_name	| start_station_id |	end_station_name	| end_station_id	| start_lat |	start_lng |	end_lat |	end_lng |	member_casual |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|**5860563** |	BD56BA20F42E4794	| electric_bike	| 2024-12-11 08:23:46.564	| 2024-12-11 08:37:34.532 |	Clybourn Ave & Division St	| TA1307000115	| NaN |	NaN	| 41.904634 |	-87.640518 |	41.880000 |	-87.630000	| member |
|**5860564**	| 3074643A6B60B300	| electric_bike	| 2024-12-09 12:26:15.677	| 2024-12-09 12:37:32.712	| Canal St & Jackson Blvd	| 13138	| NaN	| NaN	| 41.878125 |	-87.639968 |	41.900000 |	-87.620000	| member |
|**5860565**	| 15602635C5DF484E	| electric_bike	| 2024-12-31 17:10:03.113	| 2024-12-31 17:17:21.838	| Albany Ave & Bloomingdale Ave |	15655 |	California Ave & Milwaukee Ave |	13084	| 41.914027 |	-87.705126 |	41.922695 |	-87.697153 |	member |
|**5860566**	| F15ABBA961560B75	| electric_bike	| 2024-12-01 14:39:47.216	| 2024-12-01 14:45:21.268	| Albany Ave & Bloomingdale Ave	| 15655	| California Ave & Milwaukee Ave |	13084	| 41.914003	| -87.705099 |	41.922695	| -87.697153 |	member |
|**5860567**	| 8AF273287533B527	| electric_bike	| 2024-12-17 06:38:32.320	| 2024-12-17 06:46:27.167	| Albany Ave & Bloomingdale Ave	| 15655	| NaN |	NaN	| 41.914027 |	-87.705126 |	41.920000 |	-87.690000 |	member |

From looking at the output information, there are no columns to be removed. All the data collected can be used to get insights for the analysis. Moreover, from looking at the output information from the last 5 rows, NaN values are observed.

Now, the large dataframe is ready to check that data is clean, free of errors and check if modifying data is needed.

> Note: The large dataframe is exported to .CSV file for a saved version.

```
CyclisticTripData.to_csv('~/projects/20250109_CyclisticBikeShare/2.PreparedData/20250205_CyclisticTripData.csv', index=False)
```

### Data manipulation

Next, a closer look at data is taken to check for duplicates, null values, and inconsistency on values that needs to be cleaned.

```
duplicate_number = CyclisticTripData['ride_id'].duplicated().sum()
duplicate = CyclisticTripData[CyclisticTripData['ride_id'].duplicated()]

print("Number of duplicate ride_id:", duplicate_number)
print("Duplicate Observations:", duplicate)
```

- There are 211 duplicates. A closer look at the duplicates allowed to identify that the duplicates correspond to data duplicated in month 05 and 06, and recordings started on 2024-05-31 and finishing on 2024-06-01. Moreover, the data collected changed time format from HH:MM:SS, until month 05, to HH:MM:SS.SSS, after month 06. Then I first proceeded to make consistency the date format to match HH:MM:SS considering the purpose of the analysis.

```
CyclisticTripData[['started_at', 'ended_at']] = CyclisticTripData[['started_at', 'ended_at']].apply(lambda x: pd.to_datetime(x, format='mixed').dt.strftime('%Y-%m-%d %H:%M:%S'))
```

And, then I get only one record for each duplicate.

```
count_row_initial = CyclisticTripData.shape[0]
CyclisticTripData = CyclisticTripData.drop_duplicates(keep='first')
count_row_keep_one = CyclisticTripData.shape[0]

print('Duplicate rows removed:', count_row_initial - count_row_keep_one)
```

Next, a closer look at data with unique observations is taken to check for null or empty cells.

```
nan_count = CyclisticTripData.isna().sum().sum()
null_count = CyclisticTripData.isnull().sum().sum()
nan_count_column = CyclisticTripData.isna().sum()
null_count_column = CyclisticTripData.isnull().sum()

print('Number of NaN values in each column:', nan_count_column)
print('Number of null values in each column:', null_count_column)
print('Number of NaN values:', nan_count)
print('Number of null values:', null_count)
```

![image](https://github.com/user-attachments/assets/d17017cb-0ca2-4e9b-8663-5756505a763f)

- There are 4371386 total number of NaN or null values. These values are observed in a mixed way without a pattern in columns 'start_station_name', 'start_station_id', 'end_station_name', 'end_station_id', 'end_lat' and 'end_long'. Then, the observations where there are NaN or null values can be removed.
- In the end, the large dataframe has now 4208188 observations and 13 features.

Now, the consistency on characters length across columns can be checked.

```
max_char = CyclisticTripData.astype(str).map(len).max()
min_char = CyclisticTripData.astype(str).map(len).min()

print('Maximum character length per column:', max_char)
print('Minimum character length per column:', min_char)
```
![image](https://github.com/user-attachments/assets/d92cb354-a785-4b68-ac28-81ac0a8df30c)

- There are consistency on characters length on columns 'ride_id', 'started_at', 'ended_at' and 'member_casual'.
- Columns 'start_station_id', 'start_station_name', 'end_station_id' and 'end_station_name' will be kept for now, but if they do not add value in future steps, they can be removed.

Finally, the uniqued values for columnns 'rideable_type' and 'member_casual' can be checked.



