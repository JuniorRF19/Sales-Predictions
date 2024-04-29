# Sales-Predictions


A sales prediction will be made for food products sold in different stores. The aim of this analysis is to help the store understand the properties of products and establishments that play a crucial role in increasing sales.


Nota: [Fuente original de los datos](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/#About)

#Data cleaning is performed (see code for more details)

## Regression Models Comparison for Sales Prediction

| Model               | Training R² | Test R² | MSE       | RMSE     |
|---------------------|-------------|---------|-----------|----------|
| Linear Regression   | 0.776       | 0.793   | 618035.53 | 786.15   |
| KNN (K-Nearest Neighbors) | 0.768  | 0.760   | 813052.21 | 901.69   |
| Random Forest       | 0.834       | 0.796   | 615540.74 | 784.56   |
| Decision Tree       | 0.817       | 0.755   | 746823.66 | 864.19   |

### Conclusions

- The Random Forest model achieved the highest coefficient of determination (R²) on the test set, indicating better generalization ability.
- Although the Linear Regression model has good R² performance, its RMSE is higher compared to other models, suggesting greater dispersion of errors.
- The Decision Tree model has a similar R² to other models but presents a higher RMSE, indicating greater variability in predictions.
- Based on the performance metrics and balance between accuracy and generalization, the Random Forest regression model would be the preferred choice for predicting sales.
- It is advisable to perform adjustments, optimizations, and explore other models to further improve the accuracy of predictions.


# Data Analisis
We will start by analyzing the types of items and the quantity of sales that each type represents. In order to analyze the products with the most market share.

![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/7c689387-bb96-4e04-939e-74399c8ff4a3)

We can observe that the top three products in the market are: Snack Foods, Fruits and Vegetables, and Household. We will start by analyzing the top 1 (Fruits and Vegetables).
We can create a correlation matrix in an attempt to identify trends.

![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/e94221d1-0937-4000-a958-ae284c519930)

We found a correlation between sales and MRP, but it is not definitive. We will try to make the filtering more specific in order to obtain better correlation values.
For this reason, we proceed to group by Outlet Type to determine the type of market that has the most market share of Fruits and Vegetables.

<div style="display:flex;">
    <img src="https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/e9813b8d-2547-419e-b815-7730f35b256c" alt="Image 1" style="width:45%;">
    <img src="https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/5890bba5-845a-4c55-90d5-05cd0dfbedee" alt="Image 2" style="width:45%;">
</div>

We will analyze why Supermarket Type 1 is so successful in selling this product.
To do this, we will filter this type of supermarket and the product (Fruits and Vegetables). Then, we will group the sales by the store identification code (Outlet_Identifier) to observe the behavior of all stores of this type.

![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/7c1d9726-2d77-43a4-92bd-4fc4206fdbba)

We can conclude that Supermarkets of Type 1 present similar sales for the type of product fruits and vegetables. Additionally, this Type 1 supermarket covers 87% of the fruits and vegetables market.

Now, we will redo the correlation matrix focusing on Supermarkets of Type 1 and the product of Fruits and Vegetables.

![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/421d2d4d-7b58-4131-ad28-200a647fa947)

We observe that the relationship between sales and MRP has increased slightly, but it remains inconclusive. However, the hypothesis can be proposed that Supermarkets of Type 1 dominate the market. 
We will work under this assumption.



#Analyzing the types of outlets


**Supermarket Type1**
![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/ee76c6af-56dd-45e2-b5ed-d5fc7856b86f)
Similar to the graph created with all types of markets, it is observed that the products with the largest market share are Snack Foods, Fruits and Vegetables, and Household. We can conclude that.


**Supermarket Type2**
![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/ebaf9744-c350-4cb0-8f7c-581300fe7808)
We can conclude that the products with the largest market share are Snack Foods, Fruits and Vegetables, and Household.


**Grocery Store**
![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/00b35201-5a37-4ad4-9a7b-8fd5d36d6dd8)
We can conclude that the products with the largest market share are Snack Foods, Fruits and Vegetables and Household.


**Grafico de Pie por types of outlets**
![image](https://github.com/JuniorRF19/Sales-Predictions/assets/160083935/d271c4da-ceb4-4390-8e36-97f34fd8d757)

It is observed that Supermarket Type 1 represents 86% of the sales.


**Conclusions and recommendations:**

1.   There is a predominance of three products (Snack Foods, Fruits and Vegetables, and Household) in all types of supermarkets.
2.   Supermarket Type 1 accounts for 86% of the total market. It is recommended not to neglect this type of supermarket to avoid losing market share.
3.   It could be analyzed whether Grocery Stores are profitable, as they capture a tiny percentage of the market.
