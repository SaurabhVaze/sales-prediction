# Outlet Store Sales Prediction
## Determine how store item and branch variables explain outlet sales

**Saurabh Vaze**: 

### Business problem:
Outlet store executives would like to know what variables within their product and branch offerings drive overall sales.


### Data: source:https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/\
This dataset originally included 8523 entries with 12 columns explaining product and store traits. 

#### Target:
***Item_Outlet_Sales***

#### Features

Item_Identifier ***(excluded from analysis)***

Item_Weight

Item_Fat_Content

Item_Visibility 

Item_Type             

Item_MRP 

Outlet_Identifier ***(excluded from analysis)***

Outlet_Establishment_Year ***(excluded from analysis)***

Outlet_Size  

Outlet_Location_Type

Outlet_Type

## Methods
All features related to identification were excluded, along with the year stores opened


The numerical columns were scaled, and categorical columns were one-hot-encoded to process the data for modeling.


I tried a linear regression and a regression tree model to determine which model best accounted for variablity across features.

Afer dropping certain redundant or unneeded fetaures, the resulting dataset, with only 3 numerical features gave me doubts regarding the eventual efficacy of my modeling attempts.

## Results

#### Visual 1 Title
![locationvsmeansalesviz](https://user-images.githubusercontent.com/43122737/176916024-932767c1-3cd5-4c43-b015-1f8be8706c73.png)

> This visualization showed us that tier 2 stores tended to have the highest sales, with minimal variance, while tier 1 stores returned the lowest sales

#### Visual 2 Title
![weightvsvisibilityviz](https://user-images.githubusercontent.com/43122737/176916065-0b76b618-bd7b-48bf-839b-ea794c6f40f6.png)

> We see little to no correlation between item weight and item visibility across all stores, indicating the two features are not dependant on one another

## Model

The regression tree model, in the end, proved more effective in accounting for variation, with an R^2 score ***(0.59)***, higher than that of my linear regression model(0.56). It must be noted that these values are relatively low, but this is likely a limitation from the data, rather than the model chosen. The decision tree model had a depth of 42, and after a test of max R^2 scores, I was able to determine that the optimal depth was 5. After tuning the model to its most effective state, the variability within the test data was explained 59% of the time.


## Recommendations:

The store executives can treat this project as a good first step, but *I would recommend them to provide a more robust data set that will better encompass the dozens of likely factors that influence total outlet sales.* However, this preliminary study will show that, for example, items with greater visibility will drive sales, while other factors may not be as impactful. 

## Limitations & Next Steps

This dataset would be improved with a larger number of quantitative numerical features, focusing more on product attributes, which will give us the best idea of how sales may react. Multiple redundant columns regarding store size can likely be replaced with information regarding average income of the customer base for a store(which will likely affect the magnitude of spending at a specific store), or the population of the surrounding area, which would provide a larger customer base, and therefore more sales.

Next steps will be contingent on more usable data with a larger feature count, that will more directly relate to the target information we are looking for, and a test of a wider range of models to best assess which strategy will give us the most accurate outputs.

### For further information


For any additional questions, please contact **svaze7@gmail.com**
