# Data Wrangling 3

In the last chapter, we looked at using one-table Wickham verbs to `filter`, `arrange`, `group_by`, `select`, `mutate` and `summarise` the pong data. We also learnt a little more about <a class='glossary' target='_blank' title='' href='https://psyteachr.github.io/glossary/p#pipe'>pipes</a> and we saw how to do some quick counting and some ungrouping. Be sure to try out those activities before moving on as we will start to add a few more functions to allow us a few more skills in <a class='glossary' target='_blank' title='The process of preparing data for visualisation and statistical analysis.' href='https://psyteachr.github.io/glossary/d#data-wrangling'>data wrangling</a>. 

Today, as a progression from working with one table/tibble, we will focus on working with data across two or more tibbles To do this we are going to add two more functions, to the skills we already know. Those are:

* `pivot_longer()` which allows us to **transform** a <a class='glossary' target='_blank' title='A container for tabular data with some different properties to a data frame' href='https://psyteachr.github.io/glossary/t#tibble'>tibble</a> from <a class='glossary' target='_blank' title='Data where all of the observations about one subject are in the same row' href='https://psyteachr.github.io/glossary/w#wide'>wide</a> format to <a class='glossary' target='_blank' title='Data where each observation is on a separate row' href='https://psyteachr.github.io/glossary/l#long'>long</a> format.
* `inner_join()` which allows us to **combine** two tibbles together based on common columns. We actually saw this <a class='glossary' target='_blank' title='A named section of code that can be reused.' href='https://psyteachr.github.io/glossary/f#function'>function</a> in Chapter 3 so this might be more of a recap.

And just to recap, if you are still struggling with the idea of a function, remember that a function takes an input, performs some action, and gives an output. Think of your toaster again like we mentioned before: it takes bread as an input; it performs the action of heating it up; and it gives an output, the toast. A good thing about a lot of the functions we use is that they are nicely named as verbs to describe what they do - `mutate()` mutates (adds on a column); `arrange()` arranges columns, `summarise()` summarises, etc. But keep in mind that you don't have to know or memorise all the different functions; through practice and repetition you will quickly learn to remember which ones are which and what <a class='glossary' target='_blank' title='A group of R functions.' href='https://psyteachr.github.io/glossary/p#package'>package</a> they come from. Sort of like where to find your spoons in your kitchen - you don't look in the fridge, and then the washing machine, and then the drawer. Nope, you learnt, by repetition, to look in the drawer first time. It's the same with functions. Keep in mind that research methods is like a language in that the more you use it and work with it the more it makes sense. So with that, let's do some practicing! 

## Tidy data 

But first a little more on data structure and organisation.For most of this book, we will use a type of data organisation known as <a class='glossary' target='_blank' title='A format for data that maps the meaning onto the structure.' href='https://psyteachr.github.io/glossary/t#tidy-data'>tidy data</a>. Any data in this format is easily processed through the `tidyverse` package. However, the data you work with will not always start formatted in the most efficient way possible. If that happens then our first step is to put it into `Tidy Data` format. There are two fundamental principles defining `Tidy Data`:

1. Each variable must have its own column.
2. Each observation must have its own row.

<a href = "https://www.jstatsoft.org/article/view/v059i10/v59i10.pdf" target = "_blank">Tidy Data (Wickham, 2014)</a> adds the following principle:

* Each type of observation unit forms a table. 

And <a href = "https://r4ds.had.co.nz/tidy-data.html" target = "_blank">Grolemund and Wickham (2017)</a> restate this third principle as:

* Each value must have its own cell (i.e. no grouping two variables together, e.g. time/date in one cell).

Where a cell is where any specific row and column meet; a single data point in a tibble is a cell for example. The <a href = "https://r4ds.had.co.nz/tidy-data.html" target = "_blank">Grolemund and Wickham (2017)</a> book is a very useful read and it is free, but browsing the chapter on Tidy Data will help you visualise how you want to arrange data. Try to keep the principles in mind whilst doing so.  


<div class="info">
<p>If you've worked with any kind of data before, particularly if you've used Excel, it's very likely that you will have used <strong>wide format</strong> or <strong>long format</strong> data. In wide format, each participant's data is all in one row with multiple columns for different data points. This means that the data set tends to be very wide and you will have as many rows as you have participants.</p>
<p>Long format is where each <strong>row</strong> is a single observation, typically a single trial in an experiment or a response to a single item on a questionnaire. When you have multiple trials per participant, you will have multiple rows for the same participant. To identify participants, you would need a variable with some kind of participant id, which can be as simple as a distinct integer value for each participant. In addition to the participant identifier, you would have any measurements taken during each observation (e.g., response time) and what experimental condition the observation was taken under.</p>
<p>In wide format data, each <strong>row</strong> corresponds to a single participant, with multiple observations for that participant spread across columns. So for instance, with survey data, you would have a separate column for each survey question.</p>
<p><code>Tidy</code> is a mix of both of these approachs and most functions in the tidyverse assume the tidy format, so typically the first thing you need to do when you get data, particularly wide-format data, is to reshape it through wrangling. Which is why we teach these really important skills.</p>
<p>There is more information about <a href="https://r4ds.had.co.nz/tidy-data.html">tidy data available here</a>.</p>
</div>

## Analysing the Autism Spectrum Quotient (AQ)

To continue building your data wrangling skills in this chapter you will tidy data from the Autism Spectrum Quotient (AQ) questionnaire. The AQ10 is a non-diagnostic short form of the AQ with only 10 questions per participant. It is a discrete scale and the higher a participant scores on the AQ10 the more autistic-like traits they are said to display. Any person scoring 6 or above is recommended for further diagnosis. You can see an example of the AQ10 through this link: <a href="http://docs.autismresearchcentre.com/tests/AQ10.pdf">AQ10 Example</a>.  

**Today's Goal**

Today we will be working with data from 66 participants and your goal in this chapter is to find an AQ score for each of them through your data-wrangling skills. 

There are four data files to work with that you should download into your chapter folder. You can either right click and save each file separately below, or [click here to download all the files in a zip file](data/chpt6/PsyTeachR_FQA_Chpt6-data.zip){target="_blank"} for you to unzip: 

* <a href="responses.csv" download>responses.csv</a> containing the AQ survey responses to each of the 10 questions for the 66 participants
* <a href="qformats.csv" download>qformats.csv</a> containing information on how a question should be coded - i.e. forward or reverse coding
* <a href="scoring.csv" download>scoring.csv</a> containing information on how many points a specific response should get; depending on whether it is forward or reverse coded 
* <a href="pinfo.csv" download>pinfo.csv</a> containing participant information such as Age, Sex and importantly `ID` number.  

<br>

<div class="info">
<p><strong>Why do we use .csv</strong></p>
<p><code>csv</code> stands for 'comma separated variable', and is a very basic way of storing and transferring data. It really just stores numbers and text and nothing else. The great thing about being this basic is that it can be read by many different machines and does not need expensive licenses to open it.</p>
</div>

And now over a series of eight activities we will build on our data wrangling skills. Remember to try things out,and to ask questions, but that the solutions are at the bottom of the chapter if you are stuck.

## Getting Set-Up 

This first activity is about getting ourselves ready to analyse the data so try out the steps and if you need help, consult the earlier chapters.

### Activity 1: Set-up Data Wrangling 3 {#dw3-a1}

* Open RStudio and set the working directory to your chapter folder. Ensure the environment is clear.
    * If you're using the Rserver, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Open a new R Markdown document and save it in your working directory. Call the file "DataWrangling3".    
* Make sure that you have downloaded the four .csv files above and saved them in your chapter folder. Remember not to change the file names at all and that `data.csv` is not the same as `data (1).csv`.
* Delete the default R Markdown welcome text and insert a new code chunk that loads the package `tidyverse` using the `library()` function. Remember the solutions if needed.

## Loading in Data

Now you need to load in the `.csv` data files using the `read_csv()` function and save them as tibbles in the environment. For example, to load in the `responses.csv` file and save it as the object `responses`, we would type:


```r
responses <- read_csv("responses.csv") 
```

### Activity 2: Load in the data {#dw3-a2}

* Add the following lines of code to your RMarkdown in a new code chunk and complete them to load in all four `.csv` data files. Use the above code as an example and name each object the same as its original file name (minus the .csv part), again as above, e.g. `responses.csv` gets saved as `responses`. Remember to run the lines so that the data loaded in and is stored in your environment. 


```r
responses <-  read_csv()    # load in survey responses
qformats <-                 # load in question formats
scoring <-                  # load in scoring info
pinfo <-                    # load in participant information
```


## Looking at Data

Now that we have the data loaded in it is always best to have a look at it to get an idea of its layout. We showed you a number ways of doing this before such as the `glimpse()` or `View()` functions. Remember you put these in your Console window and put the name of the data between the brackets to see how it is arranged. Don't add these to your Markdown file, these are just for trying things out in the Console window

### Activity 3: Look at your data {#dw3-a3}

Have a look at the data in `responses` to see if you think it is Tidy or not and answer the following question: 

* The data in `responses` is in what format? <div class='webex-radiogroup' id='radio_LGEBBBMCLZ'><label><input type="radio" autocomplete="off" name="radio_LGEBBBMCLZ" value=""></input> <span>Tidy</span></label><label><input type="radio" autocomplete="off" name="radio_LGEBBBMCLZ" value=""></input> <span>Long</span></label><label><input type="radio" autocomplete="off" name="radio_LGEBBBMCLZ" value="answer"></input> <span>Wide</span></label></div>
 


<div class='webex-solution'><button>Explain this answer</button>

The `reponses` tibble is far from being tidy; each row represents multiple observations from the same participant, i.e. each row shows responses to multiple questions and there are the same number of rows as there are participants (66)- `wide format`. Remember we want the data in tidy format as described above.
    
Eh, remind what's a tibble?

Remember, a tibble is simply a dataframe - or a table of data with columns and rows - that is really handy for working with when using the `tidyverse` package. When we say tibble, you can think of a dataframe with rows and columns of information and numbers stored in them - like `responses`, it is a tibble. For more info, see here: <a href="https://cran.r-project.org/web/packages/tibble/vignettes/tibble.html" target = "_blank">Tibbles</a>.
    

</div>
  

## Gathering Your Data

We now have all the data we need loaded in, but in order to make it easier for us to get the AQ score for each participant, we need to change the layout of the `responses` tibble to Tidy Data. 

### Activity 4: Gathering with pivot_longer() {#dw3-a4}

The first step is to use the function `pivot_longer()` to transform the data. The pivot functions can be easier to show than tell - you may find it a useful exercise to run the below code and compare the tibble in the newly created object `rlong` with the tibble in the original object, `respones`, before reading on.


```r
rlong <- pivot_longer(data = responses,
                      cols = Q1:Q10,
                      names_to = "Question", 
                      values_to = "Response")
```

To break this code down a little to help you understand it more:

* As with the other tidyverse functions, the first argument specifies the dataset to use as the base, in this case `responses`. 
    * And remember the more experienced and confident you get you do not have to write the argument names, e.g. `data = `.
* The second argument, `cols` specifies all the columns you want to transform. The easiest way to visualise this is to think about which columns would be the same in the new long-form dataset and which will change. In this case, we only have a single column `Id` that will remain constant and we will transform all the the other columns that contain participant's responses to each question. 
    * The colon notation `first_column:last_column` is used to select all variables from the first column specified to the second column specified. So in our code, `cols` specifies that the columns we want to transform are `Q1` to `Q10`.
    * Note that "Gathering" of columns is based on position in the tibble. If the order of columns in the tibble was Q1 then Q10, the above code would only gather those two columns. As it is, in our tibble, the order, is Q1, Q2, Q3, ... Q10, and therefore the code gathers all the columns between Q1 and Q10.
* The third and fourth arguments are the names of the new columns we are creating.
    * `names_to` specifies the names of the new columns that will be created. 
    * Finally, `values_to` names the new column that will contain the measurements, in this case we'll call it `Response`. 
    * These new column names are put in quotes because they do not already exist in the tibble. This is not always the case but is the case for this function.
    * Note also that these names could have been anything but by using these names the code makes more sense.
    * Lastly, you do need to write names_to = ... and values_to = ... otherwise the columns won't be created correctly.    
    
And now that we have run the code and explained it a bit, you may find it helpful to go back and compare `rlong` and `responses` again to see how each argument matches up with the output of the table.

## Joining Your Data

Now the `responses` data is in tidy format, you are closer to being able to calculate an AQ score for each person. However, you still need some extra information:

* Were the questions reverse or forward scored (i.e., is strongly agree a positive or negative response)? This information is found in `qformats`
* How many points are given to a specific response? This information is found in `scoring`. 

This is a typical analysis situation where different information is in different tables and you need to join them altogether. Both these pieces of information are contained in `qformats` and `scoring` respectively, but we want to join them to `responses` to create one informative tidy table with all the information we need. We can do this type of join through the function `inner_join()`; a function to combine information in two tibbles using a column common to both tibbles.

### Activity 5: Combining data {#dw3-a5}

A wee bit different of an approach here in this activity but try it out and see how you get on. Remember that the solutions are at the end of the chapter.

* Copy the code below into a new code chunk.
* Next, replace the `NULL` values in the below code with the necessary variable names to join `rlong` and `qformats` by `Question`. If you need extra help, revisit Starting with Data chapter as you used the same function then! Make sure you try yourself first.
    * **Hint:** join two tibbles (x and y) by "a common column".


```r
rlong2 <- inner_join(x = NULL, 
                     y = NULL, 
                     by = "NULL")
```

* Now have a look at the tibble in `rlong2`. As you can see we have matched each question with its scoring format, `forward` or `reverse`.

<div class="info">
<p><strong>What is forward and reverse scoring</strong></p>
<p>A lot of questionnaires have some questions that are Forward scored and some questions that are Reverse scored. What does this mean? Imagine a situation where your options in replying to a question are: 1 - extremely agree, 2 - agree, 3 - neutral, 4 - disagree, 5 - extremely disagree. In a forward-scoring question you would get 1 point for extremely agree, 2 for agree, 3 for neutral, etc. In a reverse scoring question you would get 5 for extremely agree, 4 for agree, 3 for neutral, etc.</p>
<p>The reasoning behind this shift is that sometimes agreeing or disagreeing might be more favorable depending on how the question is worded. Secondly, sometimes these questions are used just to catch people out - imagine if you had two similar questions where one has the reverse meaning of the other. In this scenario, people should respond opposites. If they respond the same then they might not be paying attention.</p>
</div>
  
So far so good but there is more information we want to bring into the tibble. We now need to combine the information in our new tibble, `rlong2`, with the `scoring` tibble so you know how many points to attribute each question based on the answer the participant gave, and whether the question was forward or reverse coded. Again, you can use the `inner_join()` function, but this time the common columns found in `rlong2` and `scoring` are `QFormat` and `Response` - i.e. there are two common columns. 

### Activity 6: Combining more data {#dw3-a6} 

Here, in the code below, we are going to show you how to combine data with two common columns. Really this is about combining tibbles were there is corresponding information in the two tibbles - participants appear in both tibbles but there is different info in each tibble and you want it all in the one tibble. This is called an <a class='glossary' target='_blank' title='A mutating join that returns all the rows that have a match in the other table.' href='https://psyteachr.github.io/glossary/i#inner-join'>inner-join</a> But first some information on this task.

* You can only ever join two tables with `inner_join()` at once. If you have multiple tibbles to join like we do, you need to do multiple calls to `inner_join()`.
* When there is more than one common column between two tibbles you are joining, it is best to combine by all the columns to avoid repeated columns names in the new tibble. For example, if you run a join and it produces columns named `variable.x` and `variable.y` it means that there was another column that was the same in both datasets that you didn't add to `by =`.
* You have to be very careful to use `c()` if you have multiple variables for `by`. This is a common error and results in the `variable.x`/`variable.y` issue above. If you forget to use the `c()` and just state different columns, the code will only look at the first column and ignore the rest.

Now type the below line into a new code chunk in your RMarkdown file, run it, and then view the new object. What this code does is it combines `rlong2` and `scoring` based on the matching data in `QFormat` and `Response`


```r
rscores <- inner_join(rlong2, 
                      scoring, 
                      c("QFormat", "Response"))
```

You have now created `rscores` which has information on how each participant responded to each question and how each question should be coded and scored, all within the one tibble. All you need now is to sum the scores for each participant to get their AQ score. 

### Activity 7: Calculating the AQ scores {#dw3-a7}

* First, based on your knowledge from the last chapter, type the below line into your code and replace the NULLs to obtain individual `aq_scores` for each participant.
    * **hint:** `group_by()` - how will you group individual participants?
    * **hint:** `summarise()` - which column will you sum to obtain AQ scores? 
* Then, save your Markdown and knit it to make sure all your code works. 


```r
aq_scores <- rscores %>% 
             group_by(NULL) %>%
             summarise(AQ = sum(NULL))
```


<div class='webex-solution'><button>Additional Hints</button>

Each participant could be grouped by their Id.

If we summed up the value for each Score we might get a full AQ Score for each particpipant.
    

</div>
  

Excellent. Have a look at `aq_scores` and see that you have all the individual AQ scores for each participant!

## Pipes Again!

You now have a complete code to load in your data, convert it to Tidy, combine the tables and calculate an AQ score for each participant. But, if you look at it, some of your code could be more efficient by using pipes. Let's see how well we understand pipes now!

### Activity 8: One last thing on pipes {#dw3-a8}

* Go back through your code and try to rewrite it using pipes `%>%` so that it is as efficient as possible. 
    * **hint:** At any point where the first argument of your function is the name of an object created before that line, there is a good chance you could have used a pipe!


<div class='webex-solution'><button>Additional Hints</button>

 Here are all the bits of this code that could be piped together into one chain:
 
 

```r
`rlong <- pivot_longer(responses, names_to = "Question", values_to = "Response", Q1:Q10)`

`rlong2 <- inner_join(rlong, qformats, \"Question\")`

`rscores <- inner_join(rlong2, scoring, c(\"QFormat\", \"Response\"))`

`aq_scores <- rscores %>% group_by(Id) %>% summarise(AQ = sum(Score))`
```

</div>


## Finished

Brilliant work again today! You have now recapped one-table verbs and started to expand your knowledge of two-table verbs. These are great to know as for example, as seen above, it actually only took a handful of reproducible steps to get from messy data to tidy data; could you imagine doing this by hand in Excel through cutting and pasting? Not to mention the mistakes you could make! Excellent work! You are a DataWrangling expert! Before finishing, remember to go over anything you are unsure of, and if you have any questions, please post them on Teams. There are some additional questions below to help you check your understanding.

## Test yourself {#dw3-test}

* Complete the sentence, the higher the AQ score...<div class='webex-radiogroup' id='radio_LBNQOQDBBU'><label><input type="radio" autocomplete="off" name="radio_LBNQOQDBBU" value=""></input> <span>the less autistic-like traits displayed</span></label><label><input type="radio" autocomplete="off" name="radio_LBNQOQDBBU" value=""></input> <span>has no relation to autistic-like traits</span></label><label><input type="radio" autocomplete="off" name="radio_LBNQOQDBBU" value="answer"></input> <span>the more autistic-like traits displayed</span></label></div>
  

* Assuming that your code all worked, what was the AQ score (just the number) of Participant ID No. 87: <div class='webex-radiogroup' id='radio_ZEVCHNJUTJ'><label><input type="radio" autocomplete="off" name="radio_ZEVCHNJUTJ" value="answer"></input> <span>2</span></label><label><input type="radio" autocomplete="off" name="radio_ZEVCHNJUTJ" value=""></input> <span>3</span></label><label><input type="radio" autocomplete="off" name="radio_ZEVCHNJUTJ" value=""></input> <span>5</span></label><label><input type="radio" autocomplete="off" name="radio_ZEVCHNJUTJ" value=""></input> <span>6</span></label></div>
  

* Type in the box how many participants had an AQ score of 3 (again just the number): <input class='webex-solveme nospaces' size='10' data-answer='["13"]'/>  

* The cut-off for the AQ10 is usually said to be around 6 meaning that anyone with a score of more than 6 should be referred for diagnostic assessment. Based on this data, how many participants might be referred for further assessment? <div class='webex-radiogroup' id='radio_AWLSADPRZW'><label><input type="radio" autocomplete="off" name="radio_AWLSADPRZW" value=""></input> <span>2</span></label><label><input type="radio" autocomplete="off" name="radio_AWLSADPRZW" value=""></input> <span>4</span></label><label><input type="radio" autocomplete="off" name="radio_AWLSADPRZW" value="answer"></input> <span>6</span></label><label><input type="radio" autocomplete="off" name="radio_AWLSADPRZW" value=""></input> <span>8</span></label></div>




<div class='webex-solution'><button>Explain these answers</button>


1. As mentioned, the higher the score on the AQ10 the more autistic-like traits a participant is said to show.

2. You could do this by code with `filter(aq_scores, Id == 87)`, which would give you a tibble of 1x2 showing the ID number and score. If you just wanted the score you could use `pull()` but we haven't shown you that yet: `filter(aq_scores, Id == 87) %>% pull(AQ)`. The answer is an AQ score of 2.

3. Same as above but changing the argument of the filter. `filter(aq_scores, AQ == 3) %>% count()`. The answer is 13. Remember you can do this by counting but the code makes it reproducible and accurate every time. You might make mistakes.

4. `filter(aq_scores, AQ > 6) %>% count()` or `filter(aq_scores, AQ >= 7) %>% count()`. The answer is 6.
        

</div>
  

**Recap on Wickham Verbs!**

Which function(s) would you use to approach each of the following problems?

* We have a dataset of 400 adults, but we want to remove anyone with an age of 50 years or more. To do this, we could use the <select class='webex-select'><option value='blank'></option><option value=''>group_by()</option><option value=''>select()</option><option value=''>arrange()</option><option value=''>summarise()</option><option value=''>mutate()</option><option value='answer'>filter()</option></select> function.

* We are interested in overall summary statistics for our data, such as the overall average and total number of observations. To do this, we could use the <select class='webex-select'><option value='blank'></option><option value=''>arrange()</option><option value=''>filter()</option><option value=''>select()</option><option value=''>mutate()</option><option value=''>group_by()</option><option value='answer'>summarise()</option></select> function.

* Our dataset has a column with the number of cats a person has, and a column with the number of dogs. We want to calculate a new column which contains the total number of pets each participant has. To do this, we could use the <select class='webex-select'><option value='blank'></option><option value=''>group_by()</option><option value=''>filter()</option><option value='answer'>mutate()</option><option value=''>summarise()</option><option value=''>select()</option><option value=''>arrange()</option></select> function.

* We want to calculate the average for each participant in our dataset. To do this we could use the <select class='webex-select'><option value='blank'></option><option value=''>group_by() and arrange()</option><option value='answer'>group_by() and summarise()</option><option value=''>filter() and select()</option><option value=''>arrange() and mutate()</option></select> functions.

* We want to order a dataframe of participants by the number of cats that they own, but want our new dataframe to only contain some of our columns. To do this we could use the <select class='webex-select'><option value='blank'></option><option value=''>select() and summarise()</option><option value='answer'>filter() and select()</option><option value='answer'>arrange() and select()</option><option value=''>group_by() and mutate()</option></select> functions.



<div class='webex-solution'><button>Explain these Answers</button>


* `filter()` helps us keep and remove rows!
* `summarise()` is the main function for creating means, medians, modes, etc.
* `mutate()` can be used to add columns to help add more information.
* When you want summary statistics for individual groups or participants you have to first `group_by()` and then `summarise()`.
* You would need to `filter()` first to reduce the people based on their number of cats and then just `select()` the columns you want to keep.

</div>


## Activity solutions {#dw3-sols}

Below you will find the solutions to the above questions. Only look at them after giving the questions a good try and trying to find help on Google or Teams about any issues.

### Activity 1 {#dw3-a1sol}

* To load the tidyverse into the library we would do the following:


```r
library(tidyverse)
```


### Activity 2 {#dw3-a2sol}

* Remember that you should always use `read_csv()` when working with this book. 
* You read the data into the objects as follows.


```r
responses <- read_csv("responses.csv")                  
qformats <- read_csv("qformats.csv")                 
scoring <- read_csv("scoring.csv")                  
pinfo <- read_csv("pinfo.csv")
```


### Activity 5 {#dw3-a5sol}

* In this `inner_join()` the first tibble is in `rlong`, the second tibble is in `qformats` and the common column is `Question`.


```r
rlong2 <- inner_join(x = rlong, 
                     y = qformats, 
                     by = "Question")
```



### Activity 7 {#dw3-a7sol}

* To create the AQ score we would first group_by the `Id` column so that we have each individual participants data, and then we would sum the `Score` column to obtain their AQ score.


```r
aq_scores <- rscores %>% 
             group_by(Id) %>% # group by the ID number in column Id
             summarise(AQ = sum(Score)) # sum column Score to obtain AQ scores.
```

### Activity 8 {#dw3-a8sol}

This was a tricky one but here is how you might read out the below code. Remember that `%>%` can be read as `and then...`

* First, take the data in `responses` and then
* take columns Q1 to Q10, put the column names in Question and the scores in Response and then
* join with `qformats` and match the data by the column `Question` and then
* join with `scoring` and match the data by the columns `Qformat` and `Response` and then
* group by participant ID and then
* calculate the total AQ score


```r
aq_scores2 <- responses %>% 
  pivot_longer(cols = Q1:Q10,
               names_to = "Question", 
               values_to = "Response") %>%  
  inner_join(qformats, "Question") %>% 
  inner_join(scoring, c("QFormat", "Response")) %>% 
  group_by(Id) %>% 
  summarise(AQ = sum(Score)) 
```

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                           |definition                                                                      |
|:--------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------|
|[data wrangling](https://psyteachr.github.io/glossary/d.html#data-wrangling){class="glossary" target="_blank"} |The process of preparing data for visualisation and statistical analysis.       |
|[function](https://psyteachr.github.io/glossary/f.html#function){class="glossary" target="_blank"}             |A named section of code that can be reused.                                     |
|[inner join](https://psyteachr.github.io/glossary/i.html#inner-join){class="glossary" target="_blank"}         |A mutating join that returns all the rows that have a match in the other table. |
|[long](https://psyteachr.github.io/glossary/l.html#long){class="glossary" target="_blank"}                     |Data where each observation is on a separate row                                |
|[package](https://psyteachr.github.io/glossary/p.html#package){class="glossary" target="_blank"}               |A group of R functions.                                                         |
|[pipe](https://psyteachr.github.io/glossary/p.html#pipe){class="glossary" target="_blank"}                     |                                                                                |
|[tibble](https://psyteachr.github.io/glossary/t.html#tibble){class="glossary" target="_blank"}                 |A container for tabular data with some different properties to a data frame     |
|[tidy data](https://psyteachr.github.io/glossary/t.html#tidy-data){class="glossary" target="_blank"}           |A format for data that maps the meaning onto the structure.                     |
|[wide](https://psyteachr.github.io/glossary/w.html#wide){class="glossary" target="_blank"}                     |Data where all of the observations about one subject are in the same row        |


That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!


