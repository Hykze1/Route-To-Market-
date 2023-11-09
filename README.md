# Route-To-Market-Trade Depot USING EXCEL

![trade](https://github.com/Hykze1/Route-To-Market-/assets/100960483/f04bfbd3-fac3-4667-afd3-816bbb2ea198)


# Introduction 

This is a sample dataset of orders generated on the TradeDepot platform for the month of December, 2020

Each row shows a line item as a component of an order.

The dataset contains 15 columns and 2046 row. The details of the columns include:

Fields	  Definitions	

OrderedAt Date 	  The Order Date


Order No.        	The Unique Order Number for Each Order	

Customer           Name	Name Of The Retail Outlet						

Producer	        The Line Item Producer								

Product	          The Line Item Product							

Category Group	  The Broad Category of the Line Item				

Category 	        The Line Item Product Category						

Variant	          The Line Item Stock Keeping Unit (SKU)			

Quantity	        The Quantity Of The Line Item (SKU)					

Unit Price	      The Unit Price Of The Line Item (SKU)					

shippingStatus 	  The Fulfilment Status Of The Line Item (SKU)		

Delivery Date 	  The Date Delivery Was Attempted								

Delivery Agent 	  The Delivery Agent The Order Was Assigned To		

Customer Type	    The Classification of the customer

Order Channel	    The Channel The Order Was Raised Through


So in this dataset we will be answering some crucial question associated with Trade Depot Need.
Before we proceed you need to know that Trade Depot are Top consumer goods producers as well as importers and local manufacturers in Nigeria.

# 1) Show the following topline numbers in a Dashboard format in excel 																		
																		
a)	Number of Unique Customers

b)	Number of Unique Orders			

c)	Total Order Value								

d)	Average Order Value						

e)	Fulfilment Rate (Order Count)			

f)	Average Fulfilment Time (In hours)		

g)	Loss Sale														

h)	Unique Number of SKUs					

i)	Average Unique SKUs per Customer																	

# QUESTION 1 answer

# a)	Number of Unique Customers = 243
# use a PivotTable in Excel to calculate the number of unique customers and the number of unique orders. Here's how  we go about it :

1. Select the data range that contains the information provided.
   
3. Go to the "Insert" tab in Excel.
   
5. Click on "PivotTable" and a dialog box will appear.
   
7. In the dialog box, make sure that the range you selected is displayed in the "Table/Range" field.
   
9. Choose where you want the PivotTable to be placed, either in a new worksheet or an existing one.
    
11. Click "OK" to create the PivotTable.
    
13. In the PivotTable Field List on the right, you will see the fields you mentioned (e.g., "Customer Name" and "Order No.").
    
15. Drag the "Customer Name" field to the "Rows" area, and drag the "Order No." field to the "Values" area.
    
17. By default, Excel will count the number of orders (since "Order No." is a unique identifier for orders) in the "Values" area. You can see the count of unique orders in the PivotTable.
    
19. To calculate the number of unique customers, right-click on the "Order No." field in the "Values" area and choose "Value Field Settings."
    
21. In the dialog that appears, choose "Distinct Count" as the summary function. This will give you the count of unique customers based on the "Customer Name."
    
23. Click "OK," and now  PivotTable will display the count of unique customers.

Alterenatively we can also use the # COUNTIFS FORMULAR 


# b)	Number of Unique Orders = 621
    =([Quantity]*[Unit Price])

to get the Value then =SUM($K$3:$K$2048) to get the Total Value sum

# c) Average Order Value = 15960.69257

      =AVERAGE([Value]) 

# d)	Fulfilment Rate (Order Count)  = 2046

      =COUNTA(Table1[Order No.])

# e)	To extract the hour from the date and time "12/2/2020 12:01:26 PM," we  use the following formula:

    =HOUR([@[Delivery Date]]-[@[OrderedAt Date ]]) 
  = Fulfilment Time (In hours)

# f)	Average Fulfilment Time (In hours) = 10.88465298

      =AVERAGE(Table2[Fulfilment Time (In hours)])

# g)	To calculate the "Loss Sale," we need to determine the value of orders that have not been delivered or have been cancelled. 

    =SUMIFS([Value], [shippingStatus], "cancelled")  
  = 3756188.5
    
# h)	To calculate the unique number of SKUs and the average unique SKUs per customer using a pivot table in Excel, you can follow these steps:

   Create a Pivot Table:
    
  - Drag the "Customer Name" field to the "Rows" area.
    
   - Drag the "Variant" field to the "Values" area. By default, it will be counted
    	Unique Number of SKUs	

# I) Now, to calculate the average unique SKUs per customer, you'll need to add a calculated field:

   - In the PivotTable Field List, right-click on the "Variant" field in the "Values" area and choose "Value Field Settings."
     
   - In the "Value Field Settings" dialog, select "Average" as the function to summarize the data.
   - 
    The table should now display the unique number of SKUs for each customer and the average unique SKUs per customer.

# Question 1 dashborad
  
  ![TRADE](https://github.com/Hykze1/Route-To-Market-/assets/100960483/6998c25b-c6da-4ab6-a064-4445be62b25e)

  

# 2) Answer the following questions using any charts of your choice for visualisation (Show working for all answers provided)																				
																				
a)	Analyse the Breakfast & Snacks category group indicating the market leading product(s) in terms of distribution and sales value		

b)	Which six producers contribute the most of the sales value and what are their five most popular variants with customers?			

c)	Which customer type has the highest average order value and which channels are the most used by customer type?				

d)	Analyse the number of orders by time of day showing peak periods during the day. Is there any tangible difference in order times across the order channels?		

e)	Which three producers dominate the Food category group and what variants drive that dominance?	

f)	Is there any significant difference in the popularity of Home Care variants across customer types or order channels?																			
																				
Insights			

i)	What two variants are most likely to be bought together?			

ii)	What three variants have the highest order frequencies				

iii)	What is the rate of purchase of high valued SKUs (>10,000) to lower valued SKUs and what is the average order frequency for both bands?																			

# Question 2 Answers

a). To analyze the "Breakfast & Snacks" category group, indicating the market-leading product(s) in terms of distribution and sales value using a pivot table in Excel, you can follow these steps:

1. Create a pivot table:

2. In the PivotTable Fields pane (usually on the right side of Excel), drag the following fields into their respective areas:

   - For "Rows," drag "Product."
   - For "Values," drag "Quantity" (to show distribution) and "Value Price" (to show sales value).

3. You now have a pivot table showing the distribution and sales value of products in the "Breakfast & Snacks" category group. Filter by shippingStatus to determine the delivered or done deal

4. To find the market-leading product(s), we can sort the pivot table. Click on the drop-down arrow in the "Quantity" or “Value Price" column in the Values area and choose "Sort Largest to Smallest."

The product(s) at the top of the list, with the highest quantity and sales value, can be considered the market leaders in the "Breakfast & Snacks" category group which is NESTLE MILO.

# Brief Analysis
# I). what two variants are most likely to be bought together?

To determine which two variants are most likely to be bought together, we check for common purchasing patterns. In this data, we can observe that "Nestle Milo" has a very high order frequency (556.5) and is often bought together with "Dano Cool Cow" (438.25). This suggests that "Nestle Milo" and "Dano Cool Cow" are the two variants most likely to be bought together.

# ii). what three variants have the highest order frequencies?

To find the three variants with the highest order frequencies, we can simply look at the order frequencies in the provided data. The top three variants with the highest order frequencies are:
   - "Nestle Milo" with 556.5 orders
   - "Dano Cool Cow" with 438.25 orders
   - "Peak Milk" with 260.5 orders

# iii). what is the rate of purchase of high-valued SKUs (>10,000) to lower-valued SKUs, and what is the average order frequency for both bands?

To analyze the rate of purchase of high-valued SKUs (greater than 10,000) compared to lower-valued SKUs and their average order frequencies, we need to categorize the products based on their values. Let's assume that products with a "Value" greater than 10,000 are considered high-valued SKUs.

From the provided data, we calculate:

- High-Valued SKUs Total Value: 8,765,757.5 (Nestle Milo, Dano Cool Cow, and Peak Milk)
- Lower-Valued SKUs Total Value: 9,400,443.5 (The rest of the products)

- High-Valued SKUs Total Order Frequency: 1,255.25 (Nestle Milo, Dano Cool Cow, and Peak Milk)
- Lower-Valued SKUs Total Order Frequency: 1,798.75 (The rest of the products)

Now, we can calculate the rate of purchase and average order frequency for both bands:

- Rate of Purchase (High-Valued SKUs): Total Value / Total Order Frequency
  = 8,765,757.5 / 1,255.25 ≈ 6,987.35

- Rate of Purchase (Lower-Valued SKUs): Total Value / Total Order Frequency
  = 9,400,443.5 / 1,798.75 ≈ 5,225.89

- Average Order Frequency (High-Valued SKUs): Total Order Frequency / Number of High-Valued SKUs
  = 1,255.25 / 3 ≈ 418.42

- Average Order Frequency (Lower-Valued SKUs): Total Order Frequency / Number of Lower-Valued SKUs
  = 1,798.75 / 18 ≈ 99.93

# In a nut shell, the rate of purchase for high-valued SKUs is approximately 6,987.35, and the average order frequency for high-valued SKUs is 418.42. For lower-valued SKUs, the rate of purchase is approximately 5,225.89, and the average order frequency is approximately 99.93. High-valued SKUs have a higher rate of purchase and a significantly higher average order frequency compared to lower-valued SKUs. Purchasing patterns. In this data, we can observe that "Nestle Milo" has a very high order frequency (588) and is often bought together with "Nestle Golden Morn" (271.5). This suggests that "Nestle Milo" and "Nestle Golden Morn" are the two variants most likely to be bought together.

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/0c8c77df-9b0d-405c-98a0-971dd1d93818)

# b). to find the six producers that contribute the most to sales value and their five most popular variants with customers using a pivot table, you can follow these steps:

Create a pivot table:

#Drag the "Producer" field to the "Rows" area.
   
#Drag the "Value Price" field to the "Values" area. Ensure that it's set to sum.
   
#Sort the pivot table in descending order based on the "Sum of Value Price" (sales value)
   
To find the top six producers contributing the most to sales value, just look at the first six rows of the sorted pivot table (descending order)

Lastly we drag the customer name to the filter session so as to determine the customer with the variant, and the producer.

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/9be95ff3-0d5e-4d11-987c-5ce75810c583)

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/abf56498-0ce1-46d2-9133-2e4001d4f262)

# 2. To find the five most popular variants for each of these six producers, create a new pivot table:	
				

   a. Drag the "Producer" field to the "Report Filter" area and select the first producer from the filter dropdown.

   b. Drag the "Variant" field to the "Rows" area.

   c. Drag the "Quantity" field to the "Values" area. Ensure that it's set to sum.

   d. Sort this pivot table in descending order based on the "Sum of Quantity" (popularity).

   e. To find the top five variants, look at the first five rows of this sorted pivot table.

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/8bcf3091-6f43-406a-a0b9-33b098511a4c)

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/ed172015-93c4-4859-be69-f7d29dc9e909)

# d). Analyze the number of orders by time of day showing peak periods during the day. Is there any tangible difference in order times across the order channels?

To analyse the number of orders by time of day and identify peak periods while comparing order times across different order channels, you can make the following observations:

# 1. Peak Order Times:

   - Based on the provided data, it appears that the peak order times are generally in the afternoon and early evening, specifically between 2 PM and 5 PM. During this time, the total number of orders is the highest.

# 2. Order Channels:

   - The data shows the distribution of orders across different order channels, including Mobile App, USSD, Web App, and Whatsapp.

# 3. Time of Day vs. Order Channels:

   - For a more detailed analysis, we can observe the distribution of orders across different order channels for each time of day.
  
   - For example, at 5 PM, the majority of orders (340) are from the Web App channel, while the Mobile App channel has 58 orders.

# 4. Least Active Times:

   - The data also shows that the least active times for orders are late at night (1 AM to 3 AM) and early in the morning (5 AM to 6 AM). During these hours, there are very few orders.

# 5. Overall Distribution:

In conclusion, we can conclude that the peak order times are in the afternoon and early evening, with variations in order distribution across different order channels at different times of the day. This analysis can help make informed decisions about resource allocation and marketing strategies for different order channels.

# f). to determine if there is a significant difference in the popularity of Home Care variants across customer types or order channels, let's analyze the provided data and provide insights:

# 1.	Popularity of Home Care Variants Across Customer Types:
   
•	Under "Customer Type," you have categories like "Mobile App," "Web App," and "Whatsapp."

•	In the "Home Care" row, you can see the quantities sold for each customer type.

•	For "Mobile App," it's 818.5.

•	For "Web App," it's 8

•	For "Whatsapp," it's 594.

From this data, it appears that "Mobile App" has the highest quantity of Home Care variants sold, followed by "Whatsapp." "Web App" has the lowest quantity.

# 3.	Popularity of Home Care Variants Across Order Channels:

•	Under "Order Channel," you have categories like "General Trade," "Modern Trade," and "Wholesale."

•	In the "Home Care" row, you can see the quantities sold for each order channel.

•	For "General Trade," it's 1420.5.

•	For "Modern Trade," it's 2.

•	For "Wholesale," it's 34.

It's evident that "General Trade" has the highest quantity of Home Care variants sold, followed by "Wholesale." "Modern Trade" has the lowest quantity.

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/55c610f9-692e-4b99-aa11-4b6d4a50a211)

# 4. What Two Variants Are Most Likely to Be Bought Together:

   - "Good Mama Cleaning Detergent Floral 80g x 50" and "Good Mama Cleaning Detergent 170g x 26 Floral" are the two variants most likely to be bought together, with a total quantity of 489.

# 5. What Three Variants Have the Highest Order Frequencies

   - The three variants with the highest order frequencies are:
     
     - "Good Mama Cleaning Detergent 170g x 26 Floral" with a total quantity of 471.
       
     - "Good Mama Cleaning Detergent Floral 80g x 50" with a total quantity of 489.
       
     - "So Easy 80g x 51" with a total quantity of 160.

# In conclusion, the popularity of Home Care variants varies across different customer types and order channels. "General Trade" and "Mobile App" customers tend to purchase the most Home Care variants. Two Home Care variants, "Good Mama Cleaning Detergent Floral 80g x 50" and "Good Mama Cleaning Detergent 170g x 26 Floral," are often bought together. The variants "Good Mama Cleaning Detergent 170g x 26 Floral," "Good Mama Cleaning Detergent Floral 80g x 50," and "So Easy 80g x 51" have the highest order frequencies. However, further analysis would be needed to assess the rate of purchase for high-valued versus lower-valued SKUs and calculate average order frequencies.

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/1d36dda4-e8be-43e1-9a35-9fa5ab9ea690)

# Question 2 visualization

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/2feb2acf-3a48-47df-ae46-2117eb9c521c)

# 3) Answer the following questions using any charts of your choice for visualisation (Show working for all answers provided)																				
																				
a)	What is the Peak Delivery Time (Hours of the Day)		

b)	Show the breakdown of orders by turnaround time from order to fulfilment (Use bands). What percentage of orders were delivered within the expected delivery timeline?		

c)	Show the fulfilment rate by the top 10 delivery agents also indicating what volume of orders were delivered by them			

d)	What is the correlation between time of order and delivery success?	

e)	What products contribute to 80% of the loss sale value and what five delivery agents are mostly responsible for that?																			
																				
Insights																				
i)	What insight can you identify between the delivery timelines of the worst and the least performing Delivery Agent.

ii)	Rank Delivery Agents by their average time to fulfilment highlighting the top 10 agents with the shortest turnaround times

iii)	Analyse the relationship between value of products in the delivery agent's van and successful delivery (Use Value Bands)		

v)	Provide insights as to the relationship between late or no fulfilment and how they affect customer buying frequency																			

# Question 3 Answers

# a). what is the Peak Delivery Time (Hours of the Day)

To find the peak delivery time (hours of the day)

We extracted time from Delivery date to create a column Delivery Time 
Using 

    =TEXT([@[Delivery Date]], "hh:mm:ss")

1. Create a pivot table:
   
2. Drag the "Delivery Date" or "OrderedAt Date" field into the "Rows" area.
   
3. Drag the "Delivery Time" field into the "Values" area.

# To calculate the peak delivery time, you can sort the table by the count of deliveries in descending order. The time with the highest count will be the peak delivery time.

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/e045b598-9c31-4a32-8157-363b3df59e0c)

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/704570f2-8f9b-4ff6-8327-f53b4ce735df)


# b). To show the breakdown of orders by turnaround time from order to fulfillment and calculate the percentage of orders delivered within the expected delivery timeline you can follow these steps:

1. We create a Time interval column band 0-6 hours by using the formula

        =INT([@[Fulfilment Time]]/0.25)*0.25
   
We got 0.25 by inserting 06:00 to one of the cell and changing the data-type to general, this will covert it to  0.25

2. Create a pivot table and do the following:
   
   - Drag the "Order No." field to the "Rows" area.
     
   - Drag the “Time interval” field to the "Values" area. By default, it count the number of orders within each time band.
     
3. To calculate the percentage of orders delivered within the expected delivery timeline, we can create a calculated field. Right-click anywhere in the PivotTable and select "Fields, Items & Sets," then
 choose "Calculated Field."

4. In the "Insert Calculated Field" dialog, name your calculated field (e.g., "On-Time Percentage"). In the formula box, enter the following formula:
   
   `=COUNT (Time interval) / COUNT ([Order No.])`
   
   This formula calculates the percentage of orders delivered within 6 hours (Time interval)
   
5. PivotTable will now show the breakdown of orders by fulfillment time bands, and the "On-Time Percentage"
   
# Analysis 

My defined delivery timeline is 0-6 hours. Here's the breakdown of orders by turnaround time within the 0-6 hour’s band:

- Orders Delivered within 0-6 Hours: 98 orders
  
- Orders Delivered within 7-12 Hours: 43 orders
  
- Orders Delivered within 13-18 Hours: 18 orders
  
- Orders Delivered within 19-24 Hours: 9 orders
  
Now, to calculate the percentage of orders delivered within the expected delivery timeline (0-6 hours):

    Percentage = (Orders Delivered within 0-6 Hours / Total Orders) * 100
    Percentage = (98 / 1790) * 100
    Percentage ≈ 5.47%

# So, approximately 5.47% of orders were delivered within the expected delivery timeline of 0-6 hours.

# c). to show the fulfillment rate by the top 10 delivery agents and indicate the volume of orders delivered by them, you can follow these steps:
I
   a. Drag "Delivery Agent" to the "Rows" area.
   
   b. Drag "Order No." to the "Values" area. By default, it will show the count of orders.
   
   c. Drag "shippingStatus" to the "Filters" area and filter it to show only "Delivered" orders.

# II. To show only the top 10 delivery agents by order count:

   a. Click on the drop-down arrow next to "Delivery Agent" in the PivotTable.
   
   b. Select "Value Filters" and choose "Top 10."
   
   c. In the "Top 10 Filter" dialog, select "Top" and set it to 10.
   
   d. Choose to filter by "Sum of Order No." (count of orders).

   ![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/44e5e91b-9a44-4762-8387-f590612f43ae)

# III. We also calculated the fulfillment rate for each delivery agent by dividing the count of "Delivered" orders by the total count of orders for that agent. 

    =COUNTIF([Delivery Agent], [@[Delivery Agent]])/1790
    
# IV. We added Fulfilment Time (In hours)_ to the value area and convert it to average to get Average of Fulfilment Time (In hours)_

# Analysis

# 1. Insight between delivery timelines of the worst and least performing Delivery Agent:

•	The worst performing Delivery Agent, "Mary Paul," has an average fulfillment time of 5.67 hours.

•	The least performing Delivery Agent, "Fidelia Martins," has an average fulfillment time of 1.00 hour.

•	The worst performing agent has a shorter average fulfillment time compared to the least performing agent. This means "Mary Paul" tends to fulfill orders faster than "Fidelia Martins."

# 2. Ranking Delivery Agents by average time to fulfillment (Top 10):

•	To rank the top 10 agents with the shortest turnaround times, you can sort the "Average of Fulfilment Time (In hours)" in descending order. 

Here are the top 10 agents with the shortest turnaround times:

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/84ab9850-9149-41c9-a043-205a8579a786)

    
9.	AMANDA Jonathan (Average Fulfilment Time: 2.35 hours)
    
10.	Victoria Sam (Average Fulfilment Time: 1.00 hour)
    
# 3. Based on the "Count of Product" and "Sum of fulfillment rate." Here are some insights into the relationship between the value of products and successful delivery:

Ps: 
    
      =IF(AND([@[fulfillment rate ]]< 0.01), "Low", IF(AND([@[fulfillment rate ]] <= 0.04), "Medium", "High")) was used to Derive fulfillment rate band 
            
# I). High-Value Products:

•	Mary Paul and Bernice Segs both have "High" value products in their vans.

•	Mary Paul had 79 products with a fulfillment rate of 10.72%.

•	Bernice Segs had 72 products with a fulfillment rate of 8.91%.

# II). Medium-Value Products:

•	There are several agents with "Medium" value products in their vans, such as Maryjane Joel, Martins Obafemi, Esther Victor, and many others.

•	They have varying numbers of products and fulfillment rates, ranging from 7.37% to 0.01%.

# III). Low-Value Products:

•	Agents with "Low" value products include Ashimedua Godson, Grace George, Tife Chibunnam, and others.

•	They also have varying numbers of products and fulfillment rates, ranging from 0.50% to 0.01%.

The data suggests that agents with "High" value products in their vans tend to have higher fulfillment rates compared to those with "Medium" and "Low" value products. 

# d). to analyze the correlation between the time of order and delivery success you can follow these steps:

  # I). In the PivotTable Field List, drag and drop the following fields into the appropriate areas:
  
   - Rows: Date
     
   - Values: Count of "Delivery Agent" (to track successful deliveries)
     
  - Values: Average of "Fulfilment Time (In hours)" (to measure the average delivery time)

    ![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/cce5cf26-8846-4fe8-aef5-59fd5c199858)
    
Iv). we now have a pivot table that shows the count of deliveries and the average fulfilment time for each date (or time period).

# e). what products contribute to 80% of the loss sale value and what five delivery agents are mostly responsible for that?

# I. In the new worksheet (or within the existing one), you will see the PivotTable Field List on the right. Drag and drop the following fields to the relevant areas:

   - Drag "Product" to the Rows area.
     
   - Drag "Unit Price" to the Values area, and set the calculation to "Sum."
     
   - Drag "Producer" to the Columns area.
     
   - Drag "Delivery Agent" to the Filters area.
     
# II. To identify products contributing to 80% of the loss sale value:

   - Sort the "Product" field in descending order by the "Value."
     
   - Start scrolling down the list of products and sum the values in your head or in a separate cell. Continue until you reach the point where the cumulative sum exceeds 80% of the total sales value.

# III. To find the top five delivery agents responsible for that loss:

   - In the Filters area, select the Delivery Agents one by one and observe how the "Sum of Value" changes for each agent. Sort them in descending order of sales value.
     
   - Identify the top five delivery agents contributing to the loss based on your observations.

Here's a list of the products and their respective loss sale values (Sum of Value):

1. Dano Cool Cow - 3,399,537.5
   
2. Good Mama Cleaning Detergent - 2,592,550
   
3. Peak Milk - 2,370,600
   
4. Nestle Golden Morn - 1,958,775
   
5. Hollandia Evap. Milk - 1,806,820
    
6. Golden Penny Spaghetti - 1,525,750
 
7. Three Crowns Milk - 1,110,500
  
8. Golden Penny Semovita - 931,147.5

9. My Boy Eldorin Infant Formula - 764,400

10. Bournvita - 749,200
 
11. Cowbell Milk - 719,050
  
12. Titus Sardines - 707,850
 
13. Canoe Bar Soap - 623,250
 
14. So Easy Detergent - 620,700

15. Molfix Jumbo - 529,650

16. Tasty Tom Sachet - 486,300

17. Premier Bar Soap - 456,200
    
18. Nasco Cornflakes - 448,500
  
19. Molfix Twin - 376,000
 
20. Sonia Tomato Paste - 369,000
  
21 Dano Full Cream - 359,120

22. Golden Penny Noodles - 325,750
 
23. Indomie Indomitable Pack - 305,440

24. Molfix Small - 279,650
  
25. Sonia Tomato Tin - 277,100
  
26. Nibit Cookies - 246,000
  
27. Ariel Detergent - 219,770
  
28. WAW Detergent - 210,900
  
29. Nittol Antibacterial Powder Detergent - 210,400
 
30. Gino Max Cube

To find the products that contribute to 80% of the loss sale value, you can sum the values of these products in descending order until you reach or exceed 80% of the total loss sale value. 

Starting from the top products:

1. Dano Cool Cow - 3,399,537.5
2. Good Mama Cleaning Detergent - 2,592,550
3. Peak Milk - 2,370,600
4. Nestle Golden Morn - 1,958,775
5. Hollandia Evap. Milk - 1,806,820

These products sum up to approximately 10,128,282.5. This is already over 80% of the total loss sale value. These are the products that contribute to 80% of the loss sale value.

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/112de2d8-1d2d-4ba4-bff6-8b4597a70e80)


# Question 3 Visualization

![image](https://github.com/Hykze1/Route-To-Market-/assets/100960483/3ffec772-e601-4b59-9b2d-cc9a1372a2ef)


