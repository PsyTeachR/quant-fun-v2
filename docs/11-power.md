# Power and error

Until now we have mainly spent time on data-wrangling, visualising our data, and running inferential tests. In the lectures you have also learned about additional aspects of inferential testing and trying to reduce certain types of error in your analyses:

* **Type I error** - rejecting the null hypothesis when it is true (otherwise called **alpha** or $\alpha$). Probably better recalled as **False Positives** 
* **Type II error** - retaining the null hypothesis when it is false (otherwise called **beta** or $\beta$). Probably better recalled as **False Negatives**

Building from there we have started to discuss the idea of **power** ($1-\beta$) which you should understand as the probability of correctly rejecting the null hypothesis when it is false; i.e. finding an effect that is there rather than having a false negative and missing the effect. In short, **the higher the power of your study the better**, with the field standard proposed as $power >= .8$. Often in fact Registered Reports are required to have a power of at least $power >= .9$.

In the past a number of studies have fallen short of the field standard and it is this lack of power that is thought to be a key issue in the replication crisis. This makes sense because, if you think about it, if previous studies only have a $power = .5$ then they only have a .5 probability of correctly rejecting the null hypothesis. As such there may be a large number of studies where the null hypothesis has been rejected when it should not have been; the field becomes noisy at that point and you are unsure which studies will replicate.  It is issues like this that led us to redevelop our courses and why we really want you to understand power as much as possible.

When designing an experiment any good researcher will consider four key elements of a study. The **APES**:

* **alpha** - most commonly thought of as the significance level (i.e., your p-value); usually set at $\alpha = .05$
* **power** - typically set at $power = .8$
* **effect size** - size of the relationship/difference between two variables
* **sample size** - number of participants you ran in your study

And the beautiful thing is that **if you know three of these elements then you can calculate the fourth**. The two most common calculations prior to a study would be:

1. to determine the appropriate sample size required to obtain the effect size that you are interested in. I.e. you know everything except the sample size. Generally, **the smaller the effect size, the more participants you will need**, assuming power and alpha are held constant at **.8** and **.05** respectively.
2. to determine the smallest effect size you can reliably detect given your sample size. I.e. you know everything except the effect size. For example, say you are using an open dataset (like the mini-project) and you know they have run 100 participants, you can't add any more participants, but you want to know what is the minimum effect size you could reliably detect in this dataset.

**Note:** Most papers would discourage you from calculating what is called Observed Power. This is where you calculate the power after running the study, based on your effect size and sample size. Similarly, this would be running an analysis on an open dataset, finding the outcome, and then calculating the power based on the outcome. Avoid this. You can read more about why, here, in your own time if you like: [Lakens (2014) Observed Power, and what to do if your editor asks for post-hoc power analyses](http://daniellakens.blogspot.com/2014/12/observed-power-and-what-to-do-if-your.html)

So let's jump into this a bit now and start running some analyses to help further our understanding of alpha, power, effect sizes and sample size!

## Effect Size

We will focus on effect sizes for t-tests for this worksheet.  There are a number of different effect sizes to choose from in the field but today we will look at one type of effect size - **Cohen's d**: the standardised difference between two means (in units of SD). The thing to note is that the formula is slightly different depending on the type of t-test used and it can sometimes change depending on who you read. For this worksheet, let's go with the following formulas:

* One-sample t-test & paired-sample t-test:  

> $d = t\ / \sqrt(N)$

* Independent t-test: 

> $d = 2t\ / \sqrt(df)$


Let's now try out some calculations. We will start with just looking at effect sizes from t-tests before calculating power in later tasks.

## Activity 1: Set-up {#power-a1}

Do the following. 

* Open R Studio and set the working directory to your chapter folder.  
* Open a new R Markdown document and save it in your working directory. Call the file "Power and Effect Size".    
* If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Delete the default R Markdown welcome text and insert a new code chunk that loads the packages `pwr`, `broom`, and `tidyverse` using the `library()` function. You may need to install `pwr` if you are working on your own machine but remember **never install packages on a university machine**.

## Activity 2: Effect size from a one-sample t-test {#power-a2}

* You run a one-sample t-test and discover a significant effect, t(25) = 3.24, p < .05. Using the above formulas, calculate `d` and determine whether the effect size is small, medium or large.


<div class='webex-solution'><button>Helpful hint</button>


    
* Use the appropriate formula from above for the one-sample t-tests. 
* You have been given a t-value and df (degrees of freedom), you still need to determine `n` before you calculate `d`. 
* According to Cohen (1988), the effect size is small (.2 to .5), medium (.5 to .8) or large (> .8).
    
    

</div>
  

Answering the following questions to check your answers. The solutions are at the bottom if you need them:

* Enter, in digits, how many people were run in this study: <input class='webex-solveme nospaces' size='2' data-answer='["26"]'/>
* Which of these codes is the appropriate calculation of `d` in this instance:<select class='webex-select'><option value='blank'></option><option value='answer'>d = t/sqrt(N)</option><option value=''>d = 2t/sqrt(df)</option></select>
* Enter the correct value of `d` for this analysis rounded to 2 decimal places: <input class='webex-solveme nospaces' size='4' data-answer='["0.64",".64"]'/>
* According to Cohen (1988), the effect size for this t-test would probably be considered: <select class='webex-select'><option value='blank'></option><option value=''>small</option><option value='answer'>medium</option><option value=''>large</option></select>  

## Activity 3: Effect size from between-subjects t-test {#power-a3}

* You run a between-subjects t-test and discover a significant effect, t(30) = 2.9, p < .05. Calculate `d` and determine whether the effect size is small, medium or large.


<div class='webex-solution'><button>Helpful hint</button>


    
* Use the appropriate formula above for between-subjects t-tests. 
* According to Cohen (1988), the effect size is small (.2 to .5), medium (.5 to .8) or large (> .8).
    
    

</div>
  

Answer the following questions to check your answers. The solutions are at the bottom if you need them:

* Enter, in digits, how many people were run in this study: <input class='webex-solveme nospaces' size='2' data-answer='["32"]'/>
* Which of these codes is the appropriate calculation of `d` in this instance:<select class='webex-select'><option value='blank'></option><option value=''>d = t/sqrt(N)</option><option value='answer'>d = 2t/sqrt(df)</option></select>
* Enter the correct value of `d` for this analysis rounded to 2 decimal places:  <input class='webex-solveme nospaces' size='4' data-answer='["1.06"]'/>
* According to Cohen (1988), the effect size for this t-test would probably be considered: <select class='webex-select'><option value='blank'></option><option value=''>small</option><option value=''>medium</option><option value='answer'>large</option></select>


## Activity 4: t-value and effect size for a between-subjects Experiment {#power-a4}

* You run a between-subjects design study and the descriptives tell you: **Group 1**, M = 10, SD = 1.3, n = 30; **Group 2**, M = 11, SD = 1.7, n = 30. Calculate `t` and `d` for this between-subjects experiment.


<div class='webex-solution'><button>Helpful hint</button>


    
* Before you can calculate `d` (using the appropriate formula for a between-subjects experiment), you need to first calculate `t` using the formula:  

`t = (Mean1 - Mean2)/sqrt((var1/n1) + (var2/n2))`

* `var` stands for variance in the above formula. Variance is not the same as the standard deviation, right? Variance is measured in squared units. So for this equation, if you require variance to calculate `t` and you have the standard deviation, then you need to remember that `var = SD^2`.
* Now you have your t-value, but for calculating `d` you also need degrees of freedom. Think about how you would calculate `df` for a between-subjects experiment, taking `n` for both Group 1 and Group 2 into account.
* Remember that convention is that people report the `t` and `d` values as positive.

    

</div>
   

Answer the following questions to check your answers. The solutions are at the bottom if you need them:

* Enter the correct `t-value` for this test, rounded to two decimal places: <input class='webex-solveme nospaces' size='5' data-answer='["2.56","-2.56"]'/>

* Which of these codes is the appropriate calculation of `d` in this instance:<select class='webex-select'><option value='blank'></option><option value=''>d = t/sqrt(N)</option><option value='answer'>d = 2t/sqrt(df)</option></select>
* Based on the above t-value above, enter the correct value of `d` for this analysis rounded to 2 decimal places: <input class='webex-solveme nospaces' size='4' data-answer='[".67","0.67"]'/>
* According to Cohen (1988), the effect size for this t-test would probably be described as: <select class='webex-select'><option value='blank'></option><option value=''>small</option><option value='answer'>medium</option><option value=''>large</option></select>

We've asked you to calculate Cohen's D by hand above to reinforce your understanding of what `d` actually means, however, if you were conducting a t-test in R, chances are that you would get R is calculate this for you.

* Think back to the t-test chapter. What is the name of the function for calculating Cohen's D? <input class='webex-solveme nospaces' size='7' data-answer='["cohensD"]'/>. What package does this come from? <input class='webex-solveme nospaces' size='3' data-answer='["lsr"]'/>

**Excellent!** Now that you are comfortable with calculating effect sizes, we will look at using them to establish appropriate sample sizes for a given power. Remember, in analysis, in nearly all occasions we should set the effect size as the minimum effect size we are interested. This can be determined through discussion, through previous studies, through pilots studies, or through rules of thumb like Cohen (1988). However, also keep in mind that the lower the effect size, the larger the sample size you will need. Everything is a trade-off.

## Activity 5: `pwr.t.test()` {#power-a5}

Today we will use the functions `pwr.t.test()`, `pwr.r.test()` and `pwr.chisq.test` from the package `pwr` to run power calculations for t-tests, correlations and chi-square.

Remember that for more information on this function, simply do `?pwr.t.test` in the console. On doing this you will see that `pwr.t.test()` takes a series of inputs:

* **n** - Number of observations (**per sample**)
* **d** - Effect size (Cohen's d) - difference between the means divided by the pooled standard deviation
* **sig.level** - Significance level (Type I error probability) or $\alpha$
* **power** - Power of test (1 minus Type II error probability) or $1-\beta$
* **type** - Type of t test : `one.sample`, `two.sample`, or `paired`
* **alternative** - the type of hypothesis; `"two.sided", "greater", "less"`

The function works on a leave one out principle. You give it all the information you have and it returns the element you are missing.  So, for example, say you needed to know how many people per group (n) you would need to detect an effect size of `d = .4` with `power = .8`, `alpha = .05` in a `two.sample` (between-subjects) t-test on a `two.sided` hypothesis test.  

* Run the below code:





```r
pwr.t.test(d = .4,
           power = .8,
           sig.level = .05,
           alternative = "two.sided",
           type = "two.sample")
```

The output tells you that you would need 99.0803248 people **per condition**. But you only get whole people and we like to be conservative on our estimates so we would actually run 100 **per condition**. That is a lot of people!!!

To make the output of `pwr.t.test()` easier to work with, we're going to amend the code to just give us exactly the number that we want. 

* `tidy()` will tidy the output and store it in a table (you have used this before)
* `pull()` will pull out a single value (in this case `n` but it could be anything)
* `ceiling()` rounds up to give us the next highest whole number


```r
pwr.t.test(d = .4,
           power = .8,
           sig.level = .05,
           alternative = "two.sided",
           type = "two.sample") %>% 
  tidy() %>% 
  pull(n) %>%
  ceiling()
```

## Activity 6: Sample size for standard power one-sample t-test {#power-a6}

* Assuming you are interested in detecting a minimum Cohen's d of **d = .23**, what would be the minimum number of participants you would need in a one-sample t-test, assuming **power = .8**, $\alpha$ **= .05**, on a two-sided hypothesis? 

Using a pipeline, store the answer as a single, rounded value called `sample_size_t` (i.e. use `tidy() %>% pull() %>% ceiling()`).


<div class='webex-solution'><button>Helpful hint</button>


* Use the list of inputs above as a kind of check-list to clearly determine which inputs are known or unknown. This can help you enter the appropriate values to your code.
* The structure of the `pwr.t.test()` would be very similar to the one shown above except two.sample would become one.sample
* You will also need to use `tidy() %>% pull(n)` to help you obtain the sample size and `%>% ceiling()` to round up to the nearest whole participant.

</div>
  

Answer the following question to check your answers. The solutions are at the bottom if you need them:

* Enter the minimum number of participants you would need in this one-sample t-test: <input class='webex-solveme nospaces' size='3' data-answer='["151"]'/>

## P&E Activity 7: Effect size from a high power between-subjects t-test

* Assuming you run a between-subjects t-test with 50 participants per group and want a power of .9, what would be the minimum effect size you can reliably detect? Assume standard $\alpha$ and alternative hypothesis settings.

Answer the following questions to check your answers. The solutions are at the bottom if you need them:

* Based on the information given, what will you set `type` as in the function? <select class='webex-select'><option value='blank'></option><option value=''>one.sample</option><option value='answer'>two.sample</option></select>
* Based on the output, enter the minimum effect size you can reliably detect in this test, rounded to two decimal places: <input class='webex-solveme nospaces' size='4' data-answer='[".65","0.65"]'/>
* According to Cohen (1988), the effect size for this t-test is <select class='webex-select'><option value='blank'></option><option value=''>small</option><option value='answer'>medium</option><option value=''>large</option></select>
* Say you run the study and find that the effect size determined is d = .50. Given what you know about power, select the statement that is true: <select class='webex-select'><option value='blank'></option><option value=''>the study is sufficiently powered as the analysis indicates you can detect only effect sizes smaller than d = .65</option><option value='answer'>the study is underpowered as the analysis indicates you can detect only effect sizes larger than d = .65</option></select>

## Activity 8: Sample size for a correlation {#power-a8}

Now, we're going to do the same thing but for a correlation analysis using `pwr.r.test`. The structure of this function is very similar to `pwr.t.test()` and works on the same leave-one-out principle:

* **n** - Number of observations
* **r** - Correlation coefficient
* **sig.level**	- Significance level (Type I error probability)
* **power** - Power of test (1 minus Type II error probability)
* **alternative** - a character string specifying the alternative hypothesis, must be one of `two.sided` (default), `greater` (a positive correlation) or `less` (a negative correlation).

* Assuming you are interested in detecting a minimum correlation of **r = .4** (in either direction), what would be the minimum number of participants you would need for a correlation analysis, assuming **power = .8**, $\alpha$ **= .05**? 

Using a pipeline, store the answer as a single, rounded value called `sample_size_r` (i.e. use `tidy() %>% pull() %>% ceiling()`).

* Enter the minimum number of participants you would need in this correlation: <input class='webex-solveme nospaces' size='2' data-answer='["46"]'/>

## Activity 9: Effect size for a correlation analysis {#power-a9}

* You run a correlation analysis with 50 participants and the standard power and alpha levels and you have hypothesised a positive correlation, what would be the minimum effect size you can reliably detect? 

Answer the following questions to check your answers. The solutions are at the bottom if you need them:

* Based on the information given, what will you set `alternative` as in the function? <select class='webex-select'><option value='blank'></option><option value=''>two.sided</option><option value='answer'>greater</option><option value=''>less</option></select>
* Based on the output, enter the minimum effect size you can reliably detect in this test, rounded to two decimal places: <input class='webex-solveme nospaces' size='4' data-answer='[".34","0.34"]'/>
* According to Cohen (1988), the effect size for this correlation is <select class='webex-select'><option value='blank'></option><option value=''>small</option><option value='answer'>medium</option><option value=''>large</option></select>
* Say you run the study and find that the effect size determined is d = .24. Given what you know about power, select the statement that is true: <select class='webex-select'><option value='blank'></option><option value=''>the study is sufficiently powered as the analysis indicates you can detect only effect sizes smaller than d = .24</option><option value='answer'>the study is underpowered as the analysis indicates you can detect only effect sizes larger than d = .34</option></select>

## Activity 10: Power of published research {#power-a10}

Thus far we have used hypothetical situations - now go look at the paper on the [Open Stats Lab](https://sites.trinity.edu/osl/data-sets-and-activities/t-test-activities) website called Does Music Convey Social Information to Infants? (we have used this dataset in the t-test chapter). You can download the pdf and look at it, but here we will determine the power of the significant t-tests reported in Experiment 1 under the Results section on Pg489. There is a one-sample t-test and a paired-samples t-test to consider, summarised below. Assume testing was at power = .8, alpha = .05. Based on your calculations are either of the stated effects underpowered?

1. one-sample: t(31) = 2.96, p = .006, d = 0.52
2. paired t-test: t(31) = 2.42, p = .022, d= 0.43


<div class='webex-solution'><button>Helpful hint</button>


    
* To calculate n: `n = df + 1`.
    

</div>


Which of the t-tests do you believe to be underpowered? Why do you think this may be? Additional information about this can be found in the solution to task 8 at the end of this activity.

### Finished! {#power-fin}

**Great!** Hopefully you are now starting to see the interaction between alpha, power, effect sizes, and sample size. We should always want really high powered studies and depending on the size of the effect we are interested in (small to large), and our $\alpha$ level, this will mean we will need to run more or less participants to make sure our study is well powered. Points to note:

* Lowering the $\alpha$ level (e.g. .05 to .01) will reduce the power.
* Lowering the effect size (e.g. .8 to .2) will reduce the power.
* Increasing power (.8 to .9) will require more participants.

A high-powered study looking to detect a small effect size at a low alpha will require a large number of participants!

There are additional functions in the `pwr` package for other types of statistical analyses. We will include these calculates as part of the ANOVA and regression chapters. 

If you want more examples of power to reinforce your understanding, go back and calculate the power of the t-tests, correlations, and chi-squares from earlier chapters. 


## Activity solutions {#power-sols}

Below you will find possible solutions to the above tasks. But first, be sure to try the tasks before looking at the solutions and only look at them when you have exhausted all possibilities and yourself.  If that is the case, and you are sure you want to do this, then here are the potential solutions.

### Activity 1 {#power-a1sol}


<div class='webex-solution'><button>Activity 1</button>


```r
library(pwr)
library(broom)
library(tidyverse)
```

</div>

<br>
Click on the tab to reveal the solution

### Activity 2 {#power-a2sol}


<div class='webex-solution'><button>Activity 2</button>


```r
d <- 3.24 / sqrt(25 +1)

# effect is medium to large; d = .64
```

</div>

<br>
Click on the tab to reveal the solution

### Activity 3 {#power-a3sol}


<div class='webex-solution'><button>Activity 3</button>


```r
d <- (2*2.9) / sqrt(30)

# effect is large; d = 1.06
```

</div>

<br>
Click on the tab to reveal the solution

### Activity 4 {#power-a4sol}

<div class='webex-solution'><button>Activity 4</button>


```r
t = (10 - 11)/sqrt((1.3^2/30) + (1.7^2/30))

d = (2*t)/sqrt((30-1) + (30-1))

# t = 2.56
# d = .67

# Remember that convention is that people report the t and d as positive.
```

</div>

<br>
Click on the tab to reveal the solution

### Activity 6 {#power-a6sol}

<div class='webex-solution'><button>Activity 6</button>


```r
sample_size_t <- pwr.t.test(d = .23,
                            power = .8, 
                            sig.level = .05, 
                            alternative = "two.sided", 
                            type = "one.sample") %>% tidy() %>% pull(n) %>% ceiling()

sample_size_t
```

[1] 151

</div>

<br>
Click on the tab to reveal the solution

### Activity 7 {#power-a7sol}

<div class='webex-solution'><button>Activity 7</button>


```r
pwr.t.test(n = 50,
           power = .9, 
           sig.level = .05, 
           alternative = "two.sided", 
           type = "two.sample")
```

     Two-sample t test power calculation 

              n = 50
              d = 0.654752
      sig.level = 0.05
          power = 0.9
    alternative = two.sided

NOTE: n is number in *each* group

</div>

<br>
Click on the tab to reveal the solution


### Activity 8 {#power-a8sol}

<div class='webex-solution'><button>Activity 8</button>


```r
sample_size_r <- pwr.r.test(r = .4, 
                            sig.level = .05, 
                            power = .8, 
                            alternative = "two.sided") %>%
  tidy() %>% pull(n) %>% ceiling()
```

</div>

<br>
Click on the tab to reveal the solution


### Activity 9 {#power-a9sol}

<div class='webex-solution'><button>Activity 9</button>


```r
pwr.r.test(n = 50,
           sig.level = .05, 
           power = .8, 
           alternative = "greater")
```

     approximate correlation power calculation (arctangh transformation) 

              n = 50
              r = 0.3443671
      sig.level = 0.05
          power = 0.8
    alternative = greater

</div>

<br>
Click on the tab to reveal the solution

### Activity 10 {#power-a10sol}


<div class='webex-solution'><button>Activity 11</button>


```r
# Achievable Cohen d for Example 1
pwr.t.test(power = .8, 
           n = 32, 
           type = "one.sample", 
           alternative = "two.sided", 
           sig.level = .05)
```

     One-sample t test power calculation 

              n = 32
              d = 0.5112738
      sig.level = 0.05
          power = 0.8
    alternative = two.sided

```r
# This study seems ok as the authors could achieve an effect size as low as .51 and found an effect size at .52

# Achievable Cohen d for Example 2
pwr.t.test(power = .8, 
           n = 32, 
           type = "paired", 
           alternative = "two.sided", 
           sig.level = .05) 
```

     Paired t test power calculation 

              n = 32
              d = 0.5112738
      sig.level = 0.05
          power = 0.8
    alternative = two.sided

NOTE: n is number of *pairs*

```r
# this effect might not be reliable given that the effect size found was much lower than the achievable effect size. The issue here is that the researchers established their sample size based on a previous effect size and not on the minimum effect size that they would find important. If an effect size as small as .4 was important then they should have powered all studies to that level and ran the appropriate n ~52 babies (see below). Flipside of course is that obtaining 52 babies isnt easy; hence why some people consider the Many Labs approach a good way ahead.

# Below you could calculate the actual sample size required to achieve a power of .8:

sample_size <- pwr.t.test(power = .8,
                          d = .4, 
                          type = "paired", 
                          alternative = "two.sided", 
                          sig.level = .05) %>%
tidy() %>% pull(n) %>% ceiling()

sample_size
```

[1] 52

</div>

<br>
Click on the tab to reveal the solution.
