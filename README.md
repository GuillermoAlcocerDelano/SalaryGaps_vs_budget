# SalaryGaps_vs_budget
In this project I analyze if there is a tendency or relationship between the years an employee has worked in baltimore city and the gap from their budgeted salary to their gross salary. We also make a multiple model where we also include de dept cluster to see if this has any significance.

## Calculations and definition of variables
  Salary GAP: In order to normalize the data, we used the percentage of salary difference  (Gross Salary / Annual Salary). This was important in order to make fair comparisons despite the difference in salaries.
    Therefore having over 100% means they were paid more than their Annual salary was expected to be, likewise if it is below 100% it means they were payed less than their Annual Salary.   Note that the gross salary should be lower than the annual since it includes the tax bracket cuts, however when if it increases its because of overtime or other activities that lead to increase in the payroll.
  Years worked:  I calculated the time they worked using the formula days() divided by 365. This made the calculations easier since I had a continuous variable instead of a date format.
  Department type: I realized that there is already a cluster for departments. It is represented as a letter in Dept Id. Using LEFT() I extracted the value and then assigned each letter a value via VLOOKUP so that Excel could run the correlations and linear regressions.
  
  # Why is this important for the state?
  A gap between the annual salary and the gross value should be affected by the tax brackets if done accurately. However, an increase can be particularly important since it means they are paying more that what they had budgeted to pay. This can result in not having enough fundings and could also be interpreted as suspicious (since a person is collecting more than "they should"). Paying less than budget also has a negative impact since it is money that could have been spent in other needs the state may have. Having accurate budget will help the state be more efficient and financially stable (in the payroll department directly and indirectly in any other).
  
    
 # Analysis
 
 For single linear, we compared the years an employee has worked for the State and the % GAP. Consider that 100% means that they where paid exactly the amount of their Annual salary.
 As we can see in the graph, there is a relatively positive correlation that suggests that as the people work more in the goverment, their gap vs salary increases. Consider that a natural relationship is that people with longer time in the goverment will very likely have a higher salary (at least for the same position). Therefore it is important to find out why this happens. In the graph we can see that the results are very random for the first 10 years, but after a certain period, it is clear that there are more people with a GAP higher than 100% than those below. 
 
 *For multiple linear regression we additionally included the Department type to see if it was a meaningful factor but the results were fairly similar.
 
 <img src= https://github.com/GuillermoAlcocerDelano/SalaryGaps_vs_budget/blob/master/GAPvsYears.png> 
 
## Statistical accuracy of the model?
   The model has a R-correlation of 0.3419 which could be interpreted such an increase in the GAP is only 34.19% proportional to an increase in Years Worked. To be more specific, the R-squared is 0.1169 which means that the model (Linear regression) can only explain 11% of the results from GAP. When we look at the standard error, we see that it is of 0.365. Given that our variable (GAP) is a percentage, this means that the actual value for the GAP can be 36.5% more (or less) than what is predicted by this model. However, the F statistic is VERY HIGH, it is 1811, we will look further into this.
    For multiple regression we saw similar results (Correlation R=0.356, R-square=0.126, standard error= 0.36, F=990) which determines that the model was nos improved significantly by adding the new variable. In fact, since the F decreases significantly we can conclude that we should use the single linear model instead.  It is true that R squared increased suggesting its better, but this will always happen when you increase variables (which will result in over-fitting, a common error in linear regression), in this case the decrease in F is more relevant the increase in R.

Considering that the single linear model is better, it is important to highlight however that the F was very high (1800) which proves that there IS a relationship from the variable (Years worked) to the response (GAP). Since the r-quare is very low and the F is very high, this suggests there can be a model to predict the behaviour using this variables, however this model would not be a linear regression. The F shows how significant a factor is to predict the value of another, though there is no rule as to what makes an F large, usually a value higher than 10 is considered significant.
    
 # Conclusion and next steps
 
 The model is not accurate enough for us to use it to predict the real GAP, however we have seen that there is a clear tendency that there are more people getting over payed (GAP greater than 100%) than underpayed (GAP lower than 100%) from 20 years and after. This suggests that we look into other variables that may cause this trend. We tried using a multiple linear relation with department type as a factor but the model was proven to be less useful. Additionaly, since the F statistic was very high and the R-square very low, we should try different distributions or models to predict. Another approach we can do is to make a separate analysis for employees under 20 years and for employees with 20 or more years working.
  
  
# Methodology
  1. Extract data into CSV
  2. Clean data  (in this case, I removed values with blank values in hiring date  (HIRE_DT)
  3. Generate calculations described earlier in a column for each
  4. Run Excel toolkits
    4.1 For Simple Linear Regression (Simple LR): 
      a) Generate linear regression where X=Yearks Worked and Y=Salary GAP
      b) Plot graphs and ANOVA table
      c) Make analysis and conclusions
    4.2 For Multiple Linear Regression: 
      a) Run correlation between my two predictors 'Years Worked' and 'Clusters'.
      b) Generate multiple linear regression with these two predictors as X and Y= Salary Gap.
      c) Plot graphs and ANOVA table
      d) Compare to Single LR, make analysis and conclusions
   5. Final analysis and conclusions
   6. Upload to Github

 
 # Sources
  The data was retrieved from https://data.baltimorecity.gov/City-Government/Baltimore-City-Employee-Salaries-FY2018/biyh-j8tc
