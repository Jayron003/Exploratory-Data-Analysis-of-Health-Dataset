# Exploratory Data Analysis of Health Data
![](display_image.JPEG)

There are two datasets used for this analysis, they were provided by [Turing](https://turing.com). The datasets consist of health data of several correspondents. The datasets are:
Cardio_base.csv consist: 70000 rows, 9 columns
Cardio_alco.csv consist: 56903 rows, 2 columns
## Data Description
•	Objective: factual information
•	Examination: result from medical examination
•	Subjective: information given by the subject
## Features
1.	id- is the unique key per person		|
2.	age- is calculated in days			| 
3.	gender: 1- female and 2- male		| Objective
4.	height- the height of a person (cm)	| 
5.	weight- the weight of a person (kg)	| 
6.	ap_hi- Systolic blood pressure (mmHg)	| Examination
7.	ap_lo- Diastolic blood pressure (mmHg)	| Examination
8.	cholesterol: 1- normal | 2- above normal | 3- well above normal | Examination
9.	smoke: 0- no and 1- yes			|Subjective
10.	alco: 0- no and 1- yes			| Subjective
## Data Manipulation / Feature Engineering
The `age` column within the cardio_base.csv is a measure of days.
I had to convert days to year and rounded down.
Formula used: cardio_df["age"] = (cardio_df["age"]/ 365.25).astype(int)
-	First, divide every row within the `age` column by 362.25 to convert days to years.
-	`.astype(int)` rounds down the ages to the nearest whole number.
## Handling the Outliers
![](outliers.PNG)
* There are a number of extreme values (outliers) here, most of which are abnormal blood pressure as humans.
* having `ap_lo` and `ap_hi` levels lower than 0 and as high as 10,000.
> Diastolic blood pressure `ap_lo` exerts within arteries between heartbeats. Normal diastolic blood pressure is 80 mmHg or below. If you have high blood pressure, the diastolic number is often higher even during rest. Diastolic blood pressure is considered dangerously low when it is 60 mmHg or lower and dangerously high when it is 110 mmHg or over. Reference: [verywell_health](https://www.verywellhealth.com/systolic-and-diastolic-blood-pressure-1746075)

> Systolic blood pressure `ap_hi` exerts when blood is ejected into arteries. Normal systolic blood pressure is 120 mmHg or below. `ap_hi` below 90 mmHg is considered low and may require intervention and management from your healthcare provider. If you get `ap_hi` readings above 180 mmHg, it is considered dangerously high and should be addressed by your healthcare provider. Reference: [verywell health](https://www.verywellhealth.com/systolic-and-diastolic-blood-pressure-1746075)
![](vwh.JPG)

## Business Questions
1.	How much heavier is the age group with the highest average weight than the age group with the lowest weight?
2.	Are men more likely to be a smoker than women are?
3.	How tall are the tallest 1% of people?
4.	What is the percentage of people above 50 that consume alcohol?
5.	Which of the following statements is true with 95% confidence?
a.	smokers have higher blood pressure than `non_smokers`
b.	smokers have higher cholesterol level than `non smokers`

## Summary
Key findings from the exploratory analysis. The following information were derived from the dataset
1.	There are 28 unique age groups within the dataset, with ages ranging from 29 to 64 years
2.	About 19,000 patients suffer from hypertension with a higher percentage of them being women.
3.	There is a strong positive correlation of 0.71 between `ap_hi` and `ap_lo`
4.	There is a strong positive correlation of 0.5 between `height` and `gender`
5.	Large percentage of the dataset do not consume alcohol.
6.	Age groups `49`, `57`, `53` and `55` consume alcohol the most.


