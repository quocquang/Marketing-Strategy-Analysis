# 🛒 Marketing Strategy Analysis

---

# :briefcase: Business Case and Requirement
 # Analysis of marketing strategy and its impact on sales volume.

 - What is the impact of each marketing strategy and sales turnover on Sales Volume (Revenue)?
 - Is the same strategy valid for all different types of customers?
 - Statistical analysis:
    - The impact of marketing strategy:
    - Conduct correlation analysis, regression, and decision tree analysis to evaluate the influence of marketing strategy on revenue.
    - Analyze the differences in effectiveness of strategies among various customer segments.
  - The impact of competitive rivals:
    - Evaluate the impact of the number of competitive rivals on revenue.
    - Determine the interaction between marketing strategy, competitive rivals, and revenue.
  - Final Recommendations (Optimal Revenue):
    - Based on the analysis, propose the most effective marketing strategy for each customer segment.
    - Identify the optimal investment level for different marketing channels.
    - Predict potential revenue based on the proposed strategies.


---

# :bookmark_tabs: Campaign-Data Datasets

###  Campaign-Data dataset
 - Client ID: Unique identifier for each client.
 - Client Type: Type or category of the client.
 - Number of Customers: The count of customers associated with each client.
 - Monthly Target: The target set for each month, possibly representing sales or revenue goals.
 - Zip Code: The postal code or zip code associated with the client's location.
 - Calendar Date: Date information, likely indicating when the data was recorded.
 - Amount Collected: The total amount collected, possibly representing revenue generated.
 - Units Sold: The number of units or products sold.
 - Campaign (Email): Information about marketing campaigns conducted via email.
 - Campaign (Flyer): Information about marketing campaigns conducted via flyers.
 - Campaign (Phone): Information about marketing campaigns conducted via phone calls.
 - Sales Contact 1, Sales Contact 2, Sales Contact 3, Sales Contact 4, Sales Contact 5: Details of sales contacts or representatives involved in the sales process.
 - Number of Competitors: The count of competitors or competing entities in the market.

<details><summary>  Click to expand Campaign-Data Dataset </summary>

<div align="center">

**Table: Campaign-Data_dataset** 

<div align="center">
First 10 rows

| Client ID | Client Type     | Number of Customers | Monthly Target | Zip Code | Calendar Date | Amount Collected | Unit Sold | Campaign (Email) | Campaign (Flyer) | Campaign (Phone) | Sales Contact 1 | Sales Contact 2 | Sales Contact 3 | Sales Contact 4 | Sales Contact 5 | Number of Competition |
|-----------|-----------------|---------------------|----------------|----------|---------------|------------------|------------|-------------------|------------------|------------------|-----------------|-----------------|-----------------|-----------------|-----------------|------------------------|
| ID-987275 | Medium Facility| 2800                | 125            | 1003     | 16-01-2014    | 0                | 0          | 0.0               | 0.0              | 0.0              | 0.0             | 0.0             | 0.0             | 0.0             | 0.0             | Low                    |
| ID-987275 | Medium Facility| 2800                | 125            | 1003     | 16-02-2014    | 3409460          | 24         | 0.0               | 0.0              | 0.0              | 0.0             | 0.0             | 0.0             | 0.0             | 322500.0        | Low                    |
| ID-987275 | Medium Facility| 2800                | 125            | 1003     | 18-03-2014    | 10228384         | 75         | 0.0               | 0.0              | 0.0              | 0.0             | 0.0             | 0.0             | 0.0             | 0.0             | Low                    |
| ID-987275 | Medium Facility| 2800                | 125            | 1003     | 18-04-2014    | 17047304         | 123        | 0.0               | 0.0              | 0.0              | 0.0             | 3547500.0       | 1290000.0       | 0.0             | 0.0             | Low                    |
| ID-987275 | Medium Facility| 2800                | 125            | 1003     | 19-05-2014    | 23866224         | 171        | 0.0               | 0.0              | 0.0              | 0.0             | 0.0             | 0.0             | 0.0             | 0.0             | Low                    |

</details>

---

#  IMPORT LIBRARY & CLEAN & TRANSFORM DATA.

  
```python
import pandas as pd
import numpy as np
import seaborn as sns
import scipy.stats
import os 
os.chdir("C:/Users/phu/OneDrive/Pictures")
```

```python
#Upload dataset
data = pd.read_csv('Campaign-Data.csv')
```
<details><summary> The  Overall Infomation </summary>
 
```python
data['Calendardate']=pd.to_datetime(data['Calendardate'])
data['Calendar_Month']=data['Calendardate'].dt.month
data['Calendar_Year']=data['Calendardate'].dt.year
```

---

## Result.
* The Impact of Marketing Strategy on Sales Volume
* Distribution of Customers by Type:
    - Large Facility: 45.97%
    - Small Facility: 28.23%
    - Medium Facility: 16.94%
    - Private Facility: 8.87%
 ```python
# Distribution of Customers by Type
data['Client Type'].value_counts(normalize=True)
```
![Screenshot 2024-03-02 122029](https://github.com/quocquang/Marketing-Strategy-Analysis/assets/87820013/91273883-0bd6-4648-acc4-47c985a76fe3) 
*  The correlation between the number of competitors and the customer type:
   - According to the ratio:
   - High:
       - Large Facility: 16.67%
       - Medium Facility: 16.67%
       - Private Facility: 16.67%
       - Small Facility: 16.67%
   - Low:
       - Large Facility: 83.33%
       - Medium Facility: 83.33%
       - Private Facility: 83.33%
       - Small Facility: 83.33%
 ```python
      pd.crosstab(data['Number of Competition'],data['Client Type'],margins=True,normalize='columns')
 ```
  ![Screenshot 2024-03-02 122524](https://github.com/quocquang/Marketing-Strategy-Analysis/assets/87820013/b0bd27c3-2e38-45a2-b538-c715d36e5983)
  - Average by the number of competitors:
    - Large Facility:
       - Number of customers: 1380.84
       - Average sales volume: 19,998,800
    -  Medium Facility:
       - Number of customers: 3940.76
       - Average sales volume: 40,759,970
    - Private Facility:
       - Number of customers: 400.73
       - Average sales volume: 5,030,246
    - Small Facility:
       - Number of customers: 422.51
       - Average sales volume: 1,637,759
 ```python
      data.groupby('Client Type').mean()
 ```

| Client Type      | Number of Customers | Montly Target | Zip Code | Amount Collected | Unit Sold | Campaign (Email) | Campaign (Flyer) | Campaign (Phone) | Sales Contact 1 | Sales Contact 2 | Sales Contact 3 | Sales Contact 4 | Sales Contact 5 | Calendar Month | Calendar Year |
|------------------|---------------------|---------------|----------|-------------------|-----------|-------------------|------------------|------------------|-----------------|-----------------|-----------------|-----------------|-----------------|----------------|---------------|
| Large Facility  | 1380.842105         | 71.578947     | 1003.0   | 1.999880e+07      | 143.098684| 142273.609649     | 8.192056e+05     | 45595.436623     | 133667.763158   | 2.034013e+06    | 2.017039e+06    | 119287.280702   | 16266.447368    | 6.5            | 2014.5        |
| Medium Facility | 3940.761905         | 202.857143    | 1003.0   | 4.075997e+07      | 290.583333| 437217.097817     | 1.552603e+06     | 49176.847619     | 398645.833333   | 4.822783e+06    | 4.698646e+06    | 85104.166667    | 33273.809524    | 6.5            | 2014.5        |
| Private Facility| 400.727273          | 20.454545     | 1003.0   | 5.030246e+06      | 35.784091 | 5183.715152       | 2.272919e+05     | 5522.470455      | 1221.590909     | 6.376705e+05    | 4.434375e+05    | 3664.772727     | 12215.909091    | 6.5            | 2014.5        |
| Small Facility  | 422.514286          | 21.285714     | 1003.0   | 1.637759e+06      | 11.689286 | 11975.986310      | 9.120875e+04     | 0.000000         | 8062.500000     | 7.617143e+05    | 3.727946e+05    | 4223.214286     | 1535.714286     | 6.5            | 2014.5        |


*  The correlation between customer type and sales revenue:
   - Large Facility: Average sales revenue: 19,998,800
   - Medium Facility: Average sales revenue: 40,759,970
   - Private Facility:Average sales revenue: 5,030,246
   - Small Facility: Average sales revenue: 1,637,759
 
    ---
    
* Linear regression analysis (OLS - Ordinary Least Squares) was conducted to evaluate the influence of independent variables (Campaign_Email, Campaign_Flyer, Campaign_Phone, Sales_Contact_1, Sales_Contact_2, Sales_Contact_3, Sales_Contact_4, Sales_Contact_5) on the dependent variable (Amount_Collected), which represents the amount of money collected
- The advertising campaign using Flyers has the most significant positive impact with a coefficient of 4.1059.
  - Sales Contact 2 has a positive effect with a coefficient of 3.5778.
  - Sales Contact 1 has a positive effect with a coefficient of 3.1365.
  - Sales Contact 3 has a positive effect with a coefficient of 2.1174.
- Large Facility:
  - Sales Contact 1 has a positive effect with a coefficient of 11.6731.
  - Sales Contact 4 has a positive effect with a coefficient of 10.6145.
  - Sales Contact 2 has a positive effect with a coefficient of 4.0031.
- The advertising campaign using Flyers has a positive effect on the coefficient of 2.7204.
  - Sales Contact 3 has a positive effect with a coefficient of 2.0316.
- The advertising campaign using Phone has a negative effect on the coefficient of -3.5361.
  - Small Facility:
  - Sales Contact 2 has a positive effect with a coefficient of 0.810100.
  - Private Facility:
  - Sales Contact 2 has the largest positive effect with a coefficient of 6.6223.

 | Variable         | Coefficient (Impact) | Account Type      |
|------------------|----------------------|-------------------|
| Campaign_Flyer   | 4.105900             | Medium Facility   |
| Sales_Contact_2  | 3.577800             | Medium Facility   |
| Sales_Contact_1  | 3.136500             | Medium Facility   |
| Sales_Contact_3  | 2.117400             | Medium Facility   |
| Sales_Contact_1  | 11.673100            | Large Facility    |
| Sales_Contact_4  | 10.614500            | Large Facility    |
| Sales_Contact_2  | 4.003100             | Large Facility    |
| Campaign_Flyer   | 2.720400             | Large Facility    |
| Sales_Contact_3  | 2.031600             | Large Facility    |
| Campaign_Phone   | -3.536100            | Large Facility    |
| Sales_Contact_2  | 0.810100             | Small Facility    |
| Campaign_Phone   | -0.000004            | Small Facility    |
| Sales_Contact_2  | 6.622300             | Private Facility  |

 * In accounts Medium Facility:
- The Flyer advertising campaign (Campaign_Flyer) has an ROI of $4.1 for every dollar spent.
  - Sales Contact 2 has an ROI of $3.6 for every dollar spent.
  - Sales Contact 1 has an ROI of $3.1 for every dollar spent.
  - Sales Contact 3 has an ROI of $2.1 for every dollar spent.
- Within the Large Facility account:
   - Sales Contact 1 has the highest ROI, at $11.7 for every dollar spent.
   - Sales Contact 4 has an ROI of $10.6 for every dollar spent.
   - Sales Contact 2 has an ROI of $4 for every dollar spent.
- The Flyer advertising campaign (Campaign_Flyer) has an ROI of $2.7 for every dollar spent.
  - Sales Contact 3 has an ROI of $2 for every dollar spent.
- The Phone advertising campaign (Campaign_Phone) has an ROI of -$3.5 for every dollar spent, indicating that this campaign is not effective and leads to a loss.
  - Within the Small Facility account:
  - Sales Contact 2 has an ROI of $0.8 for every dollar spent.
- The Phone advertising campaign (Campaign_Phone) has an ROI of $0 for every dollar spent.
  - Within the Private Facility account:
  - Sales Contact 2 has an ROI of $6.6 for every dollar spent.

 Variable             | Return on Investment | Account Type
---------------------|----------------------|-----------------
Campaign_Flyer       | 4.1                  | Medium Facility
Sales_Contact_2      | 3.6                  | Medium Facility
Sales_Contact_1      | 3.1                  | Medium Facility
Sales_Contact_3      | 2.1                  | Medium Facility
Sales_Contact_1      | 11.7                 | Large Facility
Sales_Contact_4      | 10.6                 | Large Facility
Sales_Contact_2      | 4.0                  | Large Facility
Campaign_Flyer       | 2.7                  | Large Facility
Sales_Contact_3      | 2.0                  | Large Facility
Campaign_Phone       | -3.5                 | Large Facility
Sales_Contact_2      | 0.8                  | Small Facility
Campaign_Phone       | 0.0                  | Small Facility
Sales_Contact_2      | 6.6                  | Private Facility

  
---


  # 🧾 What can you practice with this case study?
- Python
  - pandas, numpy,matplotlib,seaborn.
  - cleaning, check Null values, transforming.
  - import, save csv file. 
