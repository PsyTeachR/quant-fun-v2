# Data wrangling 2

As we have said previously, one of the key aspects in a researcher's toolbox is the knowledge and skill to work with data - regardless of how it comes to you. In fact, when you run an experiment you might get lots of different <a class='glossary' target='_blank' title='The kind of data represented by an object.' href='https://psyteachr.github.io/glossary/d#data-type'>types of data</a> in various different files. For instance, it is not uncommon for an experimental software to create a new file for every <a class='glossary' title='the word used to describe someone who has taken part in a study. Note that subject is outdated and no longer used.'>participants</a> you run and for each participant's file to contain numerous columns and rows of different data types, only some of which are important. Being able to <a class='glossary' target='_blank' title='The process of preparing data for visualisation and statistical analysis.' href='https://psyteachr.github.io/glossary/d#data-wrangling'>wrangle</a> that data, manipulate it into different layouts, extract the parts you need, and summarise it, is one of the most important skills we will help you learn through this book.

In the last chapter we introduced you to the **Wickham six** one-table <a class='glossary' target='_blank' title='A named section of code that can be reused.' href='https://psyteachr.github.io/glossary/f#function'>functions</a> which we use to do that data wrangling. Over the course of this book we will reiterate these functions and skills, and <a class='glossary' target='_blank' title='A group of R functions.' href='https://psyteachr.github.io/glossary/p#package'>packages</a> like the `tidyverse` and the packages it contains, across a number of different datasets to give you a wide range of exposure to what Psychology is about, and to reiterate that the same skills apply across different datasets. Always remember, **the whilst the data changes, the skills stay the same!**

We have also started to introduce different types of data and data structures. For example, data is often stored in two-dimensional tables, either called data frames, tables, or <a class='glossary' target='_blank' title='A container for tabular data with some different properties to a data frame' href='https://psyteachr.github.io/glossary/t#tibble'>tibbles</a>. There are other ways of storing data that you will discover in time but mainly, in this book, we will be using tibbles, which we mentioned in the previous chapter (if you would like more info, type `vignette("tibble")` in the console). A tibble is really just a table of data with columns and rows of information - and some additional features we will learn about - and  within the cells of the tibble, a cell being where a row and a column meets, you get different types of data, e.g. <a class='glossary' target='_blank' title='A data type representing a real decimal number' href='https://psyteachr.github.io/glossary/d#double'>double</a>, <a class='glossary' target='_blank' title='A data type representing whole numbers.' href='https://psyteachr.github.io/glossary/i#integer'>integer</a>, <a class='glossary' target='_blank' title='A data type representing strings of text.' href='https://psyteachr.github.io/glossary/c#character'>character</a> and <a class='glossary' target='_blank' title='A data type where a specific set of values are stored with labels; An explanatory variable manipulated by the experimenter' href='https://psyteachr.github.io/glossary/f#factor'>factor</a>

|Type of Data | Description                                                  |
|:------------|:-------------------------------------------------------------| 
|Double       | Numbers that can take decimals                               |
|Integer      | Numbers that cannot take decimals                            |
|Character    | Tends to contain letters or be words                         |
|Factor       | Nominal (categorical). Can be words or numbers (e.g., animal or human, 1 or 2)|

* **Note 1:** Double and Integer can both be referred to as <a class='glossary' target='_blank' title='A data type representing a real decimal number or integer.' href='https://psyteachr.github.io/glossary/n#numeric'>numeric</a> data, and you will see this word from time to time. For clarity, we will use Double as a term for any number that can take a decimal (e.g. 3.14) and Integer as a term for any whole number (no decimal, e.g. 3).
* **Note 2:** A wee bit confusingly Double data does not have to have decimal places in it. For instance, the value of 1 could be Double as well as Integer. However, the value of 1.1 could only be Double and never Integer. Integers cannot have decimal places. Again, the more you work with data the more this will make sense, but it highlights the importance of looking at your data and checking what type it is as the type determines what you can do with the data.

Today, we are going to continue developing our understanding of data, and build on the knowledge and skills we have seen to this point, to help you develop your ability to work with data. The only difference in this chapter is we are going to ask you to do more of the wrangling yourself, based on what we have shown you previously. To build our skills we will analyse a novel dataset and some activities based around manipulating that data. Remember to be pro-active in your learning and to refer back to what we have done before, using the example code as a guide. The solutions for all the tasks are at the bottom of the page as well for you to check yourself, but do be sure to try the tasks first. There is also the online [cheatsheets](https://www.rstudio.com/resources/cheatsheets/){target="_blank"} if you need more help - the key cheatsheet for this chapter is the Data Transformation with **`dplyr`**  -  and don't forget to ask questions on ours forums.

## Learning to wrangle: Is there a chastity belt on perception

Today we are going to be using data from the paper [Is there a Chastity Belt on Perception](http://journals.sagepub.com/doi/abs/10.1177/0956797617730892){target="_blank"}[@witt2018]. You can read the full paper if you like but we will summarise the paper for you. The paper asks the research question of **does your ability to perform an action influence your perception?** For instance, does your ability to hit a tennis ball influence how fast you perceive the ball to be moving? Or to phrase another way, do expert tennis players perceive the ball moving slower than novice tennis players?  

This experiment does not use tennis players however. Instead they used the Pong task: "a computerised game in which participants aim to block moving balls with various sizes of paddles". A bit like a very classic retro arcade game. Participants tend to estimate the balls as moving faster when they have to block it with a smaller paddle as opposed to when they have a bigger paddle. You can read the paper to get more details if you wish but hopefully that gives enough of an idea to help you understand the wrangling we will do on the data. We have cleaned up the data a little to start with. Let's begin!

### Activity 1: Set-up Data Wrangling 2 {#dw2-a1}

* First, download <a href="data/chpt5/PongBlueRedBack 1-16 Codebook.csv" download>PongBlueRedBack 1-16 Codebook.csv</a> into your chapter folder.
    * If you are having trouble downloading .csv files directly you may prefer to download the data as a zip file and unzip it from this link: <a href="data/chpt5/PsyTeachR_FQA_Chpt5-data.zip" download>PongBlueRedBack 1-16 Codebook.zip</a>. Again just unzip it into your chapter folder. 
* Next, set the <a class='glossary' target='_blank' title='The filepath where R is currently reading and writing files.' href='https://psyteachr.github.io/glossary/w#working-directory'>working directory</a> to your chapter folder. Ensure the <a class='glossary' target='_blank' title='A data structure that contains R objects such as variables and functions' href='https://psyteachr.github.io/glossary/e#environment'>environment</a> is clear.
    * If you're using the Rserver, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Now, open a new R Markdown document and save it in your working directory and call the file something informative like "DataWrangling2". 
* Next, delete the default R Markdown welcome text and insert a new code <a class='glossary' target='_blank' title='A section of code in an R Markdown file' href='https://psyteachr.github.io/glossary/c#chunk'>chunk</a>.
* Finally, copy and paste the below code into this code chunk and then run the code.


```r
library("tidyverse")
pong_data <- read_csv("PongBlueRedBack 1-16 Codebook.csv")
summary(pong_data)
```

**Remember: ** We use the `read_csv()` function to load in data, and the data filename must be a) in quotation marks and b) spelt exactly as the filename states, including spaces and the file extension (in this case .csv)

If you have done this task correctly you should see the following output:


```
##   Participant     JudgedSpeed      PaddleLength   BallSpeed    TrialNumber    
##  Min.   : 1.00   Min.   :0.0000   Min.   : 50   Min.   :2.0   Min.   :  1.00  
##  1st Qu.: 4.75   1st Qu.:0.0000   1st Qu.: 50   1st Qu.:3.0   1st Qu.: 72.75  
##  Median : 8.50   Median :1.0000   Median :150   Median :4.5   Median :144.50  
##  Mean   : 8.50   Mean   :0.5471   Mean   :150   Mean   :4.5   Mean   :144.50  
##  3rd Qu.:12.25   3rd Qu.:1.0000   3rd Qu.:250   3rd Qu.:6.0   3rd Qu.:216.25  
##  Max.   :16.00   Max.   :1.0000   Max.   :250   Max.   :7.0   Max.   :288.00  
##  BackgroundColor      HitOrMiss       BlockNumber   
##  Length:4608        Min.   :0.0000   Min.   : 1.00  
##  Class :character   1st Qu.:0.0000   1st Qu.: 3.75  
##  Mode  :character   Median :1.0000   Median : 6.50  
##                     Mean   :0.6866   Mean   : 6.50  
##                     3rd Qu.:1.0000   3rd Qu.: 9.25  
##                     Max.   :1.0000   Max.   :12.00
```

`summary()`, from the **`base`** package - the default packages automatically installed - provides a quick overview of the variables in your dataset and can be useful as a quick check that you have indeed imported the correct data. It will also provide some basic <a class='glossary' target='_blank' title='Statistics that describe an aspect of data (e.g., mean, median, mode, variance, range)' href='https://psyteachr.github.io/glossary/d#descriptive'>descriptive</a> statistics and some information on whether the data is character (text) data which can also be useful to check.

An alternative approach for looking at data types would be to use the `glimpse()` function, from the **`dplyr`** package, loaded in with **`tidyverse`**. Try the following in your <a class='glossary' target='_blank' title='The pane in RStudio where you can type in commands and view output messages.' href='https://psyteachr.github.io/glossary/c#console'>console</a> window:


```r
glimpse(pong_data)
```

And you will see:


```
## Rows: 4,608
## Columns: 8
## $ Participant     <dbl> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, ~
## $ JudgedSpeed     <dbl> 1, 0, 1, 0, 1, 0, 1, 0, 0, 0, 1, 1, 0, 1, 0, 1, 0, 1, ~
## $ PaddleLength    <dbl> 50, 250, 50, 250, 250, 50, 250, 50, 250, 50, 50, 250, ~
## $ BallSpeed       <dbl> 5, 3, 4, 3, 7, 5, 6, 2, 4, 4, 7, 7, 3, 6, 5, 7, 2, 5, ~
## $ TrialNumber     <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16,~
## $ BackgroundColor <chr> "red", "blue", "red", "red", "blue", "blue", "red", "r~
## $ HitOrMiss       <dbl> 0, 1, 0, 1, 1, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 0, 1, 1, ~
## $ BlockNumber     <dbl> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, ~
```

And if you look at that table you can see the eight column names followed by `<dbl>`, short for double, or `<chr>` short for character. Again, this might not mean that much to you but as you progress you will become very adept at recognising the type of data you are working with, as the type of data changes what you can do to the data.

### Activity 2: Look at your data {#dw2-a2}

Great! Now that we have the data loaded in, let's have a look at the `pong_data` and see how it is organized. Again you can do this various ways, but today, click on `pong_data` in your environment pane.

In the dataset you will see that each row (observation) represents one trial per participant and that there were 288 trials for each of the 16 participants. The columns (variables) we have in the dataset are as follows:

| Variable       |       Type                       |           Description          |
|:--------------:|:---------------------------------|:-------------------------------|
| Participant    | double| participant number             |
| JudgedSpeed    | double| speed judgement (1 = fast, 0 = slow)|
| PaddleLength   | double| paddle length (pixels)        |
| BallSpeed      | double  | ball speed (2 pixels/4ms)      |
| TrialNumber    | double| trial number                   |
| BackgroundColor| character| background display colour  |
| HitOrMiss      | double  | hit ball = 1, missed ball = 0      |
| BlockNumber    | double| block number (out of 12 blocks)|

Just as we saw with `glimpse()`, some of the data is `double` - i.e. numbers - and some of the data is `character` - i.e. text. We will use this data to master our skills of the Wickham Six verbs, taking each verb in turn. You should refer to the explanations and example code in the previous chapter to help you complete these. Remember the six main functions were:

|Function|Description|
|:------:|:----------|
|`select()`| Include or exclude certain variables (columns)|
|`filter()`| Include or exclude certain observations (rows)|
|`mutate()`| Create new variables (columns)|
|`arrange()`| Change the order of observations (rows)|
|`group_by()`| Organize the observations (rows) into groups|
|`summarise()`| Create summary variables for groups of observations|

Now, let's do some wrangling!!! And don't forget, it can help to take a new code chunk on each activity and write yourself some notes between the code chunks!

### Activity 3: **`select()`** {#dw2-a3}

We are going to start with some selections!

* Either by inclusion (stating all the variables you want to keep) or exclusion (stating all the variables you want to drop), select only the `Participant`, `PaddleLength`, `TrialNumber`, `BackgroundColor` and `HitOrMiss` columns from `pong_data` and store it in a new object named `select_dat`.  

### Activity 4: Reorder the variables {#dw2-a4}

Good work! Now, we previously mentioned that `select()` can also be used to reorder the columns in a tibble, as the new tibble will display the variables in the order that you entered them. 

* Use `select()` to keep only the columns `Participant`, `JudgedSpeed`, `BallSpeed`, `TrialNumber`, and `HitOrMiss` from `pong_data` but have them display in alphabetical order, left to right. Save this tibble in a new object named `reorder_dat`.

### Activity 5: **`arrange()`** {#dw2-a5}

We are now master of selections!!! Let's move on to a different skill and test our ability to change the order of the data in the rows.

* Arrange the data by the following two variables: `HitOrMiss` (putting hits - 1 - first), and `JudgedSpeed` (putting fast judgement - 1 - first) and store this in an object named `arrange_dat`.

### Activity 6: **`filter()`** {#dw2-a6}

Great! But what about keeping and removing some of the rows with `filter()`! You may need to refer back to the different boolean operations to complete this activity!

Use `filter()` to extract all Participants in the original `pong_data` that had:

* a fast speed judgement;
* for speeds 2, 4, 5, and 7;
* but missed the ball.   

Store this remaining data in a new object called `pong_fast_miss`


<div class='webex-solution'><button>Helpful Hint</button>

There are three parts to this filter so it is best to think about them individually and then combine them.

1. Filter all fast speed judgements (`JudgedSpeed`)

2. Filter for the speeds 2, 4, 5 and 7 (`BallSpeed`)

3. Filter for all Misses (`HitOrMiss`)

You could do this in three filters where each one uses the output of the preceding one, or remember that filter functions can take more than one argument. You may also need to use `==` instead of just `=`.

</div>


<br>

<div class="warning">
<p>The filter function is very useful but if used wrongly can give you very misleading findings. This is why it is very important to always check your data after you perform an action. Let's say you are working in comparative psychology and have run a study looking at how cats, dogs and horses perceive emotion. Let's say the data is all stored in the tibble <code>animal_data</code> and there is a column called <code>animals</code> that tells you what type of animal your participant was. Imagine you wanted all the data from just cats:</p>
<p><code>filter(animal_data, animals == "cat")</code></p>
<p>Exactly! But what if you wanted cats and dogs?</p>
<p><code>filter(animal_data, animals == "cat", animals == "dog")</code></p>
<p>Right? Wrong! This actually says "give me everything that is a cat and a dog". But nothing is a cat and a dog, that would be weird - like a dat or a cog. In fact you want everything that is either a cat <strong>or</strong> a dog, so you could do:</p>
<p><code>filter(animal_data, animals == "cat"| animals == "dog")</code></p>
<p>Or you could do:</p>
<p><code>filter(animal_data, animals %in% c("cat", "dog"))</code></p>
<p>You used this last approach, using <code>%in%</code>, when producing your own graph of <code>babynames</code>. It is a very helpful function so don't forget it exists!</p>
</div>


### Activity 7: **`mutate()`** {#dw2-a7}

Brilliant work on getting this far! You really are starting to get the hang of wrangling! Now, let's test our skills on `mutate()` but first we want to introduce a new function to help understand what we can do with `mutate()`.

Previously you learned how the `mutate()` function lets us create a new variable in our dataset. However, it also has another useful function in that it can be combined with `recode()` to create new columns with recoded values - where you change how different categories in a variable are represented. For example, the code below adds a new column to `pong_data` in which the judged speed  is converted into a text label where `1` will become `Fast`, and `0` will become "Slow". Run the code and look at the output! 


```r
pong_data_mut1 <- mutate(pong_data, 
                    JudgedSpeedLabel = recode(JudgedSpeed, 
                                                    "1" = "Fast", 
                                                    "0" = "Slow"))
```

The code here is a bit complicated but we will explain:

* `JudgedSpeedLabel` is the name of your new column, 
* `JudgedSpeed` is the name of the old column and the one to take information from
    * Note that if you gave the recoded variable the same name as the original it would overwrite it.
* Fast and Slow are the new codings of 1 and 0 respectively in the new column

The `mutate()` function is also handy for making some calculations on or across columns in your data. For example, say you realise you made a mistake in your experiment where your participant numbers should be 1 higher for every participant, i.e. Participant 1 should actually be numbered as Participant 2, etc. You could do something like:


```r
pong_data_mut2 <- mutate(pong_data, 
                         Participant = Participant + 1)
```

Note here, in this second example, you are giving the new column the same name as the old column `Participant`. Again, happens here is that you are **overwriting the old data with the new data**! So watch out, mutate can create a new column or overwrite an existing column, depending on what you tell it to do!  

Ok great! Now, imagine you realise that there is a mistake in your dataset and that all your trial numbers are wrong. The first trial (trial number 1) was a practice so should be excluded and your experiment actually started on trial 2. Your turn! You can either do this following activity in two separate steps and create a new object each time, or you can uses pipes `%>%` and do it it one line of code. The final tibble should be stored in an object called `pong_data_renumbered`.

* Filter out all trials with the number 1 (`TrialNumber` column) from `pong_data`. 
* Then use the `mutate()` function to renumber all the remaining trial numbers, starting them at one again instead of two, overwriting the values that were in the `TrialNumber` column.


<div class='webex-solution'><button>Helpful Hint</button>


* Step 1. filter(`TrialNumber` does not equal 1). Remember to store this output in a variable if you are not using pipes.

* Step 2. mutate(`TrialNumber` = TrialNumber minus 1)

</div>
  

### Activity 8: Summarising data {#dw2-a8}

Excellent! And now that we have done some wrangling we want to calculate some descriptive statistics for the data using `summarise()`. `summarise()` has a range of internal functions that make life really easy, e.g. `mean`, `sum`, `max`, `min`, etc. See the [dplyr cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf) for more examples. And additional one that we will use from time-to-time is `na.rm = TRUE` which we can add when calculating descriptive statistics to say what to do if there are missing values. Missing values often appear as `NA` and the job of `na.rm` is to say whether to remove (rm) the NAs (`na.rm = TRUE`) or not (`na.rm = FALSE`). If you try to calculate values from data that have NAs, such as the mean, it would return `NA` as the result because it doesn't know how to average nothing. This dataset has no missing values but we will show you how to use it here and try to remember this argument exists, as you will use it often and it save you a lot of time!

Back to the activity. Here, using the data in `pong_data_renumbered` we will calculate:

* The total (sum) number of hits for each combination of background colour and paddle length.
* The mean number of hits for each combination of background colour and paddle length

Remember though, because we want to produce descriptive statistics by groups (background colour and paddle length), there are two steps:

* First we group the data by `BackgroundColor` and `PaddleLength` using `group_by()`.
* Then, we use `summarise()` to calculate the total and mean number of hits (`HitOrMiss`) using the grouped data

We will do this activity using pipes to reduce the amount of code we write. Remember to try and read the code out loud and to pronounce `%>%` as 'and then'. Copy and paste the below code into a new code chunk and run the code.




```r
pong_data_hits <- pong_data_renumbered %>% 
  group_by(BackgroundColor, 
           PaddleLength) %>% 
  summarise(total_hits = sum(HitOrMiss, 
                             na.rm = TRUE),
            meanhits = mean(HitOrMiss, 
                            na.rm = TRUE))
```

```
## `summarise()` has grouped output by 'BackgroundColor'. You can override using the `.groups` argument.
```

<div class="info">
<p>Remember, if you get what looks like an error that says "<code>summarise()</code> has grouped output by 'BackgroundColor'. You can override using the <code>.groups</code> argument.", don't worry, this isn't an error it's just the code telling you how the final object is grouped.</p>
</div>

* View `pong_data_hits` and answer the following questions to see if you have completed the task correctly.



* What was the total number of hits made with the small paddle (50) and the blue colour background? <div class='webex-radiogroup' id='radio_UPEZPFLCMB'><label><input type="radio" autocomplete="off" name="radio_UPEZPFLCMB" value=""></input> <span>516</span></label><label><input type="radio" autocomplete="off" name="radio_UPEZPFLCMB" value=""></input> <span>1059</span></label><label><input type="radio" autocomplete="off" name="radio_UPEZPFLCMB" value="answer"></input> <span>527</span></label><label><input type="radio" autocomplete="off" name="radio_UPEZPFLCMB" value=""></input> <span>1057</span></label></div>




* To three decimal places, what was the mean number of hits made with the small paddle (50) and the blue colour background? <div class='webex-radiogroup' id='radio_QIHLYNVZEE'><label><input type="radio" autocomplete="off" name="radio_QIHLYNVZEE" value=""></input> <span>0.92</span></label><label><input type="radio" autocomplete="off" name="radio_QIHLYNVZEE" value=""></input> <span>0.922</span></label><label><input type="radio" autocomplete="off" name="radio_QIHLYNVZEE" value=""></input> <span>0.451</span></label><label><input type="radio" autocomplete="off" name="radio_QIHLYNVZEE" value="answer"></input> <span>0.459</span></label></div>


**Note:**

* The name of the column within `pong_data_hits` is `total_hits`; this is what you called it in the above code. You could have called it anything you wanted but always try to use something sensible.
* Make sure to call your variables something you (and anyone looking at your code) will understand and recognize later (i.e. not variable1, variable2, variable3. etc.), and avoid spaces (use_underscores_never_spaces). 

## Ungrouping, counting, pipes - quick notes!

You have done some superb work today! Congratulations. You should be really proud of yourself. Before ending we just want to show a couple more new functions and approaches that will help in future activities.

### Counting data {#dw2-a9}

First we want to look at different ways of counting your observations. Often it is helpful to know how many observations you have, either in total, or broken down by groups. This can help you spot if something has gone wrong in a calculation, for example, if you've done something with the code and your mean or median is only being calculated using a subset of the values you intended.

There are two ways of counting the number of observations. The first uses `summarise()` and the function `n()` within the `summarise()`. For example, the below code is the same as the previous activity, but with an extra line that will add a column called `n` to the table that contains the number of observations in each group. This is useful for when you want to add a column of counts to a table of other descriptive statistics. 

* **Note:** the function is `n()` and takes no arguments it is just left blank as shown, `n()`.  However, as in other functions, the `n` prior to the `=` could be called anything you want the column to be called, e.g. `n = n()` or `number = n()` would do the same but just give different names to the column.


```r
pong_count <- pong_data_renumbered %>% 
  group_by(BackgroundColor, 
           PaddleLength) %>% 
  summarise(total_hits = sum(HitOrMiss, 
                             na.rm = TRUE),
            meanhits = mean(HitOrMiss, 
                            na.rm = TRUE),
            n = n())
```

However, if you're just interested in counts rather than also calculating descriptives, this above method is a bit clunky. Instead, we can use the function `count()` which is specifically designed to count observations and doesn't require the use of `summarise()` or `group_by()`.

To count the total number of observations in the dataset for example we would do:


```r
pong_data %>% # take pong_data
  count() # and then count the observations in it
```

And it would give the answer of:

<div class="kable-table">

|    n|
|----:|
| 4608|

</div>

Alternatively, to count the number of observations in each level of a variable you could do:


```r
pong_data %>%
  count(BackgroundColor)
```

And it would give the answer of:

<div class="kable-table">

|BackgroundColor |    n|
|:---------------|----:|
|blue            | 2304|
|red             | 2304|

</div>

Which method you use will depend on whether you want to add the counts to a table of other descriptives, but both functions are useful to know.

### Ungrouping data {#dw2-ungroup}

After grouping data together using the `group_by()` function and then performing a task on it, e.g. `filter()`, it can be very good practice to ungroup the data before performing another function - by piping it into the `ungroup()` function - this is related to what the warnings about `summarise()` mean as they are changing the groupings so removing all groupings can be good to do. Forgetting to ungroup the dataset won't always affect further processing, but can really mess up other things. Again just a good reminder to always check the data you are getting out of a function a) makes sense and b) is what you expect.

This is an example of how you might use the function:


```r
pong_data_ungroup <- pong_data %>%
  group_by(BackgroundColor, 
           PaddleLength) %>%
  summarise(total_hits = sum(HitOrMiss)) %>%
  ungroup
```

### Recapping Pipes (**`%>%`**) {#dw2-pipes}  

And finally today we just want to throw in a quick recap on <a class='glossary' target='_blank' title='' href='https://psyteachr.github.io/glossary/p#pipe'>pipes</a>. We have used pipes a little above but you might still not have got the hang of it so reading through this will help a little. Remember where pipes become most useful is when we **string a series of functions together**, rather than using them as separate steps and having to save the data each time under a new variable name and getting ourselves all confused. In non-piped code we have to create a new object each time, for example, `data`, `data_filtered`, `data_arranged`, `data_grouped`, `data_summarised` just to get to the final one we actually want.  This creates a lot of variables and tibbles in our environment and can make everything unclear, difficult to follow, and eventually slow down our computer. Piped code however uses one variable name, saving space in the environment, and is clear and easy to read. With pipes we skip unnecessary steps and avoid cluttering our environment.  

Here is an example of code that doesn't use pipes to find how many hits there were with the large paddle length and the red background:

* First we group the data accordingly, storing it in `pong_data_group`
* And then we summarise it, storing the answer in `total_hits`
* And finally we filter just the red, small paddle hits


```r
pong_data_group <- group_by(pong_data, 
                            BackgroundColor, 
                            PaddleLength)

pong_data_hits <- summarise(pong_data_group, 
                            total_hits = sum(HitOrMiss))

pong_data_hits_red_small <- filter(pong_data_hits, 
                                   BackgroundColor == "red", 
                                   PaddleLength == 250)
```

Alternatively we can make our code even more efficient, using less code, by stringing our sequence of functions together using pipes. This would look like:


```r
pong_data_hits_red_small <- pong_data %>% 
  group_by(BackgroundColor, 
           PaddleLength) %>% 
  summarise(total_hits = sum(HitOrMiss)) %>% 
  filter(BackgroundColor == "red", 
         PaddleLength == 250) 
```

So the code becomes easier to read as you remember the data goes into one function "and then" into another, "and then" into another, and so on. 

It is also worth remembering that whilst pipes and code can be written in a single line, but it is much easier to see what the pipe is doing if each function takes its own line. You just have to remember that every time you add a function to the pipeline, add a `%>%` first and **note that when using separate lines for each function, the `%>%` must appear at the end of the line and not the start of the next line**. Compare the two examples below. The first won't work but the second will because the second puts the pipes at the end of the line where they need to be!


```r
# Piped version that won't work 
data_arrange <- pong_data 
                %>% filter(PaddleLength == "50")
                %>% arrange(BallSpeed) 

# Piped version that will work 
data_arrange <- pong_data %>%
                filter(PaddleLength == "50") %>%
                arrange(BallSpeed) 
```

## Finished! {#dw2-fin}

Brilliant work again! We have now learned a number of functions and verbs that you will need as you progress through this book.  You will use them in the next chapter so be sure to go over these and try them out to make yourself more comfortable with them.  If you have any questions please post them on Teams. **Happy Wrangling!**

## Test yourself {#dw2-test}

### Knowledge Questions

1. What type of data would these most likely be:

* Male = <select class='webex-select'><option value='blank'></option><option value='answer'>Character</option><option value=''>Numeric</option><option value=''>Integer</option></select>

* 7.15 = <select class='webex-select'><option value='blank'></option><option value=''>Character</option><option value='answer'>Double</option><option value=''>Integer</option></select>

* 137 = <select class='webex-select'><option value='blank'></option><option value=''>Character</option><option value=''>Double</option><option value='answer'>Integer</option></select>


<div class='webex-solution'><button>Explain these answers</button>


There is a lot of different types of data and as well as different types of levels of measurements and it can get very confusing. It's important to try to remember which is which because you can only do certain types of analyses on certain types of data and certain types of measurements. For instance, you can't take the average of Characters just like you can't take the average of Categorical data. Likewise, you can do any maths on Double data, just like you can on Interval and Ratio data. Integer data is funny in that sometimes it is Ordinal and sometimes it is Interval, sometimes you should take the median, sometimes you should take the mean. The main point is to always know what type of data you are using and to think about what you can and cannot do with them.

* Note that the last answer, 137, could also be double as it isn't clear if it could take a decimal or not. 

</div>


<br>

2. Which of the Wickham Six would you use to sort columns from smallest to largest: <div class='webex-radiogroup' id='radio_RVQDDFGMKO'><label><input type="radio" autocomplete="off" name="radio_RVQDDFGMKO" value=""></input> <span>select</span></label><label><input type="radio" autocomplete="off" name="radio_RVQDDFGMKO" value=""></input> <span>filter</span></label><label><input type="radio" autocomplete="off" name="radio_RVQDDFGMKO" value=""></input> <span>mutate</span></label><label><input type="radio" autocomplete="off" name="radio_RVQDDFGMKO" value="answer"></input> <span>arrange</span></label><label><input type="radio" autocomplete="off" name="radio_RVQDDFGMKO" value=""></input> <span>group_by</span></label><label><input type="radio" autocomplete="off" name="radio_RVQDDFGMKO" value=""></input> <span>summarise</span></label></div>

3. Which of the Wickham Six would you use to calculate the mean of a column: <div class='webex-radiogroup' id='radio_WBVLSSCYNK'><label><input type="radio" autocomplete="off" name="radio_WBVLSSCYNK" value=""></input> <span>select</span></label><label><input type="radio" autocomplete="off" name="radio_WBVLSSCYNK" value=""></input> <span>filter</span></label><label><input type="radio" autocomplete="off" name="radio_WBVLSSCYNK" value=""></input> <span>mutate</span></label><label><input type="radio" autocomplete="off" name="radio_WBVLSSCYNK" value=""></input> <span>arrange</span></label><label><input type="radio" autocomplete="off" name="radio_WBVLSSCYNK" value=""></input> <span>group_by</span></label><label><input type="radio" autocomplete="off" name="radio_WBVLSSCYNK" value="answer"></input> <span>summarise</span></label></div>

4. Which of the Wickham Six would you use to remove certain observations - e.g. remove all males: <div class='webex-radiogroup' id='radio_BLFPOIKFWC'><label><input type="radio" autocomplete="off" name="radio_BLFPOIKFWC" value=""></input> <span>select</span></label><label><input type="radio" autocomplete="off" name="radio_BLFPOIKFWC" value="answer"></input> <span>filter</span></label><label><input type="radio" autocomplete="off" name="radio_BLFPOIKFWC" value=""></input> <span>mutate</span></label><label><input type="radio" autocomplete="off" name="radio_BLFPOIKFWC" value=""></input> <span>arrange</span></label><label><input type="radio" autocomplete="off" name="radio_BLFPOIKFWC" value=""></input> <span>group_by</span></label><label><input type="radio" autocomplete="off" name="radio_BLFPOIKFWC" value=""></input> <span>summarise</span></label></div>
 
5. What does this line of code say? `data %>% filter() %>% group_by() %>% summarise()`: <div class='webex-radiogroup' id='radio_CRSITTVZIT'><label><input type="radio" autocomplete="off" name="radio_CRSITTVZIT" value=""></input> <span>take the data and then group it and then filter it and then summarise it</span></label><label><input type="radio" autocomplete="off" name="radio_CRSITTVZIT" value="answer"></input> <span>take the data and then filter it and then group it and then summarise it</span></label><label><input type="radio" autocomplete="off" name="radio_CRSITTVZIT" value=""></input> <span>take the data and then summarise it and then filter it and then group it</span></label><label><input type="radio" autocomplete="off" name="radio_CRSITTVZIT" value=""></input> <span>take the data and then group it and then summarise it and then filter it</span></label></div>
  

### Debugging tips {#dw2-debug}

There are no debugging challenges today as we have done a lot of work but here are some tips to keep in mind.

* Remember to run the library and not just write the code
* Make sure you have spelt the data file name **exactly** as it is shown. Spaces and everything. Do not change the name of the csv file, fix your code instead. If you have a different name for your file than someone else then your code is not reproducible.
* Remember when uploading data we use `read_csv()` which has an underscore, whereas the data file itself will have a dot in its name, `filename.csv`. 
* Check that the datafile is actually in the folder you have set as your working directory. 
* Remember to start a new session each time you start a new analysis - the more functions and packages you use the great a chance of conflicting functions. 
* Watch the spelling of functions and remember to put the data first. Often people forget to include the data as they are focussing on what they want to do.
* Always look at the output of your functions as you build the code. Often code runs but it doesn't do what you think it is doing because you wrote the code wrong. Code only does what you tell it to do!
* When using pipes, remember that you only need the data once, at the start.
* If separating pipes across different lines, remember the line ends with the pipe, it does not start with the pipe.
* And lastly, remember that only the data changes, the skills stay the same. Always look back to when you had the code working and go from there.

## Solutions to Activities {#dw2-sols}

Below you will find the solutions to the above questions. Only look at them after giving the questions a good try and speaking to the tutor about any issues.

### Activity 3 {#dw2-a3sol}

* To include variables we would name all the variables we want:


```r
select_dat <- select(pong_data, 
                     Participant, 
                     PaddleLength, 
                     TrialNumber, 
                     BackgroundColor, 
                     HitOrMiss)
```

* in contrast, to exclude variables we would name the ones we don't want and put a `-` prior to the name:


```r
select_dat <-select(pong_data, 
                    -JudgedSpeed, 
                    -BallSpeed, 
                    -BlockNumber)
```

### Activity 4 {#dw2-a4sol}

* To reorder variables using the `select()` we state the order of the variables we want them in. Note that this only works on column order.


```r
reorder_dat <- select(pong_data, 
                      BallSpeed, 
                      HitOrMiss, 
                      JudgedSpeed, 
                      Participant, 
                      TrialNumber)
```


### Activity 5 {#dw2-a5sol}

* To arrange the rows by certain columns we use `arrange()` but you need to remember to include `desc()` to change it from running smallest-to-largest to largest-to-smallest.


```r
arrange_dat <- arrange(pong_data, 
                       desc(HitOrMiss), 
                       desc(JudgedSpeed))
```


### Activity 6 {#dw2-a6sol}

* Remembering that filters can take more than one argument then the below code would filter for data where:

* JudgedSpeed is 1 AND
* BallSpeed is either 2, 4, 5, or 7, AND
* HitOrMiss is 0.


```r
pong_fast_miss <- filter(pong_data, 
                         JudgedSpeed == 1, 
                         BallSpeed %in% c("2", "4", "5", "7"), 
                         HitOrMiss == 0)
```
 
### Activity 7 {#dw2-a7sol}

If you didn't use pipes then the following code would be appropriate:

* First you filter. And remember that you can call the first object `pong_data_filt` anything that makes sense to you and others.
* Then in a separate step you mutate.


```r
pong_data_filt <- filter(pong_data, 
                         TrialNumber >= 2) 

pong_data_renumbered <- mutate(pong_data_filt, 
                               TrialNumber = TrialNumber - 1)
```

And if you used pipes this would be the solution:

* Remember you include the data once, and the pipes end the line, they do not start the line.


```r
pong_data_renumbered <- filter(pong_data, 
                               TrialNumber >= 2) %>%
  mutate(TrialNumber = TrialNumber - 1)
```

which could also be written as below - which some find better to remember the data goes in first and only once:


```r
pong_data_renumbered <- pong_data %>%
  filter(TrialNumber >= 2) %>%
  mutate(TrialNumber = TrialNumber - 1)
```

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                 |definition                                                                                                                 |
|:--------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------|
|[character](https://psyteachr.github.io/glossary/c.html#character){class="glossary" target="_blank"}                 |A data type representing strings of text.                                                                                  |
|[chunk](https://psyteachr.github.io/glossary/c.html#chunk){class="glossary" target="_blank"}                         |A section of code in an R Markdown file                                                                                    |
|[console](https://psyteachr.github.io/glossary/c.html#console){class="glossary" target="_blank"}                     |The pane in RStudio where you can type in commands and view output messages.                                               |
|[data type](https://psyteachr.github.io/glossary/d.html#data-type){class="glossary" target="_blank"}                 |The kind of data represented by an object.                                                                                 |
|[data wrangling](https://psyteachr.github.io/glossary/d.html#data-wrangling){class="glossary" target="_blank"}       |The process of preparing data for visualisation and statistical analysis.                                                  |
|[descriptive](https://psyteachr.github.io/glossary/d.html#descriptive){class="glossary" target="_blank"}             |Statistics that describe an aspect of data (e.g., mean, median, mode, variance, range)                                     |
|[double](https://psyteachr.github.io/glossary/d.html#double){class="glossary" target="_blank"}                       |A data type representing a real decimal number                                                                             |
|[environment](https://psyteachr.github.io/glossary/e.html#environment){class="glossary" target="_blank"}             |A data structure that contains R objects such as variables and functions                                                   |
|[factor](https://psyteachr.github.io/glossary/f.html#factor){class="glossary" target="_blank"}                       |A data type where a specific set of values are stored with labels; An explanatory variable manipulated by the experimenter |
|[function](https://psyteachr.github.io/glossary/f.html#function){class="glossary" target="_blank"}                   |A named section of code that can be reused.                                                                                |
|[integer](https://psyteachr.github.io/glossary/i.html#integer){class="glossary" target="_blank"}                     |A data type representing whole numbers.                                                                                    |
|[numeric](https://psyteachr.github.io/glossary/n.html#numeric){class="glossary" target="_blank"}                     |A data type representing a real decimal number or integer.                                                                 |
|[package](https://psyteachr.github.io/glossary/p.html#package){class="glossary" target="_blank"}                     |A group of R functions.                                                                                                    |
|[participant](https://psyteachr.github.io/glossary/p.html#participant){class="glossary" target="_blank"}             |the word used to describe someone who has taken part in a study. Note that subject is outdated and no longer used.         |
|[pipe](https://psyteachr.github.io/glossary/p.html#pipe){class="glossary" target="_blank"}                           |                                                                                                                           |
|[tibble](https://psyteachr.github.io/glossary/t.html#tibble){class="glossary" target="_blank"}                       |A container for tabular data with some different properties to a data frame                                                |
|[working directory](https://psyteachr.github.io/glossary/w.html#working-directory){class="glossary" target="_blank"} |The filepath where R is currently reading and writing files.                                                               |


That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!



