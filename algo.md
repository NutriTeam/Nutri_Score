---
layout: default
title: Algo
---
# Algorithm
We have created several algorithms that take place at different times in the application. These are the calculation of the NutriScore, the creation of nutrient recommendations and the proposal of a healthier product for users.

## NutriScore
This algorithm evolved during the project. The first version, based on the document from the French Ministry of Agriculture, was developed to calculate a single product. We have managed to have a good percentage of success as you can see on the page: Data visualization. 

This algorithm takes into account different aspects of the food. First, it determines whether or not it is a drink. Indeed, the regulations are not the same between these two categories. For beverages, for example, only pure water can have an A grade. In general, we calculate the difference in points between negative and positive points to determine the grade of the food. 

On the positive side, they are determined by the content of fruit, fibre and protein for solid foods while for beverages, only fruit will lower the product's score. Only energy and sugars are considered as negative points for both types of food. In addition, we consider lipids and sodium as negative for solid foods.

For our application, we needed to think differently. Indeed, we don't stupidly want to give a NutriScore per food to the user but a general NutriScore. To do this we created a treatment of the products before the final calculation made by our first algorithm. 
To do this, we will retrieve the selected products from the database but also, if the user has eaten raw products, we collect the nutritional values of the product using the API of American agriculture. On the basis of the quantities indicated by the user, we calculate the proportions of each product and standardize to 100g in a general product. Throughout this process, it was necessary to manage the exceptions defined by the NutriScore rules for each product before creating a single product.

## Recommendations
On the basis of the quantities of nutritional values provided by the previous algorithm and the daily recommendations defined by the Swiss Society of Nutrition (SSN), we can indicate to our users where they stand in their nutrition.  We can therefore indicate to him the weaknesses and advantages of his diet, which allows him to make clear choices to improve it. 

