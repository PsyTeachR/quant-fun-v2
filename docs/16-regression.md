# Regression

In this activity, you will be working with real data and using regression to explore the question of whether there is a relationship between statistics anxiety and engagement in course activities.  The hypothesis is that students who are more anxious about statistics are less likely to engage in course-related activities.

We are going to analyse data from the STARS Statistics Anxiety Survey, which was administered to students in the third-year statistics course in Psychology at the University of Glasgow. All the responses have been anonymised by associating the responses for each student with an arbitrary ID number (integer).

The STARS survey (Cruise, Cash, & Bolton, 1985) is a 51-item questionnaire, with each response on a 1 to 5 scale, with higher numbers indicating greater anxiety.

Cruise, R. J., Cash, R. W., & Bolton, D. L. (1985). Development and validation of an instrument to measure statistical anxiety. *Proceedings of the American Statistical Association, Section on Statistical Education*, Las Vegas, NV.

![*Example items from the STARS survey (Cruise, Cash, & Bolton, 1985)*](images/stars_survey.png)

As a measure of engagement in the course, we will use data from Moodle usage analytics. Over the course of the term, there were eight optional weekly on-line sessions that students could attend for extra support. The variable `n_weeks` in the `psess.csv` file tells you how many (out of eight) a given student attended.

Our hypothesis was that greater anxiety would be reflected in lower engagement.  Answer the following question.

If our hypothesis is correct then there should be <select class='webex-select'><option value='blank'></option><option value=''>a positive</option><option value=''>no</option><option value='answer'>a negative</option></select> correlation between students' mean anxiety levels and `n_weeks`.

## Activity 1: Setup {#regression-a1}

* Open R Studio and set the working directory to your chapter folder. Ensure the environment is clear.   
* Open a new R Markdown document and save it in your working directory. Call the file "Regression".    
* Download <a href="L3_stars.csv" download>L3_stars.csv</a> and <a href="psess.csv" download>psess.csv</a> and save them in your chapter folder. Make sure that you do not change the file name at all.    
* If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Delete the default R Markdown welcome text and insert a new code chunk that loads `pwr`, `broom`, `see`, `performance`, `report` and `tidyverse` using the `library()` function.
* Load the two CSV datasets into variables called `stars` and `engage` using `read_csv()`.





## Activity 2: Tidy the data {#regression-a2}

* Take a look at both of the datasets you loaded in.

The next thing we need to do is to calculate a mean anxiety score for each student (recall that individual students are identified by the `ID` variable).

Recall the difference between *wide* and *tidy* data. In wide data, each row represents an individual case, with observations for that case in separate columns; in tidy data, each row represents a single observation, and the observations are grouped together into cases based on the value of a variable (for these data, the `ID` variable).

* The STARS data are currently in <select class='webex-select'><option value='blank'></option><option value='answer'>wide</option><option value=''>tidy</option></select> format.

Before we calculate means, you need to use `pivot_longer()` to restructure the STARS data into the appropriate "tidy" format; i.e., so that it looks like the table below.


| ID | Question | Score |
|:--:|:--------:|:-----:|
| 3  |   Q01    |   1   |
| 3  |   Q02    |   1   |
| 3  |   Q03    |   1   |
| 3  |   Q04    |   1   |
| 3  |   Q05    |   1   |
| 3  |   Q06    |   1   |

* Write and run the code to do tidy the STARS data, and store the resulting table as `stars2`.


## Activity 3: Calculate mean anxiety for each student {#regression-a3}

* Now that you've got the data into a tidy format, use `summarise()` and `group_by()` to calculate mean anxiety scores (`mean_anxiety`) for each student (`ID`). Store the resulting table in a variable named `stars_means`. 




## Activity 4: Join the datasets together {#regression-a4}

* In order to perform the regression analysis, combine the data from `stars_means` with `engage` using `inner_join()`. Call the resulting table `joined`. It should look like this:


| ID | mean_anxiety | n_weeks |
|:--:|:------------:|:-------:|
| 3  |     1.06     |    5    |
| 7  |     2.71     |    2    |
| 12 |     2.24     |    3    |
| 16 |     2.86     |    2    |
| 23 |     1.71     |    6    |
| 29 |     1.80     |    7    |

## Activity 5: Calculate descriptives for the variables overall {#regression-a5}

It is also useful to calculate descriptives statistics for the sample overall so that you can check that the sample scores are what you were expecting (e.g., are they comparable to previous studies and samples?). This is also useful for the write-up.

* Run the below code. Read each line and ensure you understand what is being calculated.


```r
descriptives <- joined %>%
  summarise(mean_anx = mean(mean_anxiety, na.rm = TRUE),
            sd_anx = sd(mean_anxiety, na.rm = TRUE),
            mean_weeks = mean(n_weeks, na.rm = TRUE),
            sd_weeks = sd(n_weeks, na.rm = TRUE))
```


## Activity 6: Visualisations {#regression-a6}

* Now that you've have all of the variables in one place, write the code to reproduce the exact scatterplot below (using ggplot2).

<div class="figure" style="text-align: center">
<img src="16-regression_files/figure-html/scatter-1.png" alt="Scatteplot of mean anxiety and attendance" width="100%" />
<p class="caption">(\#fig:scatter)Scatteplot of mean anxiety and attendance</p>
</div>

* According to the scatterplot, <select class='webex-select'><option value='blank'></option><option value=''>there is no apparent relationship</option><option value='answer'>as anxiety increases, engagement decreases</option><option value=''>as anxiety increases, engagement increases</option></select>


## Activity 7: Run the regression {#regression-a7}

The `lm()` function from Base R is the main function to estimate a *L*inear *M*odel (hence the function name `lm`). `lm()` uses formula syntax that you have seen before, i.e., `DV ~ predictor`.  

* Use the `lm()` function to predict `n_weeks` (DV) from `mean_anxiety` (predictor).  Store the result of the call to `lm()` in the variable `mod`.  To see the results, use `summary(mod)`.



```r
mod <- lm(n_weeks ~ mean_anxiety, joined)
mod_summary <- summary(mod)
```

Answer the following questions about the model. You may wish to refer to the lecture notes to help you answer these questions.

1. The estimate of the y-intercept for the model, rounded to three decimal places, is <input class='webex-solveme nospaces' size='5' data-answer='["9.057"]'/>
2. To three decimal places, if the GLM for this model is $Y_i = \beta_0 + \beta_1 X_i + e_i$, then $\beta_1$ is <input class='webex-solveme nospaces' size='6' data-answer='["-2.173"]'/>
3. To three decimal places, for each unit increase in anxiety, `n_weeks` decreases by <input class='webex-solveme nospaces' size='5' data-answer='["2.173"]'/>
4. To two decimal places, what is the overall F-ratio of the model? <input class='webex-solveme nospaces' size='5' data-answer='["11.99"]'/>
5. Is the overall model significant? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
6. What proportion of the variance does the model explain? <input class='webex-solveme nospaces' size='5' data-answer='["23.39"]'/>


<div class='webex-solution'><button>Explain these answers</button>

1. In the summary table, this is the estimate of the intercept.
2. In the summary table, this is the estimate of mean_anxiety, i.e., the slope.
3. In the summary table, this is also the estimate of mean_anxiety, the slope is how much it decreases so you just remove the - sign. 
4. In the summary table, the F-ratio is noted as he F-statistic.
5. The overall model p.value is .001428 which is less than .05, therefore significant. 
6. The variance explained is determined by R-squared, you simply multiple it by 100 to get the percent. You should always use the adjusted R-squared value.

</div>
  
<br>

## Activity 8: Assumption checking {#regression-a8}

Just like with ANOVA, you can't check the assumptions until you've run the regression so now we'll do that to check whether there's anything to be concerned about. As we covered in the lecture, the assumptions for regression are a little bit more involved than they were for ANOVA.

1. The outcome/DV is a interval/ratio level data 
2. The predictor variable is interval/ratio or categorical (with two levels)
3. All values of the outcome variable are independent (i.e., each score should come from a different participant)
4. The predictors have non-zero variance
5. The relationship between outcome and predictor is linear
6. The residuals should be normally distributed
7. There should be homoscedasticity (homogeneity of variance, but for the residuals)

Assumptions 1-3 are nice and easy. We know this from the data we have and the design of the study. Assumption 4 simply means that there is some spread in the data - for example, there's no point running a regression with age as a variable if all your participants are 20 years old. We can check this using the scatterplot we created in Activity 4 and we can see that this assumption is met, we do indeed have a spread of scores. 

For the rest of the assumptions, we're going to use functions from the packages `see` and `performance` that make life a whole lot easier. 

First, we can use `check_model()` to produce a range of assumption test visualisations. Helpfully, this function also provides a brief explanation of what you should be looking for in each plot - if only all functions in R were so helpful!

* If you get the error message `Failed with error:  ‘there is no package called ‘qqplotr’’`, install the package `qqplotr`, you don't need to load it using `library()`, but `check_model()` uses it in the background.

* If your `check_model()` plots are not showing, try maximising your plot window.


```r
check_model(mod)
```

<div class="figure" style="text-align: center">
<img src="16-regression_files/figure-html/check_model-1.png" alt="Visual assumption checks" width="100%" />
<p class="caption">(\#fig:check_model)Visual assumption checks</p>
</div>

For Assumption 5, linearity, the plot suggests it's not perfect but it looks pretty good.

As we've already noted, it's good to visualise your assumption checks because just relying on statistics can be problematic, as they can be sensitive to small or large sample sizes. However, it can also be reassuring to have a statistical test to back up your intuitions from the plot.

For Assumption 6, normality of residuals, the plot does suggest that the residuals might not be normal, so we can check this with `check_normality()` which runs a Shapiro-Wilk test.


```r
check_normality(mod)
```

```
## Warning: Non-normality of residuals detected (p = 0.008).
```

The result confirms that the residuals are not normally distributed, something that is likely being exacerbated by the relatively small sample size. If you're feeling confident, you can see how we might resolve this below, but for the core aims of this chapter we'll conclude that it's because of the sample and continue.


<div class='webex-solution'><button>Transforming the data to correct for non-normality</button>


There are multiple ways you can transform data to deal with non-normality, you can find more information about data transformation in the [Appendix here](https://psyteachr.github.io/msc-conv/data-transformation.html).

First, we need to get a sense of what the issue is with our dependent variable, in this case `n_weeks`. A simple histogram shows that the DV isn't a normal distribution, instead, it looks more like a [uniform distribution](https://openstax.org/books/introductory-statistics/pages/5-2-the-uniform-distribution).


```r
ggplot(joined, aes(x = n_weeks)) +
  geom_histogram(binwidth = 1)
```

<img src="16-regression_files/figure-html/unnamed-chunk-2-1.png" width="100%" style="display: block; margin: auto;" />

It's important to remember that the assumptions of regression are that the residuals are normally distributed, not the raw data, however, transforming the DV can help.

To transform the uniform distribution to a normal distribution, we're going to use the `unif2norm` function from the `faux` package (which you may need to install).

This code uses `mutate()` to create a new variable `n_weeks_transformed` that is the result of the transformation. 


```r
library(faux)
joined <- mutate(joined, 
                 n_weeks_transformed = unif2norm(n_weeks))

ggplot(joined, aes(x = n_weeks_transformed)) +
  geom_histogram()
```

<img src="16-regression_files/figure-html/unnamed-chunk-3-1.png" width="100%" style="display: block; margin: auto;" />

You'll notice that the histogram for the transformed variable still doesn't look amazing, but remember it's the residuals, not the raw data that matters. If we re-run the regression with the transformed data and then check the model again, things are looking much better.


```r
mod_transformed <- lm(n_weeks_transformed ~ mean_anxiety, joined)
check_normality(mod_transformed)
check_model(mod_transformed)
```

<img src="16-regression_files/figure-html/unnamed-chunk-4-1.png" width="100%" style="display: block; margin: auto;" />

```
## OK: residuals appear as normally distributed (p = 0.107).
```

It's worth saying at this point that which transformation you use, and whether it works, can be a bit of trial-and-error.


</div>

<br>

For homoscedasticity, the plot looks mostly fine, but we can double check this with `check_heteroscedasticity()` and the result confirms that the data have met this assumption.


```r
check_heteroscedasticity(mod)
```

```
## OK: Error variance appears to be homoscedastic (p = 0.542).
```


## Activity 9: Power and effect size {#regression-a9}

First we can calculate the minimum effect size we were able to detect given the sample size and design of the study using `pwr.f2.test()`. As usual, we fill in all the information we have and set the effect size argument, in this case `f2`, to `NULL`.


```r
pwr.f2.test(u = 1, v = 35, f2 = NULL, sig.level = .05, power = .8)
```


<div class='webex-solution'><button>Explain the pwr.f2.test function</button>

**u** - Numerator degrees of freedom. This the number of coefficients you have in your model (minus the intercept)
**v** - Denominator degrees of freedom. This is calculated as v=n-u-1, where n is the number of participants
**f2** - The effect size - here we are solving the effect size, so this parameter is left as NULL
**sig.level** - The significance level of your study
**power** - The power level of your study

</div>
  
<br>

* Based on the power analysis, what is the minimum effect size we were able to detect rounded to 2 decimal places? <input class='webex-solveme nospaces' size='0.22' data-answer='[".22"]'/>  
* According to Cohen's guidelines, this would be a <select class='webex-select'><option value='blank'></option><option value=''>Small</option><option value='answer'>Medium</option><option value=''>Large</option></select> effect.

There is no formula to calculate our observed f^2^, we must do it manually using the formula from the lecture.


```r
f2 <- mod_summary$adj.r.squared/(1 - mod_summary$adj.r.squared)
```

* Is the observed effect size larger than the minimum effect size we could detect? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes, our study is sufficiently powered</option><option value=''>No, our study is underpowered</option></select>

## Activity 10: Write-up {#regression-a10}

There's two ways we can use R to help with the write-up. The first is inline coding like we've done in the other chapters, and the second is to use the `report` package. Which one you use is entirely up to you but it's nice to have options.

We need to manually calculate the p-value for the inline coding as you can't extract it from the `lm()` model. Run the below code to do this.


```r
f <-mod_summary$fstatistic
mod_p <- pf(f[1], f[2], f[3], lower=FALSE) 
```

Now, copy and paste the below code into **white-space** and knit the document.


```r
A simple linear regression was performed with engagement (M = `r descriptives$mean_weeks %>% round(2)`, SD = `r descriptives$sd_anx %>% round(2)`) as the outcome variable and statistics anxiety (M = `r descriptives$mean_anx %>% round(2)`, SD = `r descriptives$sd_anx %>% round(2)`) as the predictor variable. The results of the regression indicated that the model significantly predicted course engagement (F(`r mod_summary$fstatistic[2]`, `r mod_summary$fstatistic[3]`) = `r mod_summary$fstatistic[1] %>% round(2)`, p < .001, Adjusted R2 = `r mod_summary$adj.r.squared %>% round(2)`, f2 = .63), accounting for `r (mod_summary$adj.r.squared %>% round(2))*100`% of the variance. Anxiety was a significant predictor (β = `r mod$coefficients[2] %>% round(2)`, p < `r mod_p %>% round(3)`.
)
```

A simple linear regression was performed with engagement (M = 4.54, SD = 0.56) as the outcome variable and statistics anxiety (M = 2.08, SD = 0.56) as the predictor variable. The results of the regression indicated that the model significantly predicted course engagement (F(1, 35) = 11.99, p < .001, Adjusted R2 = 0.23, f^2^ = .63), accounting for 23% of the variance. Anxiety was a significant predictor (β = -2.17, p < 0.001.
)

The second option uses `report`. Just like with the t-test, the output of these functions doesn't tend to be useable without some editing but particularly when you're first learning how to write-up stats it can be useful to have this kind of template (and also to see that there's different ways of reporting stats).

Running `report()` will output a summary of the results which you could copy and past into your Word document.


```r
report(mod)
```

```
## We fitted a linear model (estimated using OLS) to predict n_weeks with mean_anxiety (formula: n_weeks ~ mean_anxiety). The model explains a statistically significant and moderate proportion of variance (R2 = 0.26, F(1, 35) = 11.99, p = 0.001, adj. R2 = 0.23). The model's intercept, corresponding to mean_anxiety = 0, is at 9.06 (95% CI [6.32, 11.80], t(35) = 6.71, p < .001). Within this model:
## 
##   - The effect of mean anxiety is statistically significant and negative (beta = -2.17, 95% CI [-3.45, -0.90], t(35) = -3.46, p = 0.001; Std. beta = -0.51, 95% CI [-0.80, -0.21])
## 
## Standardized parameters were obtained by fitting the model on a standardized version of the dataset. 95% Confidence Intervals (CIs) and p-values were computed using the Wald approximation.
```

## Activity solutions {#regression-sols}

### Activity 1 {#regression-a1sol}


<div class='webex-solution'><button>Solution</button>


```r
library("pwr")
library("broom")
library("see")
library("performance")
library("report")
library("tidyverse")

stars <- read_csv("L3_stars.csv")
engage <- read_csv("psess.csv")
```

</div>


** Click tab to see solution **

### Activity 2 {#regression-a2sol}


<div class='webex-solution'><button>Solution</button>


```r
stars2 <- pivot_longer(data = stars, names_to = "Question", values_to = "Score",cols = Q01:Q51) %>%
  arrange(ID)
```

</div>


** Click tab to see solution **

### Activity 3 {#regression-a3sol}


<div class='webex-solution'><button>Solution</button>


```r
stars_means <- stars2 %>%
  group_by(ID) %>%
  summarise(mean_anxiety = mean(Score, na.rm = TRUE),
            min = min(Score), 
            max = min(Score),
            sd = sd(Score))
```

</div>


** Click tab to see solution **

### Activity 4 {#regression-a4sol}


<div class='webex-solution'><button>Solution</button>


```r
joined <- inner_join(stars_means, engage, "ID")
```

</div>


** Click tab to see solution **

### Activity 6 {#regression-a6sol}


<div class='webex-solution'><button>Solution</button>


```r
ggplot(joined, aes(mean_anxiety, n_weeks)) +
  geom_point() +
  geom_smooth(method = "lm")+
  theme_minimal()
```

</div>


** Click tab to see solution **

