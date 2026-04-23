# Deloitte Project 

### Dashboard Link : 

## Problem Statement

The objective of this project is to analyze operational machine performance data to identify patterns of equipment downtime across different factories and device types. The dataset contains timestamped machine status logs, including temperature readings, device identifiers, device types, and factory locations.

### Task 1

Your task is to analyze the telemetry data collected by Daikibo using software called Tableau/Power BI. 
Here is the background information on your task
Using a data unification algorithm, the tech team at our client, Daikibo, has converted all telemetry data collected from its 4 factories:

Daikibo Factory Meiyo (Tokyo, Japan)
Daikibo Factory Seiko (Osaka, Japan)
Daikibo Berlin (Berlin, Germany)
Daikibo Shenzhen (Shenzhen, China)
Each location has 9 types of machines, sending a message every 10 mins. Daikibo has been collecting this data for one month (May 2021) and they've shared this data in the form of a single JSON file.

The reason the client wanted to collect telemetry was to answer 2 questions:

In which location did machines break the most?
What are the machines that broke most often in that location?


### Steps followed:

- Step 1: I downloaded the daikibo-telemetry-data.json.zip file and loaded it into Power BI Desktop.
<img width="345" height="269" alt="Image" src="https://github.com/user-attachments/assets/b65a7e62-6039-4d67-98c3-7a8ccfe98ae7" />
<img width="1087" height="558" alt="Image" src="https://github.com/user-attachments/assets/a5f77219-4e5e-4afe-b04a-caceec15ffda" />
- Step 2: Using Power Query, I changed the data types of the relevant columns.
- Step 3: Created a calculated measure field called "Unhealthy" with a value of 10 for every unhealthy status (representing 10 mins of potential downtime since the previous message).


		Unhealthy = CALCULATE( COUNTROWS('daikibo-telemetry-data'), 'daikibo-telemetry-data'[status] = "unhealthy") * 10


- Step 4: Created the first report view, Sheet1, using a Column chart titled Downtime per Factory to represent unhealthy machine counts by factory.
  
  <img width="932" height="495" alt="Image" src="https://github.com/user-attachments/assets/b0a97804-f8ce-4b2a-bc4b-089e39dfeb77" />
  
- Step 5: Created a new report view, Sheet2, using a Column chart titled Downtime per Device to represent unhealthy machine counts by device type.
 
  <img width="931" height="495" alt="Image" src="https://github.com/user-attachments/assets/490afba3-7729-4a77-bcc7-e8ef1716c7a9" />

- Step 6: Created a Dashboard with the 2 previous sheets and set the first chart to be used as a filter (selecting a factory in the first chart shows only the downtime of the machines in this factory in the second chart).

<img width="896" height="494" alt="Image" src="https://github.com/user-attachments/assets/745ff425-30c3-4083-9418-f952d1ad0456" />


- Step 7: A factory was selected to analyze the filtered output of downtime for unhealthy machines at the factory level.

<img width="856" height="469" alt="Image" src="https://github.com/user-attachments/assets/eccae030-0b51-47c7-aab3-1bc88929620e" />


## Problem Statement: 
After a worrisome number of internal complaints about gender inequality in terms of salary, Daikibo Industrials wants us to help them investigate.

The Forensic Tech team has built an algorithm to quantify “level of gender pay equality” for most job roles within the company, in all company locations. Our Forensics lead thinks it would be a great idea for you to finish the job.

### Task 2

We have processed all data on employee compensation and generated an Excel file (Equality Table.xlsx, available in the Resources) containing 3 columns:

Factory
Job Role
Equality Score (integer; ranging between -100 and +100; 0 is ideal)
Here is your task:

Create a 4th column (Equality class), classifying the equality score into 3 types:
Fair (+-10)
Unfair (<-10 AND >10)
Highly Discriminative (<-20 AND >20)

<img width="545" height="526" alt="Image" src="https://github.com/user-attachments/assets/ce083014-9308-4a59-ad25-f2a73406f099" />

<img width="504" height="384" alt="Image" src="https://github.com/user-attachments/assets/c1e68a4a-57ba-4bf3-aa0b-fc0e0a5624d4" />

<img width="789" height="425" alt="Image" src="https://github.com/user-attachments/assets/3dcb3ebf-7439-4a77-800b-fdf98fb280e8" />


📊 Key Insights: Factory-Level Discrimination Analysis
🥇 Most Discriminative Factory → Daikibo Factory Meiyo
Highest number of “Highly Discriminative” roles
Affects senior leadership levels:
C-Level
VP
Jr. Manager
Operational Support
Indicates systemic inequality across hierarchy, not isolated roles

👉 Conclusion:
Meiyo shows the most severe and widespread discrimination
