## City of Chicago Car Crashes

Project Website URL: https://ever30.github.io/Chicago-Car-Accidents/


![Screenshot 2024-03-26 at 11 49 37 AM](https://github.com/Ever30/Chicago-Car-Accidents/assets/149534473/0101d734-aa8d-40e1-9e0a-b40bd9037ab1)


## Description

The purpose of this is to analyze the data regarding car crashes in the City of Chicago and to create visualizations that will help us answer some questions like:

1. How does lighting affect the amount of car crashes? 
2. What are the areas in Chicago with the most accidents and what are the primary reasons? 
3. How does the presence of traffic control devices affect car crash rates and the incidence of severe injuries or fatalities? 
4. Which accident type on average has the highest injury count and what is the average cost of associated damages? 
5. Are crash crashes more prevalent during certain days of week or months of year? 


## Data Cleaning

The initial dataset obtained from the source was extensive, containing data on car crashes within the city of Chicago dating back to 2015, with over 800,000 rows in the CSV file imported into Jupyter Notebook. Due to the size, the data was narrowed down to include only car crashes from 2022 and 2023, resulting in a dataset of 219,125 rows. Twenty-seven columns deemed irrelevant to the research questions were dropped. The "CRASH_DATE" column was then converted to datetime format to enable accurate date filtering. This refined dataset was used to create the majority of the visualizations. However, the map displayed under the "Map Data" tab on the webpage utilizes live data sourced directly from Socrata’s API.


## Instructions

Click on the link to access the website. The home page includes a project summary and four tabs, each dedicated to a different visualization: Lighting and Weather, Map Data, Average Costs, and Monthly Data. Each tab addresses one of the five primary questions through visualizations created using Python, JavaScript, and various libraries. Below are instructions for using and interacting with each visualization to explore insights related to each question.

#### 1. Lighting & Weather: How does lighting affect the amount of car crashes? 
The purpose of these barplot visualizations is to examine the number of crashes depending on lighting and weather conditions in Chicago. It can give the viewer insight as to what certain type of conditions lead to the most amount of crashes. The barplots themselves have various options to further examine the data. Using the drop down menu and the legend on the right hand side, they can filter out data based on what they want to see. Hovering the cursor over the bar plots will also allow the user to see the amount of crashes that a specific condition has. 

#### 2. Map Data: What are the areas in Chicago with the most accidents and what are the primary reasons? 

The purpose of this map visualization is to show the areas of Chicago with the most car accidents, while also finding the most common causes. This map uses live data from https://dev.socrata.com/foundry/data.cityofchicago.org/85ca-t3if.

- At the top right of the screen we have two ways to view our map (Street Map and Satellite). The user can select one at a time.
- In the same white box but a little lower, we have three other ways to display our data, you can choose one, two or three at a time. It's up to you. Each mark on the map is a car accident that occurred in the previous 4 or 5 days. If you click on one of those marks, you will be able to see information about this accident (location, date of accident, date of accident, cause of accident, lighting conditions, and weather conditions).
- In the lower right part we can see all the Accidents Cause arranged in descending order (from most common to least common).
- In the lower left part we can see the data we are seeing from what day until what day is this data.


#### 3. Traffic Control Devices Map: How does the presence of traffic control devices affect car crash rates and the incidence of severe injuries or fatalities? 

Using Plotly Express and Dash in Jupyter Notebook, a scatter mapbox was created to compare serious car accidents (those resulting in fatal or incapacitating injuries) with or without a traffic control device, such as a traffic signal, yield sign, or school zone. This scatter mapbox aims to reveal any impact of traffic control devices on serious car accidents. The data set focuses on car crashes in the city of Chicago for 2022 and 2023, and the app was deployed using PythonAnywhere.

The map centers on Chicago, with markers representing car crashes. According to the legend, red markers indicate fatal accidents with a device present, blue markers indicate fatal accidents without a device, yellow markers represent incapacitating injuries with a device, and green markers indicate incapacitating injuries without a device. The legend also displays counts for each crash type over the selected timeframe.

Two dropdown menus allow for filtering: “Select Year” and “Select Month.” To view all accidents for either 2022 or 2023, select "All of 2022" or "All of 2023" in the "Select Year" menu. For monthly data, choose the year in "Select Year" and then a specific month in "Select Month." Hovering over the markers displays the crash date and any traffic control device present.


#### 4. Average Incident Information: Which accident type on average has the highest injury count and what is the average cost of associated damages? 

Using Pandas and Plotly Express in Jupyter Notebook / VS Code, two bar charts were created. The first bar chart highlighted the "Crash Type," detailing types of incidents like rear-end collisions, side swipes, and parked car incidents. This chart displays the average number of injuries per accident, ordered from the highest to the lowest number of injured individuals, helping identify the most harmful accident types. By hovering over each bar, additional information appears, and a Box Select option enables zooming in for a closer view.

The second chart provides a basic count of damage costs per accident across three cost groups: "$500 or less," "$501 - $1500," and "Over $1,500." The raw data lacks specific property damage or collision costs, so amounts are likely estimates by the Chicago Police Department. With over 150K accidents falling under the "Over $1,500" category, it suggests that typical damages from an accident would exceed $1,500. This Plotly Express file also allows users to gather more information by hovering over each bar and using the Box Select feature for a more focused view.

   
#### 5. Monthly Data: Are crash crashes more prevalent during certain days of week or months of year?
   
The working dataset was sourced from `data_cleaning.ipynb`, saved as a CSV file, and later converted into JSON format with the `csvtojson.py` script, separated by each year. Within VS Code, the D3.js library and Plotly.js in JavaScript were used to extract car crash data by month and weekday over 2022 and 2023. Two data visualizations were created in web browsers that can be launched from the HTML file.

Accessing the console window through ‘Inspect’ on the generated web page allows verification that the `.js` code is running without issues. The console will auto-populate with logs for "2022-2023 Total Crashes by Month" and "2022-2023 Total Crashes by Weekday" data. Concurrently, the webpage displays one scatter plot and one bar chart visualizing this data. Both visuals represent the number of car crashes in Chicago between 2022 and 2023. Users can toggle the years individually from the legend on each graph, providing the option to examine car crash data for a single year. By hovering over each data point, users can view the total number of car crashes in pop-up tooltips. These visuals provide insight into specific weekdays or months with higher occurrences of car crashes during this two-year period.


## Ethical Considerations

The dataset for this project contains crash data within the Chicago city limits, under the jurisdiction of the Chicago Police Department (CPD). The data is sourced from the electronic reporting system (E-Crash), used by CPD, and excludes any personally identifiable information. Given that this is a public dataset API, data usage for the project was made more secure by the absence of personal information in sensitive records such as car accidents.

One ethical consideration involves the acquisition of Socrata, the creator of this API, by Tyler Technologies in 2018, now forming the Data and Insights division of Tyler. The platform remains powered by the same software previously known as Socrata, though it includes references to Data & Insights. The transfer of data ownership in company mergers and acquisitions can create risks that require careful navigation. Nonetheless, the dataset was deemed suitable for this project as its primary purpose is to allow public exploration of crash data.


## Data Limitations

- Data from E-Crash are available for some police districts in 2015, but citywide data are not available until September 2017.
- About half of all crash reports, mostly minor crashes, are self-reported at the police district by the driver(s) involved and the other half are recorded at the scene by the police officer responding to the crash.
- Many of the crash parameters, including street condition data, weather condition, and posted speed limits, are recorded by the reporting officer based on best available information at the time, but many of these may disagree with posted information or other assessments on road conditions.
- If any new or updated information on a crash is received, the reporting officer may amend the crash report at a later time.
- A traffic crash within the city limits for which CPD is not the responding police agency, typically crashes on interstate highways, freeway ramps, and on local roads along the City boundary, are excluded from this dataset.

## Sources

https://dev.socrata.com/foundry/data.cityofchicago.org/85ca-t3if

https://data.cityofchicago.org/resource/85ca-t3if.json


## Built With:

Mapping:  

https://leafletjs.com/

https://plotly.com/python/scattermapbox/

https://dash.plotly.com/




