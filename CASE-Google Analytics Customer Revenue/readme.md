# Google Analytics Customer Revenue  

Analyze how much GStore customers are spending
---  
#### 08.05.20234 v1 dbe - initial version for CAS DA6
---  
![image](https://github.com/sawubona-gmbh/CAS-DA/assets/52699611/15af78f5-6b98-4a07-8d26-90ee515c8ce6)

In this [Kaggle competition](https://www.kaggle.com/competitions/ga-customer-revenue-prediction/overview), you’re challenged to analyze a Google Merchandise Store (also known as GStore, where Google swag is sold) customer dataset to predict revenue per customer. Hopefully, the outcome will be more actionable operational changes and a better use of marketing budgets for those companies who choose to use data analysis on top of GA data.


### File Descriptions  
+ ga-split-12000.csv - contains approx **12'000 user transactions** from August 1st 2016 to April 30th 2018
+ ga-split-22000.csv - contains approx **22'000 user transactions** from August 1st 2016 to April 30th 2018

### Data Fields   
Each row in the dataset is one visit to the GSstore. 

+ fullVisitorId- A unique identifier for each user of the Google Merchandise Store (GStore)
+ channelGrouping - The channel via which the user came to the Store
+ date - The date on which the user visited the Store
+ device - The specifications for the device used to access the Store
+ geoNetwork - This section contains information about the geography of the user
+ socialEngagementType - Engagement type, either "Socially Engaged" or "Not Socially Engaged"
+ totals - This section contains aggregate values across the session
+ trafficSource - This section contains information about the Traffic Source from which the session originated
+ visitId - An identifier for this session. This is part of the value usually stored as the _utmb cookie. This is only unique to the user. 
For a completely unique ID, you should use a combination of fullVisitorId and visitId
+ visitNumber - The session number for this user. If this is the first session, then this is set to 1
+ visitStartTime - The timestamp (expressed as POSIX time)
+ hits - This row and nested fields are populated for any and all types of hits. Provides a record of all page visits
+ customDimensions - This section contains any user-level or session-level custom dimensions that are set for a session. 
This is a repeated field and has an entry for each dimension that is set.
+ totals - This set of columns mostly includes high-level aggregate data

IMPORTANT: Due to the formatting of fullVisitorId you must load the Id's as strings in order for all Id's to be properly unique!
There are multiple columns which contain **JSON** blobs of varying depth. In one of those JSON columns, totals, the sub-column transactionRevenue contains the revenue information we are trying to predict. 
This sub-column exists only for the training data.


---   
### Mögliche Aufgaben/Fragestellungen für die QS3 Fall Studie    
+ Explorative Analyse des Dataset 
+ Regressionsanalyse: Vorhersage der pro Kund:inn generierten Umsatzes, wenn sie den GStore besucht
+ weitere explorative und visuelle Analysen mit Blick auf mögliche Erkenntnisse/Insights 

*WORK IN PROGRESS*   
Machine learning problem formulation :
Here we are going to predict the revenue generated by the customer (in dollars) when he visits the store --> so we can pose this problem as **regression problem**  
By following some of the kaggle discussions and winners solution, they are building a *classification model* that will predict whether the user will visit the store or not in the test period time 
and then suppose if there is chance that he is visiting store then by using *regression model* we will predict the revenue is going to be generated by the customer.
