# Geospatial Analysis of Costa Rica

Costa Rica is located in Central America, comprised of 51,100 square kilometers of land. The country is bordered by Nicaragua to the north and Panama to the south. Additionally, it is situated between the Caribbean Sea (along the 185 mile northeastern coastline) and the Pacific Ocean (along the 630 mile southwestern coastline). 

## Political Subdivisions of Costa Rica

Costa Rica is composed of provinces, cantons, and districts. Within Costa Rica, there are 7 provinces each composed of a series of cantons, totaling to 81 cantons throughout the country. Each of these cantons are then further divided into districts (totaling to 473 districts country wide). 

![](sanjose.png)

The map above provides a general overview of the country’s provinces, along with a more specified view of two: the provinces of Guanacaste and Limón. (Due to the influence of tourism in both of these areas, I was hoping to focus on these provinces for later analysis. However, due to their high population numbers, I had to select different areas for subsequent analysis.)

## Modeling the Population of Costa Rica

![](all.png)

To begin my attempt at modeling Costa Rica’s population, I began by collecting many different types of data on the country as a whole. This included data surrounding the nigh-time lights of the area, the distance to water sources, topographical data, slope of the land, etc. By collaborating all of these attributes (and going through some logistical processes to adjust the data’s format), I was able to make a model of the country’s population based on these geospatial covariates. I found that the most convincing correlation was made when all available variables were utilized in a combined model, resulting in an r-squared value of about .83. (The graph above is an illustration of this combined model.) 

![](21.png)

By far the most predictive single variable was night-time lights. Utilizing this attribute alone still provided a strong r-squared value of about 0.79. The resulting model for this variable is shown above, along with a simple map showing the illustration of nigh-time lights throughout the country. Comparing this map to the political boundaries, one can notice a fixation of lights focused around the region of the capital city, San Jose. Upon noticing this association, it was interesting to perform further analysis on the distribution of night-time lights throughout the country. The histogram below shows density as a function of night-time lights, and it can be seen that a few cities fall well above the norm of light present. One of these cities is likely the capital.

![](histogram.png)

To further my analysis of Costa Rica’s population modeling, I created three final models. The first two models used the population of the country as the response variable and come variation of the geospatial covariates as the predictors. One model used the sum of these covariates, and one used the mean of each covariate. The final model also used the mean as a predictor but employed the log of the population as the response variable. A table comparing the vital determinants of accuracy for each model is shown below. (The sum of absolute differences is a summation of all individual differences between predicted values and the actual values throughout the country.) 

| **Model**        | **Sum of Absolute Differences**| **Adjusted R-Squared Value**  |
| ---------------- |:------------------------------:| -----------------------------:|
| Sums             | 4,664,191                      | .8009                         |
| Means            | 4,559,883                      | .01015                        |
| Log of Population| 4,643,811                      | .07743                        |

Although none of these models were perfect in their predictions of Costa Rica’s population distribution, in comparison, the sum model would be considered the most accurate in my eyes. (The map below is a visual representation of the difference of model vs. reality for the sum models along with a 3D visual as well.) The sum model did accumulate the largest sum of absolute differences; however, the variance among the models in terms of the sums of their absolute differences varied by less than 3% of each other. Meanwhile, the differences between the models’ r-squared values are much more intense. The mean and log of population models resulted in r-squared values that show almost no correlation between the actual population data and the model’s regression.; however, the sum model resulted in a strong r-squared value. Overall, I believe that the large difference in r-squared values between the models is a better indicator than the smaller differences between the absolute error sums. With a unique population distribution in Costa Rica (resulting from poverty, overpopulation, tourism, geography, etc.), I believe that the summation model is the best model due to its assumed ability to better align with the country’s unique population trends as a result of its elevated r-squared value. 

![](differencesums.png)
![](gif.gif)

