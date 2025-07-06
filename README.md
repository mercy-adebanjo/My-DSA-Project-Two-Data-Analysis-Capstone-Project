# My-DSA-Project-Two-Data-Analysis-Capstone-Project

It is an amazing time to learn under the Incubator Hub and here is the documentation of my Project in Data Analysis under the supervision of Digital SkilledUp Africa. The project is in 2 categories: Case Study 1: Amazon Product Review Analysis in Data Analysis and Case Study 2: Palmora Group HR Analysis

However, we shall be treating the Case Study 3: Palmora Group HR Analysis in this Resipository.The Project topic contains, Case study 3 data set, Palmora Group HR Analysis  description of data sets and requirements.

## Project Overview
This data analysis project aims to focus on  gender-related issues within the organization and its regions generate 

Project Topic: Case Study 3: Palmora Group HR Analysis
Data set: [download here the Excel file](
Below are other informations attached to the data set:

Company Overview
You are working as a Junior Data Analyst at RetailTech Insights, a company that provides e-commerce analytics solutions to sellers on platforms like Amazon. Your team has been tasked with analysing product and customer review data to generate insights that can guide product improvement, marketing strategies, and customer engagement.

Dataset Description
The dataset contains information scraped from Amazon product pages, including: • Product details: name, category, price, discount, and ratings • Customer engagement: user reviews, titles, and content • Each row represents a unique product, with aggregated reviewer data stored as comma-separated values Total Records: 1,465 rows TotalFields: 16 columns 5.

Data Source
The primary data source used here is (xlsx) provided by DSA Incubator Hub.Here is the link download here the Excel file

Tools Used
MS Excel
Data cleaning
Data manipultion
Data munching
Data Cleanig and Preparation
In the initial phase of the data cleaning and preparations,we perform the following actions;

Data loading and inspection
Handling missings variables
Data cleaning and formatting
Expository data Analysis
EDA involves the exploring of data to answers some questions about the data.some of this questions are : Use pivot tables and calculated columns where necessary to answer the following:

What is the average discount percentage by product category?
How many products are listed under each category?
What is the total number of reviews per category?
Which products have the highest average ratings?
What is the average actual price vs the discounted price by category?
Which products have the highest number of reviews?
How many products have a discount of 50% or more?
What is the distribution of product ratings (e.g., how many products are rated 3.0, 4.0, etc.)?
What is the total potential revenue (actual_price × rating_count) by category?
What is the number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)?
How does the rating relate to the level of discount?
How many products have fewer than 1,000 reviews?
Which categories have products with the highest discounts?
Identify the top 5 products in terms of rating and number of reviews combined.
Final Task: Dashboard Creation Using your cleaned dataset and pivot outputs, build an Excel dashboard. Unleash your Creativity
Data Analysis
These include, step by steps of the Analysis of the Dataset.The analysis are thereby stated below:

Ultimate Underlying Assumption: No product should have more than a record since its all about reviews and ratings.

So to get that done with your dataset, you'll need remove duplicated Product_Id.

So to confirm if there are duplicated products simply because of the nature of info we are required to get insight on, you need to do this.

Click any cell within your dataset and apply Ctrl + A to highlight all the data.

So while still highlighted, click your Data Tab.

Goto highlight duplicate, then remove duplicate.

Click on unselect All first and click on product id.

After a message pops up after removing duplicates.

Now that you have your Unique/Distinct Products, NEXT is CATEGORY

Right click on the category column and click copy or go to the home tab and copy

Paste in the new worksheet: only the category column and proceed do text to column

seperate them using delimetre common to it(|)

pick the first one and give it a name it,here I gave it "Category" or "Main Categoty"

Do the same for product

The question would be why? Yeah, because its "multi-level Product" same as Category.

Insert the newly created Category and Product,then delte the old ones in your dataset.

Then go ahead and delete that sheet for the category-splits as if nothing has happened there.

Confirm that columns H to L values are reliable. How do you do that?

Use your filter tool to validate each columns's values in Column (DFGKL)

For the ones with blank cell,You have 2 options here - either to uncheck this particular row OR you go further to visit the product site as provided in cell T1167.Here I uncheked the blank row,since it is not a real life situation.

Next is calculated Column

Below are the Calculated Columns

Price Range Bucket was calculate using if fuctions =IF(D2<200,"< ₹200",IF(D2<=500,"₹200–₹500","> ₹500")).drag this function down the column.
Discount Band was calculate using if fuctions=IF(G2<=10%,"1%-10%",IF(G2<=20%,"11%-20%",IF(G2<=30%,"21%-30%",IF(G2<=40%,"31%-40%", IF(G2<=50%,"41%-50%",IF(G2<=60%,"51%-60%",IF(G2<=70%,"61%-70%",IF(G2<=80%,"71%-80%",IF(G2<=90%,"81%-90%",IF(G2<=100%,"91%-100%"))))))))))
Discount Range, calculated with if function,=IF(G2>=50%,"= or more than 50%","less than 50%")
Rating and rating Count Combined was calculate by =K2*L2
Lower Reviewed was calculate using if fuctions =IF(L2<1000,"Yes","No")
Total Potential Revenue was calculate by multiplying =F2*L2
Table Analysis
All the stated above analysis is done in the table here download my Calculated table here

Pivot Analysis
My Pivot Analysis was done using the above Table Analysis. download here my Pivote Analysis

Steps taking to anwser the question under EDA are:
1.Average discount percentage by product category Add a calculated column: = (Actual Price - Discounted Price) / Actual Price * 100
Then use a Pivot Table:

Rows: Category

Values: Discount % → summarize by Average

2.How many products are listed under each category Pivot Table:
Rows: Category

Values: Product Name → set to Count (Distinct)

3.Total number of reviews per category Use Rating Count column
Pivot Table:

Rows: Category

Values: Rating Count → Sum

4.Which products have the highest average ratings Sort your dataset by the Average Rating column (descending)
Pick top entries

5.Average actual price vs discounted price by category Pivot Table:
Rows: Category

Values: Actual Price → Average Discounted Price → Average

6.Which products have the highest number of reviews Sort Rating Count column in descending order
7.How many products have a discount of 50% or more Add calculated column: =IF(Discount % >= 50, "Yes", "No")
Then use a COUNTIF

8.Distribution of product ratings Pivot Table:
Rows: Rating (rounded if needed)

Values: Product Name → Count.

9.Total potential revenue by category (Actual Price × Rating Count) Add calculated column: =Actual Price * Rating Count
Pivot Table:

Rows: Category

Values: Potential Revenue → Sum

10.Number of unique products per price range bucket Create new column Price Bucket:
Excel formular=IF(Discounted Price < 200, "<₹200", IF(Discounted Price <= 500, "₹200–₹500", ">₹500")) (they should take note of the symbol for some systems) Pivot Table:

Rows: Price Bucket

Values: Product Name → Count

11.How does the rating relate to the level of discount Create a scatter chart:
X-axis: Discount %

Y-axis: Average Rating. Steps:

Create a new column that groups Discount % into buckets like:

0–10%, 11–20%, ..., 91–100%

excel formular=IF([@Discount%]<=10, "0-10%", IF([@Discount%]<=20, "11-20%", IF([@Discount%]<=30, "21-30%", ...))) Use a Pivot Table:

Rows: Discount Bucket

Values: Average Rating → summarize as Average

Insert a line chart to show trend of average rating across discount buckets

12.How many products have fewer than 1,000 reviews Filter Rating Count < 1000
Use COUNT or check the status bar, count is there.

13.Which categories have products with the highest discounts Use the earlier Discount % column
Pivot Table:

Rows: Category

Values: Discount % → Max

14.Top 5 products by rating + number of reviews combined Create calculated column: =Average Rating + (Rating Count / Scaling Factor) (Choose a factor like 1000 to balance weight)
Sort descending and pick top 5.

My Dash
My dash board was calculated using my Pivot Analysis, below is the link to my Dash board download here

Limitation
This project expository and ,analysis is limited by material and a litle time frame.

Referencies
Class notes
DSA Youtube lectures
CHATGPT
dowload my workings here
About
No description, website, or topics provided.
Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 0 watching
Forks
 0 forks
Releases
No releases published
Create a new release
Packages
No packages published
Publish your first package
Footer
© 2025 GitHu
