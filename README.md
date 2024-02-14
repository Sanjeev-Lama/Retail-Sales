# Retail-Sales

## Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [EDA Questions](#eda-questions)
  - [Query Sample](#query-sample) 
- [Tableau Visualizations](#tableau-visualizations)
  - [Gender-specific Shopping Trends Across Time](#gender-specific-shopping-trends-across-time)
  - [Typical Amount Spent in Each Purchase](#typical-amount-spent-in-each-purchase)
  - [How Different Age Groups and Genders Spend Over Time](#how-different-age-groups-and-genders-spend-over-time)
  - [Understanding Price Variations Across Product Categories](#understanding-price-variations-across-product-categories)
- [Recommendations](#recommendations) 
- [Links](#links)


## Project Overview

This project focuses on leveraging data analytics techniques to derive insights from a retail sales dataset. The primary objective is to understand various aspects of customer behavior, purchasing patterns, and product preferences. Through collaborative efforts and advanced data analytics techniques, this project successfully uncovered valuable insights into retail sales dynamics, contributing to informed decision-making processes.
For a detailed project walkthrough, refer to the comprehensive documentation available [here](https://chat.openai.com/share/ffc827e0-0d0d-44f9-aa64-09175c67f5a2).

#### Key Components:
- Data Cleaning and Preparation: The dataset was cleaned and prepared using MySQL, ensuring data integrity.
- Utilization of ChatGPT: ChatGPT played a pivotal role in refining SQL queries and fostering critical thinking throughout the project.
- Exploratory Data Analysis: Various questions were addressed, including inquiries into customer demographics, purchasing behaviors, and product category preferences.
- Visualization in Tableau: The project culminated in the creation of visually appealing dashboards using Tableau to showcase key findings and insights.


## Data Source

Retail Sales Dataset : [Kaggle](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset/data) 

## EDA Questions

All of my thinking approaches and queries of the questions can be found in this [link](https://docs.google.com/document/d/16_NAU0MkbFRbCRxEkoUAJ61tVwdl7P3K1UMS07PMvbE/edit) along with all other details as well.

- How does customer age and gender influence their purchasing behavior?
- Are there discernible patterns in sales across different time periods?
- Which product categories hold the highest appeal among customers?
- What are the relationships between age, spending, and product preferences?
- How do customers adapt their shopping habits during seasonal trends?
- Are there distinct purchasing behaviors based on the number of items bought per transaction?
- What insights can be gleaned from the distribution of product prices within each category?

#### Query Sample 
- What are the relationships between age, spending, and product preferences?

```
SELECT 
    age,
    product_category,
    COUNT(DISTINCT transaction_id) AS num_transactions,
    SUM(quantity) AS total_quantity,
    SUM(total_amount) AS total_spent,
    SUM(total_amount) / COUNT(DISTINCT transaction_id) AS avg_spending_per_transaction,
    SUM(quantity) / SUM(total_amount) AS quantity_to_amt_ratio
FROM retail_sales
GROUP BY 1, 2
ORDER BY 6 DESC;
```


## Tableau Visualizations

### Gender-specific Shopping Trends Across Time

I went with a bar graph because it's straightforward and shows us how spending varies between men and women. The setup, with bars side by side, really highlights those differences over time. looking at three specific product types and their trends—the bar graph is the way to go. It's just easy to understand and lets us compare things efficiently.
![Gender-specific Shopping Trends Across Time](https://github.com/Sanjeev-Lama/Retail-Sales/assets/158605914/47b0ba77-dbac-447e-8474-d658cb550004)

### Typical Amount Spent in Each Purchase

This visualization displays average spending per transaction across age groups and product categories using horizontal bars. Each bar represents a product category, with length indicating average spending. Filters for date and gender enable customized analysis. Color coding by age group enhances readability and reveals spending patterns. Additional insights on quantity, total amount, and quantity to amount ratio deepen understanding of purchasing behavior within each group and category.
![Typical Amount Spent in Each Purchase](https://github.com/Sanjeev-Lama/Retail-Sales/assets/158605914/dc0050a1-b19b-47dc-99ed-1cc07a1b4eab)

### How Different Age Groups and Genders Spend Over Time

This line graph visualization is chosen for its ability to effectively capture temporal spending patterns, allowing users to track spending evolution over time. It facilitates comparison across age groups and genders, providing clear insight into shifts or patterns. Segmentation by product category through color coding adds depth, highlighting significant contributors to spending. The option to filter by age group and gender enhances customization and relevance to specific demographics. Overall, its comprehensive and intuitive format makes it the preferred choice for analyzing spending behaviors over time.
![How Different Age Groups and Genders Spend Over Time](https://github.com/Sanjeev-Lama/Retail-Sales/assets/158605914/69a630e0-8e84-4449-a32b-d2f04c069243)

### Understanding Price Variations Across Product Categories

This bar chart visualization is favored for its clarity and adaptability in analyzing price variations across product categories. It enables straightforward comparisons of average price per unit and enhances category differentiation through color coding. Users can customize the analysis with filters for gender, date, and age group, providing relevant insights. Additionally, details on total quantity purchased and maximum/minimum prices per unit enrich the analysis, offering a comprehensive understanding of price dynamics. Overall, it provides an intuitive and insightful exploration of price variations across product categories, making it the preferred choice for this metric.
![Understanding Price Variations Across Product Categories](https://github.com/Sanjeev-Lama/Retail-Sales/assets/158605914/2bbb281f-3841-454b-a0e8-5d1cb338715a)

## Recommendations

- We need to tailor marketing efforts to cater to gender-specific shopping trends, focusing on clothing for females and electronics for males, while enhancing overall customer engagement through personalized strategies.
- Optimizing the marketing strategies based on age group spending behaviors over time, capitalizing on peak purchasing periods and utilizing dynamic filters for targeted promotions.
- We also need to focus on leveraging strong consumer demand in clothing to drive revenue growth, highlight the value proposition of beauty products through targeted marketing, and maintain consistent pricing strategies across all categories for balanced offerings.

## Links
1. Entire conversation with [ChatGPT](https://chat.openai.com/share/ffc827e0-0d0d-44f9-aa64-09175c67f5a2)
2. My Approach and Queries are [here](https://docs.google.com/document/d/16_NAU0MkbFRbCRxEkoUAJ61tVwdl7P3K1UMS07PMvbE/edit)
3. Tableau Story Visualizations are [here](https://public.tableau.com/app/profile/sanjeev.lama/viz/Retail_Sales_17075229358090/RetailSales?publish=yes)
4. [Video Presentation](https://www.canva.com/design/DAF8mGNlKZE/cHp1k_Gg0znXmH3QkFOJ1Q/view?utm_content=DAF8mGNlKZE&utm_campaign=designshare&utm_medium=link&utm_source=recording_view)
5. Project Presentation [here]([Retail Sales Project.pdf](https://github.com/Sanjeev-Lama/Retail-Sales/files/14284508/Retail.Sales.Project.pdf) 


