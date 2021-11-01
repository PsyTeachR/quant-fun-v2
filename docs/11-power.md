# Power and Effect Sizes

Up until now we have mainly spent time on data-wrangling, understanding probability, visualising our data, and more recently, running inferential tests, i.e. t-tests. In the lectures, however, you have also started to learn about additional aspects of inferential testing and trying to reduce certain types of error in your analyses. It is this balance of minimising error in our inferential statisitcs that we will focus on today. 

First thing to remember is that, in the branch of statistics we are using here, that is Null Hypothesis Significance Testing (NHST), there are two types of <a class='glossary' target='_blank' title='A proposed explanation made on the basis of limited evidence as a starting point for further investigation.' href='https://psyteachr.github.io/glossary/h#hypothesis'>hypotheses</a>,  and what you are trying to establish is the <a class='glossary' target='_blank' title='A number between 0 and 1 where 0 indicates impossibility of the event and 1 indicates certainty' href='https://psyteachr.github.io/glossary/p#probability'>probability</a> of the null hypothesis not being accepted. Those two hypotheses are:

* The **null hypothesis** which states that the compared values **are equivalent** and, when referring to means, is written as: $H_0: \mu_1 = \mu_2$ 
* And the **alternative hypothesis** which states that the compared values **are not equivalent** and, when referring to means, is written as: $H_1: \mu_1 \ne \mu_2$.

Now, each decision about a hypothesis is prone to some degree of error and, as you will learn, the two main types of error that we worry about in Psychology are:

* **Type I error** - or <a class='glossary' target='_blank' title='When a test concludes there is an effect when there really is no effect' href='https://psyteachr.github.io/glossary/f#false-positive'>false positive</a>, is the probability of rejecting the null hypothesis when it should not be rejected (otherwise called <a class='glossary' target='_blank' title='(stats) The cutoff value for making a decision to reject the null hypothesis; (graphics) A value between 0 and 1 used to control the levels of transparency in a plot' href='https://psyteachr.github.io/glossary/a#alpha'>alpha</a> or $\alpha$). In other words, you conclude that there is a real "effect" when in fact there is no effect. The field standard rate of acceptable false positives is $\alpha = .05$ meaning that in theory 1 in 20 studies may be a false positive.
* **Type II error** - or <a class='glossary' target='_blank' title='When a test concludes there is no effect when there really is an effect' href='https://psyteachr.github.io/glossary/f#false-negative'>false negative</a>, is the probability of retaining the null hypothesis when it is false (otherwise called <a class='glossary' target='_blank' title='The false negative rate we accept for a statistical test.' href='https://psyteachr.github.io/glossary/b#beta'>beta</a> or $\beta$). In other words, you conclude that there was no real "effect" when in fact there was one. The field standard rate of acceptable false negatives is $\beta = .2$ meaning that in theory 1 in 5 studies may be a false negative. 

Adding to the ideas of hypotheses and errors, we are going to look at the idea of **power** which you will learn is the long-run probability of correctly rejecting the null hypothesis for a fixed effect size and fixed sample size; i.e. correctly concluding there is an effect when there is a real effect to detect. <a class='glossary' target='_blank' title='The probability of rejecting the null hypothesis when it is false.' href='https://psyteachr.github.io/glossary/p#power'>Power</a> is calculated as $power = 1-\beta$ and is directly related to the False Negative rate. If the field standard of False Negatives is $\beta = .2$ then the field standard of power should be $power = 1 - .2 = .8$, for a given effect size and sample size (though some papers, including Registered Reports are often required to have a power of at least $power >= .9$). As such, $power = .8$ means that the majority of studies should find an effect if there is one to detect, assuming that your study maintains these rates of error and power.

In the past a number of studies have fallen short of the field standard and it is this lack of power that is thought to be a key issue in the <a class='glossary' target='_blank' title='The extent to which the findings of a study can be repeated with new samples from the same population.' href='https://psyteachr.github.io/glossary/r#replicability'>replication</a> crisis. This makes sense because, if you think about it, if previous studies only have a $power = .5$ then they only have a .5 probability of correctly rejecting the null hypothesis. As such there may be a large number of studies where the null hypothesis has been rejected when it should not have been; the field becomes noisy at that point and you are unsure which studies will replicate.  It is issues like this that led us to redevelop our courses and why we really want you to understand power as much as possible.

## Designing Studies

To reiterate, power is defined as the probability of correctly rejecting the null hypothesis for a fixed effect size and fixed sample size. As such, power is a key decision when you design your study, under the premis that the higher the power of your planned study, the better.

Two relationships you will learn in this chapter are that:

* for a given sample size and $\alpha$, the power of your study is higher if the effect you are looking for is assumed to be a large effect as opposed to a small effect; large effects are easier to detect.
* and, for a given effect size and $\alpha$, the power of your study is higher when you increase your sample size.

From these relationships we see that, because you have little control over the size of the effect you are trying to detect (it lives in the real world which you don't control), you can instead increase the power of your study by increasing the size of your sample (and also reducing sources of noise and measurement error in your study). As such, when planning a study, any good researcher will consider the following four key elements - and we thank Dr Ian Walker (University of Bath) for the excellent acronym - the **APES**:

* **alpha** - most commonly thought of as the significance level (i.e., your p-value); usually set at $\alpha = .05$
* **power** - the probability of correctly rejecting the null hypothesis for a given effect size and sample size, typically set at $power = .8$.
* **effect size** - size of the relationship/difference between two variables
* **sample size** - the number of observations (usually, participants, but sometimes also stimuli) in your study. 

And the beautiful thing is that **if you know three of these elements then you can calculate the fourth**. The two most common calculations prior to a study would be:

1. to determine the appropriate <a class='glossary' target='_blank' title='A subset of the population that you wish to make an inference about through your test.' href='https://psyteachr.github.io/glossary/s#sample'>sample</a> size required to obtain the effect size that you are interested in. That is, prior to the experiment you decide you would be interested in testing for a small, medium, or large effect sizes, so you know everything except the sample size - how many people you need to run in your study. Generally, **the smaller the effect size, the more participants you will need**, assuming power and alpha are held constant at **.8** and **.05** respectively.
  * Here you know alpha, the power, and the effect size and you want to know the sample size.
2. to determine the smallest effect size you can reliably detect given your sample size. For example, you know everything except the effect size. For example, say you are taking a <a class='glossary' target='_blank' title='data that has been collected already and made available to you to ask research questions of.' href='https://psyteachr.github.io/glossary/s#secondary-data'>secondary data</a> approach and using an open dataset, and you know they have run 100 participants, you can't add any more participants, but you want to know what is the minimum effect size you could reliably detect in this dataset.
  * Here you know alpha, the power, and the sample size and you want to know the smallest effect size you can determine.

Hopefully that gives you an idea of how we use power to determine sample sizes for studies - and that the sample size should not just be pulled out of thin air. Both of these approaches described above **a priori power analyses** as you are stating the power level you want **before** (a priori means before) the study - though the second approach of determining the smallest effect size you can determine based on a known sample size is also referred to as a **sensitivity power analysis**. However, you may now be thinking though, if everything is connected, then can we use the effect size from our study and the sample size to determine the power of the study after we have run it? No! Well, you can but it would be wrong to do so. This is actually called **Observed** or **Post-Hoc** power and most papers would discourage you from calculating it on the grounds that the effect size you are using is not the true effect size of the population you are interested in; it is just the effect size of your sample. As such any indication of power from this analysis is misleading. Avoid doing this. You can read more about why, here, in your own time if you like: [Lakens (2014) Observed Power, and what to do if your editor asks for post-hoc power analyses](http://daniellakens.blogspot.com/2014/12/observed-power-and-what-to-do-if-your.html). In brief, Observed Power conflates the effect size of the sample with the effect size within the population and those two are not the same. Stick to using only a priori power analyses approaches and use them to determine your required sample size or achievable reliable effect size.

So let's jump into this a bit now and start running some analyses to help further our understanding of alpha, power, effect sizes and sample size! We will start by looking at effect sizes, before moving on to calculating power.

## Effect Size By Hand

There are a number of different "effect sizes" that you can choose to calculate but a common one for t-tests, as we have seen previously, is **Cohen's d**: the standardised difference between two means (in units of SD) and is written as d = effect-size-value. The key point is that Cohen's d is a standardised difference, meaning that it can be used to compare against other studies regardless of how the measurement was made. Take for example height differences in men and women which is estimated at about 5 inches (12.7 cm). That in itself is an effect size, but it is an unstandardised effect size in that for every sample that you test, that difference is dependent on the measurement tools, the measurement scale, and the errors contained within them (Note: ask Helena about the time she photocopied some rulers). As such using a standardised effect size allows you to make comparisons across studies regardless of measurement error. In standardised terms, the height difference above is considered a medium effect size (d = 0.5) which Cohen (1988, as cited by Schafer and Schwarz (2019)) defined as representing "an effect likely to be visible to the naked eye of a careful observer". Cohen (1988) in fact stated three sizes of Cohen's d that people could use as a guide:

<br>

|Effect size|Cohen's d value|
|:--:|:---:|
|small| .2 to .5|
|medium| .5 to .8|
|large| > .8|

<br>

You may wish to read this paper later about different effect sizes in psychology - <a href="https://www.frontiersin.org/articles/10.3389/fpsyg.2019.00813/full" target = "_blank">Schafer and Schwarz (2019) The Meaningfulness of Effect Sizes in Psychological Research: Differences Between Sub-Disciplines and the Impact of Potential Biases</a>.

The thing to note is that the formula is slightly different depending on the type of t-test used and it can sometimes change depending on who you read. For this worksheet, let's go with the following formulas:

* One-sample t-test & paired-sample t-test:  

> $d = t\ / \sqrt(N)$

* Independent t-test: 

> $d = 2t\ / \sqrt(df)$


Let's now try out some calculations. We will start with just looking at effect sizes from t-tests before calculating power in later tasks.

#### Activity 1: Set-up {#power-a1}

* Open RStudio and set the working directory to your chapter folder. Ensure the environment is clear.
    * If you're using the Rserver, avoid a number of issues by restarting the session - click `Session` - `Restart R`
* Open a new R Markdown document and save it in your working directory. Call the file "APES". 
* Delete the default R Markdown welcome text and insert a new code chunk that loads the following packages, in this specific order, using the `library()` function. Remember the solutions if needed.
  * Load the packages in this order, `pwr`, and `tidyverse`
  * we have not used the `pwr` package before so you will likely need to install them using `install.packages()`. Remember though that you should only do this on your own machine and only in the console window. If you are using the RServer you will not need to install them.

#### Activity 2: Effect size from a one-sample t-test {#power-a2}

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

#### Activity 3: Effect size from between-subjects t-test {#power-a3}

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


#### Activity 4: t-value and effect size for a between-subjects Experiment {#power-a4}

* You run a between-subjects design study and the descriptives tell you: **Group 1**, M = 10, SD = 1.3, n = 30; **Group 2**, M = 11, SD = 1.7, n = 30. Calculate `t` and `d` for this between-subjects experiment.

* Note: the hint contains the appropriate t-test formula if you are unsure.


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

**Excellent!** Now that you are comfortable with calculating effect sizes, we will look at using them to establish the sample size for a required power. One thing you will realise as we progress is that the true effect size in a population is something we do not know, but we need to justify one for our design. A clever approach is laid out by Daniel Lakens in the blog on the Smallest Effect Size of Interest (SESOI) - you set the smallest effect that you as a researcher would be interested in! This can be determined through theoretical analysis, through previous studies, through pilot studies, or through rules of thumb like Cohen (1988). However, also keep in mind that the lower the effect size, the larger the sample size you will need. Everything is a trade-off.

## Power Calculations

Today we will use the functions `pwr.t.test()`, `pwr.r.test()` and `pwr.chisq.test` from the package `pwr` to run power calculations for t-tests, correlations and chi-square.

### t-tests

Remember that for more information on a function, for example `pwr.t.test()`, simply do `?pwr.t.test` in the console. Or you can have a look at these webpages later to get an idea (or bad ideas if you spot where they erroneously calculate post-hoc power!):

* A quick-R summary of the **`pwr`** package - <a href= "https://www.statmethods.net/stats/power.html" target = "_blank">https://www.statmethods.net/stats/power.html</a>
* the **`pwr`** package vignette - <a href = "https://cran.r-project.org/web/packages/pwr/vignettes/pwr-vignette.html" target = "_blank"> https://cran.r-project.org/web/packages/pwr/vignettes/pwr-vignette.html</a>

From these you will see that `pwr.t.test()` takes a series of inputs:

* **n** - Number of observations/participants, **per group** for the independent samples version, or the **number of subjects or matched pairs** for the paired and one-sample designs.
* **d** - the effect size of interest (Cohen's d) - difference between the means divided by the pooled standard deviation
* **sig.level** - the significance level (False Positive Rate) or $\alpha$
* **power** - the power of test (1 minus False Negative Rate) or $1-\beta$
* **type** - the type of t test : `one.sample`, `two.sample`, or `paired`
* **alternative** - the type of hypothesis; `"two.sided", "greater", "less"`

And the function works on a leave one out principle. You give it all the information you have and it returns the element you are missing.  So, for example, say you needed to know how many people per group (n) you would need to detect an effect size of `d = 0.4` with `power = .8`, `alpha = .05` in a `two.sample` (between-subjects) t-test on a `two.sided` hypothesis test.  


#### Activity 5: `pwr.t.test()` {#power-a5}

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

* `pluck()` will pull out the value from the analysis that we want. e.g. `pluck("n")` will give us the sample size and `pluck("d")` will give us the effect size.
* `ceiling()` rounds up to give us the next highest whole number


```r
pwr.t.test(d = .4,
           power = .8,
           sig.level = .05,
           alternative = "two.sided",
           type = "two.sample") %>% 
  pluck("n")
  ceiling()
```

**Note:** `ceiling()` is better to use than `round()` when dealing with people as it always rounds up. For example, `ceiling(1.1)` gives you 2. `round()` on the other hand is useful for rounding an effect size, for example, to two decimal places - e.g. d = `round(.4356, 2)` would give you d = 0.44. So use `ceiling()` for sample sizes and `round()` for effect sizes.

#### Activity 6: Sample size for standard power one-sample t-test {#power-a6}

* Assuming you are interested in detecting a minimum Cohen's d of **d = 0.23**, what would be the minimum number of participants you would need in a one-sample t-test, assuming **power = .8**, $\alpha$ **= .05**, on a two-sided hypothesis? 

Using a pipeline, store the answer as a single, rounded value called `sample_size_t` (i.e. use `pluck() %>% ceiling()`).


<div class='webex-solution'><button>Helpful hint</button>


* Use the list of inputs above as a kind of check-list to clearly determine which inputs are known or unknown. This can help you enter the appropriate values to your code.
* The structure of the `pwr.t.test()` would be very similar to the one shown above except two.sample would become one.sample
* You will also need to use `pluck("n")` to help you obtain the sample size and `%>% ceiling()` to round up to the nearest whole participant.

</div>
  

Answer the following question to check your answers. The solutions are at the bottom if you need them:

* Enter the minimum number of participants you would need in this one-sample t-test: <input class='webex-solveme nospaces' size='3' data-answer='["151"]'/>

#### Activity 7: Effect size from a high power between-subjects t-test

* Assuming you run a between-subjects t-test with 50 participants per group and want a power of .9, what would be the minimum effect size you can reliably detect? Assume standard $\alpha$ and alternative hypothesis settings.

Answer the following questions to check your answers. The solutions are at the bottom if you need them:

* Based on the information given, what will you set `type` as in the function? <select class='webex-select'><option value='blank'></option><option value=''>one.sample</option><option value='answer'>two.sample</option></select>
* Based on the output, enter the minimum effect size you can reliably detect in this test, rounded to two decimal places: <input class='webex-solveme nospaces' size='4' data-answer='[".65","0.65"]'/>
* According to Cohen (1988), the effect size for this t-test is <select class='webex-select'><option value='blank'></option><option value=''>small</option><option value='answer'>medium</option><option value=''>large</option></select>
* Say you run the study and find that the effect size determined is d = 0.50. Given what you know about power, select the statement that is true: <select class='webex-select'><option value='blank'></option><option value=''>the study is sufficiently powered as the analysis indicates you can detect only effect sizes smaller than d = 0.65</option><option value='answer'>the study is underpowered as the analysis indicates you can detect only effect sizes larger than d = 0.65</option></select>

#### Uneven groups

There is an additional function that is very worthwhile knowing about called `pwr.t2n.test()` that allows you to run power analyses for t-tests where there are uneven sample sizes in the two groups. For instance, say you wanted to know the minimum effect size you could determine in a between-subjects t-test where you have 25 participants in one group and 30 participants in the second group. The additional aspect of this function is that instead of `n = `, you would do:

* `n1 = ...` for the number of people in group 1
* `n2 = ...` for the number of people in group 2
* note that there is no `type` argument in this function because it has to be two samples.

Assuming $\alpha = .05$, Power = .8, and it is a two-tailed test, you would do:


```r
pwr.t2n.test(n1 = 25,
             n2 = 30,
             power = .8,
             sig.level = .05,
             alternative = "two.sided") %>%
  pluck("d") %>%
  round(3)
```

```
## [1] 0.773
```

Meaning that the minimum effect size you could determine would be d = 0.773.

### Correlations

Now, we're going to do the same thing but for a correlation analysis using `pwr.r.test`. The structure of this function is very similar to `pwr.t.test()` and works on the same leave-one-out principle:

* **n** - Number of observations
* **r** - Correlation coefficient
* **sig.level**	- Significance level (Type I error probability)
* **power** - Power of test (1 minus Type II error probability)
* **alternative** - a character string specifying the alternative hypothesis, must be one of `two.sided` (default), `greater` (a positive correlation) or `less` (a negative correlation).

#### Activity 8: Sample size for a correlation {#power-a8}

* Assuming you are interested in detecting a minimum correlation of **r = .4** (in either direction), what would be the minimum number of participants you would need for a correlation analysis, assuming **power = .8**, $\alpha$ **= .05**? 

Using a pipeline, store the answer as a single, rounded value called `sample_size_r` (i.e. use `pluck() %>% ceiling()`).

* Enter the minimum number of participants you would need in this correlation: <input class='webex-solveme nospaces' size='2' data-answer='["46"]'/>

#### Activity 9: Effect size for a correlation analysis {#power-a9}

* You run a correlation analysis with 50 participants and the standard power and alpha levels and you have hypothesised a positive correlation, what would be the minimum effect size you can reliably detect? 
Answer the following questions to check your answers. The solutions are at the bottom if you need them:

* Based on the information given, what will you set `alternative` as in the function? <select class='webex-select'><option value='blank'></option><option value=''>two.sided</option><option value='answer'>greater</option><option value=''>less</option></select>
* Based on the output, enter the minimum effect size you can reliably detect in this test, rounded to two decimal places: <input class='webex-solveme nospaces' size='4' data-answer='[".34","0.34"]'/>
* According to Cohen (1988), the effect size for this correlation is <select class='webex-select'><option value='blank'></option><option value=''>small</option><option value='answer'>medium</option><option value=''>large</option></select>
* Say you run the study and find that the effect size determined is d = 0.24. Given what you know about power, select the statement that is true: <select class='webex-select'><option value='blank'></option><option value=''>the study is sufficiently powered as the analysis indicates you can detect only effect sizes smaller than d = 0.24</option><option value='answer'>the study is underpowered as the analysis indicates you can detect only effect sizes larger than d = 0.34</option></select>

### Effect Sizes in Published Research

#### Activity 10: Power of published research {#power-a10}

Thus far we have used hypothetical situations - now go look at the paper on the [Open Stats Lab](https://sites.trinity.edu/osl/data-sets-and-activities/t-test-activities) website called Does Music Convey Social Information to Infants? (we have used this dataset in the t-test chapter). You can download the pdf and look at it, but here we will determine the power of the significant t-tests reported in Experiment 1 under the Results section on Pg489. There is a one-sample t-test and a paired-samples t-test to consider, summarised below. Assume testing was at power = .8, alpha = .05. Based on your calculations are either of the stated effects underpowered?

1. one-sample: t(31) = 2.96, p = .006, d = 0.52
2. paired t-test: t(31) = 2.42, p = .022, d= 0.43


<div class='webex-solution'><button>Helpful hint</button>


    
* To calculate n: `n = df + 1`.
    

</div>


Which of the t-tests do you believe to be underpowered? Why do you think this may be? Additional information about this can be found in the solution to task 8 at the end of this activity.

**One caveat to Task 10:** We have to keep in mind that here we are looking at single studies using one sample from a potentially huge number of samples within a population. As such there will be a degree of variance in the true effect size within the population regardless of the effect size of one given sample. What that means is we have to be a little bit cautious when making claims about a study. Ultimately the higher the power the better as you can detect smaller effect sizes!

## Finished! {#power-fin}

**Great!** Hopefully you are now starting to see the interaction between alpha, power, effect sizes, and sample size. We should always want really high powered studies and depending on the size of the effect we are interested in (small to large), and our $\alpha$ level, this will mean we will need to run more or less participants to make sure our study is well powered. Points to note:

* Lowering the $\alpha$ level (e.g. .05 to .01) will reduce the power.
* Lowering the effect size (e.g. .8 to .2) will reduce the power.
* Increasing power (.8 to .9) will require more participants.

A high-powered study looking to detect a small effect size at a low alpha will require a large number of participants!

There are additional functions in the `pwr` package for other types of statistical analyses. We will include these calculates as part of the ANOVA and regression chapters. 

If you want more examples of power to reinforce your understanding, go back and calculate the power of the t-tests, correlations, and chi-squares from earlier chapters. 

## Test Yourself

1. Assuming you were running a between-subjects t-test on secondary data ($\alpha = .05$, Power = .8, alternative = two-tailed) and that this secondary data has 100 participants in both groups. The smallest effect size, to three decimal places, you could determine with this data is: <div class='webex-radiogroup' id='radio_GWDIIOHRFX'><label><input type="radio" autocomplete="off" name="radio_GWDIIOHRFX" value=""></input> <span>d = 0.399</span></label><label><input type="radio" autocomplete="off" name="radio_GWDIIOHRFX" value=""></input> <span>d = 0.281</span></label><label><input type="radio" autocomplete="off" name="radio_GWDIIOHRFX" value="answer"></input> <span>d = 0.398</span></label><label><input type="radio" autocomplete="off" name="radio_GWDIIOHRFX" value=""></input> <span>d = 0.280</span></label></div>



<div class='webex-solution'><button>Solution</button>

The code for this test would be:


```r
pwr.t.test(n = 100, 
           sig.level = .05, 
           power = .8,
           type = "two.sample",
           alternative = "two.sided") %>% 
  pluck("d") %>% 
  round(3)
```

* Meaning that the smallest effect size would be d = 0.39


</div>


2. Assuming you were running a between-subjects t-test on secondary data ($\alpha = .05$, Power = .8, alternative = two-tailed) and that this secondary data has 60 participants in Group 1 and 40 participants in Group 2. The smallest effect size, to three decimal places, you could determine with this data is: <div class='webex-radiogroup' id='radio_XHAJKRSHLK'><label><input type="radio" autocomplete="off" name="radio_XHAJKRSHLK" value=""></input> <span>d = 0.577</span></label><label><input type="radio" autocomplete="off" name="radio_XHAJKRSHLK" value=""></input> <span>r = .578</span></label><label><input type="radio" autocomplete="off" name="radio_XHAJKRSHLK" value=""></input> <span>r = .577</span></label><label><input type="radio" autocomplete="off" name="radio_XHAJKRSHLK" value="answer"></input> <span>d = 0.578</span></label></div>



<div class='webex-solution'><button>Solution</button>

The code for this test would be:


```r
pwr.t2n.test(n1 = 60,
           n2 = 40,
           sig.level = .05, 
           power = .8,
           alternative = "two.sided") %>% 
  pluck("d") %>% 
  round(3)
```

* Meaning that the smallest effect size would be d = 0.578


</div>


3. Assuming you ran a correlation on secondary data ($\alpha = .05$, Power = .8, alternative = two-tailed) and that this secondary data has 50 observations. The smallest effect size, to three decimal places, you could determine with this data is: <div class='webex-radiogroup' id='radio_AAUQWSBYYQ'><label><input type="radio" autocomplete="off" name="radio_AAUQWSBYYQ" value=""></input> <span>r = .276</span></label><label><input type="radio" autocomplete="off" name="radio_AAUQWSBYYQ" value=""></input> <span>r = .275</span></label><label><input type="radio" autocomplete="off" name="radio_AAUQWSBYYQ" value="answer"></input> <span>r = .384</span></label><label><input type="radio" autocomplete="off" name="radio_AAUQWSBYYQ" value=""></input> <span>r = .385</span></label></div>



<div class='webex-solution'><button>Solution</button>

The code for this test would be:


```r
pwr.r.test(n = 50,
           sig.level = .05, 
           power = .8,
           alternative = "two.sided") %>% 
  pluck("r") %>% 
  round(3)
```

* Meaning that the smallest effect size would be r = .384


</div>



## Activity solutions {#power-sols}

Below you will find the solutions to the above questions. Only look at them after giving the questions a good try and trying to find help on Google or Teams about any issues.

#### Activity 1 {#power-a1sol}



```r
library(pwr)
library(broom)
library(tidyverse)
```


#### Activity 2 {#power-a2sol}


```r
d <- 3.24 / sqrt(25 +1)

# effect is medium to large; d = .64
```

#### Activity 3 {#power-a3sol}



```r
d <- (2*2.9) / sqrt(30)

# effect is large; d = 1.06
```


#### Activity 4 {#power-a4sol}


```r
t = (10 - 11)/sqrt((1.3^2/30) + (1.7^2/30))

d = (2*t)/sqrt((30-1) + (30-1))

# t = 2.56
# d = .67

# Remember that convention is that people report the t and d as positive.
```


#### Activity 6 {#power-a6sol}


```r
sample_size_t <- pwr.t.test(d = .23,
                            power = .8, 
                            sig.level = .05, 
                            alternative = "two.sided", 
                            type = "one.sample") %>% pluck("n") %>% ceiling()

sample_size_t
```

[1] 151


#### Activity 7 {#power-a7sol}


```r
pwr.t.test(n = 50,
           power = .9, 
           sig.level = .05, 
           alternative = "two.sided", 
           type = "two.sample") %>%
  pluck("d") %>%
  round(3)
```

[1] 0.655



#### Activity 8 {#power-a8sol}


```r
sample_size_r <- pwr.r.test(r = .4, 
                            sig.level = .05, 
                            power = .8, 
                            alternative = "two.sided") %>%
  pluck("n") %>% 
  ceiling()
```



#### Activity 9 {#power-a9sol}


```r
pwr.r.test(n = 50,
           sig.level = .05, 
           power = .8, 
           alternative = "greater") %>%
  pluck("r") %>%
  round(3)
```

[1] 0.344


#### Activity 10 {#power-a10sol}

**Achievable Cohen d for Example 1**


```r
pwr.t.test(power = .8, 
           n = 32, 
           type = "one.sample", 
           alternative = "two.sided", 
           sig.level = .05) %>%
  pluck("d") %>%
  round(2)
```

[1] 0.51

* Giving an achievable effect size of 0.51 and they found an effect size of 0.52.

This study seems ok as the authors could achieve an effect size as low as .51 and found an effect size at .52

**Achievable Cohen d for Example 2**


```r
pwr.t.test(power = .8, 
           n = 32, 
           type = "paired", 
           alternative = "two.sided", 
           sig.level = .05) %>%
  pluck("d") %>%
  round(2)
```

[1] 0.51

* Giving an achievable effect size of 0.51 and they found an effect size of 0.43.

This effect might not be reliable given that the effect size found was much lower than the achievable effect size. The issue here is that the researchers established their sample size based on a previous effect size and not on the minimum effect size that they would find important. If an effect size as small as .4 was important then they should have powered all studies to that level and ran the appropriate n ~52 babies (see below). Flipside of course is that obtaining 52 babies isnt easy; hence why some people consider the Many Labs approach a good way ahead.

**ONE CAVEAT** to the above is that before making the assumption that this study is therefore flawed, we have to keep in mind that this is one study using one sample from a potentially huge number of samples within a population. As such there will be a degree of variance in the true effect size within the population regardless of the effect size of one given sample. What that means is we have to be a little bit cautious when making claims about a study. Ultimately the higher the power the better.

Below you could calculate the actual sample size required to achieve a power of .8:


```r
sample_size <- pwr.t.test(power = .8,
                          d = .4, 
                          type = "paired", 
                          alternative = "two.sided",
                          sig.level = .05) %>%
  pluck("n") %>% 
  ceiling()

sample_size
```

[1] 52

* Suggesting a sample size of n = 52 would be appropriate.

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                           |definition                                                                                                                                                            |
|:--------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|[alpha](https://psyteachr.github.io/glossary/a.html#alpha){class="glossary" target="_blank"}                   |(stats) The cutoff value for making a decision to reject the null hypothesis; (graphics) A value between 0 and 1 used to control the levels of transparency in a plot |
|[beta](https://psyteachr.github.io/glossary/b.html#beta){class="glossary" target="_blank"}                     |The false negative rate we accept for a statistical test.                                                                                                             |
|[false negative](https://psyteachr.github.io/glossary/f.html#false-negative){class="glossary" target="_blank"} |When a test concludes there is no effect when there really is an effect                                                                                               |
|[false positive](https://psyteachr.github.io/glossary/f.html#false-positive){class="glossary" target="_blank"} |When a test concludes there is an effect when there really is no effect                                                                                               |
|[hypothesis](https://psyteachr.github.io/glossary/h.html#hypothesis){class="glossary" target="_blank"}         |A proposed explanation made on the basis of limited evidence as a starting point for further investigation.                                                           |
|[power](https://psyteachr.github.io/glossary/p.html#power){class="glossary" target="_blank"}                   |The probability of rejecting the null hypothesis when it is false.                                                                                                    |
|[probability](https://psyteachr.github.io/glossary/p.html#probability){class="glossary" target="_blank"}       |A number between 0 and 1 where 0 indicates impossibility of the event and 1 indicates certainty                                                                       |
|[replicability](https://psyteachr.github.io/glossary/r.html#replicability){class="glossary" target="_blank"}   |The extent to which the findings of a study can be repeated with new samples from the same population.                                                                |
|[sample](https://psyteachr.github.io/glossary/s.html#sample){class="glossary" target="_blank"}                 |A subset of the population that you wish to make an inference about through your test.                                                                                |
|[secondary data](https://psyteachr.github.io/glossary/s.html#secondary-data){class="glossary" target="_blank"} |data that has been collected already and made available to you to ask research questions of.                                                                          |

## Additional Information

### A blog on how to choose an effect size of interest

A really quick analogy from Ian Walker's "Research Methods and statistics", is say your test is not a stats test but a telescope. And say you have a telescope that is specifically designed only for spotting animals that are the size of elephants or larger (similar to saying a cohens d of .8 or greater for example - very big effect). If your telescope can only reliably detect something down to the size of an elephant but when you look through it you see something smaller that you think might be a mouse, you can't say that the "object"" is definitely is a mouse as you don't have enough power in your telescope - it is too blurry. But likewise you can't rule out that it isn't a mouse as that would be something you don't know for sure - both of these are true because your telescope was only designed to spot things the size of an elephant or larger. You only bought a telescope that was able to spot elephants because that was all your were interested in. Had you been interested in spotting mice you would have had to have bought a more powerful telescope. And that is the point of Lakens' SESOI (Smallest Effect Size of Interest) blog mentioned at the start - you power to the minimum effect size (minimum object size) you would be interested in. This is why it is imperative that you decide before your study what effect you are interested in - and you can base this on previous literature or theory.

### A blog on interpreting and writing up power

A few points on interpreting power to consolidate things a bit. Firstly, it is great that you are now thinking about power and effect sizes in the first place. It is important that this becomes as second nature as thinking about the design of your study and in future years and future studies the first question you should ask yourself when designing your study/secondary analysis is what size are my APES - Alpha, Power, Effect Size and Sample. And remember that a priori power analysis is the way ahead. The power and alpha are determined in advance of the study and you are using them to determine the effect size or the sample size.

Power is stated more and more commonly again in papers now and you will start to notice it in the Methods or Results sections. You will see something along the lines of "Based on a power =..... and alpha =...., given we had X voices in our sample, a power analysis (pwr package citation) revealed d = ...... as the minimum effect sizes we could reliably determine."

But how do you interpret a study in terms of power? Well, lets say you run a power analysis for a t-test (or for a correlation), and you set the smallest effect size of interest as d = .4 (or the equivalent r-value). If you then run your analysis and find d = .6 and the effect is significant, then your study had enough power to determine this effect. The effect that you found was bigger than the effect you could have found. You can have some confidence that you have a reliable effect at that given power and alpha values. However, say that instead of d = .6 you found a significant effect but with an effect size just below .4, say d = .3 - the effect size you found is smaller than the smallest effect you could reliably find. In this case you have to be cautious as you are still unclear as to whether there actually is an effect or whether you have found an effect by chance due to your study not having enough power to reliably detect an effect size that small. You can't say for sure that there is an effect or that there isn't an effect. You need to consider both stances in your write up. Remember though that you have sampled a population, so how representative that sample is of your population will also influence the validity of your power. Each sample will give a slightly different effect size.

Alternatively, and probably quite likely in many degree projects due to time constraints, say you find a non-significant effect at an effect size smaller than what you predicted; say you find a non-significant effect with an effect size of d = .2 and your power analysis said you could only reliably detect an effect as small as d = .4. The issue you have here is that you can't determine solely based on this study if you a) have a non-significant effect because you are under powered or b) that you have a non-significant effect because there is actually no effect in the first place. Again in your discussion you would need to consider both stances. What you can however say is that the effect that you were looking for is not any bigger than d = 0.4. That is still useful information. Ok you don't know how small the effect really is, but you can rule out any effect size bigger than your original d-value. In turn this helps future researchers plan their studies better and can guide them better in knowing how many participants to run. See how useful it would be if we published null findings!

Basically, when your test finds an effect size smaller than you can detect, you don't know what it is but you know what it isn't - we aren't sure if it is a mouse but we know it is not an elephant. Instead you would use previous findings to support the object being a mouse or not but caveat the conclusion with the suggestion that the test isn't really sensitive to finding a mouse. Similar to a finding that has an effect size smaller than you can detect. You can use previous literature to support their not being an effect but you can't rule it out for sure. You might have actually found an effect had you had a more powerful test. Just like you might have been able to determine that it was a mouse had you had a more powerful telescope.

Taking this a bit further in some studies there really is enough power (in terms of N - say a study of 25000 participants) to find a flea on the proverbial mouse, but where nevertheless there is a non-significant finding. In this case you have the fortunate situation where you have a well-powered study and so can say with some degree of confidence that your hypothesis and design is unlikely to ever produce a replicable significant result. That is probably about as certain as you can get in our science or as close as you can get to a "fact", a very rare and precious thing. However, incredibly high powered studies, with lots of participants, tend to be able to find any difference as a significant difference. A within-subjects design with 10000 participants (Power = .8, $\alpha = .05$) can determine reliably detect an incredibly small effect size of d = 0.04. The question at that stage is whether that effect has any real world significance or meaning.

So the take-home message here is that your discussion should always consider the result in relation to the hypothesis, integrating previous research and theory, and if there is an additional issue of power, then your discussion could also consider the result in relation to whether you can truly determine the effect and how that might be resolved (e.g. re-assessing the effect size, changing the design (within is more powerful), low sample, power to high (e.g. .9), alpha to low (e.g. .01)). This issue of power would probably be a small part in the generalisability/limitation section.

And finally, n all of the above you can swap effect and relationship, d and r, and other analyses accordingly.


That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!
