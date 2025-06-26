# Gold Membership Prediction Analysis

This data analysis project aims to develop a predictive model to identify customers with a higher likelihood of purchasing the "Gold Membership" offer at the superstore. The objective is to optimize the marketing campaign by targeting the appropriate customer segment and increasing the probability of a positive response to the offer.

Folder Structure
final code/: This folder contains the Gold_Membership.Rmd file which is necessary to replicate our analysis and results in RStudio.

## Getting Started:
To run the final R code and reproduce the analysis, follow these steps:

-Ensure you have R and RStudio installed on your machine.

-Clone or download this repository to your local system.

-Open RStudio and set the working directory to the "final code" folder using the setwd() function or the RStudio GUI.

-To run the analysis code for this project, the following R packages need to be installed and loaded:

```R
packages <- c("readr", "lubridate", "tidyverse", "ggplot2", "car", "corrgram", "RColorBrewer", "rpart", "rpart.plot", "randomForest", "caret", "ROCR",
              "rcompanion", "visreg", "MASS", "pscl", "dplyr", "pROC", "car", "ggplot2")

-Please ensure that you have these packages installed before running the code.

-The dataset used for this analysis can be found at https://www.dropbox.com/s/47xqmnl2464ee26/superstore_data.csv?dl=1

-Install the required packages as mentioned above by running install.packages("package_name") in the R console.

-Download the dataset with the link given above and save it in the project directory or load it directly with the link as it is laoded in the Gold_Membership.Rmd file.
 
-Execute the R scripts and functions provided in the project code.

Results and Outputs:

The analysis will generate various results and outputs, including:

Predictive model performance metrics (accuracy, precision, recall, etc.).
Visualizations such as plots, charts, and graphs illustrating the findings.
Summary, statistics and insights regarding the key factors influencing customer response to the "Gold Membership" offer.

Data Description:
The dataset variables are described as follows:

*Response (target): 1 if the customer accepted the offer in the last campaign, 0 otherwise
*ID: Unique ID of each customer
*Year_Birth: Age of the customer
*Complain: 1 if the customer complained in the last 2 years, 0 otherwise
*Dt_Customer: Date of the customer's enrollment with the company
*Education: Customer's level of education
*Marital_Status: Customer's marital status
*Kidhome: Number of small children in the customer's household
*Teenhome: Number of teenagers in the customer's household
*Income: Customer's yearly household income
*MntFishProducts: Amount spent on fish products in the last 2 years
*MntMeatProducts: Amount spent on meat products in the last 2 years
*MntFruits: Amount spent on fruit products in the last 2 years
*MntSweetProducts: Amount spent on sweet products in the last 2 years
*MntWines: Amount spent on wine products in the last 2 years
*MntGoldProds: Amount spent on gold products in the last 2 years
*NumDealsPurchases: Number of purchases made with a discount
*NumCatalogPurchases: Number of purchases made using a catalog (buying goods to be shipped through the mail)
*NumStorePurchases: Number of purchases made directly in stores
*NumWebPurchases: Number of purchases made through the company's website
*NumWebVisitsMonth: Number of visits to the company's website in the last month
*Recency: Number of days since the last purchase

Preprocessing Steps:
The following preprocessing steps were performed as part of the data cleaning and analysis:

*Transformed 'Dt_Customer' from character to date type.
*Dropped the 'ID' column.
*Aggregated individual expenditure subcategories ('MntFishProducts', 'MntMeatProducts', 'MntFruits', 'MntSweetProducts', 'MntWines', 'MntGoldProds') into a total expenditure variable called 'MntSpent'. This consolidation allows us to focus on overall spending behavior rather than specific subcategories.
*Converted 'Education' and 'Marital_Status' to categorical variables.
*In the 'Marital_Status' column, values such as "Absurd", "YOLO", and "Alone" were identified as non-standard entries and potentially errors. We converted 'Marital_Status' to a categorical variable, with the base set as "Single".
*Investigated and handled outliers in 'Income' and 'Year_Birth' variables.
*Removed entries with birth years recorded as 1900 or earlier, considering them as errors or placeholders.
*Removed the outlier in the 'Income' variable with a value of 666,666, as it significantly deviated from the mean income.
*Employed Cook's Distance and Standard Deviation Method to detect and remove outliers in 'Year_Birth' variable.
*Converted 'Kidhome' and 'Teenhome' variables to binary format.
*With the completion of the data cleaning, preprocessing, exploratory analysis, and feature engineering steps, a refined dataset named "superstore_ready"" was created. This well-structured dataset will serve as the foundation for the model building phase.

After performing the essential preprocessing steps, which primarily focused on data cleaning, these are the resulting dataset variables that will serve as the foundation for our model development:

Year_Birth 
Education 
Marital_Status 
Income 
Dt_Customer
Recency 
NumDealsPurchases
NumWebPurchases 
NumCatalogPurchases 
NumStorePurchases 
NumWebVisitsMonth 
Response 
Complain 
MntTotalSpent 
Together 
Divorced 
Widow 
Second_Cycle 
Graduation 
Master 
PHD 
Kidhome_binary 
Teenhome_binary 
Income_NumStore_Interact 
Divorced 
Widow 
Second_Cycle 
Graduation 
Master 
PHD 
Kidhome_binary 
Teenhome_binary 
Income_NumStore_Interact 
Income_NumWeb_Interact
Income_MntTotal_Spent 

License
This project is licensed under the Team20 Superstore Analytics Team License.

Contact Information
For any questions or inquiries, please contact Team20 Superstore Analytics Team.

Acknowledgments
We would like to acknowledge the contributions and support of the Team20 Superstore Analytics Team in conducting this analysis and developing the predictive model.
