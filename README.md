# SalaryGaps_vs_budget
In this project we analyze if there is a tendency or relationship between the years an employee has worked in baltimore city and the gap from their budgeted salary to their gross salary. We also make a multiple model where we also include de dept cluster to see if this has any significance.

## Calculations and definition of variables
  Salary GAP: In order to normalize the data, we used the percentage of salary difference  (Gross Salary / Net Salary). This was important in order to make fair comparisons despite the difference in salaries.
  Years worked:  I calculated the time they worked using the formula days() divided by 365. This made the calculations easier since I had a continuous variable instead of a date format.
  Clusters: I realized that there is already a cluster for departments. It is represented as a letter in Dept Id. Using LEFT() I extracted the value and then assigned each letter a value via VLOOKUP so that Excel could run the correlations and linear regressions.
  
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
   
 # Conclusions
