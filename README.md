# sparks_foundation #
**Prediction, linear regression**
# setting work directory #
> ```setwd ("G:/sparks foundation") ```
# reading the dataset from the text document #
> ```grip_dataset <- ```
+ ```read.table("grip_dataset.txt", header = TRUE, sep = ",")```
+    2.5     21
2    5.1     47
3    3.2     27
4    8.5     75
5    3.5     30
6    1.5     20
7    9.2     88
8    5.5     60
9    8.3     81
10   2.7     25
11   7.7     85
12   5.9     62
13   4.5     41
14   3.3     42
15   1.1     17
16   8.9     95
17   2.5     30
18   1.9     24
19   6.1     67
20   7.4     69
21   2.7     30
22   4.8     54
23   3.8     35
24   6.9     76
25   7.8     86
# summarizing statistics #
   > ```summary (grip_dataset) ```
>
 Hours              Scores     
 Min.   :1.100   Min.   :17.00  
 1st Qu.:2.700   1st Qu.:30.00  
 Median :4.800   Median :47.00  
 Mean   :5.012   Mean   :51.48  
 3rd Qu.:7.400   3rd Qu.:75.00  
 Max.   :9.200   Max.   :95.00  
# viewing the first few rows of the dataset #
> ```head(grip_dataset) ```

  Hours Scores
1   2.5     21
2   5.1     47
3   3.2     27
4   8.5     75
5   3.5     30
6   1.5     20
# checking the structure of the dataset #
> ``` str(grip_dataset) ```
> 
'data.frame':   25 obs. of  2 variables:
 $ Hours : num  2.5 5.1 3.2 8.5 3.5 1.5 9.2 5.5 8.3 2.7 ...
 $ Scores: int  21 47 27 75 30 20 88 60 81 25 ...
# Scatter Plot to visualise the relationship between hours and scrores #
> ```plot(grip_dataset$Hours, grip_dataset$Scores, main = "Scatter Plot", xlab = "Hours", ylab = "Scores", pch = 16) ```
# Saved the scatter plot as a PNG file #
> ``` plot(grip_dataset$Hours, grip_dataset$Scores, main = "Scatter Plot", xlab = "Hours", ylab = "Scores", pch = 16) ```
> 
>  dev.off()
null device 
          1
> ![scatter_plot](https://github.com/mosalah2510/sparks_found/assets/128469983/02ab8029-e847-425d-be3f-0cd0adaad03f)

 # predicting the score for a student studying 9.25 hours/day #
> ``` model <- lm(Scores ~ Hours, data = grip_dataset) ```
> 
>``` summary (model) ```
> 
> Call:
lm(formula = Scores ~ Hours, data = grip_dataset)

Residuals:
    Min      1Q  Median      3Q     Max 
-10.578  -5.340   1.839   4.593   7.265 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)   2.4837     2.5317   0.981    0.337    
Hours         9.7758     0.4529  21.583   <2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 5.603 on 23 degrees of freedom
Multiple R-squared:  0.9529,    Adjusted R-squared:  0.9509 
F-statistic: 465.8 on 1 and 23 DF,  p-value: < 2.2e-16

> # displaying the predicted score #
> 
> ``` cat("Predicted Score for 9.25 hours/day", predicted_score) ```
> Predicted Score for 9.25 hours/day 92.90985
> 
> *THE STUDENT'S SCORE WILL BE APPROX 92.9% IF HE STUDIES FOR 9.25 HOURS*
# Scatter Plot With Regression Line #
``` ggplot(grip_dataset, aes(x = Hours, y = Scores))+ geom_point() + geom_smooth(method = "lm", se = FALSE) + labs(x = "Hours Studied", y = "Scores Obtained")+ ggtitle("Relationship between study hours and scores") ```
# Save the plot as PNG file #
> ``` ggsave("study_hours_vs_scores.png", width = 8, height = 6, units = "in", dpi = 300) ```
 ![study_hours_vs_scores](https://github.com/mosalah2510/sparks_found/assets/128469983/cb9c4143-357c-4a8e-bcc6-0dc3a9d3d989)
