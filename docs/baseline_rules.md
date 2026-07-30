# Project Feature

Route Recommendation
Crime Hotspot
Patrol Priority

## How to measure risky place? What is the condition of risk?

- Crime frequency in a particular place
- Type of crimes
- Crime occur environment

## Crime frequency

- crime count
- crime per week
- crime per month
- crime trend
- rolling average
- moving avarage
- crime growth

## Crime Severity

- Is importancy of every crime is same???

No, 6 types of crime.

- murder
- assault
- rape
- robbery
- bodyfound
- kidnap
So the weight of importance is not same for every tipe
Weight can be selected in three method
- Method-01 Domain Knowledge
- Method-02 Expert Opinio(may police assign)
- Method-03 Data Driven(adjust weight after clustering)

## Supportive Feature

- Environment but not every features in environment are not equally important
--> season thats the important one

## Risk score of place

- so we have to convert this row level dataset to place level dataset
- Feature aggregation

## Modelling Table

| Place | Crime Count | Murder | Robbery | Avg Temp | Humidity | Density | Police Station |
| ----- | ----------- | ------ | ------- | -------- | -------- | ------- | -------------- |

 which features will be count/average/max/min/mode/weighted

## Most Important: risk mapping

- crime frequency: total crime

//
We have to give score to every place by part of the day. In each part risk score will be change.
//

Feature - Aggregation
Total Crime - count
Murder - count
Robbery - count
Assault - count
Kidnap - count
Rape - count
BodyFound - count
Avg Temp - mean
Max Temp - mean
Min Temp - mean
Humidity - mean
Visibility - mean
Cloud Cover - mean
Heat Index - mean
Precipitation - mean
Weather Code - mode
Population - max / first
Density - max / first
Literacy - max / first
Household - max / first
Police Station - max / first
Park - max / first
Playground - max / first
School - max / first
College - max / first
Cinema - max / first

## broadcasting group information back to every row

## how the crime_frequency, crime_serevity, env_score, loc_score has derived

Crime Severity has a higher weight because it indicates the impact of crime.
Crime Frequency indicates recurrence.
Environment and Location scores are created in a data-driven manner from Random Forest feature importance.

We first estimate the contextual risk using crime frequency, severity, environmental and location factors.
Then we distribute that contextual risk among crime types according to their observed proportions within the context
