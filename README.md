# GOODCABS TRANSPORTATION PERFORMANCE ANALYSIS REPORT
#### Prepared by Emeka Kingsley
#### Date: May 29 – May 31, 2025

## Executive Summary
This report presents an end-to-end performance analysis of Good-cabs, a cab service company operating across 10 tier-2 Indian cities. The goal of this analysis was to assess business performance in 2024 by tracking trip volumes, passenger behavior, fare patterns, and target achievements. Using Power BI and DAX, this report delivers actionable insights for business executives, supported by advanced KPIs, dynamic visuals, and strategic observations.

## Business Objective:
### To evaluate operational efficiency, passenger engagement, and goal achievement across cities in order to:
i; Identify high-performing and underperforming cities.

ii; Track trip growth and pricing effectiveness.

iii; Evaluate passenger loyalty and satisfaction.

iv; Assess monthly and city-specific progress toward company targets.

## Dataset Overview
#### The analysis is based on 8 interconnected tables:
1; City Target Passenger Ratings.

2; City.

3; Date.

4; Repeat Trip Distribution.

5; Passenger Summary.

6; Trips (Fact).

7; Monthly Target New Passengers.

8; Monthly Target Trips.


#### Additional Calculated Columns and Measures Created:

Trip Sort Order, Total Passengers,  Total New Passengers,  Total Repeat Passengers,  Percentage(%) of Repeat Passengers,  Actual New Passengers,  Actual Trips,  Average Trip Distance,  New Passenger Target Achievement (%)  , New Passenger Trips,  New vs Repeat Passenger Trip Ratio,  Repeat Passenger Trip,  Revenue Growth Rate (%),   Target New Passengers,  Target Trips,  Total Revenue,  Total Trip Distance,  Total Trip Count,  Trip Target Achievement (%).

## Tools & Techniques Used

Power BI Desktop for data modeling and visualization.

DAX (Data Analysis Expressions) for calculations and KPI generation.

Matrix, Card, Donut, Waterfall, Line, and Bar Charts for interactive insights.


## Key KPIs & Visuals
#### Displayed Using Cards:

i; Total Revenue: ₹108M.

ii; Total Passengers: 238K.

iii; New Passengers: 177K.

iv; Repeat Passengers: 61K.

v; Total Trips: 426K.

vi; Avg Trip Distance: 19.13 km.


#### Other Visuals:
vii; Average Fare Per Trip by City (Stacked Column Chart).

viii; Total Trip Count by Month (Line Chart).

ix; Top and Bottom Performing Cities (Bar Chart).

x; Trip Count by Month and Day Type (Clustered Bar Chart).

xi; New vs Repeat Passenger Trip Ratio (Donut Chart).

xii; Revenue Growth Rate by Month (Waterfall Chart).

xiii; Repeat Trip Frequency by City (Matrix).

xiv; Month and City_Name (Slicers).

#### Additional sheet with:
xv; Avg Ratings by City & Passenger Type.

xvi; Trip Target Achievement Rate.

xvii; New Passenger Target Achievement Rate.

## Insights & Observations :
i; Good-cabs generated a total revenue of ₹108M.

ii; Passenger breakdown: 238K total; 177K new; 61K repeat.

iii; Total of 426K trips recorded, with an average distance of 19.13 km.

iv; February had the highest trip volume (75K trips).

v; Jaipur has the highest avg fare per trip (₹483.92) and tops total trip count.

vi; Top 3 Cities: Jaipur, Lucknow, Surat. Bottom 3: Visakhapatnam, Coimbatore, Mysore.

vii; Weekdays outperform weekends in trip volume.

viii; Repeat passengers make up 58.44% of trips, showing strong loyalty.

ix; Sequential pattern in repeat trip distribution: 2-trips (30.06%) down to 10-trips (1.20%).

x; Jaipur leads in repeat passenger % (15.79%).

xi; Highest driver ratings: Jaipur & Kochi (8.99). Highest passenger rating: Mysore (8.70).

xii; All cities met trip targets. Highest: Mysore (120.28%). Lowest: Vadodara (85.40%).

xiii; All cities met new passenger targets. Highest: Coimbatore (113.52%). Lowest: Jaipur (84.92%).

xiv; Revenue growth rate: Up in Feb (+7.61%), down in Mar (-5.15%), Apr (-6.06%), up slightly in May (+1.64%), sharp drop in Jun (-14.61%).

## Business Impact of Observations :
i; High repeat trip ratios suggest strong brand loyalty in cities like Jaipur and Kochi — these are strategic zones for deeper engagement.

ii; Revenue volatility month-to-month highlights a need for seasonal campaign planning.

iii; Top cities by fare and trips (e.g., Jaipur) offer scalable blueprints for underperforming regions.

iv; Lower achievement rates in cities like Vadodara and Jaipur (for different KPIs) suggest the need for tailored strategies — one may need demand generation, the other operational support.
v; Rating analysis helps target driver/passenger experience improvements where needed.

## Recommendations :
1; Replicate Jaipur’s pricing and engagement model in similar cities to boost fare and loyalty.

2; Investigate passenger experience in Mysore to understand drivers of high satisfaction.

3; Launch marketing campaigns in underperforming cities during off-peak months (e.g., June).

4; Prioritize retention programs to increase 3-trip and 4-trip segments.

5; Use trip distribution patterns to predict churn risk and optimize incentives.


## Conclusion
This analysis provides a robust foundation for Good-cabs to make strategic, data-driven decisions in operations, pricing, and customer retention. The Power BI dashboard supports ongoing tracking, while these insights equip stakeholders to scale what works and fix what doesn’t.


## Appendix: DAX Code Snippets

i; Total Revenue = SUM('Trips'[Fare Amount]).

ii; Total Passengers = SUM('Passenger Summary'[Total Passengers]).

iii; Avg Fare per Trip = DIVIDE([Total Revenue], [Total Trips]).

iv; Repeat Passenger Rate (%) = DIVIDE(SUM('Passenger Summary'[Repeat Passengers]), SUM('Passenger Summary'[Total Passengers])) * 100.

v; Trip Target Achievement (%) = DIVIDE([Actual Trips], [Target Trips]) * 100.

vi; New Passenger Target Achievement (%) = DIVIDE([Actual New Passengers], [Target New Passengers]) * 100.

vii; Revenue Growth Rate (%) =
VAR Current = [Total Revenue]
VAR Previous = CALCULATE([Total Revenue], DATEADD('Date'[Date], -1, MONTH))
RETURN DIVIDE(Current - Previous, Previous) * 100.

viii; New vs Repeat Trip Ratio = DIVIDE([New Passenger Trips], [Repeat Passenger Trips]).

ix; City Trip Rank = RANKX(ALL('City'[City Name]), [Total Trips], , DESC).

