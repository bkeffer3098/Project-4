# Final Project- Maryland Housing Market 2011-2023

### Members: 
[Brian Keffer](https://github.com/bkeffer3098),
[Ryan Pfefferle](https://github.com/peff22)

## Content

### Selected Topic
An analysis of the Housing Market sales data from 2011-2023.

### Reasons for Topic Selection
As individuals who are or will eventually be looking to own property in Maryland, we found an intial pull to this topic. As we began to explore and analyze this data, we began to see a path to be able to answer different economical questions about where someone may want to purchase property within the state.

### Description of Source Data
Our initial data source is the Maryland Realtors website: https://www.mdrealtor.org/News-and-Events/Housing-Statistics

The monthly housing statistics found there are presented as reported by Bright MLS, which is a multiple listing service (MLS) that offers a centralized platform for real estate professionals to access property listings and related information.

The data is stored in PDF format, so we converted each file into a CSV which enabled us to manipulate the data to create the visualizations and machine learning elements of the project.

The “Units” category represents sales settled in that month. The average sales is the weighted average of sales prices in the county. The average sales is the weighted average of sales prices in the county, calculated by weighting the price of homes by the number of homes sold. The median price is the middle value of the prices of all homes sold in the period—the price at which half the sold homes are above and half are below in selling price.

![source_2022](./Images/source_2022.jpg)

Our secondary source was from the Maryland state website within the Department of Assessments and Taxation: https://dat.maryland.gov/Pages/Sales-Data.aspx

This Sales Data became necessary for this projects success because it offered hundreds more observations for the machine learning models to learn from. This data is broken down into a count of quarterly sales throughout the last decade as well as the median price those units were sold for. 

![2nd_source_2023](./Images/2nd_source_2023.jpg)

### Analysis Questions

#### Tableau
Over the last 5 years, which Maryland counties have:
1. The lowest average price?
2. Shown the lowest levels of percent increase?
3. Experienced a low or high median number of days on the market? (Low days could indicate higher prices and high days could indicate lower prices)
4. Sold homes at the highest or lowest prices?
5. Sold the highest and lowest number of homes?

#### Supervised Learning
Using a decades worth of Maryland home sales data, can we:
1. Use a Logistic Regression, SVM, or Random Forest model to accurately classify whether prices for 2024 will increase of decrease?
2. Use a Linear Regression and line of best fit to predict the median price of homes?
3. Improve upon the linear regression using encoding and scaling?

## ETL Process (Extract, Transform, Load)

For our inital data, our analysis began by exporting the pdfs we were able to find as excel files. We then cleaned these excel files by deleting rows and columns we deemed uneccesary such as State Totals, Units Pending, Active Inventory, etc. Once cleaned, the manually merged the excel files into one larger dataset to display the county, year, units sold, average price, price % change, median price, median days on the market, and a column from an excel formula intially prediciting if the county's price had increased or decreased that year. This datset was then saved as a CSV for analysis purposes. 

A similar cleaning process was used for our secondary data: unnecessary rows and columns were deleted, the data was merged into one file, and the final dataset displays the county, what quarter of the year, the count of units sold, and the median price. 

# Results of Analysis

## Tableau Visualizations



## Machine Learning: Supervised

For this project and the data we analyzed, we centered around supervised learning models due to our targets being labeled and already existing within our datasets. We began by performing a logistic regression to classify for future years whether or not the county would experience a percent increase or decrease in price. 

![edited_all_stats_df](./Images/edited_all_stats_df.jpg)

We then proceeded to split our target, Increase of Decrease % Change, from our features, year, units sold, units % change, and average price, to then use a train_test_split. In this way we are using as a logistic regression to train the model to be able to accurately classify our testing group as being an increase or decrease year. Next we utilized the confusion matrix upon our training data, testing data, and predicted values to assess how accurately our model was classifying. 

![confusion_matrix](./Images/confusion_matrix.jpg)
It was here we began to notice our dataset was not as robust as we initially believed as referenced by the number of observations just being shy of 300. We were able to see high accuracy in both the training and testing groups as shown below.

![training_test_report](./Images/training_test_report.jpg)
94% accuracy for the training group and 98% accuracy for the testing group. 
