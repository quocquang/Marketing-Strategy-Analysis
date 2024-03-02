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
Provide information about orders
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

<details><summary> 👆🏼 Click to expand Campaign-Data Dataset </summary>

<div align="center">

**Table: Campaign-Data_dataset** 

<div align="center">
First 10 rows

| Client ID | Client Type   | Number of Customers | Monthly Target | Zip Code | Calendardate | Amount Collected | Unit Sold | Campaign (Email) | Campaign (Flyer) | Campaign (Phone) | Sales Contact 1 | Sales Contact 2 | Sales Contact 3 | Sales Contact 4 | Sales Contact 5 | Number of Competition |
|:----------|:--------------|:--------------------|:----------------|:---------|:-------------|------------------|------------|-------------------|------------------|------------------|-----------------|-----------------|-----------------|-----------------|-----------------|------------------------|
| ID-987275 | Medium Facility | 2800 | 125 | 1003 | 16-01-2014 | 0 | 0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | Low |
| ID-987275 | Medium Facility | 2800 | 125 | 1003 | 16-02-2014 | 3409460 | 24 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 322500.0 | Low |
| ID-987275 | Medium Facility | 2800 | 125 | 1003 | 18-03-2014 | 10228384 | 75 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | Low |
| ID-987275 | Medium Facility | 2800 | 125 | 1003 | 18-04-2014 | 17047304 | 123 | 0.0 | 0.0 | 0.0 | 0.0 | 3547500.0 | 1290000.0 | 0.0 | 0.0 | Low |
| ID-987275 | Medium Facility | 2800 | 125 | 1003 | 19-05-2014 | 23866224 | 171 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 | Low |



</div>
</div>

</details>

---
# Kết quả.
* Tác động của Chiến lược Tiếp thị đối với Doanh số Bán hàng
*  Phân phối khách hàng theo loại:
    - Large Facility: 45.97%
    - Small Facility: 28.23%
    - Medium Facility: 16.94%
    - Private Facility: 8.87%
*  Tương quan giữa số lượng cạnh tranh và loại khách hàng:
   - Theo tỷ lệ:
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
  - Trung bình theo số lượng cạnh tranh:
    - Large Facility:
       - Số lượng khách hàng: 1380.84
       - Doanh số bán hàng trung bình: 19,998,800
    -  Medium Facility:
       - Số lượng khách hàng: 3940.76
       - Doanh số bán hàng trung bình: 40,759,970
    - Private Facility:
       - Số lượng khách hàng: 400.73
       - Doanh số bán hàng trung bình: 5,030,246
    - Small Facility:
       - Số lượng khách hàng: 422.51
       - Doanh số bán hàng trung bình: 1,637,759
*  Tương quan giữa loại khách hàng và doanh số bán hàng:
   - Large Facility: Doanh số bán hàng trung bình: 19,998,800
   - Medium Facility: Doanh số bán hàng trung bình: 40,759,970
   - Private Facility: Doanh số bán hàng trung bình: 5,030,246
   - Small Facility: Doanh số bán hàng trung bình: 1,637,759
 
    ---
    
* Phân tích hồi quy tuyến tính (OLS - Ordinary Least Squares) được thực hiện để đánh giá mức độ ảnh hưởng của các biến độc lập (Campaign_Email, Campaign_Flyer, Campaign_Phone, Sales_Contact_1, Sales_Contact_2, Sales_Contact_3, Sales_Contact_4, Sales_Contact_5) đối với biến phụ thuộc (Amount_Collected), tức là số tiền thu được.
- Chiến dịch quảng cáo bằng Flyer có ảnh hưởng tích cực lớn nhất với hệ số là 4.1059.
  - Sales Contact 2 có ảnh hưởng tích cực với hệ số là 3.5778.
  - Sales Contact 1 có ảnh hưởng tích cực với hệ số là 3.1365.
  - Sales Contact 3 có ảnh hưởng tích cực với hệ số là 2.1174.
- Large Facility:
  - Sales Contact 1 có ảnh hưởng tích cực lớn nhất với hệ số là 11.6731.
  - Sales Contact 4 có ảnh hưởng tích cực với hệ số là 10.6145.
  - Sales Contact 2 có ảnh hưởng tích cực với hệ số là 4.0031.
  - Chiến dịch quảng cáo bằng Flyer có ảnh hưởng tích cực với hệ số là 2.7204.
  - Sales Contact 3 có ảnh hưởng tích cực với hệ số là 2.0316.
  - Chiến dịch quảng cáo bằng Phone có ảnh hưởng tiêu cực với hệ số là -3.5361.
- Small Facility:
  - Sales Contact 2 có ảnh hưởng tích cực với hệ số là 0.810100.
- Private Facility:
  - Sales Contact 2 có ảnh hưởng tích cực lớn nhất với hệ số là 6.6223.
 * Trong tài khoản Medium Facility:

- Chiến dịch quảng cáo Flyer (Campaign_Flyer) có ROI là 4.1 đô la cho mỗi đô la chi tiêu.
  - Sales Contact 2 có ROI là 3.6 đô la cho mỗi đô la chi tiêu.
  - Sales Contact 1 có ROI là 3.1 đô la cho mỗi đô la chi tiêu.
  - Sales Contact 3 có ROI là 2.1 đô la cho mỗi đô la chi tiêu.
 - Trong tài khoản Large Facility:
   - Sales Contact 1 có ROI cao nhất, là 11.7 đô la cho mỗi đô la chi tiêu.
   - Sales Contact 4 có ROI là 10.6 đô la cho mỗi đô la chi tiêu.
   - Sales Contact 2 có ROI là 4 đô la cho mỗi đô la chi tiêu.
- Chiến dịch quảng cáo Flyer (Campaign_Flyer) có ROI là 2.7 đô la cho mỗi đô la chi tiêu.
  - Sales Contact 3 có ROI là 2 đô la cho mỗi đô la chi tiêu.
- Chiến dịch quảng cáo qua điện thoại (Campaign_Phone) có ROI là -3.5 đô la cho mỗi đô la chi tiêu, có thể hiểu là chiến dịch này không hiệu quả và gây lỗ.
  - Trong tài khoản Small Facility:
  - Sales Contact 2 có ROI là 0.8 đô la cho mỗi đô la chi tiêu.
- Chiến dịch quảng cáo qua điện thoại (Campaign_Phone) có ROI là 0 đô la cho mỗi đô la chi tiêu.
  - Trong tài khoản Private Facility:
  - Sales Contact 2 có ROI là 6.6 đô la cho mỗi đô la chi tiêu.
  
---


  # 🧾 What can you practice with this case study?
- Python
  - pandas, numpy,matplotlib,seaborn.
  - cleaning, check Null values, transforming.
  - import, save csv file. 
