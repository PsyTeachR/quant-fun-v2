# Starting with data

Part of becoming a psychologist is formulating and asking research questions and then gathering data to enable you to answer those questions effectively. In order to do that, it is very important that you understand all aspects of the research process such as experimental design, ethics, data management and visualisation. 

In this chapter you will continue to develop reproducible scripts. This means you will develop scripts that completely and transparently perform an analysis from start to finish in a way that yields the same result for different people using the same software on different computers. And transparency is a key value of science as embodied in the “trust but verify” motto. When you do things reproducibly, others can understand and check your work. This idea of open science is a big debate in the scientific community at the moment. Some classic psychological experiments have been found not to be **<a class='glossary' target='_blank' title='The extent to which the findings of a study can be repeated with new samples from the same population.' href='https://psyteachr.github.io/glossary/r#replicability'>replicable</a>** and part of the explanation for this has been a historical lack of transparency about data and analysis methods. This is a topic we're going to cover more in the lectures and in your reading.

**<a class='glossary' target='_blank' title='Research that documents all of the steps between raw data and results in a way that can be verified.' href='https://psyteachr.github.io/glossary/r#reproducible-research'>Reproducible research</a>** benefits science, but there is a selfish reason, too: the most important person who will benefit from a reproducible script is your future self. When you return to an analysis after two weeks of vacation, you will thank your earlier self for doing things in a transparent, reproducible way, as you can easily pick up right where you left off. 

As part of your skill development it is important that you work with data so that you can become confident and competent in your management and analysis of data. In this course, we will work with real data that has been shared by other researchers to show you what real data looks like and to get your used to the issues that arise! 

## Getting ready to work with data

In this chapter you will learn how to load the **<a class='glossary' target='_blank' title='A group of R functions.' href='https://psyteachr.github.io/glossary/p#package'>packages</a>** required to work with the data. You'll then load the data into RStudio before getting it organised into a format (or structure) that helps us answer our research question. And a top tip to remember is to always think back to what we have done before - for instance, if you can't remember what packages are, go back and revise the [Programming Basics](programming-basics.html){target="_blank"}.

Before we begin working with the data we need to do some set-up and get the data into our working directory. 

### Activity 1: Set-up the data, working directory and Rmd file {#ld-a1}

* Download <a href="ahi-cesd.csv" download>`ahi-cesd.csv`</a> and <a href="participant-info.csv">`participant-info.csv`</a> into the folder on your computer you want to use for this chapter! 
    * To download a file from this book, right click the link and select "save link as". Make sure that both files are saved as ".csv". Do not open them on your machine as often other software like Excel can change setting and ruin the files and cause you problems. We will look at the data once we load it into R and RStudio.
    * If you are working on the server, you will need to upload the files to the server as well.
* Next, open RStudio and ensure the environment is clear.
    * If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Set the working directory to your chapter folder. You might want to refer to [Activity 2 in Chapter 2](#intro-a2){target="_blank"} if you are unsure about this step.
* Now open a new R Markdown document (.Rmd file) and save it in your working directory. Call the file "LoadingData". You can refer to [Activity 3 in Chapter 2](#intro-a3){target="_blank"}
    * **Note:** Your R Markdown file (`LoadingData.Rmd`) must be in the same folder as the datafiles or the code we are going to write will not work.
* Finally, delete the default R Markdown text and insert a new code chunk. Remember to only delete the text and code that comes below/after line 7.

We are now ready to begin working with the data. A **top tip** is to use the white space to take any notes that might help you for each activity and to make reminders to yourself about what things do!

### Activity  2: Loading a package to our library {#ld-a2}

Today we need to use the **<a class='glossary' target='_blank' title='A set of R packages that help you create and work with tidy data' href='https://psyteachr.github.io/glossary/t#tidyverse'>tidyverse</a>** package. You will use this package in almost every single chapter of this course as the functions it contains are those we use for **<a class='glossary' target='_blank' title='The process of preparing data for visualisation and statistical analysis.' href='https://psyteachr.github.io/glossary/d#data-wrangling'>data wrangling</a>**, **<a class='glossary' target='_blank' title='Statistics that describe an aspect of data (e.g., mean, median, mode, variance, range)' href='https://psyteachr.github.io/glossary/d#descriptive'>descriptive</a>** statistics, and visualisation. So let's load that package into our library using the `library()` function.

* To load the `tidyverse` type the following code into your code chunk and then run it. 
* Remember that sometimes in the **<a class='glossary' target='_blank' title='The pane in RStudio where you can type in commands and view output messages.' href='https://psyteachr.github.io/glossary/c#console'>console window</a>** you will see information about the package you have loaded, but sometimes you won't. You should however see the line of code you have just run repeated in the console window. If you see any red text, be sure to read it as it might be a warning, an error or a message. 


```r
library(tidyverse)
```

## The data

For this chapter we are going to be using real data from the following paper:

[Woodworth, R.J., O'Brien-Malone, A., Diamond, M.R. and Schüz, B., 2018. Data from, ‘Web-based Positive Psychology Interventions: A Reexamination of Effectiveness’. Journal of Open Psychology Data, 6(1).](https://openpsychologydata.metajnl.com/articles/10.5334/jopd.35/)

It would be good to read through this paper even briefly, or just the abstract, to give you a sense of what the paper is about and what the data might look like, but in summary the files contain data from two scales as well as demographic information about participants. The two scales are:

* the Authentic Happiness Inventory (AHI), 
* and the Center for Epidemiological Studies Depression (CES-D) scale. 

### Activity 3: Read in data {#ld-a3}

Now that we have our data in our folder we need to read in the data - "read" in this sense just means to bring the data into RStudio and store it in an **<a class='glossary' target='_blank' title='A word that identifies and stores the value of some data for later use.' href='https://psyteachr.github.io/glossary/o#object'>object</a>** so we can work with it. To do this we will use the function `read_csv()` that allows us to read in **<a class='glossary' target='_blank' title='Comma-separated variable: a file type for representing data where each variable is separated from the next by a comma.' href='https://psyteachr.github.io/glossary/c#csv'>.csv files</a>**. There are also functions that allow you to read in Excel files (e.g. .xlsx) and other formats, however in this course we will only use .csv files as they are not software specific and therefore are better for when looking to practice open science! A .csv file can be read by any basic text editor on nearly all machines.

* The code chunk below reads in both datafiles. Type it into your code chunk and run them. Let's look at what they do.
* First, we create an object called `dat` that contains the data in the `ahi-cesd.csv` file.
* Next we then create an object called `info` that contains the data in the `participant-info.csv`.
* Note how both lines have the same format of `object <- function("datafile_name.csv")`
    * it is imperative that you have the double quotation marks around the datafile name and that the datafile name is spelt correctly and includes the .csv part.
    * and remember that `<-` is called the **<a class='glossary' target='_blank' title='The symbol <-, which functions like = and assigns the value on the right to the object on the left' href='https://psyteachr.github.io/glossary/a#assignment-operator'>assignment operator</a>** but we can read it as "assigned to". For example, the first line can be read as the data in `ahi-cesd.csv` is assigned to the object called `dat`.


```r
dat <- read_csv("ahi-cesd.csv")
pinfo <- read_csv("participant-info.csv")
```

If you have done this activity correctly, and the preceding activities, you should now see that the objects `dat` and `pinfo` have appeared in the **<a class='glossary' target='_blank' title='A data structure that contains R objects such as variables and functions' href='https://psyteachr.github.io/glossary/e#environment'>environment</a>** pane. If they are not there then you should check the spelling of the filenames and the structure of the code lines as well as maybe the working directory.

<div class="danger">
<p>WATCH OUT! There is also a function called <code>read.csv()</code>. Be very careful NOT to use this function instead of <code>read_csv()</code> as they have different ways of naming columns. For the activities and the assignments we will always ask and expect you to use <code>read_csv()</code>. This is really a reminder to watch spelling on functions and to be careful to use the right functions.</p>
</div>

## Looking at Data

Great! Now that we have our data read in the first step you should always do is to have an initial check to see what your data looks like. Normally you will have an idea already from the experiment you ran but if you are using someones data you might not, so best to check it out. There are several ways you can look at your data and these are listed in Activity 4 below. Try them all to see how the results differ.

### Activity 4: Look at your data {#ld-a4}

* **Option 1:** In the environment pane, click on the name of the object you want to look at. For example, click the names `dat` and `pinfo`. This will open the data to give you a spreadsheet-like view (although you can't edit it like in Excel)  
* **Option 2:** In the environment pane, click the small blue play button to the left of `dat` and `pinfo`. This will show you the structure of the object information including the names of all the variables in that object and what type they are (also see `str(pinfo)`) 
* **Option 3:** In the console window, type and run `str(pinfo)` and then `str(dat)`
* **Option 4:** Repeat option 3 but this time use the `summary()` function - e.g. `summary(dat)`
* **Option 5:** Repeat option 3 but this time use the `head()` function
* **Option 6:** Type the name of the object you want to view in the console window and run it, e.g., type `dat` in the console window and run it.

As you can see there are various different ways to get an idea of what your data looks like. Each tells you similar but also different info. We will explore more as we get further into the book but for now just be aware that you can use all of these approaches to see your data. More often than not Option 1 and Option 2 give you the info you need, the quickest.

## Joining Data

So far so awesome! We have our data and we know what it looks like, so let's start trying to do things with our data! The first thing we will do is combine datafiles! We have two files, `dat` and `info` but what we really want is a single file that has both the data and the demographic information about the participants as it makes it easier to work with the data when it is all combined together. To do this we are going to use the function `inner_join()` which comes from the `dplyr` package - one of the packages loaded in as part of the `tidyverse`. But don't worry to much about deliberately trying to remember all the different packages and functions as it will come naturally with the practice we give you.

* **Top tip:** Remember to use the help function `?inner_join` if you want more information about how to use a function and to use tab auto-complete to help you write your code.

### Activity 5: Join the files together {#ld-a5}

The below code will create a new object, called `all_dat`, that combines the data from both `dat` and `pinfo` using the information in the columns `id` and `intervention` to match the participants' data across the two sets of data. This is going to be an **<a class='glossary' target='_blank' title='A mutating join that returns all the rows that have a match in the other table.' href='https://psyteachr.github.io/glossary/i#inner-join'>inner join approach</a>** - data will only be kept for a participant if they exist in both datafiles. There are lots of different joins but we will see them as we go further into the book.

* Type and run the below code in a new code chunk to inner join the two sets of data.
* Let's see if we can make sense of what is happening
    * `all_dat` is the new object that has the data combined
    * `x` is the first argument and it should be the first data/object you want to combine
    * `y` is the second argument and it should be the second data/object you want to combine
    * `by` is the third argument and it lists the names of the columns you want to combine the data by. It uses an additional function `c()` to say that there is more than one column to combine by.


```r
all_dat <- inner_join(x = dat, 
                      y = pinfo, 
                      by = c("id", "intervention"))
```

Once you have run this code you should now see the `all_dat` in the environment pane. View the new dataset using one of the methods from Activity 4. In fact, try to remember that you should always view any new object or data that you create. Code often can run but that doesn't necessarily mean it is correct. The programme only ever knows what the code says not what you thought you said. Get into the habit of always checking output!

## Selecting Data

Excellent! We have now combined our data into one big object! However, Very frequently, datasets will have more variables, information, and data than you actually want to use and it can make life easier to create a new object with just the data you need. So, our final step today is to select just some variables of interest! 
In our case, the `all_dat` contains the responses to each individual question on both the AHI scale and the CESD scale, as well as the total score (i.e., the sum of all the individual responses). Let's say for our analysis all we care about is the total scores and the demographic information about participants. We are going to use a new function called the `select()` function, again from the `dplyr` package, to select only the columns we are interested in and store them in (i.e. assign them to) a new object called `summarydata`

### Activity 6: Pull out variables of interest {#ld-a6}

* Type and run the below code in a new code chunk. Let's also have a quick look at the code.
    * summarydata is the new object we are creating using the `select()` function
    * `.data` is the first argument and it wants to know what object are we going to select columns from. In this instance `all_dat`.
    * next we have a list of columns that we want to keep. Every column must be spelt correctly and must exist in the object you are selecting it from. Makes sense really; otherwise the function wouldn't know what you wanted!


```r
summarydata <- select(.data = all_dat, 
                      ahiTotal, 
                      cesdTotal, 
                      sex, 
                      age, 
                      educ, 
                      income, 
                      occasion,
                      elapsed.days)
```

If that has worked correctly you should see `summarydata` in the environment pane and can run `head(summarydata)` now in the console window to get a view of the output. If you see any red text in the console window it would be worth checking the spelling of the objects and columns you wanted to select. If everything has gone to plan the output should look something like this:


| ahiTotal | cesdTotal | sex | age | educ | income | occasion | elapsed.days |
|:--------:|:---------:|:---:|:---:|:----:|:------:|:--------:|:------------:|
|    32    |    50     |  1  | 46  |  4   |   3    |    5     |    182.03    |
|    34    |    49     |  1  | 37  |  3   |   2    |    2     |    14.19     |
|    34    |    47     |  1  | 37  |  3   |   2    |    3     |    33.03     |
|    35    |    41     |  1  | 19  |  2   |   1    |    0     |     0.00     |
|    36    |    36     |  1  | 40  |  5   |   2    |    5     |    202.10    |
|    37    |    35     |  1  | 49  |  4   |   1    |    0     |     0.00     |

## Knitting our Reproducible code

As we saw in [Activity 8 in Chapter 2](##intro-a8-a3){target="_blank"} our final step to making a reproducible document is to knit it to HTML! Try knitting your file to HTML now! If all the code is working correctly then you should get an html document showing all your code! If you don't get the output there could be a few issues either relating to your code or to your installation. You can use the below debugging tips to ask yourself some questions about your code. If all the code looks correct be sure to speak to one of the TEAM to see what might be wrong.

### Debugging tips {#ld-debug}

* When you downloaded the files did you save the file names **exactly** as they were originally? If you download the file more than once you will find your computer may automatically add a number to the end of the file name. `data.csv` is not the same as `data(1).csv`. Pay close attention to names!
* Have you used the **exact** same object names as we did in each activity? Remember, `name` is different to `Name`. In order to make sure you can follow along with this book, pay special attention to ensuring you use the same object names as we do.  
* Have you used quotation marks where needed?  
* Have you accidentally deleted any back ticks (```) from the beginning or end of code chunks?

## Code Layout

And one very quick point before we end for the day.  You may have noticed we wrote code as such:


```r
all_dat <- inner_join(x = dat, 
                      y = pinfo, 
                      by = c("id", "intervention"))
```

But we could also have written it as:


```r
all_dat <- inner_join(x = dat, y = pinfo, by = c("id", "intervention"))
```

Both do exactly the same! In a code chunk you can take a new line after a comma (,) and the code nicely idents for you. It can make it easier to read and to debug if the code is nicely presented but it isn't essential!

## Finished! {#ld-fin}

And that's it, well done! Remember to save your work in your chapter folder and make a note of any mistakes you made and how you fixed them. You have started on your journey to become a confident and competent member of the open scientific community! 

Now would be a good time to get comfortable with what we've covered already and revise the activities and support materials presented so far if needed. If you're feeling comfortable with you can work your way through this book at your own pace or push yourself by using the additional resources highlighted in Programming Basics. And don't forget to try out the tasks below to check your understanding and knowledge of the skills you are learning!

Finally, if you're using the R server, we strongly recommend that you download a copy of any files you have been working on and save them on your machine so that you have a local back-up.

## Test yourself {#ld-test}

### Knowledge Questions

1. When loading in a .csv file, which function should you use? <div class='webex-radiogroup' id='radio_JCUEGSUMQK'><label><input type="radio" autocomplete="off" name="radio_JCUEGSUMQK" value="answer"></input> <span>read_csv()</span></label><label><input type="radio" autocomplete="off" name="radio_JCUEGSUMQK" value=""></input> <span>read.csv()</span></label><label><input type="radio" autocomplete="off" name="radio_JCUEGSUMQK" value=""></input> <span>select()</span></label><label><input type="radio" autocomplete="off" name="radio_JCUEGSUMQK" value=""></input> <span>library()</span></label></div>



<div class='webex-solution'><button>Explain this answer</button>

Remember, in this course we use `read_csv()` and it is important that you use this function otherwise you may find that the data does not work as expected.

</div>
 

2. The function `inner_join()` takes the arguments `x`, `y`, `by`. What does `by` do? <div class='webex-radiogroup' id='radio_DOKGJXCOEE'><label><input type="radio" autocomplete="off" name="radio_DOKGJXCOEE" value=""></input> <span>Specifies the first object to join</span></label><label><input type="radio" autocomplete="off" name="radio_DOKGJXCOEE" value=""></input> <span>Specifies the second object to join</span></label><label><input type="radio" autocomplete="off" name="radio_DOKGJXCOEE" value="answer"></input> <span>Specifies the column to join by that both objects have in common</span></label></div>



<div class='webex-solution'><button>Explain this answer</button>

Remember, functions have arguments and the arguments all do something slightly different. In the `inner_join()` the `by` argument says which columns to join by. If you want to join by more than one column you need to put both columns inside the `c()` function.

</div>
 

3. What does the function `select()` do? <div class='webex-radiogroup' id='radio_OUBGRDOTDE'><label><input type="radio" autocomplete="off" name="radio_OUBGRDOTDE" value=""></input> <span>Keeps only the observations you specify</span></label><label><input type="radio" autocomplete="off" name="radio_OUBGRDOTDE" value="answer"></input> <span>Keeps only the columns you specify</span></label><label><input type="radio" autocomplete="off" name="radio_OUBGRDOTDE" value=""></input> <span>Keeps only the objects you specify</span></label></div>



<div class='webex-solution'><button>Explain this answer</button>

The `select()` function comes from one of the tidyverse packages - dplyr to be precise. It is the main function we use to keep and remove columns we want or don't want. You will start to remember functions you need as you work more with them. Remember the best approach is to think back to what you did!

</div>


### Debugging exercises {#ld-debugex}

One key skill is learning how to fix errors in your code. These exercises below are specifically design to create errors. Ruun each exercise and try to solve the errors yourself before moving on to the next one. Make a note of what the error message was and how you solved it - you might find it helpful to create a new file just for error solving notes. You will find that you often make the same errors in over and over again when running analyses; experts also make tonnes of errors. The difference between a novice and an expert is that when you are first learning, an error might slow you down, but you will greatly speed you up with practice. Don't be put off by errors! 

1. Restart the R session (**`Session >> Restart R`**). Make sure that the working directory is set to the right folder and then run the below code:


```r
dat <- read_csv("ahi-cesd.csv")
```

This will produce the error:

```
`could not find function "read_csv"`
```

Once you figure out how to fix this error, make a note of it.


<div class='webex-solution'><button>Solution</button>

When you restarted the session you unloaded all the packages you previously had loaded - i.e. the `tidyverse`. The function `read_csv()` is part of the `tidyverse` package which means that in order for the code to run you need to run `library(tidyverse)` to reload the package so that you can use the function. Remember that we always need to load packages into our library but we only install them once. Again, think about apps on your phone!

</div>
 


2. Restart the R session (**`Session >> Restart R`**). Make sure that the working directory is set to the right folder and then run the below code:


```r
library(tidyverse)
dat <- read_csv("ahi-cesd")
```

This will produce the error: 

```
`Error: 'ahi-cesd' does not exist in current working directory`.
```

Once you figure out how to fix this error, make a note of it.


<div class='webex-solution'><button>Solution</button>

When loading data you need to provide the full file name including the file extension. In this case the error was caused by writing `ahi-cesd` instead of `ahi-cesd.csv`. As far as coding goes, these are two completely different files and only one of them exists in the working directory.

</div>
 


3. Restart the R session (**`Session >> Restart R`**). Make sure that the working directory is set to the right folder and then run the below code:


```r
library(tidyverse)
dat <- read_csv ("ahi-cesd.csv")
pinfo <- read_csv("participant-info.csv")
all_dat <- inner_join(x = dat, 
                      y = pinfo, 
                      by = "id", "intervention") 
summary(all_dat)
```

Look at the summary for `all_dat`. You will see that R has duplicated the `intervention` variable, so that there is now an `intervention.x` and an `intervention.y` that contain the same data. Once you figure out how to fix this error, make a note of it.


<div class='webex-solution'><button>Solution</button>

If you want to join two objects that have mulitple columns in common you need to use the `c()` command to list all of the columns. The code above hasn't done this, it's just listed `id` and `intervention` without enclosing them with `c()` so it defaults to using just the first one and ignores the other column. When it does this both objects had an `intervention` column so it keeps both. The rule is, when joining objects, join them by all common columns!.

</div>
 


## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                         |definition                                                                                                             |
|:----------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------|
|[assignment operator](https://psyteachr.github.io/glossary/a.html#assignment-operator){class="glossary" target="_blank"}     |The symbol <-, which functions like = and assigns the value on the right to the object on the left                     |
|[console](https://psyteachr.github.io/glossary/c.html#console){class="glossary" target="_blank"}                             |The pane in RStudio where you can type in commands and view output messages.                                           |
|[csv](https://psyteachr.github.io/glossary/c.html#csv){class="glossary" target="_blank"}                                     |Comma-separated variable: a file type for representing data where each variable is separated from the next by a comma. |
|[data wrangling](https://psyteachr.github.io/glossary/d.html#data-wrangling){class="glossary" target="_blank"}               |The process of preparing data for visualisation and statistical analysis.                                              |
|[descriptive](https://psyteachr.github.io/glossary/d.html#descriptive){class="glossary" target="_blank"}                     |Statistics that describe an aspect of data (e.g., mean, median, mode, variance, range)                                 |
|[environment](https://psyteachr.github.io/glossary/e.html#environment){class="glossary" target="_blank"}                     |A data structure that contains R objects such as variables and functions                                               |
|[inner join](https://psyteachr.github.io/glossary/i.html#inner-join){class="glossary" target="_blank"}                       |A mutating join that returns all the rows that have a match in the other table.                                        |
|[object](https://psyteachr.github.io/glossary/o.html#object){class="glossary" target="_blank"}                               |A word that identifies and stores the value of some data for later use.                                                |
|[package](https://psyteachr.github.io/glossary/p.html#package){class="glossary" target="_blank"}                             |A group of R functions.                                                                                                |
|[replicability](https://psyteachr.github.io/glossary/r.html#replicability){class="glossary" target="_blank"}                 |The extent to which the findings of a study can be repeated with new samples from the same population.                 |
|[reproducible research](https://psyteachr.github.io/glossary/r.html#reproducible-research){class="glossary" target="_blank"} |Research that documents all of the steps between raw data and results in a way that can be verified.                   |
|[tidyverse](https://psyteachr.github.io/glossary/t.html#tidyverse){class="glossary" target="_blank"}                         |A set of R packages that help you create and work with tidy data                                                       |

**End of Chapter**

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!
