--- 
title: "Fundamentals of Quantitative Analysis"
author: "Emily Nordmann & Phil McAleer"
date: "2022-12-19"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
csl: include/apa.csl
link-citations: yes
description: |
  This book is designed for Masters Level students who have no prior training in data skills and/or statistical analysis.
url: https://psyteachr.github.io/quant-fun-v2
github-repo: psyteachr/quant-fun-v2
cover-image: images/logos/logo.png
apple-touch-icon: images/logos/apple-touch-icon.png
apple-touch-icon-size: 180
favicon: images/logos/favicon.ico
---



# Overview {-}

<div class="small_right"><img src="images/logos/logo-quant-fun.png" 
     alt="ADS Hex Logo" /></div>

**Book Name:** Fundamentals of Quantitative Analysis

**Summary:** Materials for the University of Glasgow School of Psychology & Neuroscience Research Methods modules for MSc students. 

**Authors:** Emily Nordmann, Wil Toivo & Phil McAleer

**Aim:** This course covers data skills such as R Markdown, data wrangling with tidyverse, and data visualisation with ggplot2. It also introduces statistical concepts such as Null Hypothesis Significance Testing (NHST), alpha, power, effect size, and sample size, as well as demonstrating how to perform numerous analyses based around the general linear model including correlations, t-tests, ANOVAs and Regression.

**Contact:** This book is a living document and will be regularly checked and updated for improvements. Should you have any issues using the book or queries, please contact [Phil McAleer](mailto:philip.mcaleer@glasgow.ac.uk).

**R Version:** This book has been written with R version 4.1.1 (2021-08-10)
     


<!--chapter:end:index.Rmd-->

# Foreword {-}

<div class="small_right"><img src="images/logos/logo-quant-fun.png" 
     alt="ADS Hex Logo" /></div>

### Welcome to the Fundamentals of Quantitative Analysis {-}

This book has been written and designed to help you learn core data skills through R and RStudio. These skills will lead to you being able to manipulate and analyse quantitative data - a key component of any accredited Psychology programme. In addition to this book the team will support you with helpful skills demonstration videos, and we would encourage you to use Teams to ask any questions that you have.

The ability to work with quantitative data is a key skill for Psychologists and by using R as our tool, for working with data, we can also promote reproducible research practices. Although at first it may seem like writing a programming script is more time-consuming than other point-and-click approaches, this is not the case! Once you have written a script that does what you need it to do, you can easily re-run your analysis without having to go through each step again manually which is a) easier and b) less likely to result in errors if you do something slightly different or forget one of the steps. 

Crucially, with an analysis script other researchers can also see how you got from the raw data to the statistics you report in your final paper. Sharing  analysis scripts online on sites such as the [Open Science Framework](https://osf.io/){target="_blank"} is now seen as an important open science practice. Even if you don't continue with quantitative research, in the future, the skills you develop on this course will allow you to evaluate quantitative research and to understand what goes on behind the scenes with data before the conclusions are presented, allowing you to become much more confident and competent consumers and users of research.

### How to use this book and the accompanying videos {-}

Within the book itself, for many of the initial chapters, we will provide the code you need to use. We would always strongly encourage you to type out the code yourself, as this is good practice for learning to code, but remember you can copy and paste from the book if you need to. Typing the code will seem much slower at first and you will make errors, lots of them, but you will learn much more quickly this way so do try to write the code yourself where you can.

We also provide the solutions to many of the activities. No-one is going to check whether you tried to figured out an activity yourself rather than going straight to the solution but remember this, if you copy and paste without thinking, you will learn nothing. Learning data skills and the knowledge that underpins those skills is much like learning a language - the more you practice and the more you use it, the better you become. 

Additionally, a number of the chapters of this book have an associated video or videos. These videos are there to support you as you get comfortable in your data skills. However, it is important that you use them wisely. You should always try to work through each chapter of the book (or if you prefer each activity) on your own first, and only then watch the video if you get stuck, or for extra information. 

Finally, this book is a living document. What that means is that on occasion we will make updates to the book such as fixing typos and including additional detail or activities. When substantial changes are made, we will create new support materials such as an accompanying video. However, it would be impossible to record a new video every time we make a minor change to an activity, therefore, sometimes there may be slight differences between the videos and the content of this book. Where there are differences between the book and the video, the book should always be considered the definitive version. 

### Intended Learning Outcomes {-}

By the end of this course students will be able to:

* Clean and wrangle data into appropriate forms for analysis
* Visualise data using a range of plots
* Conduct and interpret a core set of statistical tests (t-test, correlation, ANOVA, regression)




<!--chapter:end:00-foreword.Rmd-->

# Programming basics

In this chapter, we will cover how to use R and RStudio at the University of Glasgow, as well as some basic programming concepts and terminology, common pitfalls, helpful hints, and where to get help. Those of you who have no programming experience should find this chapter particularly helpful, however, even if you've used R before, or have experience in programming, there may be some helpful hints and tips so please make sure you read through this chapter before the moving on.

This is a long chapter but we don't expect you to memorise all the information that is contained in it and some sections of it will not make sense until you start writing your own code - just make sure you know what help is available!

## R and RStudio

In short, R is a programming language that you will write code in and **<a class='glossary' target='_blank' title='An integrated development environment (IDE) that helps you process R code.' href='https://psyteachr.github.io/glossary/r#rstudio'>RStudio</a>** is an Integrated Development Environment (IDE) which makes working with R easier. Think of it as knowing English and using a plain text editor like NotePad to write a book versus using a word processor like Microsoft Word. You could do it, but it wouldn't look as good and it would be much harder without things like spell-checking and formatting. In a similar way, you can use R without RStudio but we wouldn't recommend it. The key thing to remember is that although you will do all of your work using RStudio for this course, you are actually using two pieces of software which means that you will need both, you need to keep both up-to-date, and you should cite both in any work you do (see the Appendix on [citing R and RStudio](#citing-r-rstudio){target="_blank"} when needed).

But first we need to look at starting up R and RStudio. There are two ways you can use R for Psychology as a student here at the University of Glasgow. First, you can use a online version of R and R through your web browser and we will refer to this as the **R server**. Second, you can download and install R and RStudio for free on your laptop or desktop computer.

**Which version of R should you use?**

The advantage of using the **R server** is that you do not need to install anything on your machine, you simply access it through your web browser. On our server we have already installed all the software you need for this course. We recommend using the server if you have a computer that you cannot install R on (e.g., a Chromebook), or if you have problems with installing R on your computer. 

The advantage to installing R on your computer (what we call a local installation) is that you do not need to be connected to the internet to use it, it is easier to save and manage your files, and there are no problems caused if the server stops working (a rare and short occurrence, but it does happen from time to time). 

With the exception of saving files, both approaches are largely identical in how they work, however, our experience tells us that **if you can install R on your computer, you should**. If your computer cannot install R, or if you have technical problems during the installation you cannot resolve, then you should use the server. So in short we would highly recommend installing R and RStudio on your own machine as soon as you can. However, if you can't install them for some reason, or want to use the R server to get up and running on these first couple of chapters, whilst you install R in your own time, then that is also OK!

### Installing R and RStudio on your computer

To use R and RStudio on your computer, please see [Installing R](https://psyteachr.github.io/ug1-practical/installing-r.html) which has links to detailed instructions and links to the files you need to download, as well as a links to a series of walkthroughs for installing R on different types of computers. Note that you need to install R, then RStudio, and most likely RTools.  These are all free software and do not take a lot of space on your computer. This video by [Danielle Navarro (choose the one for your own machine type)](https://www.youtube.com/playlist?list=PLRPB0ZzEYegOZivdelOuEn-R-XUN-DOjd){target="_blank"} is also highly recommended

### R server

If you prefer to use the R server for now, you will find the link to the R server on Moodle. Please note that the R server is only for use by students and staff in the School of Psychology and Neuroscience, University of Glasgow, and you will need your GUID and password to login. 

## Getting to know R Studio

Whether on the server or your own machine, the first thing to do is to get ourselves orientated in RStudio. You will know in RStudio is that it has a number of windows. RStudio has a **<a class='glossary' target='_blank' title='The pane in RStudio where you can type in commands and view output messages.' href='https://psyteachr.github.io/glossary/c#console'>console window</a>** that you can try out code in (appearing as the bottom left window in Figure \@ref(fig:img-rstudio)), there may be a **<a class='glossary' target='_blank' title='A plain-text file that contains commands in a coding language, such as R.' href='https://psyteachr.github.io/glossary/s#script'>script</a>** editor (top left - not show when you first open RStudio), a window showing functions and objects you have created in the **<a class='glossary' target='_blank' title='A data structure that contains R objects such as variables and functions' href='https://psyteachr.github.io/glossary/e#environment'>Environment</a>** tab (top right window in the figure), and a window that shows plots, files packages, and help documentation (bottom right).

<div class="figure" style="text-align: center">
<img src="images/rstudio.png" alt="RStudio interface" width="100%" />
<p class="caption">(\#fig:img-rstudio)RStudio interface</p>
</div>

You will learn more about how to use the features included in RStudio throughout this course, however, we would highly recommend at some point watching [RStudio Essentials 1](https://rstudio.com/resources/webinars/programming-part-1-writing-code-in-rstudio/) from the RStudio team. The video lasts ~30 minutes and gives a tour of the main parts of RStudio. 

### Console vs. scripts

When you first open up RStudio you won't see a script like above, there will just be a single pane on the left, which is the console window. You can write code in the console window to test it out, but the key thing to note is that you can't save that code anywhere - if you shut down RStudio you lose your code. For this chapter only, we'll use the console window to show you some simple code examples but moving forward we will tell you to work in script files or what are called **<a class='glossary' target='_blank' title='The R-specific version of markdown: a way to specify formatting, such as headers, paragraphs, lists, bolding, and links, as well as code blocks and inline code.' href='https://psyteachr.github.io/glossary/r#r-markdown'>R Markdown</a>** files. We will look at these in later chapters but you can open a new script file a number of ways, the simplest of which is on the top menu of RStudio, selecting **`File >> New File >> R Script`**, and then you'll see the extra pane appear.

## Writing code with functions and arguments

Code in R is made up of **<a class='glossary' target='_blank' title='A named section of code that can be reused.' href='https://psyteachr.github.io/glossary/f#function'>functions</a>**, and **<a class='glossary' target='_blank' title='A variable that provides input to a function.' href='https://psyteachr.github.io/glossary/a#argument'>arguments</a>** that go into the functions, to create outputs. **Functions** in R execute specific tasks and normally take a number of **arguments**. If you're into linguistics you might want to think as these as verbs (function) that require a subject and an object (arguments). Another analogy is that of a toaster - a function would be the toaster and the type of bread and the setting would be the arguments, and the output would be your toast. But a key thing to spot is that functions end in brackets or parentheses, and the arguments go within the parenthesis. They tend to look a bit like this:


```r
function_name(argument1 = value, argument2 = value)
```

That would be the layout of a function with two arguments and each argument takes a value. This will make more sense as you read on.

You will learn to use a lot of functions throughout this book and you can look up all the arguments that a function takes in the help documentation by using the format `?function`. As you will see, in functions, some arguments are required, and some are optional. Optional arguments will often use what is known as a default setting, value, or option (normally specified in the help documentation) if you do not enter any value. Again, like always leaving your toaster on the same setting - the toaster does the same task each time without you changing it.

As an example, let’s look at the help documentation for the function `rnorm()` - a function which randomly generates a set of numbers from what is known as the **<a class='glossary' target='_blank' title='A symmetric distribution of data where values near the centre are most probable.' href='https://psyteachr.github.io/glossary/n#normal-distribution'>Normal Distribution</a>**. 

### Activity 1

* Open up RStudio (either on the server or on your machine) and in the console window, type the following code:  


```r
?rnorm
```

The help documentation for `rnorm()` should appear in the bottom right help panel. In the **Usage** section of the help, we see that `rnorm()` takes the following form:


```r
rnorm(n, mean = 0, sd = 1)
```

In the **Arguments** section of the help, there are explanations for each of the arguments: 

* `n` is the number of observations/numbers/data points we want to create, 
* `mean` is the **<a class='glossary' target='_blank' title='A descriptive statistic that measures the average value of a set of numbers.' href='https://psyteachr.github.io/glossary/m#mean'>mean</a>** of the observations/numbers/data points we will create. 
* and `sd` is the **<a class='glossary' target='_blank' title='A descriptive statistic that measures how spread out data are relative to the mean.' href='https://psyteachr.github.io/glossary/s#standard-deviation'>standard deviation</a>** of the observations/numbers/data points. 

In the **Details** section of the help it notes that if no values are entered for `mean` and `sd` it will use a default of 0 for the mean and 1 for the standard deviation. So these are the values the function will use for its arguments of `mean` and `sd` if you don't state any. However, because there is no **<a class='glossary' target='_blank' title='A value that a function uses for an argument if it is skipped.' href='https://psyteachr.github.io/glossary/d#default-value'>default value</a>** for `n`, this means that you must state a value for the arguments `n`, otherwise the code won't run.

That might sound a little bit confusing so let's try an example. Still using `rnorm()` let's set the required argument `n` to ask R to produce 5 random numbers. 

### Activity 2

* Type the following two lines of code into your console window. Press enter/return at the end of each line to "run" that line. So, type `set.seed(12042016)` and press enter/return and then type `rnorm(n = 5)` and press enter/return.  


```r
set.seed(12042016)
rnorm(n = 5)
```

And you will now see these numbers in your console window:


```
## [1] -0.2896163 -0.6428964  0.5829221 -0.3286728 -0.5110101
```



These numbers have a mean close to 0 (M = -0.238) and an SD close to 1 (SD = 0.48) - they are not exact because you only sampled a very small set and that sampling is random. But now we can play with the function and let's change the additional arguments to produce a different set of numbers. This time we will say we want 5 numbers again (`n = 5`) but we want our mean closer to 10 (`mean = 10`) and our standard deviation closer to 2 (`sd = 2`). We would do that as follows and you see the output numbers below.


```r
set.seed(12042016)
rnorm(n = 5, mean = 10, sd = 2)
```

```
## [1]  9.420767  8.714207 11.165844  9.342654  8.977980
```



This time, again we have produced 5 random numbers, but now this set of numbers has a mean close to 10 (M = 9.524) and an sd close to 2 (0.961) as specified. So from this we start to get a sense of arguments within functions and how we can change them, and how we can always remember to use the help documentation to help us understand what arguments a function requires.

<div class="info">
<p><strong><code>set.seed()</code></strong> function</p>
<p>If you're looking up examples of code online, you may often see code that starts with the function <code>set.seed()</code>. This function controls the random number generator - if you're using any functions that generate numbers randomly (such as <code>rnorm()</code>), running <code>set.seed()</code> will ensure that you get the same result (in some cases this may not be what you want to do). We call <code>set.seed()</code> in this example because it means that you will get the same random numbers as this book.</p>
</div>

### Stating argument names

In the above examples, we have written out the argument names in our code (for example, we wrote `n = 5`, `mean = 10`, `sd = 2`), however, this is not strictly necessary. The following two lines of code would produce very similar outputs with the same number of values and similar means and standard deviations - although each time you run `rnorm()` it will produce a slightly different set of numbers, because it's random.


```r
rnorm(n = 6, mean = 3, sd = 1)
rnorm(6, 3, 1)
```

The main thing is that both lines of code would still work - the code knows what to do with the numbers. Importantly, however, it is key to realise that the code is following a set order of arguments - `n` then `mean` then `sd`. If you do not write out the argument names the code will use the default order of arguments: for `rnorm` it will assume that the first number you enter is `n`, the second number is `mean` and the third number is `sd`. So you can write the arguments names or not, but it is important to know the default order if you choose not to write the argument names. If however you write out the argument names then you can write the arguments in whatever order you like - the below will still work and produce six numbers with a mean close to 3 and a standard deviation close to 1.


```r
rnorm(sd = 1, n = 6, mean = 3)
```

When you are first learning R, you may find it useful to write out the argument names as it can help you remember and understand what each part of the function is doing. However, as your skills progress you may find it quicker to omit the argument names and you will also see examples of code online that do not use argument names so it is important to be able to understand which argument each bit of code is referring to (or look up the help documentation to check).

In this course, we will always write out the argument names the first time we use each function, however, in subsequent uses they may be omitted.

### Tab auto-complete

When writing code, one very useful feature of RStudio is the tab auto-complete for functions (see Figure \@ref(fig:img-autocomplete)). If you write the name of the function and then press the tab key on your keyboard, RStudio will show you the arguments that function takes along with a brief description. If you press enter on the argument name it will fill in the name for you, just like auto-complete on your phone. You can also use the tab button when writing a function name to auto-complete that function name or to find functions that start with certain letters - if maybe you can't quite remember how to spell a function for example!

<div class="figure" style="text-align: center">
<img src="images/autocomplete.png" alt="Tab auto-complete" width="100%" />
<p class="caption">(\#fig:img-autocomplete)Tab auto-complete</p>
</div>

The auto-complete is incredibly useful when you are first learning R and you should remember to use this feature frequently. 

## Base R and packages {#packages}

When you install R you will have access to a range of functions including options for data wrangling and statistical analysis. The functions that are included in the default installation of R are typically referred to as **<a class='glossary' target='_blank' title='The set of R functions that come with a basic installation of R, before you add external packages.' href='https://psyteachr.github.io/glossary/b#base-r'>Base R</a>** and there is a useful cheat sheet that shows many Base R functions which can be found about halfway down [this page under Contributed Cheatsheets here](https://www.rstudio.com/resources/cheatsheets/){target="_blank"} along with a host of other cheatsheets.

However, the power of R is that it is extendable and open source - put simply, if a function doesn't exist or doesn't work very well, anyone can create a new **<a class='glossary' target='_blank' title='A group of R functions.' href='https://psyteachr.github.io/glossary/p#package'>package</a>** that contains data and code to allow you to perform new tasks. You may find it useful to think of **Base R** as the default apps that come on your phone and other packages as additional apps - the ones that you really want to use to make the phone your own - that you need to download separately.

### Activity 3: Install the tidyverse (optional)

In order to use a package, you must first install it. The following code installs the package `tidyverse`, a package we will use very a lot on this course and we will introduce in later chapters.

**PLEASE NOTE: Do not need to do this activity if you are working on the R server or if you are using the computers in a University lab or Boyd Orr Building**. This activity should only be performed on your own device.  

* If you are working on your own computer, use the below code to install the **<a class='glossary' target='_blank' title='A set of R packages that help you create and work with tidy data' href='https://psyteachr.github.io/glossary/t#tidyverse'>tidyverse</a>**. If you are using the R server or using the Boyd Orr lab machine then skip this activity.


```r
install.packages("tidyverse")
```

<div class="danger">
<p>If you get an error message that says something like "WARNING: Rtools is required to build R packages" you may need to download and install an extra bit of software called <a href="https://cran.r-project.org/bin/windows/Rtools/">Rtools</a> (this is one of the many reasons why using the server can be easier).</p>
</div>

But how do we go about using a packge? Note that you only need to install a package once, however, each time you start R you need to load the packages you want to use. Again this is a bit like how you need to install an app on your phone once, but you need to open it every time you want to use it.

To load packages we use the function `library()` - this loads packages into your working library. Typically you would start any analysis script by loading all of the packages you need, but we will come back to that in the next chapter.

### Activity 4: Load the tidyverse

* Run the below code to load the tidyverse in to your working library. 
* Do this activity regardless of whether you are using your own computer or the server.  


```r
library(tidyverse)
```

Often when you load packages you get information in your console window. You don't always get a message but often you will. It does also tend to look like an error message at first - it's not. It's just R telling you what it's done.

Now that we've loaded the `tidyverse` package we can use any of the functions it contains but remember, you need to run the `library()` function every time you start R.

### Package updates

In addition to updates to R and R Studio, the creators of packages also sometimes update their code. This can be to add functions to a package, or it can be to fix errors. One thing to avoid is unintentionally updating an installed package. When you run `install.packages()` it will always install the latest version of the package and it will overwrite any older versions you may have installed. Sometimes this isn't a problem, however, sometimes you will find that the update means your code no longer works as the package has changed substantially. It is possible to revert back to an older version of a package but try to avoid this anyway.

<div class="danger">
<p>To avoid accidentally overwriting a package with a later version, you should <strong>never</strong> include <code>install.packages()</code> in your analysis scripts in case you, or someone else runs the code by mistake. Remember, the server will already have all of the packages you need for this course so you only need to install packages if you are using your own machine.</p>
</div>

### Package conflicts {#conflicts}

There are thousands of different R packages and each package has lots and lots of functions. Unfortunately, because packages are developed by different people, sometimes different packages have the same name for different functions. For example, the packages `dplyr` and `MASS` both have a function named `select()`. **Do not run the below code** but if you did you would see a warning telling you that there is a conflict.


```r
library(dplyr)
library(MASS)
```

```
## 
## Attaching package: 'MASS'
```

```
## The following object is masked from 'package:dplyr':
## 
##     select
```

You would see a warning that **The following object is masked from 'package:dplyr': select**. In this case, R is telling you that the function `select()` in the `dplyr` package is being hidden (or 'masked') by another function with the same name from the `MASS` package. If you were to try and use `select()`, R would use the function from the package that was loaded most recently - in this case it would use the function from `MASS`. This is an issue because you think you are using one function but really you are using another - and they often work differently and you get odd issues in your code that you don't expect. There are various solutions but one simple one, if you already know of the clash, is to specify which package you want to use for a particular function by writing the code in the format `package::function`, meaning "use the function from the package", for example:


```r
dplyr::select()
MASS::select()
```

Clashes are inevitable in your learning and when you see one you will probably not spot it at first but you will learn to resolve them quickly.

## Objects

So we have learnt about functions and arguments and earlier we said functions give us outputs. Another name for outputs, or at least specific types of outputs, are **<a class='glossary' target='_blank' title='A word that identifies and stores the value of some data for later use.' href='https://psyteachr.github.io/glossary/o#object'>objects</a>**. Objects are the output of functions basically - but really you can create objects without functions as well. A large part of your coding will involve creating and manipulating objects. Objects contain stuff. That stuff can be numbers, words, or the result of functions, operations and analyses. But the first key thing to know about object is how to create them and to give them content. You assign content to an object using `<-` - often called the "left arrow" or the **<a class='glossary' target='_blank' title='The symbol <-, which functions like = and assigns the value on the right to the object on the left' href='https://psyteachr.github.io/glossary/a#assignment-operator'>assignment operator</a>** or stated as "assigned to". Note that we don't use `=`. There is a very large discussion on why objects are assigned content and not equal to content but that is for another time. For now, just remember that we assign (`<-`) content, be it words, numbers, or function output, to objects. Let's try that now.

### Activity 5: Create some objects

* Type the following code into the console window and run each line. You should see that `name`, `age`, `today`, `new_year`, and `data` appear in the environment pane.


```r
name <- "emily"
age <- 16 + 17 
today <- Sys.Date()
new_year <- as.Date("2020-01-01")
data <- rnorm(n = 10, mean = 15, sd = 3)
```

<div class="figure" style="text-align: center">
<img src="images/objects-enviro.png" alt="Objects in the environment. Feel free to change your numbers and check that they match the environment!" width="100%" />
<p class="caption">(\#fig:img-objects-enviro)Objects in the environment. Feel free to change your numbers and check that they match the environment!</p>
</div>

Note that in these examples, `name`,`age`, and `new_year` would always contain the values `emily`, 33, and the date of New Year's Day 2020, however, `today` will draw the date from the operating system on the day you are using the computer, and `data` will be a randomly generated set of data - as we saw earlier - so the values of these objects will not be static. 

* Why don't you try changing the name to your name and the age to your age, and seeing if they update in the environment window.

Importantly, for what we will learn in future chapters, objects can be involved in calculations and can interact with each other. For example:


```r
age + 10
```

```
## [1] 43
```


```r
new_year - today
```

```
## Time difference of -1083 days
```


```r
mean(data)
```

```
## [1] 16.71506
```

Finally, you can store the result of these operations on objects in a new object as below:


```r
decade <- age + 10
```

<div class="try">
<p>Remember that you may find it helpful to read <code>&lt;-</code> as <code>contains</code> or <code>assigned to</code>, e.g., <code>name</code> contains the text <code>emily</code> or <code>emily</code> is assigned to the object <code>name</code>.</p>
</div>

You will constantly be creating objects throughout this course and you will learn more about them and how they behave as we go along, however, for now it is enough to understand that they are a way of saving values, that these values can be numbers, text, or the result of operations, and that they can be used in further operations to create new variables.

<div class="info">
<p>You may also see objects referred to as 'variables'. There is a difference between the two in programming terms, however, they are used synchronously very frequently.</p>
</div>

### Looking after the environment {#look-env}

Now that we are starting to learn about the other windows and in particular the environment window, if you've been writing a lot of code you may find that the environment window (or workspace) has become cluttered with many objects. This can make it difficult to figure out which object you need and therefore you run the risk of using the wrong data frame. If you're working on a new dataset, or if you've tried lots of different code before getting the final version, it is good practice to remember to clear the environment to avoid using the wrong object. You can do this in several way.

1. To remove individual objects, you can type `rm(object_name)` in the console. Try this now to remove one of the objects you created in the previous section. For example, you would remove the object `age` by writing `rm(age)`
2. To clear all objects from the environment run `rm(list = ls())` in the console.
3. To clear all objects from the environment you can also click the broom icon in the environment pane. 
<div class="figure" style="text-align: center">
<img src="images/broom.png" alt="Clearing the workspace" width="100%" />
<p class="caption">(\#fig:img-broom)Clearing the workspace</p>
</div>

So it is a good idea to keep your environment clean and tidy. Which leads us on to setting up some global options so that you don't get confused.

## Global options

When you open RStudio it will show you what you were last working on, including your code and any objects you have created, assuming this is not the first time you have used RStudio. This might sound helpful, but actually it tends to cause more problems than it's worth because it means that you risk accidentally using an old version of an object - say `Date` is kept over in the environment from the last time you did some work and you don't realise and you start working on the wrong `Date` because you wanted a new one etc etc etc. In reality, we recommend changing the settings so that each time you start RStudio, it opens a fresh new environment. You can do this by clicking on the top menu **`Tools >> Global Options`** and then deselecting boxes so that your box looks like the below and saving/applying the changes.

<div class="figure" style="text-align: center">
<img src="images/global_options.jpg" alt="Global options - you are aiming to make your global options look similar, in terms of what is ticked, to the above. The main thing is to make sure that Restore RData into workspace is not ticked, and we would set Save workspace to Never. The History options are optional but can help. The update options are really just in case you want to." width="100%" />
<p class="caption">(\#fig:img-options)Global options - you are aiming to make your global options look similar, in terms of what is ticked, to the above. The main thing is to make sure that Restore RData into workspace is not ticked, and we would set Save workspace to Never. The History options are optional but can help. The update options are really just in case you want to.</p>
</div>

That should save a lot of hassle going forward. You will still encounter issues of course and so we are going to end this chapter by having a quick look at getting help.

## Getting Help 

### Help and additional resources

Getting good at programming really means getting good trying stuff out, searching for help online, and finding examples of code to use as a basis of your own. If you are having difficulty with any of the exercises contained in this book then you can of course ask for help from the team, however, learning to problem solve effectively is a key skill that you will develop throughout this course. There are a wealth of additional resources in the Appendix of this book so it might be worth checking them out, but here are four approaches we take to resolving an issue when we hit a problem.

* Use the help documentation. If you're struggling to understand how a function works, remember the `?function` command.
* Think when did you last run this function or code successfully? Look back on what you did then and see what is the difference. The skills build on each other so you should always look back to go forward!
* If you get an error message, copy and paste it in to Google - it's very likely someone else has had the same problem. 
* Trying googling your question in the style of the package name or function name and what you want to do. For example, **arrange data tidyverse** or maybe **sort data in r**

And if those approaches don't work, then, in addition to these course materials and the other [PsyTeachR books](https://psyteachr.github.io/){target="_blank"}, there are a number of excellent online resources for learning data skills that can serve as quick guides:

  * individual package quickguides found via the top menu: **`Help >> Cheat Sheets`**
  * [R Cookbook](http://www.cookbook-r.com/)
  * [StackOverflow](https://stackoverflow.com/)
  * [R for Data Science](https://r4ds.had.co.nz/)
  * Search or use the [#rstats](https://twitter.com/search?f=tweets&q=%23rstats&src=typd) hashtag on Twitter
  
You will find that the #rstats community as it is referred to is very helpful and create a lot of excellent materials.

### Debugging tips

Another top skill for resolving issues is what is known as debugging - fixing your coding mistakes. In fact a large part of coding is trying to figure why your code doesn't work and this is true whether you are a novice or an expert. As you progress through this course you should keep a record of mistakes you make and how you fixed them. In the early chapters we will provide a number of common mistakes to look out for but you will undoubtedly make (and fix!) new mistakes yourself. Thing to keep in mind when coding are:

* Have you loaded the correct packages for the functions you are trying to use? One very common mistake is to write the code to load the package, e.g., `library(tidyverse)` but then forget to run it.
* Have you made a typo? Coding has to be specific on spelling and `data` is not the same as `DATA`, and `t.test` is not the same as `t_test`.
* Is there a package conflict? Have you tried specifying the package and function with `package::function`?
* Is it definitely an error? Not all red text in R means an error - sometimes it is just giving you a message with information. 

### Reset your R sessions

Finally, if you find that your code isn't working and you can't figure out why, it might be worth starting a new session. This will clear the environment and detach all loaded packages - think of it like restarting your phone.When you open up R and start writing code, loading packages, and creating objects, you're typically doing so in a new **session**. In addition to clearing the workspace, it can sometimes be useful to start a new session. This will happen automatically each time you start R on your computer, although sessions can persist on the server. 

### Activity 6

* This last activity shows a quick way to restart R from inside RStudio. On the Top Menu, click **`Session >> Restart R`**. 

<div class="figure" style="text-align: center">
<img src="images/new_session.png" alt="The truth about programming" width="100%" />
<p class="caption">(\#fig:img-session)The truth about programming</p>
</div>

All that said, don't worry about making mistakes. Accept that you will make them and learn from them. And remember we are here to help.

## Test yourself

Finally, throughout the book you will find additional questions like these to help you check your understanding. Some will have blanks to fill in, some will be Multiple Choice, but the answers will be revealed in the chapter. If you are unsure of the answer and can't find the explanation, just ask!

**Question 1.** Why should you never include the code `install.packages()` in your analysis scripts? <div class='webex-radiogroup' id='radio_LIPPBVFYBQ'><label><input type="radio" autocomplete="off" name="radio_LIPPBVFYBQ" value=""></input> <span>You should use library() instead</span></label><label><input type="radio" autocomplete="off" name="radio_LIPPBVFYBQ" value=""></input> <span>Packages are already part of Base R</span></label><label><input type="radio" autocomplete="off" name="radio_LIPPBVFYBQ" value="answer"></input> <span>You (or someone else) may accidentally install a package update that stops your code working</span></label><label><input type="radio" autocomplete="off" name="radio_LIPPBVFYBQ" value=""></input> <span>You already have the latest version of the package</span></label></div>
 


<div class='webex-solution'><button>Explain This Answer</button>

Remember, when you run `install.packages()` it will always install the latest version of the package and it will overwrite any older versions of the package you may have installed.

</div>
 
<br>

**Question 2.**What will the following code produce?
  

```r
rnorm(6, 50, 10)
```

<div class='webex-radiogroup' id='radio_YZGFWSYURJ'><label><input type="radio" autocomplete="off" name="radio_YZGFWSYURJ" value=""></input> <span>A dataset with 10 numbers that has a mean of 6 and an SD of 50</span></label><label><input type="radio" autocomplete="off" name="radio_YZGFWSYURJ" value="answer"></input> <span>A dataset with 6 numbers that has a mean of 50 and an SD of 10</span></label><label><input type="radio" autocomplete="off" name="radio_YZGFWSYURJ" value=""></input> <span>A dataset with 50 numbers that has a mean of 10 and an SD of 6</span></label><label><input type="radio" autocomplete="off" name="radio_YZGFWSYURJ" value=""></input> <span>A dataset with 50 numbers that has a mean of 10 and an SD of 6</span></label></div>
  


<div class='webex-solution'><button>Explain This Answer</button>

The default form for `rnorm()` is `rnorm(n, mean, sd)`. If you need help remembering what each argument of a function does, look up the help documentation by running `?rnorm`

</div>
  
<br>

**Question 3.** If you have two packages that have functions with the same name and you want to specify exactly which package to use, what code would you use? 

<div class='webex-radiogroup' id='radio_YNCPGFRFID'><label><input type="radio" autocomplete="off" name="radio_YNCPGFRFID" value="answer"></input> <span>package::function</span></label><label><input type="radio" autocomplete="off" name="radio_YNCPGFRFID" value=""></input> <span>function::package</span></label><label><input type="radio" autocomplete="off" name="radio_YNCPGFRFID" value=""></input> <span>library(package)</span></label><label><input type="radio" autocomplete="off" name="radio_YNCPGFRFID" value=""></input> <span>install.packages(package)</span></label></div>
  


<div class='webex-solution'><button>Explain This Answer</button>

You should use the form `package::function`, for example `dplyr::select`. Remember that when you first load your packages R will warn you if any functions have the same name - remember to look out for this!

</div>
  
<br>

**Question 4.** Which of the following is most likely to be the input to an argument? <div class='webex-radiogroup' id='radio_YTJMCNNGDE'><label><input type="radio" autocomplete="off" name="radio_YTJMCNNGDE" value="answer"></input> <span>35</span></label><label><input type="radio" autocomplete="off" name="radio_YTJMCNNGDE" value=""></input> <span><-</span></label><label><input type="radio" autocomplete="off" name="radio_YTJMCNNGDE" value=""></input> <span>read_csv()</span></label></div>



<div class='webex-solution'><button>Explain This Answer</button>

read_csv() looks like a function as it has the brackets at the end of it and the <- is the assignment symbol so it is most likely that 35 might be the input to an argument as it is just a value.

</div>
 
<br>

**Question 5.** An easy way to spot functions is to look for <div class='webex-radiogroup' id='radio_MFIOHEBJUN'><label><input type="radio" autocomplete="off" name="radio_MFIOHEBJUN" value="answer"></input> <span>brackets</span></label><label><input type="radio" autocomplete="off" name="radio_MFIOHEBJUN" value=""></input> <span>computers</span></label><label><input type="radio" autocomplete="off" name="radio_MFIOHEBJUN" value=""></input> <span>numbers</span></label></div>


<div class='webex-solution'><button>Explain This Answer</button>

Remember that functions tend to have brackets or parentheses at the end of their name and the arguments and values go inside the parentheses.

</div>
 
<br>

**Question 6.** The job of `<-` is to send the output from the function to a/an <div class='webex-radiogroup' id='radio_XJLAODVFZF'><label><input type="radio" autocomplete="off" name="radio_XJLAODVFZF" value=""></input> <span>argument</span></label><label><input type="radio" autocomplete="off" name="radio_XJLAODVFZF" value=""></input> <span>assignment</span></label><label><input type="radio" autocomplete="off" name="radio_XJLAODVFZF" value="answer"></input> <span>object</span></label></div>



<div class='webex-solution'><button>Explain This Answer</button>

This is the assignment operator and we use it, `<-`, to assign content such as the output of functions to an object.

</div>
 
<br>

**Question 7.** Why won't the following code give me 10 values with a mean close to 5 and an sd close to 1: `rnorm(n = 10, meen = 5, sd = 1)`? <div class='webex-radiogroup' id='radio_LLEDLMHZXI'><label><input type="radio" autocomplete="off" name="radio_LLEDLMHZXI" value=""></input> <span>b. The order of arguments is not correct</span></label><label><input type="radio" autocomplete="off" name="radio_LLEDLMHZXI" value="answer"></input> <span>c. One of the arguments is spelt incorrectly</span></label><label><input type="radio" autocomplete="off" name="radio_LLEDLMHZXI" value=""></input> <span>a. The values do not match what I wanted</span></label><label><input type="radio" autocomplete="off" name="radio_LLEDLMHZXI" value=""></input> <span>d. The argument names have been included</span></label></div>



<div class='webex-solution'><button>Explain This Answer</button>

The answer is c - One of the arguments is spelt incorrectly. If you look closely you will see that the argument `mean` has been spelt with two e's instead of one e, `meen`. This will create an error and the code will crash. This is a typical debugging issue in coding and just shows you need to be careful with spelling.

</div>
 
<br>

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                     |definition                                                                                                                                                       |
|:------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|[argument](https://psyteachr.github.io/glossary/a.html#argument){class="glossary" target="_blank"}                       |A variable that provides input to a function.                                                                                                                    |
|[assignment operator](https://psyteachr.github.io/glossary/a.html#assignment-operator){class="glossary" target="_blank"} |The symbol <-, which functions like = and assigns the value on the right to the object on the left                                                               |
|[base r](https://psyteachr.github.io/glossary/b.html#base-r){class="glossary" target="_blank"}                           |The set of R functions that come with a basic installation of R, before you add external packages.                                                               |
|[console](https://psyteachr.github.io/glossary/c.html#console){class="glossary" target="_blank"}                         |The pane in RStudio where you can type in commands and view output messages.                                                                                     |
|[default value](https://psyteachr.github.io/glossary/d.html#default-value){class="glossary" target="_blank"}             |A value that a function uses for an argument if it is skipped.                                                                                                   |
|[environment](https://psyteachr.github.io/glossary/e.html#environment){class="glossary" target="_blank"}                 |A data structure that contains R objects such as variables and functions                                                                                         |
|[function](https://psyteachr.github.io/glossary/f.html#function){class="glossary" target="_blank"}                       |A named section of code that can be reused.                                                                                                                      |
|[mean](https://psyteachr.github.io/glossary/m.html#mean){class="glossary" target="_blank"}                               |A descriptive statistic that measures the average value of a set of numbers.                                                                                     |
|[normal distribution](https://psyteachr.github.io/glossary/n.html#normal-distribution){class="glossary" target="_blank"} |A symmetric distribution of data where values near the centre are most probable.                                                                                 |
|[object](https://psyteachr.github.io/glossary/o.html#object){class="glossary" target="_blank"}                           |A word that identifies and stores the value of some data for later use.                                                                                          |
|[package](https://psyteachr.github.io/glossary/p.html#package){class="glossary" target="_blank"}                         |A group of R functions.                                                                                                                                          |
|[r markdown](https://psyteachr.github.io/glossary/r.html#r-markdown){class="glossary" target="_blank"}                   |The R-specific version of markdown: a way to specify formatting, such as headers, paragraphs, lists, bolding, and links, as well as code blocks and inline code. |
|[rstudio](https://psyteachr.github.io/glossary/r.html#rstudio){class="glossary" target="_blank"}                         |An integrated development environment (IDE) that helps you process R code.                                                                                       |
|[script](https://psyteachr.github.io/glossary/s.html#script){class="glossary" target="_blank"}                           |A plain-text file that contains commands in a coding language, such as R.                                                                                        |
|[standard deviation](https://psyteachr.github.io/glossary/s.html#standard-deviation){class="glossary" target="_blank"}   |A descriptive statistic that measures how spread out data are relative to the mean.                                                                              |
|[tidyverse](https://psyteachr.github.io/glossary/t.html#tidyverse){class="glossary" target="_blank"}                     |A set of R packages that help you create and work with tidy data                                                                                                 |

**End of Chapter**

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!

<!--chapter:end:01-programming-basics.Rmd-->

# Intro to R

In this chapter we are going to start introducing you to using code to create **<a class='glossary' target='_blank' title='Research that documents all of the steps between raw data and results in a way that can be verified.' href='https://psyteachr.github.io/glossary/r#reproducible-research'>reproducible research</a>**. We will cover things such as setting a working directory, what is a working directory, using R Markdown, and writing code in **<a class='glossary' target='_blank' title='The R-specific version of markdown: a way to specify formatting, such as headers, paragraphs, lists, bolding, and links, as well as code blocks and inline code.' href='https://psyteachr.github.io/glossary/r#r-markdown'>R Markdown</a>**. There are eight activities in total for this chapter, but don't worry, they are broken down into very small steps to help you follow along. 

## Using your Working Directory

Before you starting to work with data in R, and before you can save the output of what you've created (which you almost always will want to do), you first need to tell R where the **<a class='glossary' target='_blank' title='The filepath where R is currently loading files from and saving files to.' href='https://psyteachr.github.io/glossary/w#working-directory'>working directory</a>** is. What this means is that we tell R where the files we are going to use (such as our raw data) are located, and where we want to save any files you have created. Think of it just like when you have different course modules, and you have separate folders for each topic e.g. biology, history and so on. When working with data, it's useful to have all the data sets and files you need nicely organised in folders.

We would highly recommend making a new folder for this course, maybe called "PsychResearchMethods", "ResearchMethodsLabs", or "FundamentalsOfQuantAnalysis" and then add sub-folders, inside that folder as you carry out each chapter, saving any data, scripts, and portfolio files for each chapter into these folders. The main thing is that you call the folder something sensible so that you know what it is and where it is. However, see the red warning box below!

<div class="danger">
<p>Whatever you do, don't call the folder your keep your data skills work in "R". If you do this, sometimes R has an identity crisis and won't save or load your files properly. It can also really damage your setup of R and lead you to having to reinstall everthing. The reason being is that, remembering packages from the first chapter, R tends to save all the packages in a folder called R. If there is another folder called R then it gets confused and stops working properly. You can of course have a folder called "my_Rwork" but just not "R" by itself.</p>
</div>

**Top tip 1:** If you're using R on your laptop rather than the server, it can also be a good idea to save your work onto a cloud storage server like OneDrive so that you never lose your work. Particularly if the work relates to assignments. Just like your written work, you wouldn't want to lose your coding work!

**Top tip 2:** Coding is every so slightly easier when file names and folder names do not have spaces in them. We would suggest folder names like "PsychResearchMethods" instead of "Psych Research Methods".

### Activity 1: Create your a folder for all your work {#intro-a1}

* Choose a location for the work and assignments you will do for this module and then create a folder and the necessary sub-folders for each chapter. These will be blank for now but we will add to them over the semester.

### Activity 1b: Upload data files to the server {#intro-a1b}

**Note:** This activity (activity 1b) is only for those using the University of Glasgow **R Server** - if you are using a local installation on your own device you will not need to do this activity and skip down to [Activity 2]{#intro-a2}.

The main disadvantage to using the R server is that you will need create folders on the server and then upload and download any files you are working on to and from the server. Please be aware that **there is no link between your computer and the R server**. If you change files on the server, they won't appear on your computer until you download them from the server, and you need to be very careful when you submit your assessment files that you're submitting the right file. This is the main reason we recommend installing R on your computer if you can.

Going forward throughout this book, if you're using the server, you'll do an extra step where you also upload them to the sever. We're not going to use any data files in this session but let's try an example to make it clear how you get the data files on to the server.

* Log on to the **R server** using the link on the main course Moodle page.
* In the file pane click `New folder` and create the same structure you created on your computer.
* Download <a href="ahi-cesd.csv" download>`ahi-cesd.csv`</a> and <a href="participant-info.csv">`participant-info.csv`</a> into the chapter folder on your computer. To download a file from this book, right click the link and select "save link as". Make sure that both files are saved as ".csv". Do not open them on your machine as often other software like Excel can change setting and ruin the files.
* Now that the files are stored on your computer, go to RStudio on the server and click `Upload` then `Browse`and choose the folder for the chapter you're working on.
* Click `Choose file` and go and find the data you want to upload.

### Activity 2: Set the working directory {#intro-a2}

Ok great, now that we have a folder structure that will keep everything nice and ordered you need to **set the working directory** by clicking on the top menu, **`Session >> Set Working Directory >> Choose Directory`** and then select the relevant folder for this chapter as your working directory.

**Note:** Setting the working directory means that you are telling R where the data is that you want to work on. It is also where you are going to save files and output. More often than not, when learning, the most common error is because people have not set the working directory and R does not know where the data is!

**Top tip:** One of the first things we always do when we open R in RStudio is set the working directory to where our data is.

<div class="figure" style="text-align: center">
<img src="images/working-dir.png" alt="Setting the working directory" width="100%" />
<p class="caption">(\#fig:img-working-dir)Setting the working directory</p>
</div>

## R Markdown for data skills and portfolio assignments

Ok great, we now have a folder structure we are going to use and we have told R where it is so now let's write some code!

For the duration of this data skills book and the related assignments you will use a worksheet format called R Markdown (abbreviated as Rmd) which is a great way to create dynamic documents with embedded chunks of code. Remember you saw scripts in Chapter 1? Well R Markdown is like a script but has some excellent features that make it so much better. 

R Markdown documents are self-contained and fully reproducible (if you have the necessary data, you should be able to run someone else's analyses with the click of a button) which makes it very easy to share. This is an important part of your open science training as one of the reasons we teach data skills this way is that it enables us to share open and reproducible information. Using these worksheets enables you to keep a record of all the code you write during this course, and when it comes time for the portfolio assignments, we can give you a task you can and then fill in the required code.

For more information about R Markdown feel free to have a look at their main webpage sometime [http://rmarkdown.rstudio.com](http://rmarkdown.rstudio.com){target="_blank"} but for now, the key advantage to know about is that it allows you to write code into a document, along with regular text, and then **<a class='glossary' target='_blank' title='To create an HTML, PDF, or Word document from an R Markdown (Rmd) document' href='https://psyteachr.github.io/glossary/k#knit'>knit</a>** it using the package `knitr` to create your document as either a webpage (**<a class='glossary' target='_blank' title='Hyper-Text Markup Language: A system for semantically tagging structure and information on web pages.' href='https://psyteachr.github.io/glossary/h#html'>HTML</a>**), a PDF, or Word document (.docx). This will become more clear with an example!

### Activity 3: Open and save a new R Markdown document {#intro-a3}

* Open a new R Markdown document by clicking the 'new item' icon and then click 'R Markdown' as shown here:

<div class="figure" style="text-align: center">
<img src="images/new-markdown.png" alt="Opening a new R Markdown document" width="100%" />
<p class="caption">(\#fig:img-new-markdown)Opening a new R Markdown document</p>
</div>

* You will now be prompted to give it a title so let's call it "Intro to R". 
* Also, change the author name to your GUID as this will be good practice for the portfolio assignments. * Leave the output format selected as HTML for now!

Once you click **OK** this will open a new R Markdown document.

* Save this R Markdown document, by clicking **`File >> Save as`** from the top menu, and name this file "Intro to R" as well. 

If you've set the working directory correctly, you should now see this file appear in your file viewer pane in the bottom right hand corner like in the example below (your file names and folders will be different depending on what you called the folders and file).

<div class="figure" style="text-align: center">
<img src="images/file-dir.png" alt="New file in working directory" width="100%" />
<p class="caption">(\#fig:img-file-dir)New file in working directory</p>
</div>

### Activity 4: Create a new code chunk {#intro-a4}

Great. We now have our R Markdown document so let's start using it to see how we can combine code and text to create an informative document.

When you first open a new R Markdown document you will see a bunch of default text that looks like this:

<div class="figure" style="text-align: center">
<img src="images/markdown-default.png" alt="New R Markdown text" width="100%" />
<p class="caption">(\#fig:img-markdown-default)New R Markdown text</p>
</div>

The default text is just there to give you some examples of what you can do with R Markdown but we are going to show you that as well so do the following:

* Delete **everything** below line 7
* On line 8 type "About me"
* Click on the Top Menu: **`Code >> Insert Chunk`** from the top menu.

Your Markdown document should now look something like this:

<div class="figure" style="text-align: center">
<img src="images/new-chunk.png" alt="New R chunk" width="100%" />
<p class="caption">(\#fig:img-new-chunk)New R chunk</p>
</div>

What you have created is called a **<a class='glossary' target='_blank' title='A section of code in an R Markdown file' href='https://psyteachr.github.io/glossary/c#chunk'>code chunk</a>**. In R Markdown, anything written outside of a code chunk is assumed to be just normal text, just like you would have in a text editor, and anything written inside the code chunk is assumed to be code. This makes it easy to combine both text and code in one document.

<div class="warning">
<p>When you create a new code chunk you should notice that the grey box starts and ends with three back ticks, followed by the {r}, and then it ends with three back ticks again. This is the structure that creates a code chunk. You could actually just type this structure instead of using the <code>Insert</code> approach but when learning it does help a bit!</p>
<p>One common mistake is to accidentally delete these back ticks. A useful thing to notice is that code chunks tend to have a different color background - in the default viewing settings a code chunk is grey and the normal text is white. You can use this to look for mistakes. If the colour of certain parts of your Markdown doesn't look right, check that you haven't deleted the backticks.</p>
<p>In addition, remember it is backticks (i.e. this `) and not single quotes (i.e. not this ')!</p>
</div>

### Activity 5: Write some code {#intro-a5}

Awesome! You are doing great and learning more than you think you are! 

Now we're going to use the code examples you read about in Programming Basics to add some code to our R Markdown document. 

* In your code chunk write the below code but replace the values of name/age/birthday with your own details). Remember that the four lines of code should all be inside the code chunk!

**Note:** Text and dates need to be contained in quotation marks, e.g. "my name". Numerical values are written without quotation marks, e.g. 45. 

**Top tip:** Missing and/or unnecessary quotation marks are a common cause of code not working - remember this!


```r
name <- "Emily" 
age <- 35
today <- Sys.Date()
next_birthday <- as.Date("2021-07-11")
```

## Running code in R Markdown

Brilliant! We now have code in our code chunk and now we are going to **run** the code! Running the code just trying to make it work, or seeing if it works! When you're working in an R Markdown document, there are several ways to run your lines of code.

* First, one slow option is you can highlight the code you want to run and then click **`Run >> Run Selected Line(s)`**.

<div class="figure" style="text-align: center">
<img src="images/run1.png" alt="Slow method of running code" width="100%" />
<p class="caption">(\#fig:img-run1)Slow method of running code</p>
</div>

* Alternatively, you can press the green "play" button at the top-right of the code chunk and this will run **all** lines of code in that chunk.

<div class="figure" style="text-align: center">
<img src="images/run2.png" alt="Slightly faster method of running code that runs all lines within the code chunk!" width="100%" />
<p class="caption">(\#fig:img-run2)Slightly faster method of running code that runs all lines within the code chunk!</p>
</div>

Even better though is to learn some of the keyboard shortcuts below so it becomes more natural and fluid in your typing and makes your learning easier! 

* To run a single line of code, make sure that the cursor is in the line of code you want to run and press `ctrl + enter`. 
* If you want to run all of the code in the code chunk, press `ctrl + shift + enter`. 
**Note:** When using this last method of running lines of code - by positioning the cursor on the line and using `ctrl + enter` on your keyboard, note that the cursor does not have to be at any specific point of the line, i.e. it does not have to be at the start, middle or the end, it can literally be anywhere. 

### Activity 6: Run your code {#intro-a6}

* Now run your code using one of the methods above. You should see the variables `name`, `age`, `today`, and `next_birthday` appear in the environment pane in the top right corner.
* Clear out the [environment using the broom handle approach](#look-env) we saw in Chapter 1 and try a different method to see which works best for you!

### Activity 7: Inline code {#intro-a7}

Superb! Our code works and we know how to run it. But one of the incredible benefits we said about R Markdown is that you can mix text and code. Even better is that you can combined code into a sentence to put specific outputs of your code, like a value, using what is called **inline code**. Think about a time you've had to copy and paste a value or text from one file in to another and you'll know how easy it can be to make mistakes. Inline code avoids this. It's easier to show you what inline code does rather than to explain it so let's have a go.

First, copy and paste this text exactly (do not change *anything*) to the underneath and outside your code chunk - this will be the white section under the grey code chunk if you are using default views.


```r
My name is `r name` and I am `r age` years old. 

It is `r next_birthday - today` days until my birthday.
```

Ok so nothing happened there but that is because we have not done the last magic step - in the next activity!

### Activity 8: Knitting your file {#intro-a8}

As our final step we are going to **<a class='glossary' target='_blank' title='To create an HTML, PDF, or Word document from an R Markdown (Rmd) document' href='https://psyteachr.github.io/glossary/k#knit'>knit</a>** our file. This means that we're going to compile (i.e. turn) our code into a document that is more presentable. 
* From the top menu, click **`Knit >> Knit to HMTL`**. R Markdown will now create a new HTML document and it will automatically save this file in your working directory.

Now let's look at this outputted HTML document and at the sentence we copied in from Activity 7. As if by magic, that slightly odd bit of text you copied and pasted now appears as a normal sentence with the values pulled in from the objects you created.

**My name is Emily and I am 35 years old. <br><br>It is -526 days until my birthday.**

Pretty amazing isn't it! We're not going to use inline coding very often in the rest of the course but hopefully you can see just how useful this would be when writing up a report with lots of numbers! R Markdown is an incredibly powerful and flexible format - this book was written using it! The key thing about using inline coding is the structure, i.e. the backtick, followed by the lower case r, then space, then the code, then another backtick. You will get the hang of it as the semester goes on with a little practice.

There are a few final things to note about knitting that will be useful for going forward with your data skills learning and assignments:

* R Markdown will only knit if your code works - this is a good way of checking for assignments whether you've written functioning code!
* You can choose to knit to a Word document rather than HTML. This can be useful for e.g., sharing with others, however, it may lose some functionality and it probably won't look as good so we'd recommend always knitting to HTML.
* You can choose to knit to PDF, however, unless you're using the server this requires a LaTex installation and is quite complicated. If you don't already know what LaTex is and how to use it, do not knit to PDF. If you do know how to use LaTex, you don't need us to give you instructions!
* R will automatically open the knitted HTML file in the viewer, however, you can also navigate to the folder it is stored in and open the HTML file in your web browser (e.g., Chrome or Firefox).

## Finished

And you're done! On your very first time using R you've not only written functioning code but you've written a reproducible output! You could send someone else your R Markdown document and they would be able to produce exactly the same HTML document as you, just by pressing knit.

The key thing we want you to take away from this chapter is that the data skills that you are going to learn can be broken down into manageable chunks and that is how we are going to teach you to help you learn them. The skills might be very new to a lot of you, but we're going to take you through it step-by-step. You'll be amazed at how quickly you can start producing professional-looking data visualisations and analysis.

If you have any questions about anything contained in this chapter or in Programming Basics, please remember to ask us!

## Test Yourself

1. One of the key first steps when we open RStudio is to: <div class='webex-radiogroup' id='radio_ZFNUDDMKDA'><label><input type="radio" autocomplete="off" name="radio_ZFNUDDMKDA" value="answer"></input> <span>set your working directory</span></label><label><input type="radio" autocomplete="off" name="radio_ZFNUDDMKDA" value=""></input> <span>put on some top tunes as we will be here a while</span></label><label><input type="radio" autocomplete="off" name="radio_ZFNUDDMKDA" value=""></input> <span>build some folders</span></label><label><input type="radio" autocomplete="off" name="radio_ZFNUDDMKDA" value=""></input> <span>make a coffee</span></label></div>



<div class='webex-solution'><button>Explain This Answers</button>

One of the most common issues we see is that code doesn't work first time because people have forgotten to set the working directory. The working directory is the file you want to save any files to, or any output, or contains your data. Code needs to know where the data is so we set the working directory as the first step when we open RStudio

</div>


<br>
  
2. When using the default environment color settings for RStudio what color would the background of a code chunk be in R Markdown? <select class='webex-select'><option value='blank'></option><option value=''>white</option><option value=''>red</option><option value=''>green</option><option value='answer'>grey</option></select>

3. When using the default environment color settings for RStudio what color would the background of normal text be in R Markdown? <select class='webex-select'><option value='blank'></option><option value='answer'>white</option><option value=''>red</option><option value=''>green</option><option value=''>grey</option></select>


<div class='webex-solution'><button>Explain These Answers</button>

Assuming you haven't changed any of the settings in RStudio, code chunks will tend to have a grey background and normal text will tend to have a white background. This is a good way to check that you have closed and opened code chunks correctly.

</div>


<br>

4. Code chunks are started with: <div class='webex-radiogroup' id='radio_PDLNFNCDFT'><label><input type="radio" autocomplete="off" name="radio_PDLNFNCDFT" value=""></input> <span>three single quotes</span></label><label><input type="radio" autocomplete="off" name="radio_PDLNFNCDFT" value="answer"></input> <span>three backticks</span></label><label><input type="radio" autocomplete="off" name="radio_PDLNFNCDFT" value=""></input> <span>three double quotes</span></label><label><input type="radio" autocomplete="off" name="radio_PDLNFNCDFT" value=""></input> <span>three single clefs</span></label></div>



<div class='webex-solution'><button>Explain This Answers</button>

Code chunks always take the same general format of three backticks followed by curly parentheses and a lower case r inside the parentheses. Often people mistake these backticks for single quotes but that won't work. If you have set your code chunk correctly, using backticks, the background color will change!

</div>


<br>
  
5. Inline coding is: <div class='webex-radiogroup' id='radio_JGEXHYWERD'><label><input type="radio" autocomplete="off" name="radio_JGEXHYWERD" value=""></input> <span>where you nicely organise your code in a line</span></label><label><input type="radio" autocomplete="off" name="radio_JGEXHYWERD" value=""></input> <span>where you make sure all the code is nicely indented from the side</span></label><label><input type="radio" autocomplete="off" name="radio_JGEXHYWERD" value=""></input> <span>an exuberant way of exclaiming you have written good code!</span></label><label><input type="radio" autocomplete="off" name="radio_JGEXHYWERD" value="answer"></input> <span>an approach of intergrating code and text in a sentence outside of a code chunk</span></label></div>



<div class='webex-solution'><button>Explain This Answers</button>

Inline coding is an incredibly useful approach for merging text and code in a sentence outside of a code chunk. It can be really useful for when you want to add values from your code directly into your text. Copying and pasting can create errors easily so better to code it when you can!

</div>


## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                         |definition                                                                                                                                                       |
|:----------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|[chunk](https://psyteachr.github.io/glossary/c.html#chunk){class="glossary" target="_blank"}                                 |A section of code in an R Markdown file                                                                                                                          |
|[html](https://psyteachr.github.io/glossary/h.html#html){class="glossary" target="_blank"}                                   |Hyper-Text Markup Language: A system for semantically tagging structure and information on web pages.                                                            |
|[knit](https://psyteachr.github.io/glossary/k.html#knit){class="glossary" target="_blank"}                                   |To create an HTML, PDF, or Word document from an R Markdown (Rmd) document                                                                                       |
|[r markdown](https://psyteachr.github.io/glossary/r.html#r-markdown){class="glossary" target="_blank"}                       |The R-specific version of markdown: a way to specify formatting, such as headers, paragraphs, lists, bolding, and links, as well as code blocks and inline code. |
|[reproducible research](https://psyteachr.github.io/glossary/r.html#reproducible-research){class="glossary" target="_blank"} |Research that documents all of the steps between raw data and results in a way that can be verified.                                                             |
|[working directory](https://psyteachr.github.io/glossary/w.html#working-directory){class="glossary" target="_blank"}         |The filepath where R is currently loading files from and saving files to.                                                                                        |





**End of Chapter**

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!


<!--chapter:end:02-intro-to-r.Rmd-->

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

1. When loading in a .csv file, which function should you use? <div class='webex-radiogroup' id='radio_XZQLYRVGYR'><label><input type="radio" autocomplete="off" name="radio_XZQLYRVGYR" value="answer"></input> <span>read_csv()</span></label><label><input type="radio" autocomplete="off" name="radio_XZQLYRVGYR" value=""></input> <span>read.csv()</span></label><label><input type="radio" autocomplete="off" name="radio_XZQLYRVGYR" value=""></input> <span>select()</span></label><label><input type="radio" autocomplete="off" name="radio_XZQLYRVGYR" value=""></input> <span>library()</span></label></div>



<div class='webex-solution'><button>Explain this answer</button>

Remember, in this course we use `read_csv()` and it is important that you use this function otherwise you may find that the data does not work as expected.

</div>
 

2. The function `inner_join()` takes the arguments `x`, `y`, `by`. What does `by` do? <div class='webex-radiogroup' id='radio_LXCPYGPYQU'><label><input type="radio" autocomplete="off" name="radio_LXCPYGPYQU" value=""></input> <span>Specifies the first object to join</span></label><label><input type="radio" autocomplete="off" name="radio_LXCPYGPYQU" value=""></input> <span>Specifies the second object to join</span></label><label><input type="radio" autocomplete="off" name="radio_LXCPYGPYQU" value="answer"></input> <span>Specifies the column to join by that both objects have in common</span></label></div>



<div class='webex-solution'><button>Explain this answer</button>

Remember, functions have arguments and the arguments all do something slightly different. In the `inner_join()` the `by` argument says which columns to join by. If you want to join by more than one column you need to put both columns inside the `c()` function.

</div>
 

3. What does the function `select()` do? <div class='webex-radiogroup' id='radio_GXQQGQEFPZ'><label><input type="radio" autocomplete="off" name="radio_GXQQGQEFPZ" value=""></input> <span>Keeps only the observations you specify</span></label><label><input type="radio" autocomplete="off" name="radio_GXQQGQEFPZ" value="answer"></input> <span>Keeps only the columns you specify</span></label><label><input type="radio" autocomplete="off" name="radio_GXQQGQEFPZ" value=""></input> <span>Keeps only the objects you specify</span></label></div>



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

<!--chapter:end:03-loading-data.Rmd-->

# Data wrangling 1

So far we having been starting to get our head around data and storing them in <a class='glossary' target='_blank' title='A word that identifies and stores the value of some data for later use.' href='https://psyteachr.github.io/glossary/o#object'>objects</a> but as you will learn, data comes in lots of different formats. One of the most common formats is that of a <a class='glossary' target='_blank' title='Data in a rectangular table format, where each row has an entry for each column.' href='https://psyteachr.github.io/glossary/t#tabular-data'>two-dimensional table</a> (the two dimensions being rows and columns).  Usually, each row stands for a separate <a class='glossary' target='_blank' title='A word that identifies and stores the value of some data for later use.' href='https://psyteachr.github.io/glossary/o#object'>object</a> (e.g. a subject), and each column stands for a different variable (e.g. a response, category, or group). A key benefit of tabular data is that it allows you to store different <a class='glossary' target='_blank' title='The kind of data represented by an object.' href='https://psyteachr.github.io/glossary/d#data-type'>types of data</a>, e.g. numerical measurements, alphanumeric labels, categorical descriptors, etc, all in one place.

One of the core skills you will learn when working with data is <a class='glossary' target='_blank' title='The process of preparing data for visualisation and statistical analysis.' href='https://psyteachr.github.io/glossary/d#data-wrangling'>data wrangling</a>. This means completing tasks such as determining <a class='glossary' target='_blank' title='A data point that is extremely distant from most of the other data points' href='https://psyteachr.github.io/glossary/o#outlier'>outliers</a>, clearing up erroneous values, changing the structure of tables, merging information stored in separate tables, reducing the data down to a subset of observations, and producing data summaries. It may surprise you to learn that researchers actually spend far more of time cleaning and preparing their data than they spend actually analysing it. Some have estimated that up to 80% of time spent on data analysis involves such data preparation tasks [@dasu2003]!

When you ask people about data wrangling, many people seem to operate under the assumption that the only approach is the painstaking and time-consuming cutting and pasting of data within a proprietary spreadsheet programs like Excel. Indeed, many may waste days, weeks, and even months manually transforming their data through the laborious cutting, copying, and pasting of data. Wrangling your data manually, by hand, however is not only a terrible use of your time, but it is error-prone and not <a class='glossary' target='_blank' title='Research that documents all of the steps between raw data and results in a way that can be verified.' href='https://psyteachr.github.io/glossary/r#reproducible-research'>reproducible</a>. Additionally, in this day and age where we can easily collect massive datasets online, it is just not conceivable to organise, clean, and prepare this data by hand, and so the alternative and reproducible approach you have begun to learn is highly beneficial. 

In short, being able to perform some key data wrangling skills will allow you the opportunity to thrive, not only as a psychologist but in any of the numerous roles that require handling data. You see the truth is that although every dataset presents unique challenges, there are some systematic principles you should follow that will make your analyses easier, less error-prone, more efficient, and more reproducible.Putting that another way, the data changes but the skills stay the same!

So now let's get into learning some new skills. In this lesson you will see how data wrangling skills will allow you to efficiently get answers to nearly any question you might want to ask about your data. By learning how to properly make your computer do the hard and boring work for you, you can focus on the bigger issues.

## Tidyverse

In the first chapter we introduced a <a class='glossary' target='_blank' title='A group of R functions.' href='https://psyteachr.github.io/glossary/p#package'>package</a> called `tidyverse` and it is going to be at the core of a lot of the data skills you develop. The `tidyverse` [https://www.tidyverse.org/](https://www.tidyverse.org/){target="_blank"} [@tidyverse] is actually a collection of packages developed by a team led by the world-famous data scientist Hadley Wickham. Those core packages contained within `tidyverse` are  `dplyr`, `tidyr`, `readr`, `purrr`,  `ggplot2`, and `tibble`, and  within these six core packages you will have access to <a class='glossary' target='_blank' title='A named section of code that can be reused.' href='https://psyteachr.github.io/glossary/f#function'>functions</a> that will pretty much cover everything you need in order to be able to wrangle and visualise your data.. Again, don't worry about trying to remember all the different packages and what they all do, that will come with practice. The main thing to note however is that previously when you typed `library(tidyverse)` into your code, you will have seen that it loads in all of these packages in one go. You will learn how to use a whole host of functions from the `tidyverse` as we progress, but in this chapter we are going to focus on functions from the `dplyr` package, mainly for data wrangling, and `ggplot2` for visualisation (i.e. creating images and figures). 

Looking at the `dplyr` package specifically, it contains six very important functions based on common English verbs to help readability of the code. These six verbs are often referred to as the Wickham Six "one-table" dplyr verbs as they perform actions on a single table of data. Those six functions are:

|Function|Description|
|:------:|:----------|
|`select()`| Include or exclude certain variables (columns)|
|`filter()`| Include or exclude certain observations (rows)|
|`mutate()`| Create new variables (columns)|
|`arrange()`| Change the order of observations (rows)|
|`group_by()`| Organize the observations (rows) into groups|
|`summarise()`| Create summary variables for groups of observations|

Just looking at the names gives you some idea of what the functions do. For example, `select()`, which we saw previously, selects columns! But don't be fooled, although the operations of these functions may seem very simplistic, it’s amazing what you can accomplish when you string them together. Hadley Wickham, in fact, has claimed that 90% of data analysis can be reduced to the operations described by these six functions. You are going to use the functions but we will introduce them today just to show what they can do.

## Intro to the `babynames` database

To demonstrate the power of the six `dplyr` verbs we will use them to work with data from the `babynames` package. The babynames dataset has historical information about the births of babies in the U.S. from 1880 to the present day and is a nice understandable dataset that will allow us to us just focus on getting to know the functions across a series of activities, beginning now!

### Activity 1: Set-up {#dw1-a1}

Complete the following series of steps. If you are unsure, try consulting the previous two chapters, keeping in mind that this is something we have done before!

1. Open RStudio and set the working directory to your chapter folder. Ensure the environment is clear.
    i. If you are working on the Rserver, avoid a number of issues by restarting the session - top menu: **`Session >> Restart R`** 
2. Open a new R Markdown document and save it in your working directory. Call the file "DataWrangling1.Rmd".   
3. If you are working **on your own computer**, install the package `babynames` using the `install.packages()` function - you will need quotation marks around the package name. **Remember, never install packages if you are working on a university computer or on the Rserver**. 
4. Delete the default R Markdown default text (i.e. everything from line 12 down) and insert a new code <a class='glossary' target='_blank' title='A section of code in an R Markdown file' href='https://psyteachr.github.io/glossary/c#chunk'>code chunk</a> that loads the packages `babynames` and `tidyverse` using `library()` function and run this code chunk. 
    i. Note that the order of packages is deliberate!


```r
library(babynames)
library(tidyverse)
```

<div class="info">
<p><strong>On the order of libraries</strong></p>
<p>In the first chapter you will recall we mentioned the issue of conflicts - the situation where two packages loaded into the library have functions with the same name but different approaches or jobs. The default approach that R takes in this situation is to "mask" the function from the library that was loaded in first. That means that it will use the function from the library loaded in most recently. As <code>tidyverse</code> contains the functions that you will use most of the time, the safest approach is to always load in the <code>tidyverse</code> last, regardless of the other packages you are loading in. In truth, as with everything in life, there is an additional complication involved that sometimes arises but for now taking the approach of running <code>library(tidyverse)</code> last is going to save a lot of issues.</p>
</div>

### Activity 2: Look at the data {#dw1-a2}

Great! Now that we have our packages loaded in let's look at our data. The package `babynames` is a bit unique in that it contains an object of the same name, `babynames`, that contains all the data about, well, baby names, and we can look at that object to get a sense of our data.

* Have a look at your data by typing the word `babynames` into your <a class='glossary' target='_blank' title='The pane in RStudio where you can type in commands and view output messages.' href='https://psyteachr.github.io/glossary/c#console'>console</a> window and running it.


```r
babynames
```

You should see something like the following output:

<div class="kable-table">

| year|sex |name      |    n|      prop|
|----:|:---|:---------|----:|---------:|
| 1880|F   |Mary      | 7065| 0.0723836|
| 1880|F   |Anna      | 2604| 0.0266790|
| 1880|F   |Emma      | 2003| 0.0205215|
| 1880|F   |Elizabeth | 1939| 0.0198658|
| 1880|F   |Minnie    | 1746| 0.0178884|
| 1880|F   |Margaret  | 1578| 0.0161672|

</div>

The first line tells us "# A tibble: 1924665 x 5". What this means is that the object we are looking at is actually a <a class='glossary' target='_blank' title='A container for tabular data with some different properties to a data frame' href='https://psyteachr.github.io/glossary/t#tibble'>tibble</a>, a type of two dimensional table with some unique properties, and we have data across 1924665 variables (columns) with 1924665 million observations (rows). Yes, this dataset contains over 1.9 **million** observations. Interested in analyzing these data by hand? No thanks!  

Looking at the column names you start to get a sense of what the data is. The variables (columns) are as follows:

|variable|type             |description
|--------|-----------------|--------------------------------------------|
|  year  |double (numeric) |year of birth|
|  sex 	|character 	      |recorded sex of baby (F = female, M = male)|
|  name 	|character 	      |forename given to baby|
|  n 	  |integer 	        |number of babies given that name|
|  prop 	|double (numeric) |	proportion of all babies of that sex|

As such, each row represents data about births for a given name and sex in a given year. For example, the first row of the data tells us that in the year 1880, there were 7065 baby girls (F) born in the U.S.A who were given the name Mary, and this accounted for 7.238359% of all baby girls that year.

### Activity 3: Your first plot {#dw1-a3}

Brilliant! Now we know what our data looks like in terms of the table - or really the `tibble` - let's show you a quick code to help visualise some of this data.

* In a new code chunk in your R Markdwon file, type the code below and run it. 


```r
dat <- babynames %>% 
  filter(name %in% c("Emily",
                     "Kathleen",
                     "Alexandra",
                     "Beverly"), sex=="F")

ggplot(data = dat,
       aes(x = year,
           y = prop, 
           colour = name))+
  geom_line()  
```

And you should see this output:

<div class="figure" style="text-align: center">
<img src="04-wrangling-1_files/figure-html/babynames-plot-real-1.png" alt="Proportion of four baby names from 1880 to 2014" width="100%" />
<p class="caption">(\#fig:babynames-plot-real)Proportion of four baby names from 1880 to 2014</p>
</div>

Now we know that the code right now will not make much sense to you but don't worry about that as we don't expect you to fully understand the code just yet. The point is really to show you how much you can accomplish with very little code. The code creates a figure (Figure \@ref(fig:babynames-plot-real)) showing the popularity of four girl baby names - Alexandra, Beverly, Emily, and Kathleen - from 1880 to 2014. Popularity here is expressed in proportion (y-axis) in different years (x-axis). As you will come to learn, `ggplot()` is the main visualisation function, and `geom_line()` creates a linegraph.

* Now change the names in your code chunk to some female names you like and run the code to see how the Figure changes. 
* Now change the names in your code chunk to some male names and change the sex from “F” to “M”. Run the code and see what happens. Post the photos of your new plots on the Teams channel.
* Now change the code to what you want to display and post an image of your favorite figure that you have created on the TEAMS channel and get some praise from the TEAM! 


<div class='webex-solution'><button>But I want to display male AND female names!</button>


This is more complicated than you might first imagine so only read on if you're feeling confident. If you remove the filter for `sex` when creating `dat` and then run the plot code again, it will make a very messy looking plot (try it). This is because for most names there will be two data points because although the numbers might be small for gendered names, there is usually always at least one baby of the non-dominant name gender that has been assigned that name.

You can get around this by adding an additional line of code that produces separate plots by sex. See here: 


```r
dat2 <- babynames %>% 
  filter(name %in% c("Emily","Kathleen","Alexandra","Beverly"))

ggplot(data = dat2,aes(x = year,y = prop, colour=name))+
  geom_line() +
  facet_wrap(~sex, scales = "free_y", nrow = 2)
```

<div class="figure" style="text-align: center">
<img src="04-wrangling-1_files/figure-html/chpt4-hid1-1.png" alt="Plots by sex with different scales" width="100%" />
<p class="caption">(\#fig:chpt4-hid1)Plots by sex with different scales</p>
</div>

The `facet_wrap()` function is one that can split up figures based on a given variable - in this case `sex`, meaning give me a plot for all the different sex categories we have. The `scales` argument tells the code that it can use different scales on the y-axis for each plot - when there's a large difference between the two scales this is helpful to allow you to see the data in both sets (run this code and then remove the scales argument and run it again to see the difference) although it does run the risk of people misinterpreting the data if the difference between the scales isn't made clear.

On the other hand, if the scales for your two groups are fairly similar, it's better to keep the same scales to aid comparison. This time we will filter the dataset for gender neutral names where it might make more sense to have them on the same scale - again try it with and without the scales argument to see what happens


```r
dat3 <- babynames %>% 
  filter(name %in% c("Sam","Alex","Jordan","Drew"))

ggplot(data = dat3,aes(x = year,y = prop, colour=name))+
  geom_line() +
  facet_wrap(~sex, nrow = 2)
```

<div class="figure" style="text-align: center">
<img src="04-wrangling-1_files/figure-html/chpt4-show1-1.png" alt="Plots by sex with the same scale" width="100%" />
<p class="caption">(\#fig:chpt4-show1)Plots by sex with the same scale</p>
</div>

</div>



As a side point, because in most countries assigned sex at birth is binary, there is no data on intersex, trans or non-binary names. In lieu of that, here’s the [Wikipedia page](https://en.wikipedia.org/wiki/Unisex_name){target="_blank"} about gender-neutral names and naming laws around the world which will hopefully make you question why we ascribe someone’s entire gender identity to a bunch of sounds and letters we use to label them.

## Six functions for wrangling the `babynames`

Ok so now we have a fairly code understanding of the babynames, let's use it to learn a bit more about the six functions from `dplyr` that make up a lot of data wrangling!

### Activity 4: Selecting variables of interest  with `select()` {#dw1-a4}

Often data has a lot of variables we don't need and it can be easier to focus on just the data we do need. In `babynames` there are two numeric measurements of name popularity - `prop`, the proportion of all babies with each name, is probably more useful than `n`, the total number of babies with that name, because `prop` takes into account that different numbers of babies are born in different years. 

Now as we saw previously, if we wanted to create a dataset that only includes certain variables, we can use the `select()` function from the `dplyr` package. 

* In a new code chunk, type and run the below code to select only the columns `year`, `sex`, `name` and `prop` and store it as a `tibble` in the object named `babynames_reduced`.
    * the first argument `.data` is the object we want to select variables from, in this case `babynames`
    * the additional arguments are the names of the variables you want to **keep**!


```r
babynames_reduced1 <- select(.data = babynames,
                            year, 
                            sex, 
                            name, 
                            prop)
```

Alternatively, you can also state which variables you don't want to keep! This is really handy if you want to keep a lot of columns and only get rid of maybe one or two. 

* Type and run in the below code in a new code chunk.
    * Here, rather than stating you want to keep `year`, `sex`, `name` and `prop`, we can say drop (i.e. get rid of) the column `n` using the minus sign `-` before the variable name.


```r
babynames_reduced2 <- select(.data = babynames, 
                             -n)
```

**Note** that `select()` does not change the original tibble, `babynames`, but makes a new object that stores a new tibble with the specified columns, i.e. `babynames_reduced1` and `babynames_reduced2`. You will see the new objects in your environment pane. If you don't save the new tibbles to an object, they won't be saved. For example, the below code does the same as the previous code but is not saved as the output of the function is not assigned (using the <a class='glossary' target='_blank' title='The symbol <-, which functions like = and assigns the value on the right to the object on the left' href='https://psyteachr.github.io/glossary/a#assignment-operator'>assignment operator</a>, `<-`) to a new object. 


```r
select(.data = babynames, 
       -n)
```

### Activity 5: Arranging the data with `arrange()` {#dw1-a5}

Superb! We now know how to select variables. Another handy skill is being able to change the order of data in a tibble. The function `arrange()` will sort the rows in the table according to the columns you supply. 

* Type and run the below code in a new code chunk.
    * the first argument `.data` again says what object to work on
    * the second argument says what column to sort the data by - in this instance we are sorting by `name`
    * the default sorting order is ascending!


```r
sort_asc <- arrange(.data = babynames,
                    name)
```

If you look in `sort_asc` the data are now sorted in ascending alphabetical order by name. But what if you want the data in descending order? Here we can wrap the name of the variable in the `desc()` function. 

* Type and run the below code in a new code chunk. When you have run the code have a look at `sort_desc` and note that the data is now sorted by descending year!


```r
sort_desc <- arrange(babynames, 
                     desc(year)) 
```

Finally, you can also sort by more than one column and a combination of ascending and descending columns. Have a look at th below code and then answer the question below:


```r
arrange(babynames, 
        desc(year), 
        desc(sex), 
        desc(prop)) 
```

The above code will produce: <div class='webex-radiogroup' id='radio_NHTPIMHVSH'><label><input type="radio" autocomplete="off" name="radio_NHTPIMHVSH" value=""></input> <span>the data sorted by descending year and sex but ascending prop</span></label><label><input type="radio" autocomplete="off" name="radio_NHTPIMHVSH" value=""></input> <span>the data sorted by descending year and prop but ascending sex</span></label><label><input type="radio" autocomplete="off" name="radio_NHTPIMHVSH" value="answer"></input> <span>the data sorted by descending year, sex and prop</span></label><label><input type="radio" autocomplete="off" name="radio_NHTPIMHVSH" value=""></input> <span>the data sorted by ascending year, sex and prop</span></label></div>



<div class='webex-solution'><button>Explain this answer</button>

As all the columns stated are wrapped in the `desc()` function inside the `arrange()` function then all columns will be sorted in descending fashion, sorting the year first, then the sex, then the prop. Note however that the output is not being stored at all in a new object so you would not be able to work on the data later without saving it in an object first!

</div>



### Activity 6: Using `filter()` to choose observations {#dw1-a6}

We are doing well here! OK, so we have previously used `select()` to keep certain variables (i.e. columns). However, frequently you will also want to keep only certain observations (i.e. rows) - for example, only babies born after 1999, only Female babies (as above), or only babies named "Mary". You do this using the verb `filter()`. The `filter()` function is a bit more involved than the other verbs, and requires more detailed explanation, but this is because it is also extremely powerful. 

Here is an example of filter() function in action. Take a few minutes to think about what it might do. Perhaps even run it in a new code chunk and look at the ouput!


```r
filt1 <- filter(.data = babynames, 
                year > 2000)
```

Had a think about it? We are going to tell you now so maybe write down your answer before reading on!

OK, let's see if you are correct. The first part of the code tells the function to use the object `babynames`. The second argument, `year > 2000`, is what is known as a **Boolean expression**: an expression whose evaluation (or action) results in a value of either TRUE or FALSE. What `filter()` does here really is keep any observations (rows) for which the expression (`year > 2000` - which reads as "year greater than 2000") evaluates as TRUE, and excludes (removes) any row for which the expression evaluates to FALSE. So in effect, behind the scenes, `filter()` goes through the entire set of 1.9+ million observations, row by row, checking the value of year for each row, keeping it if the value is greater than 2000, and rejecting it if it is less than 2000. 

To see how a boolean expression works, consider the code below. First we create an object will all the values (let's pretend they are years) from 1996:2005.


```r
years <- 1996:2005
years
```

```
##  [1] 1996 1997 1998 1999 2000 2001 2002 2003 2004 2005
```

Now we run the same boolean expression fomr above across this set of values:


```r
years > 2000
```

```
##  [1] FALSE FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  TRUE  TRUE
```

You can see that the expression `years > 2000` returns a **logical vector** (a <a class='glossary' target='_blank' title='A type of data structure that collects values with the same data type, like T/F values, numbers, or strings.' href='https://psyteachr.github.io/glossary/v#vector'>vector</a> of TRUE and FALSE values), where each entry represents whether the expression (`year > 2000`) is TRUE or FALSE for that an entry in `years`. For the first five `years` (1996 to 2000) the answer is FALSE as they are less than 2000, and for the last five `years` (2001 to 2005) it is TRUE. Note that 2000 returns as FALSE because 2000 is not greater than 2000; it would instead be equivalent to 2000.

Here are the most commonly used Boolean expressions.

Operator	|Name	                 |is TRUE if and only if
----------|----------------------|---------------------------------
A < B 	  |less than 	           |A is less than B
A <= B 	  |less than or equal    |A is less than or equal to B
A > B 	  |greater than 	       |A is greater than B
A >= B 	  |greater than or equal |A is greater than or equal to B
A == B 	  |equivalence 	         |A exactly equals B
A != B 	  |not equal 	           |A does not exactly equal B
A %in% B 	|in 	                 |A is an element of vector B

We will run through a few of these just to introduce them so you get the idea. We would suggest typing each one in a new code chunk and running them and looking at the output to get an idea of what it does. 

First example is if you want only those observations for a specific name (e.g., Mary), you use the equivalence operator `==`. Note that you use double equal signs, not a single equal sign.


```r
only_Marys <- filter(babynames, 
                     name == "Mary")
```

Alternatively, if you wanted all the names except Mary, you use the 'not equals' operator which is a single equals sign preceeded by an exclamation mark:


```r
no_Marys <- filter(babynames, 
                   name != "Mary") 
```

Next, what if you wanted names from a defined set - e.g., names of British queens? Just like we did previously, you can use the `%in%` approach shown here.


```r
queens <- filter(babynames, 
                 name %in% c("Mary",
                             "Elizabeth",
                             "Victoria"))
```

This gives you data for the names in the vector on the right hand side of `%in%`. Note that the names are all held together in the `c()` which we have seen before, and each name is surrounded by quotation marks and seperated by a comma.

Next, a bit like when we got rid of all Marys, you can always invert an expression to get its opposite - that is what the exclamation mark tends to do. So, for instance, if you instead wanted to get rid of all Marys, Elizabeths, and Victorias you would use the following:


```r
no_queens <- filter(babynames, 
                    !(name %in% c("Mary",
                                  "Elizabeth",
                                  "Victoria")))
```

Ok so that is a brief intro to filters but it is worth keeping in mind that you can include as many expressions as you like as additional arguments to `filter()` and it will only pull out the rows for which all of the expressions evaluate to TRUE. For instance, `filter(babynames, year > 2000, prop > .01)` will keep only the rows (observations) where the year is greater than 2000  and that represent greater than 1% of the names for a given sex; any observation where either expression is false will be excluded. This ability to string together criteria makes `filter()` a very powerful member of the Wickham Six. Referring back to this section will help with a lot of the answers to problems you face when wrangling data!

### Activity 7: Creating new variables with `mutate()` {#dw1-a7}

Doing really well! Only a little more to go we promise! OK so we have really learnt a lot about changing the data we have but sometimes we need to create a new variable that doesn’t exist in our dataset. For instance, we might want to figure out what decade a particular year belongs to in out babynames data and add that to our data! To create new variables, we use the function `mutate()`. 

* Type and run the below code in a new code chunk.
    * Here, you are mutating a new column onto the data and storing it in the object `baby_decades`
    * the first argument is the original data, `babynames`
    * the second argument is the name of the new column `decade` followed by what you want in that column - the decade.
    * we are creating the decades using the code `floor(year/10)*10. This seems complicated but it says take the year and divide by 10, then get rid of the decimal places, and then multiply by 10. So for example, 1945/10 = 194.5, and if you get rid of the decimal places that becomes 194, and multiply it by 10 gives you 1940s!.


```r
baby_decades <- mutate(.data = babynames,
                  decade = floor(year/10) *10)
baby_decades
```

The start of the data will look something like this with the new column called `decade` mutated on:

<div class="kable-table">

| year|sex |name      |    n|      prop| decade|
|----:|:---|:---------|----:|---------:|------:|
| 1880|F   |Mary      | 7065| 0.0723836|   1880|
| 1880|F   |Anna      | 2604| 0.0266790|   1880|
| 1880|F   |Emma      | 2003| 0.0205215|   1880|
| 1880|F   |Elizabeth | 1939| 0.0198658|   1880|
| 1880|F   |Minnie    | 1746| 0.0178884|   1880|
| 1880|F   |Margaret  | 1578| 0.0161672|   1880|

</div>


But mutates can be much simpler like this example here. Have a look at the code and then answer the question below:


```r
baby_where <- mutate(.data = babynames,
                  country = "USA")
```

What will be stored in the object `baby_where`? <div class='webex-radiogroup' id='radio_JGMTHEPYKG'><label><input type="radio" autocomplete="off" name="radio_JGMTHEPYKG" value=""></input> <span>a tibble with one column called country that contains the decade people were born</span></label><label><input type="radio" autocomplete="off" name="radio_JGMTHEPYKG" value="answer"></input> <span>a tibble with all the original data and a new column called country stating USA</span></label><label><input type="radio" autocomplete="off" name="radio_JGMTHEPYKG" value=""></input> <span>a tibble with all the original data and a new column stating usa</span></label><label><input type="radio" autocomplete="off" name="radio_JGMTHEPYKG" value=""></input> <span>a tibble with all the original data arranged by the country USA</span></label></div>



<div class='webex-solution'><button>Explain this Answer</button>

This code will create a new object storing a tibble that has all the original data and a new column called country that states USA for each row. The `mutate()` adds to what is already there unless you add a `select()` or `filter()` to remove columns or rows. Note that one of the answers is wrong because it states usa in lowercase but the code states it in uppercase, i.e. USA. Remember to be specific.

</div>



### Activity 8: Grouping and summarising {#dw1-a8}

Brilliant! You are learning so much about changing data and just one more important step to go. The goal of wrangling in quantitative analysis is to summarise your data somehow! Perhaps you want to calculate the mean or median, or a sum total of your data. You can perform all of these operations using the function `summarise()`.

First, let's use the object `dat` from above that just has the data for the four girls names, Alexandra, Beverly, Emily, and Kathleen. Type and run this code in a new code chunk if `dat` does not already exist in your environment pane:


```r
dat <- babynames %>% 
  filter(name %in% c("Emily",
                     "Kathleen",
                     "Alexandra",
                     "Beverly"), sex == "F")
```

Now to start off, we're going to calculate the total number of babies across all years that were given one of these four names.

* Type and run the below code in a new code chunk
    * `summarise()` is the function we use to create summaries of the data
    * as per usual the first argument is the object we want to use, in this case `dat`
    * the second argument is the name of the summary column, in this case `total`, and the summary value we want to create, in this case the sum, using `sum()`, of all the values in `n`.


```r
dat_sum <- summarise(.data = dat,
                     total = sum(n))
```

A **top tip** when coding is to get in the habit of translating your code into full sentences to make it easier to figure out what's happening. You can read the above code as "run the function `summarise()` using the data in the object `dat` to create a new variable named `total` that is the result of adding up all the numbers in the column `n` and store it in `dat_sum`". If you look in `dat_sum` you will see the below output:



Here we see we have a total of 2161374 babies with those four names in our dataset! We will learn more summary functions as we go along, but `summarise()` becomes even more powerful when combined with the final `dplyr` function, `group_by()`. Quite often, you will want to produce your summary statistics broken down by groups, for examples, the scores of participants in different conditions, or the reading time for native and non-native speakers and that is what `group_by()` helps us do.

There are two ways you can use `group_by()`. First, you can create a new, grouped object as such. Here we are saying use the `group_by()` function to group the data in `dat` based on the categories in the variable `name`.

* Type and run this code in a new code chunk.


```r
group_dat <- group_by(.data = dat,
                      name) 
```

If you look at this object in the viewer, it won't look any different to the original `dat`, however, the underlying structure has changed - you can see this by typing group_dat in the console window and running it. It says the number of groups in the secpnd line of the output - "# Groups:   name [4]" 

However, let's run the above summarise code again, but now using the new `group_dat` object and look at the output.

* Type and run the below code in a new code chunk


```r
group_sum <- summarise(.data = group_dat, 
                       total = sum(n)) 
```

`summarise()` has performed exactly the same operation as before - adding up the total number in the column `n` - but this time it has done is separately for each group, which in this case was the variable `name` and gives an output that looks like this:

<div class="kable-table">

|name      |  total|
|:---------|------:|
|Alexandra | 231364|
|Beverly   | 376914|
|Emily     | 841491|
|Kathleen  | 711605|

</div>

<div class="info">
<p>If you get what looks like an error that says <code>summarise() ungrouping output (override with .groups argument)</code>don't worry, this isn't an error it's just R telling you what it's done to the groups that you have created and will become more obvious with more examples in later chapters.</p>
</div>

And two more final examples to show that you can request multiple summary calculations to be performed in the same function. For example, the following code calculates the mean and median number of babies given each name every year.


```r
sum_multi <- summarise(group_dat,
                       mean_year = mean(n),
                       median_year = median(n))
```

And you can also add multiple grouping variables. For example, the following code groups `baby_decades` by `sex` and `decade` and then calculates the summary statistics to give us the mean and median number of male and female babies in each decade.


```r
group_decades <- group_by(baby_decades, 
                          sex, 
                          decade)

sum_decades <- summarise(group_decades,
                         mean_year = mean(n),
                         median_year = median(n))
```

And again if you look at `sum_decades`, the first few lines would look something like this:

<div class="kable-table">

|sex | decade| mean_year| median_year|
|:---|------:|---------:|-----------:|
|F   |   1880|  110.5702|          13|
|F   |   1890|  128.1841|          13|
|F   |   1900|  131.3290|          12|
|F   |   1910|  187.0628|          12|
|F   |   1920|  210.5457|          12|
|F   |   1930|  214.1987|          12|

</div>

Excellent! We have now had a run through of all of the Wickham six functions that allow us to arrange, select, filter, mutate, group by and summarise our data!

## Introducing Pipes {#dw1-a9}

The final activity for this chapter essentially repeats what we've already covered but in a slightly different way. In the previous activities, you created new objects with new variables or groupings and then you called `summarise()` on those new objects in separate lines of code. As a result, you had multiple objects in your environment pane and you need to make sure that you keep track of the different names. 

Instead, you can use <a class='glossary' target='_blank' title='A way to order your code in a more readable format using the symbol %>%' href='https://psyteachr.github.io/glossary/p#pipe'>pipes</a>. Pipes are written as `%>%` and can be read as "and then". Pipes allow you to string together 'sentences' of code into 'paragraphs' so that you don't need to create intermediary objects. Really, this is something that is easier to show than tell.

The below code does very similar to all the code we wrote above but it only creates one object.


```r
pipe_summary <- babynames %>%
  mutate(decade = floor(year/10) *10) %>%
  filter(name %in% c("Emily",
                     "Kathleen",
                     "Alexandra",
                     "Beverly"), sex=="F") %>%
  group_by(name, 
           decade) %>%
  summarise(mean_decade = mean(n))
```

```
## `summarise()` has grouped output by 'name'. You can override using the `.groups` argument.
```

Again, just to note, you may see a warning when you run the above code regarding groups in the - this is similar to the previous time we saw the message and it is just letting you know what the output is grouped by. Nothing to worry about it basically. And if we then, as is good practice, look at the output from the above code, the first few lines would gives us:

<div class="kable-table">

|name      | decade| mean_decade|
|:---------|------:|-----------:|
|Alexandra |   1890|    6.500000|
|Alexandra |   1900|    8.285714|
|Alexandra |   1910|   32.700000|
|Alexandra |   1920|   37.000000|
|Alexandra |   1930|   44.400000|
|Alexandra |   1940|  117.100000|

</div>

Now just to explain a little more, the reason that this function, the `%>%`, is called a pipe is because it 'pipes' the data through to the next function. When you wrote the code previously, the first argument of each function was the dataset you wanted to work on. When you use pipes it will automatically take the data from the previous line of code so you don't need to specify it again.

<div class="info">
<p><strong>Read your pipe like a paragraph</strong></p>
<p>When learning to code it can be a useful practice to read your code 'out loud' in full sentences to help you understand what it is doing. You can read the code above as "starting with <code>babynames</code>, create a new variable called <code>decade</code> AND THEN keep only the names Emily, Kathleen, Alexandra and Beverly and that belong to female babies, AND THEN group the dataset by name and decade AND THEN calculate the mean number of babies with each name per decade." Try doing this each time you write a new bit of code and you should find the code becomes much easier to follow</p>
</div>

Some people find pipes a bit tricky to understand from a conceptual point of view, however, it's well worth learning to use them as when your code starts getting longer they are much more efficient and mean you have to write less code which is always a good thing! 

## Finished! {#dw1-fin}

Brilliant! That has been a lot of information but hopefully it has started to give you a sense of some of the approaches to data wrangling and the main functions we will use as we get deeper into the book! 

## Test yourself {#ld-test}

### Knowledge Questions

1. Which of the following is not one of the Wickham Six functions? <div class='webex-radiogroup' id='radio_UMSBOLUVIM'><label><input type="radio" autocomplete="off" name="radio_UMSBOLUVIM" value="answer"></input> <span>melt()</span></label><label><input type="radio" autocomplete="off" name="radio_UMSBOLUVIM" value=""></input> <span>arrange()</span></label><label><input type="radio" autocomplete="off" name="radio_UMSBOLUVIM" value=""></input> <span>mutate()</span></label><label><input type="radio" autocomplete="off" name="radio_UMSBOLUVIM" value=""></input> <span>filter()</span></label></div>


2. Which of the following functions would I use if I wanted to keep only certain columns? <div class='webex-radiogroup' id='radio_HLUHTZVQJU'><label><input type="radio" autocomplete="off" name="radio_HLUHTZVQJU" value="answer"></input> <span>select()</span></label><label><input type="radio" autocomplete="off" name="radio_HLUHTZVQJU" value=""></input> <span>arrange()</span></label><label><input type="radio" autocomplete="off" name="radio_HLUHTZVQJU" value=""></input> <span>mutate()</span></label><label><input type="radio" autocomplete="off" name="radio_HLUHTZVQJU" value=""></input> <span>filter()</span></label></div>


3. Which of the following functions would I use if I wanted to keep only certain rows? <div class='webex-radiogroup' id='radio_MAOSPRUCXS'><label><input type="radio" autocomplete="off" name="radio_MAOSPRUCXS" value=""></input> <span>select()</span></label><label><input type="radio" autocomplete="off" name="radio_MAOSPRUCXS" value=""></input> <span>arrange()</span></label><label><input type="radio" autocomplete="off" name="radio_MAOSPRUCXS" value=""></input> <span>mutate()</span></label><label><input type="radio" autocomplete="off" name="radio_MAOSPRUCXS" value="answer"></input> <span>filter()</span></label></div>


4. Which of the following functions would I use if I wanted to add a new column of information? <div class='webex-radiogroup' id='radio_MOXNGDQGEZ'><label><input type="radio" autocomplete="off" name="radio_MOXNGDQGEZ" value=""></input> <span>select()</span></label><label><input type="radio" autocomplete="off" name="radio_MOXNGDQGEZ" value=""></input> <span>arrange()</span></label><label><input type="radio" autocomplete="off" name="radio_MOXNGDQGEZ" value="answer"></input> <span>mutate()</span></label><label><input type="radio" autocomplete="off" name="radio_MOXNGDQGEZ" value=""></input> <span>filter()</span></label></div>


5. Which boolean expression would I add to a `filter()` function to keep only Male babies in the original `babynames` data? <div class='webex-radiogroup' id='radio_GQPEJJRSXS'><label><input type="radio" autocomplete="off" name="radio_GQPEJJRSXS" value=""></input> <span>sex == F</span></label><label><input type="radio" autocomplete="off" name="radio_GQPEJJRSXS" value="answer"></input> <span>sex == M</span></label><label><input type="radio" autocomplete="off" name="radio_GQPEJJRSXS" value=""></input> <span>sex < F</span></label><label><input type="radio" autocomplete="off" name="radio_GQPEJJRSXS" value=""></input> <span>Sex == M</span></label></div>



<div class='webex-solution'><button>Explain these Answers</button>


1. `melt()` is not a function in the Wickham six functions. It is actually a function but not one we tend to use.
2. `select()` is the function for keeping and removing columns.
3. `filter()` is the function for keeping and removing rows.
4. `mutate()` is the function for adding new columns.
5.  Assuming the original data has not been changed, `"sex == M"` would work and not `"Sex == M"` as there is no column called Sex with an uppercase S. Remember to be exact.

</div>


### Debugging exercises {#dw1-debugex}

1. Restart the R session (**`Session >> Restart R`**). Make sure that the working directory is set to the right folder and then run the below code in your console window:


```r
babynames
```

This will produce the error:

```
Error: object 'babynames' not found
```

Once you figure out how to fix this error, make a note of it.


<div class='webex-solution'><button>Solution</button>

This is an indication that you have not loaded the `babynames` package into the library using the `library()` function

</div>

<br>

2. Restart the R session (**`Session >> Restart R`**). Make sure that the working directory is set to the right folder and then run the below code in your console window:


```r
library(babynames)

dat <- summarise(.data = babynames, mean_n = mean(n))
```

This will produce the error:

```
Error in summarise(.data = babynames, mean_n = mean(n)) : 
  could not find function "summarise"
```

Once you figure out how to fix this error, make a note of it.


<div class='webex-solution'><button>Solution</button>

What the error is saying is that there is no function called `summarise()`. You know that function exists though. What you have not done is call load the function into the libary using `library(tidyverse)`

</div>

<br>

3. Restart the R session (**`Session >> Restart R`**). Make sure that the working directory is set to the right folder and then run the below code in your console window:


```r
library(babynames)
library(tidyverse)

dat <- summarise(.data = babynames mean_n = mean(n))
```

This will produce the error:

```
Error: unexpected symbol in "dat <- summarise(.data = babynames mean_n"

```
Once you figure out how to fix this error, make a note of it.


<div class='webex-solution'><button>Solution</button>

This is actually one of the most painful errors you can see as it doesn't really help you solve your issue because it is not quite clear what it means. **unexpected symbol** means effectively that the code is wrong and it is seeing something it did not think it would see. Again not that clear right? What we do when we see this is ask ourselves have we forgotten a comma somewhere or maybe a bracket or a quotation mark! Look for those issues and see if that helps. The error does show you that the error comes between `babynames` and `mean_n` it just isn't clear that that is what it means. The issue will be around the last word it mentions basically. The answer here is that there is a comma missing between the data and the arguement; between `babynames` and `mean_n`. The line should read: 


```r
library(babynames)
library(tidyverse)

dat <- summarise(.data = babynames, mean_n = mean(n))
```

Again an incredibly frustrating and time consuming error. Watch out for these. It is why partitioning the code on to new lines after a comma can be really help see errors as such:


```r
library(babynames)
library(tidyverse)

dat <- summarise(.data = babynames, 
                 mean_n = mean(n))
```

Such a dastardly error! Well done if you spotted it!!!


</div>

<br>

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                         |definition                                                                                                   |
|:----------------------------------------------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------|
|[assignment operator](https://psyteachr.github.io/glossary/a.html#assignment-operator){class="glossary" target="_blank"}     |The symbol <-, which functions like = and assigns the value on the right to the object on the left           |
|[chunk](https://psyteachr.github.io/glossary/c.html#chunk){class="glossary" target="_blank"}                                 |A section of code in an R Markdown file                                                                      |
|[console](https://psyteachr.github.io/glossary/c.html#console){class="glossary" target="_blank"}                             |The pane in RStudio where you can type in commands and view output messages.                                 |
|[data type](https://psyteachr.github.io/glossary/d.html#data-type){class="glossary" target="_blank"}                         |The kind of data represented by an object.                                                                   |
|[data wrangling](https://psyteachr.github.io/glossary/d.html#data-wrangling){class="glossary" target="_blank"}               |The process of preparing data for visualisation and statistical analysis.                                    |
|[function](https://psyteachr.github.io/glossary/f.html#function){class="glossary" target="_blank"}                           |A named section of code that can be reused.                                                                  |
|[object](https://psyteachr.github.io/glossary/o.html#object){class="glossary" target="_blank"}                               |A word that identifies and stores the value of some data for later use.                                      |
|[outlier](https://psyteachr.github.io/glossary/o.html#outlier){class="glossary" target="_blank"}                             |A data point that is extremely distant from most of the other data points                                    |
|[package](https://psyteachr.github.io/glossary/p.html#package){class="glossary" target="_blank"}                             |A group of R functions.                                                                                      |
|[pipe](https://psyteachr.github.io/glossary/p.html#pipe){class="glossary" target="_blank"}                                   |A way to order your code in a more readable format using the symbol %>%                                      |
|[reproducible research](https://psyteachr.github.io/glossary/r.html#reproducible-research){class="glossary" target="_blank"} |Research that documents all of the steps between raw data and results in a way that can be verified.         |
|[tabular data](https://psyteachr.github.io/glossary/t.html#tabular-data){class="glossary" target="_blank"}                   |Data in a rectangular table format, where each row has an entry for each column.                             |
|[tibble](https://psyteachr.github.io/glossary/t.html#tibble){class="glossary" target="_blank"}                               |A container for tabular data with some different properties to a data frame                                  |
|[vector](https://psyteachr.github.io/glossary/v.html#vector){class="glossary" target="_blank"}                               |A type of data structure that collects values with the same data type, like T/F values, numbers, or strings. |

**End of Chapter**

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!

<!--chapter:end:04-wrangling-1.Rmd-->

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



* What was the total number of hits made with the small paddle (50) and the blue colour background? <div class='webex-radiogroup' id='radio_UXEVEUZWKI'><label><input type="radio" autocomplete="off" name="radio_UXEVEUZWKI" value=""></input> <span>1059</span></label><label><input type="radio" autocomplete="off" name="radio_UXEVEUZWKI" value=""></input> <span>516</span></label><label><input type="radio" autocomplete="off" name="radio_UXEVEUZWKI" value=""></input> <span>1057</span></label><label><input type="radio" autocomplete="off" name="radio_UXEVEUZWKI" value="answer"></input> <span>527</span></label></div>




* To three decimal places, what was the mean number of hits made with the small paddle (50) and the blue colour background? <div class='webex-radiogroup' id='radio_FXCTAIVSMD'><label><input type="radio" autocomplete="off" name="radio_FXCTAIVSMD" value=""></input> <span>0.92</span></label><label><input type="radio" autocomplete="off" name="radio_FXCTAIVSMD" value="answer"></input> <span>0.459</span></label><label><input type="radio" autocomplete="off" name="radio_FXCTAIVSMD" value=""></input> <span>0.451</span></label><label><input type="radio" autocomplete="off" name="radio_FXCTAIVSMD" value=""></input> <span>0.922</span></label></div>


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

And finally today we just want to throw in a quick recap on <a class='glossary' target='_blank' title='A way to order your code in a more readable format using the symbol %>%' href='https://psyteachr.github.io/glossary/p#pipe'>pipes</a>. We have used pipes a little above but you might still not have got the hang of it so reading through this will help a little. Remember where pipes become most useful is when we **string a series of functions together**, rather than using them as separate steps and having to save the data each time under a new variable name and getting ourselves all confused. In non-piped code we have to create a new object each time, for example, `data`, `data_filtered`, `data_arranged`, `data_grouped`, `data_summarised` just to get to the final one we actually want.  This creates a lot of variables and tibbles in our environment and can make everything unclear, difficult to follow, and eventually slow down our computer. Piped code however uses one variable name, saving space in the environment, and is clear and easy to read. With pipes we skip unnecessary steps and avoid cluttering our environment.  

Here is an example of code that doesn't use pipes to find how many hits there were with the large paddle length and the red background:

* First we group the data accordingly, storing it in `pong_data_group`
* And then we summarise it, storing the answer in `total_hits`
* And finally we filter just the red, large paddle hits


```r
pong_data_group <- group_by(pong_data, 
                            BackgroundColor, 
                            PaddleLength)

pong_data_hits <- summarise(pong_data_group, 
                            total_hits = sum(HitOrMiss))

pong_data_hits_red_large <- filter(pong_data_hits, 
                                   BackgroundColor == "red", 
                                   PaddleLength == 250)
```

Alternatively we can make our code even more efficient, using less code, by stringing our sequence of functions together using pipes. This would look like:


```r
pong_data_hits_red_large <- pong_data %>% 
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

2. Which of the Wickham Six would you use to sort columns from smallest to largest: <div class='webex-radiogroup' id='radio_KYQCEXUGMH'><label><input type="radio" autocomplete="off" name="radio_KYQCEXUGMH" value=""></input> <span>select</span></label><label><input type="radio" autocomplete="off" name="radio_KYQCEXUGMH" value=""></input> <span>filter</span></label><label><input type="radio" autocomplete="off" name="radio_KYQCEXUGMH" value=""></input> <span>mutate</span></label><label><input type="radio" autocomplete="off" name="radio_KYQCEXUGMH" value="answer"></input> <span>arrange</span></label><label><input type="radio" autocomplete="off" name="radio_KYQCEXUGMH" value=""></input> <span>group_by</span></label><label><input type="radio" autocomplete="off" name="radio_KYQCEXUGMH" value=""></input> <span>summarise</span></label></div>

3. Which of the Wickham Six would you use to calculate the mean of a column: <div class='webex-radiogroup' id='radio_TOULIJFNNF'><label><input type="radio" autocomplete="off" name="radio_TOULIJFNNF" value=""></input> <span>select</span></label><label><input type="radio" autocomplete="off" name="radio_TOULIJFNNF" value=""></input> <span>filter</span></label><label><input type="radio" autocomplete="off" name="radio_TOULIJFNNF" value=""></input> <span>mutate</span></label><label><input type="radio" autocomplete="off" name="radio_TOULIJFNNF" value=""></input> <span>arrange</span></label><label><input type="radio" autocomplete="off" name="radio_TOULIJFNNF" value=""></input> <span>group_by</span></label><label><input type="radio" autocomplete="off" name="radio_TOULIJFNNF" value="answer"></input> <span>summarise</span></label></div>

4. Which of the Wickham Six would you use to remove certain observations - e.g. remove all males: <div class='webex-radiogroup' id='radio_VDCOMSLLYV'><label><input type="radio" autocomplete="off" name="radio_VDCOMSLLYV" value=""></input> <span>select</span></label><label><input type="radio" autocomplete="off" name="radio_VDCOMSLLYV" value="answer"></input> <span>filter</span></label><label><input type="radio" autocomplete="off" name="radio_VDCOMSLLYV" value=""></input> <span>mutate</span></label><label><input type="radio" autocomplete="off" name="radio_VDCOMSLLYV" value=""></input> <span>arrange</span></label><label><input type="radio" autocomplete="off" name="radio_VDCOMSLLYV" value=""></input> <span>group_by</span></label><label><input type="radio" autocomplete="off" name="radio_VDCOMSLLYV" value=""></input> <span>summarise</span></label></div>
 
5. What does this line of code say? `data %>% filter() %>% group_by() %>% summarise()`: <div class='webex-radiogroup' id='radio_QXDBOQWGUG'><label><input type="radio" autocomplete="off" name="radio_QXDBOQWGUG" value=""></input> <span>take the data and then group it and then filter it and then summarise it</span></label><label><input type="radio" autocomplete="off" name="radio_QXDBOQWGUG" value="answer"></input> <span>take the data and then filter it and then group it and then summarise it</span></label><label><input type="radio" autocomplete="off" name="radio_QXDBOQWGUG" value=""></input> <span>take the data and then summarise it and then filter it and then group it</span></label><label><input type="radio" autocomplete="off" name="radio_QXDBOQWGUG" value=""></input> <span>take the data and then group it and then summarise it and then filter it</span></label></div>
  

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
|[pipe](https://psyteachr.github.io/glossary/p.html#pipe){class="glossary" target="_blank"}                           |A way to order your code in a more readable format using the symbol %>%                                                    |
|[tibble](https://psyteachr.github.io/glossary/t.html#tibble){class="glossary" target="_blank"}                       |A container for tabular data with some different properties to a data frame                                                |
|[working directory](https://psyteachr.github.io/glossary/w.html#working-directory){class="glossary" target="_blank"} |The filepath where R is currently reading and writing files.                                                               |


That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!




<!--chapter:end:05-wrangling-2.Rmd-->

# Data Wrangling 3

In the last chapter, we looked at using one-table Wickham verbs to `filter`, `arrange`, `group_by`, `select`, `mutate` and `summarise` the pong data. We also learnt a little more about <a class='glossary' target='_blank' title='A way to order your code in a more readable format using the symbol %>%' href='https://psyteachr.github.io/glossary/p#pipe'>pipes</a> and we saw how to do some quick counting and some ungrouping. Be sure to try out those activities before moving on as we will start to add a few more functions to allow us a few more skills in <a class='glossary' target='_blank' title='The process of preparing data for visualisation and statistical analysis.' href='https://psyteachr.github.io/glossary/d#data-wrangling'>data wrangling</a>. 

Today, as a progression from working with one table/tibble, we will focus on working with data across two or more tibbles To do this we are going to add two more functions, to the skills we already know. Those are:

* `pivot_longer()` which allows us to **transform** a <a class='glossary' target='_blank' title='A container for tabular data with some different properties to a data frame' href='https://psyteachr.github.io/glossary/t#tibble'>tibble</a> from <a class='glossary' target='_blank' title='A data format where all of the observations about one subject are in the same row' href='https://psyteachr.github.io/glossary/w#wide'>wide</a> format to <a class='glossary' target='_blank' title='A data format where each observation is on a separate row' href='https://psyteachr.github.io/glossary/l#long'>long</a> format.
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

* The data in `responses` is in what format? <div class='webex-radiogroup' id='radio_MKCUGVOUVO'><label><input type="radio" autocomplete="off" name="radio_MKCUGVOUVO" value=""></input> <span>Tidy</span></label><label><input type="radio" autocomplete="off" name="radio_MKCUGVOUVO" value=""></input> <span>Long</span></label><label><input type="radio" autocomplete="off" name="radio_MKCUGVOUVO" value="answer"></input> <span>Wide</span></label></div>
 


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

* Complete the sentence, the higher the AQ score...<div class='webex-radiogroup' id='radio_PLSLUDXEUO'><label><input type="radio" autocomplete="off" name="radio_PLSLUDXEUO" value=""></input> <span>the less autistic-like traits displayed</span></label><label><input type="radio" autocomplete="off" name="radio_PLSLUDXEUO" value=""></input> <span>has no relation to autistic-like traits</span></label><label><input type="radio" autocomplete="off" name="radio_PLSLUDXEUO" value="answer"></input> <span>the more autistic-like traits displayed</span></label></div>
  

* Assuming that your code all worked, what was the AQ score (just the number) of Participant ID No. 87: <div class='webex-radiogroup' id='radio_RQLHYNEMVP'><label><input type="radio" autocomplete="off" name="radio_RQLHYNEMVP" value="answer"></input> <span>2</span></label><label><input type="radio" autocomplete="off" name="radio_RQLHYNEMVP" value=""></input> <span>3</span></label><label><input type="radio" autocomplete="off" name="radio_RQLHYNEMVP" value=""></input> <span>5</span></label><label><input type="radio" autocomplete="off" name="radio_RQLHYNEMVP" value=""></input> <span>6</span></label></div>
  

* Type in the box how many participants had an AQ score of 3 (again just the number): <input class='webex-solveme nospaces' size='10' data-answer='["13"]'/>  

* The cut-off for the AQ10 is usually said to be around 6 meaning that anyone with a score of more than 6 should be referred for diagnostic assessment. Based on this data, how many participants might be referred for further assessment? <div class='webex-radiogroup' id='radio_LUXCEJMWFD'><label><input type="radio" autocomplete="off" name="radio_LUXCEJMWFD" value=""></input> <span>2</span></label><label><input type="radio" autocomplete="off" name="radio_LUXCEJMWFD" value=""></input> <span>4</span></label><label><input type="radio" autocomplete="off" name="radio_LUXCEJMWFD" value="answer"></input> <span>6</span></label><label><input type="radio" autocomplete="off" name="radio_LUXCEJMWFD" value=""></input> <span>8</span></label></div>




<div class='webex-solution'><button>Explain these answers</button>


1. As mentioned, the higher the score on the AQ10 the more autistic-like traits a participant is said to show.

2. You could do this by code with `filter(aq_scores, Id == 87)`, which would give you a tibble of 1x2 showing the ID number and score. If you just wanted the score you could use `pull()` but we haven't shown you that yet: `filter(aq_scores, Id == 87) %>% pull(AQ)`. The answer is an AQ score of 2.

3. Same as above but changing the argument of the filter. `filter(aq_scores, AQ == 3) %>% count()`. The answer is 13. Remember you can do this by counting but the code makes it reproducible and accurate every time. You might make mistakes.

4. `filter(aq_scores, AQ > 6) %>% count()` or `filter(aq_scores, AQ >= 7) %>% count()`. The answer is 6.
        

</div>
  

**Recap on Wickham Verbs!**

Which function(s) would you use to approach each of the following problems?

* We have a dataset of 400 adults, but we want to remove anyone with an age of 50 years or more. To do this, we could use the <select class='webex-select'><option value='blank'></option><option value=''>mutate()</option><option value=''>select()</option><option value='answer'>filter()</option><option value=''>summarise()</option><option value=''>group_by()</option><option value=''>arrange()</option></select> function.

* We are interested in overall summary statistics for our data, such as the overall average and total number of observations. To do this, we could use the <select class='webex-select'><option value='blank'></option><option value='answer'>summarise()</option><option value=''>mutate()</option><option value=''>group_by()</option><option value=''>select()</option><option value=''>arrange()</option><option value=''>filter()</option></select> function.

* Our dataset has a column with the number of cats a person has, and a column with the number of dogs. We want to calculate a new column which contains the total number of pets each participant has. To do this, we could use the <select class='webex-select'><option value='blank'></option><option value=''>filter()</option><option value=''>summarise()</option><option value='answer'>mutate()</option><option value=''>group_by()</option><option value=''>arrange()</option><option value=''>select()</option></select> function.

* We want to calculate the average for each participant in our dataset. To do this we could use the <select class='webex-select'><option value='blank'></option><option value=''>filter() and select()</option><option value=''>group_by() and arrange()</option><option value=''>arrange() and mutate()</option><option value='answer'>group_by() and summarise()</option></select> functions.

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


|term                                                                                                           |definition                                                                        |
|:--------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------|
|[data wrangling](https://psyteachr.github.io/glossary/d.html#data-wrangling){class="glossary" target="_blank"} |The process of preparing data for visualisation and statistical analysis.         |
|[function](https://psyteachr.github.io/glossary/f.html#function){class="glossary" target="_blank"}             |A named section of code that can be reused.                                       |
|[inner join](https://psyteachr.github.io/glossary/i.html#inner-join){class="glossary" target="_blank"}         |A mutating join that returns all the rows that have a match in the other table.   |
|[long](https://psyteachr.github.io/glossary/l.html#long){class="glossary" target="_blank"}                     |A data format where each observation is on a separate row                         |
|[package](https://psyteachr.github.io/glossary/p.html#package){class="glossary" target="_blank"}               |A group of R functions.                                                           |
|[pipe](https://psyteachr.github.io/glossary/p.html#pipe){class="glossary" target="_blank"}                     |A way to order your code in a more readable format using the symbol %>%           |
|[tibble](https://psyteachr.github.io/glossary/t.html#tibble){class="glossary" target="_blank"}                 |A container for tabular data with some different properties to a data frame       |
|[tidy data](https://psyteachr.github.io/glossary/t.html#tidy-data){class="glossary" target="_blank"}           |A format for data that maps the meaning onto the structure.                       |
|[wide](https://psyteachr.github.io/glossary/w.html#wide){class="glossary" target="_blank"}                     |A data format where all of the observations about one subject are in the same row |


That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!



<!--chapter:end:06-wrangling-3.Rmd-->

# Intro to Data Visualisation

## Data visualisation

<a class='glossary' title='Data Visualisation is the skill of creating and interpreting plots and figures from data.'>Data Visualisation</a>. Being able to visualise our data, and relationships between our variables, is an incredibly useful and important skill. Before we do any statistical analyses or present any summary statistics, we should visualise our data as it is:

1. A quick and easy way to check our data make sense, and to identify any unusual trends.
2. A way to honestly present the features of our data to anyone who reads our research.
4. A means of checking that our data fits with the assumptions of our <a class='glossary' target='_blank' title='Statistics that describe an aspect of data (e.g., mean, median, mode, variance, range)' href='https://psyteachr.github.io/glossary/d#descriptive'>descriptive</a> and <a class='glossary' target='_blank' title='Statistics that allow you to make predictions about or comparisons between data (e.g., t-value, F-value, rho)' href='https://psyteachr.github.io/glossary/i#inferential'>inferential</a> tests and of the statistical analyses that we intend to use.

As Grolemund and Wickham tell us in [R for Data Science](http://r4ds.had.co.nz/introduction.html){target="_blank"}:

> Visualisation is a fundamentally human activity. A good visualisation will show you things that you did not expect, or raise new questions about the data. A good visualisation might also hint that you’re asking the wrong question, or you need to collect different data. Visualisations can surprise you, but don’t scale particularly well because they require a human to interpret them.

The main package we use for visualisation within the `tidyverse` umbrella is called **`ggplot2`** and the main starting function of all visualisations is `ggplot()`. The reason we say the "main starting function" is that `ggplot()` builds plots by combining layers (see, for example, Figure \@ref(fig:img-layers) from [@nordmann2021]) - i.e. one function creates the first layer, the basic plot area, and you add functions and arguments to add additional layers such as the data, the labels, the colors, etc. If you're used to making plots in other software this might seem a bit odd at first, however, it means that you can customise each layer separately in order to make very complex and beautiful figures with relative ease. You can get a sense of what is possible from ([this website](https://www.data-to-viz.com/) but we will start off slow and build as we go!

<div class="figure" style="text-align: center">
<img src="images/layers2.PNG" alt="Building a figure using the ggplot2 layers system as shown in Nordmann et al. (2021)" width="100%" />
<p class="caption">(\#fig:img-layers)Building a figure using the ggplot2 layers system as shown in Nordmann et al. (2021)</p>
</div>

## Setting up to Visaulise

We will use the same data files as in Chapter 2, Starting with Data, as we already know what the data contains so we can focus just on visualising it. 

#### Activity 1: Set-up {#introviz-a1}

This data contains happiness and depression scores:

* Download <a href="ahi-cesd.csv" download>`ahi-cesd.csv`</a> and <a href="participant-info.csv">`participant-info.csv`</a> into the folder on your computer for this chapter! 
    * Make sure that you have downloaded both .csv files above and saved them in your chapter folder. Remember not to change the file names at all and that `data.csv` is not the same as `data (1).csv`.
* Open RStudio and set the working directory to your chapter folder. Ensure the environment is clear.  
    * If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Open a new R Markdown document and save it in your working directory. Call the file "DataVisualisation1".    
* Delete the default R Markdown welcome text and insert a new code chunk. 
* Type and run the below code to load the `tidyverse` package and to load in the data files. 


```r
library(tidyverse) 

dat <- read_csv("ahi-cesd.csv")
pinfo <- read_csv("participant-info.csv")

all_dat <- inner_join(dat, 
                      pinfo, 
                      by= c("id", "intervention"))
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

You should have a good idea about what this code is doing but if not here is a brief summary:

1. It loads in the tidyverse
2. It reads both datafiles as tibbles into separate objects, `dat` and `pinfo`.
3. Joins the data together into one larger tibble and stores it in the object called `all_dat`
4. Select a number of columns to keep in our data and discards others.



## Dealing with Factors and Categories

Before we go any further we need to perform an additional step of data processing that we have glossed over up until this point. First, run the below code to look at the structure of the dataset:


```r
glimpse(summarydata)
```

```
## Rows: 992
## Columns: 8
## $ ahiTotal     <dbl> 32, 34, 34, 35, 36, 37, 38, 38, 38, 38, 39, 40, 41, 41, 4~
## $ cesdTotal    <dbl> 50, 49, 47, 41, 36, 35, 50, 55, 47, 39, 45, 47, 33, 27, 3~
## $ sex          <dbl> 1, 1, 1, 1, 1, 1, 2, 1, 2, 2, 1, 2, 1, 2, 2, 1, 1, 1, 1, ~
## $ age          <dbl> 46, 37, 37, 19, 40, 49, 42, 57, 41, 41, 52, 41, 52, 58, 5~
## $ educ         <dbl> 4, 3, 3, 2, 5, 4, 4, 4, 4, 4, 5, 4, 5, 5, 5, 4, 3, 4, 3, ~
## $ income       <dbl> 3, 2, 2, 1, 2, 1, 1, 2, 1, 1, 2, 1, 3, 2, 2, 3, 2, 2, 2, ~
## $ occasion     <dbl> 5, 2, 3, 0, 5, 0, 2, 2, 2, 4, 4, 0, 4, 0, 1, 4, 0, 5, 4, ~
## $ elapsed.days <dbl> 182.025139, 14.191806, 33.033831, 0.000000, 202.096887, 0~
```

You can see that all the variables are automatically considered as <a class='glossary' target='_blank' title='A data type representing a real decimal number or integer.' href='https://psyteachr.github.io/glossary/n#numeric'>numeric</a> (in this case <a class='glossary' target='_blank' title='A data type representing a real decimal number' href='https://psyteachr.github.io/glossary/d#double'>double</a> represented by `<dbl>`). This is going to be a problem because whilst the different categories within `sex`, `educ`, and `income` are represented by numbers, we don't want to treat them as such because they are categories, or what we call **factors**. So to get around this, we need to convert these variables into <a class='glossary' target='_blank' title='A data type where a specific set of values are stored with labels' href='https://psyteachr.github.io/glossary/f#factor-data-type'>factor data type</a>. Fortunately we already know a good function for this! We can use `mutate()` to do this by overriding the original variable with the same data but classified as a factor. 

### Activity 2: Factors {#introviz-a2}

* Type and run the below code to change the categories to factors.
    * You can read each line of the mutate as "overwrite the data that is in that column with the same values now considered factors and not doubles"
    * So for example, the 1s in `sex` change to categorical factors instead of numerical 1s.
    * Remember if you mutate a new column with the same name as the old one, it will overwrite the column.


```r
summarydata <- summarydata %>%
  mutate(sex = as.factor(sex),
         educ = as.factor(educ),
         income = as.factor(income))
```

This is a very imporant step to remember if, when you look at your data, some of your categories are represented as numbers and not factors. If you do not do this then you might end up with some really confused looking figures!

## Barplots

Ok great, we are now ready to do some visualising and some plotting. For our first example we will create a barplot of our data showing the number of male and female participants within our data. A <a class='glossary' title='A plot showing counts of categorical data where the height of each bar represents the count of that particular variable'>barplot</a> is a plot that shows counts of categorical data, or factors, where the height of each bar represents the count of that particular variable.

#### Activity 3: Bar plot {#introviz-a3}

Read through the following section and try the different code chunks. Following this, and changing parts of the code to see what happens, will help you to see how the layers build up.

**The first layer**

* The first line (or layer) sets up the base of the graph: the data to use and the aesthetics (what will go on the x and y axis, how the plot will be grouped).    
* `aes()` can take both an `x` and `y` argument, however, with a bar plot you are just asking R to count the number of data points in each group so you don't need to specify this. 


```r
ggplot(summarydata, aes(x = sex))
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/layer1-1.png" alt="First ggplot() layer sets the axes" width="100%" />
<p class="caption">(\#fig:layer1)First ggplot() layer sets the axes</p>
</div>

* The next layer adds a **geom** or a shape, in this case we use `geom_bar()` as we want to draw a bar plot. 
    * Note that we are adding layers, using a `+` between layers. This is a very important difference between pipes and visualisation. We will mention this again later but we add layers (`+`), we do not pipe them!


```r
ggplot(summarydata, aes(x = sex)) +
  geom_bar()
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-2-1.png" alt="Basic barplot with geom_bar() added" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-2)Basic barplot with geom_bar() added</p>
</div>

* Adding `fill` to the first layer will separate the data into each level of the grouping variable and give it a different colour. In this case, there is a different coloured bar for each level of `sex`.


```r
ggplot(summarydata, aes(x = sex, fill = sex)) +
  geom_bar()
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-3-1.png" alt="Barplot with colour" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-3)Barplot with colour</p>
</div>

* As you can see, adding the `fill()` has also produced a plot legend to the right of the graph. When you have multiple grouping variables you want legends to know which groups each color or part of the plot is referring to, but in this case it is redundant because it doesn't tell us anything that the axes labels don't already. We can get rid of it by adding `show.legend = FALSE` to the `geom_bar()` code.


```r
ggplot(summarydata, aes(x = sex, fill = sex)) +
  geom_bar(show.legend = FALSE)
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-4-1.png" alt="Barplot without legend" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-4)Barplot without legend</p>
</div>

Excellent. So far so good! But we might want to tidy up our plot to make it look a bit nicer. First we can edit the axis labels to be more informative. The most common functions you will use are:

* `scale_x_continuous()` for adjusting the x-axis for a continuous variable
* `scale_y_continuous()` for adjusting the y-axis for a continuous variable
* `scale_x_discrete()` for adjusting the x-axis for a discrete/categorical variable
* `scale_y_discrete()` for adjusting the y-axis for a discrete/categorical variable

And in those functions the two most common arguments you will use are:

* `name` which controls the name of each axis - i.e. what is the overall variable called for example (e.g. Groups)
* `labels` which controls the names of the break points on the axis - i.e. what are the conditions within a variable called for example (e.g. dogs and cats)

There are lots more ways you can customise your axes but we will stick with these for now. 

* Type out and and run the below code to change the axes labels and change the numeric sex codes (the 1s and 2s) into words (Female and Male).
    * **Note:** We are using `scale_x_discrete()` because our x-axis is a discrete variable in this data (Female or Male), and we are using `scale_y_continuous()` because our y-axis is continuous in this data (a count of how many people there are)
    * **Note:** The `labels` arguments must be written in the correct order of your data. Here it will make the 1's Female and the 2's Male, but if you flipped the order of Male and Female, it would make the 1's Male and the 2's Female. Remember the code does what you tell it to do so always check your output!


```r
ggplot(summarydata, aes(x = sex, fill = sex)) +
  geom_bar(show.legend = FALSE) +
  scale_x_discrete(name = "Participant Sex", 
                   labels = c("Female", 
                              "Male")) +
  scale_y_continuous(name = "Number of participants")
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-5-1.png" alt="Barplot with axis labels" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-5)Barplot with axis labels</p>
</div>

Now the default colors are ok but you might want to adjust the colours and the visual style of the plot. `ggplot2` comes built a number of different built-in themes as they are called. 

* Type the code below into a new code chunk and run it.
    * Here we use `theme_minimal()` but try changing it to others and see what happens. You start by typing `theme_` into the code chunk, instead of `theme_minimal()`, and trying the options that come up on auto-complete. Examples include, `theme_bw()`, `theme_classic()`, `theme_light()`, etc. 


```r
ggplot(summarydata, aes(x = sex, fill = sex)) +
  geom_bar(show.legend = FALSE) +
  scale_x_discrete(name = "Participant Sex", 
                   labels = c("Female", 
                              "Male")) +
  scale_y_continuous(name = "Number of participants") +
  theme_minimal()
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-6-1.png" alt="Barplot with minimal theme" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-6)Barplot with minimal theme</p>
</div>

Ok but what about the color of the individual bars of the plot? Well, there are various options to adjust the colours but a good way to be inclusive is to use a colour-blind friendly palette that can also be read if printed in black-and-white. To do this, we can add on the function `scale_fill_viridis_d()`. This function has 5 colour options, A, B, C, D, and E. We like `option = "E"` but you can play around with them and choose the one you prefer.

* Type and run the below code into a new code chunk. Try changing the option to either A, B, C or D and see which one you like!


```r
ggplot(summarydata, aes(x = sex, fill = sex)) +
  geom_bar(show.legend = FALSE) +
  scale_x_discrete(name = "Participant Sex", 
                   labels = c("Female", 
                              "Male")) +
  scale_y_continuous(name = "Number of participants") +
  theme_minimal() +
  scale_fill_viridis_d(option = "E")
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-7-1.png" alt="Barplot with colour-blind friendly colour scheme" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-7)Barplot with colour-blind friendly colour scheme</p>
</div>

Finally, you can also adjust the transparency of the bars by adding `alpha` to `geom_bar()`. Play around with the value and see what value you prefer.


```r
ggplot(summarydata, aes(x = sex, fill = sex)) +
  geom_bar(show.legend = FALSE, 
           alpha = .8) +
  scale_x_discrete(name = "Participant Sex", 
                   labels = c("Female", 
                              "Male")) +
  scale_y_continuous(name = "Number of participants") +
  theme_minimal() +
  scale_fill_viridis_d(option = "E")
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-8-1.png" alt="Barplot with adjusted alpha" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-8)Barplot with adjusted alpha</p>
</div>

So as you can see, with just a few lines of code you can create a very effective figure. The **top tip** we have is to remember a figure is a series of layers, so write the code like that. Avoid trying to write the whole figure from a blank code chunk. Instead, create the first code chunk, run it, add the next layer, run it, add the next layer, run it, etc., etc. That will make it much easier for you to follow what your code is doing and to debug any issues.

<div class="info">
<p><strong>We add layers, we don't pipe them</strong></p>
<p>We just wanted to remind you of a key point here - that you add layers through <code>+</code> and you do not pipe layers with <code>%&gt;%</code>. If you try to pip on a layer you will probably see an error that looks something like this:</p>
<p><strong>Error: <code>mapping</code> must be created by <code>aes()</code>. Did you use %&gt;% instead of +?</strong></p>
<p>Do watch out for that as it is a very common errore we see when people are first starting to learn to visualise through ggplot2</p>
</div>

## The Violin-boxplot

There are numerous different styles of visualisations and figures that you can create. They all start with the format of `ggplot(data, aes(x, y)) + geom_...` and will learn more as you get deeper into the book or you can look at the cheatsheets in the help menus: top menu - **`Help >> Cheat Sheets >> Data Visualisation with ggplot2`**. For instance, `geom_point()` for scatterplots, `geom_histogram()` for histograms, and `geom_line()` for lineplots. But we want to show you a type of figure that is becoming a lot more common in the field due to the quality of information if tells you about your data - the violin-boxplot.

#### Activity 4: Violin-boxplot {#introviz-a4}

The violin boxplot is actually a merge of a <a class='glossary' title='A plot showing the probability density of data with a smoothed kernel function and look like a rotated and mirrored histogram'>violin plot</a> and a <a class='glossary' title='A plot summarising distributions using five key values: the median, the upper and lower interquartile values, and the max and min value not considered and outlier. The length of the box represents the interquartile range.'>boxplot</a>. The violin-boxplot is just the boxplot laid over the top of the violin plot - to give additional information. As part of our final activities today we will create a violin-boxplot, hopefully now you will be able to see how similar it is in structure to the bar chart code. In fact, there are only three differences:

1. We have added a `y` argument to the first layer because we wanted to represent two variables, not just a count.
2. `geom_violin()` has an additional argument `trim`. 
3. `geom_boxplot()` has an additional argument `width`. Try adjusting the value of this and see what happens. 

* Type and run the below code in a new code chunk and see what it produces.
    * Try setting the `trim` argument in `geom_violin()` to `TRUE` and seeing what happens. 
    * Try adjusting the value of the `width` argument within `geom_boxplot()` and seeing what happens.


```r
ggplot(summarydata, aes(x = income, 
                        y = ahiTotal, 
                        fill = income)) +
  geom_violin(trim = FALSE, 
              show.legend = FALSE, 
              alpha = .4) +
  geom_boxplot(width = .2, 
               show.legend = FALSE, 
               alpha = .7)+
  scale_x_discrete(name = "Income",
                   labels = c("Below Average", 
                              "Average", 
                              "Above Average")) +
  scale_y_continuous(name = "Authentic Happiness Inventory Score")+
  theme_minimal() +
  scale_fill_viridis_d()
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-10-1.png" alt="Violin-boxplot" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-10)Violin-boxplot</p>
</div>

## Layer order

As we said above, one key thing to note about `ggplot2` is the use of layers. Whilst we have built layers up step-by-step in this chapter, they are independent and you could remove any of them except for the first layer. Additionally, although they are independent, the order you put them in does matter as we will show you now.

#### Activity 5: Layers part 2 {#introviz-a5}

* Type and run this code into a new code chunk and look at the output.


```r
ggplot(summarydata, aes(x = income, y = ahiTotal)) +
  geom_violin() +
  geom_boxplot()
```

* Now type and run this code into a new code chunk and compare the output to the output of the code above. Do you see the difference?


```r
ggplot(summarydata, aes(x = income, y = ahiTotal)) +
  geom_boxplot() +
  geom_violin()
```

If you compare the two figures, shown here below for ease, the first puts the boxplots on top of the violins whereas the second puts the violins on top of the boxplots. It does that because each plot is a different layer that it literally puts on top of what is already there. Again a great reason to always look at your output and not just run code blindly as you don't always get what you think you are doing!

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/patch-layers-1.png" alt="Showing the impact of changing the order of layers. Figure A shows the boxplots on top of the violin plots. Figure B shows the violins on top of the boxplots. The codes are the same but the order of the geoms is different." width="100%" />
<p class="caption">(\#fig:patch-layers)Showing the impact of changing the order of layers. Figure A shows the boxplots on top of the violin plots. Figure B shows the violins on top of the boxplots. The codes are the same but the order of the geoms is different.</p>
</div>

## Saving your Figures

Great work today! We just want to show you one last very helpful function on how to save and export your figures. Much like your favourite jumper, there is no point having it if nobody gets to see it! It is so useful to be able to save a copy of your plots as an image file so that you can use them in a presentation or report. One approach we can use is the function `ggsave()`.

#### Activity 6: Saving plots {#introviz-a6}

There are two ways you can use `ggsave()`. If you don't tell `ggsave()` which plot you want to save, by default it will save **the last plot you created**. To demonstrate this let's run the code from Activity 5 again to produce the nice violin-boxplot:


```r
ggplot(summarydata, aes(x = income, 
                        y = ahiTotal, 
                        fill = income)) +
  geom_violin(trim = FALSE, 
              show.legend = FALSE, 
              alpha = .4) +
  geom_boxplot(width = .2, 
               show.legend = FALSE, 
               alpha = .7)+
  scale_x_discrete(name = "Income",
                   labels = c("Below Average", 
                              "Average", 
                              "Above Average")) +
  scale_y_continuous(name = "Authentic Happiness Inventory Score")+
  theme_minimal() +
  scale_fill_viridis_d()
```

<div class="figure" style="text-align: center">
<img src="07-data-viz_files/figure-html/unnamed-chunk-13-1.png" alt="Violin-boxplot2" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-13)Violin-boxplot2</p>
</div>

Now that we've got the plot we want to save as our last produced plot, all that `ggsave()` requires is for you to tell it what file name it should save the plot to and the type of image file you want to create (the below example uses .png but you could also use e.g., .jpeg and other image types).

* Type and run the below code into a new code chunk and then check your chapter folder. If you have performed this correctly then you see the saved image file.


```r
ggsave("violin-boxplot.png")
```

Note that the image tends to save at a default size, or the size that the image is displayed in your viewer, but you can change this manually if you think that the dimensions of the plot are not correct or if you need a particular size or file type.

* Type and run the below code to overwrite the image file with new dimensions.
    * try different dimensions and units to see the difference. You might want to create violin-boxplot-v1, ...-v2, ...-v3, and compare them. Remeber you can use `?ggsave()` in the console window to bring up the help on this function.


```r
ggsave("violin-boxplot.png", 
       width = 10, 
       height = 8, 
       units = "in")
```

Alternatively, the second way of using `ggsave()` is to save your plot as an object, just like we have done with tibbles, and then tell `ggsave()` which object you want to save. 

* Type and run the below code and then check your folder for the image file. Resize the plot if you think it needs it.
    * The below code saves the plot from Activity 5 into an object named `viobox` and then saves it to an image file "violin-boxplot-stored.png". 
    * **Note:** We do not add on `ggsave()`. Instead it is a separate line of code and we tell it which object to save. So, do not do `+ ggsave()`   


```r
viobox <- summarydata %>%
  ggplot(aes(x = income,
             y = ahiTotal,
             fill = income)) +
  geom_violin(trim = FALSE, 
              show.legend = FALSE, 
              alpha = .4) +
  geom_boxplot(width = .2, 
               show.legend = FALSE, 
               alpha = .7)+
  scale_x_discrete(name = "Income",
                   labels = c("Below Average", 
                              "Average", 
                              "Above Average")) +
  scale_y_continuous(name = "Authentic Happiness Inventory Score")+
  theme_minimal() +
  scale_fill_viridis_d()


ggsave("violin-boxplot-stored.png", plot = viobox)
```

Finall, note that when you save a plot to an object, you will not see the plot displayed anywhere. To get the figure to display you need to type the object name in the console (i.e., `viobox`). The benefit of saving figures this way is that if you are making lots of plots, you can't accidentally save the wrong one because you are explicitly specifying which plot to save rather than just saving the last one.

## Finished! {#introviz-fin}

Well done! `ggplot` can be a bit difficult to get your head around at first, particularly if you've been used to making graphs a different way. But once it clicks, you'll be able to make informative and professional visualisations with ease, which, amongst other things, will make any report you write look more professional!

## Test Yourself

1. Which of these is the appropriate order of functions to create a boxplot? <div class='webex-radiogroup' id='radio_RLOGEUROLM'><label><input type="radio" autocomplete="off" name="radio_RLOGEUROLM" value=""></input> <span>geom_plot() + geom_boxplot()</span></label><label><input type="radio" autocomplete="off" name="radio_RLOGEUROLM" value=""></input> <span>geom_boxplot() + ggplot()</span></label><label><input type="radio" autocomplete="off" name="radio_RLOGEUROLM" value="answer"></input> <span>ggplot() + geom_boxplot()</span></label><label><input type="radio" autocomplete="off" name="radio_RLOGEUROLM" value=""></input> <span>ggplot() %>% geom_boxplot()</span></label></div>


2. Would this line of code run, assuming all data and libraries had been loaded in and the data and column names were spelt correctly?


```r
ggplot(summarydata, aes(x = sex, fill = sex)) %>%
  geom_bar()
```

<div class='webex-radiogroup' id='radio_XXGCYKPLRE'><label><input type="radio" autocomplete="off" name="radio_XXGCYKPLRE" value=""></input> <span>Yes, as the code looks perfectly acceptable and no errors are visible</span></label><label><input type="radio" autocomplete="off" name="radio_XXGCYKPLRE" value="answer"></input> <span>No, because you have piped the geom_bar() instead of adding it</span></label></div>


3. Why would this line of code not create a barplot, assuming all data and libraries had been loaded in and the data and column names were spelt correctly?


```r
ggplot(summarydata, aes(x = sex, fill = sex)) +
  geom_barplot()
```

<div class='webex-radiogroup' id='radio_SBSXZKWREW'><label><input type="radio" autocomplete="off" name="radio_SBSXZKWREW" value=""></input> <span>because you have piped the barplot and not added it</span></label><label><input type="radio" autocomplete="off" name="radio_SBSXZKWREW" value="answer"></input> <span>because there is no geom_barplot() and it should be geom_bar()</span></label><label><input type="radio" autocomplete="off" name="radio_SBSXZKWREW" value=""></input> <span>because you have not included a y axis</span></label><label><input type="radio" autocomplete="off" name="radio_SBSXZKWREW" value=""></input> <span>because this would create a boxplot</span></label></div>


4. If I wanted a boxplot on top of a violin plot, what order of functions would I write? <div class='webex-radiogroup' id='radio_CPSVVRMNXZ'><label><input type="radio" autocomplete="off" name="radio_CPSVVRMNXZ" value="answer"></input> <span>ggplot() + geom_violin() + geom_boxplot()</span></label><label><input type="radio" autocomplete="off" name="radio_CPSVVRMNXZ" value=""></input> <span>ggplot() %>% geom_violin() %>% geom_boxplot()</span></label><label><input type="radio" autocomplete="off" name="radio_CPSVVRMNXZ" value=""></input> <span>ggplot() %>% geom_boxplot() %>% geom_violin()</span></label><label><input type="radio" autocomplete="off" name="radio_CPSVVRMNXZ" value=""></input> <span>ggplot() + geom_boxplot() + geom_violin()</span></label></div>



<div class='webex-solution'><button>Explain these answers</button>


`r unhide()`

1. `ggplot() + geom_boxplot()` would be the correct answer as the rest either use pipes, have the wrong order, or have the wrong functions.
2. The line of code would not run because it uses pipes instead of adding a layer
3. The line of code would not run because there is no `geom_barplot()` function and it should be `geom_bar()`
4. The correct order would be `ggplot() + geom_violin() + geom_boxplot()` as the others either use pipes, have the wrong order, or have the wrong functions.

</div>


## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                   |definition                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|[barplot](https://psyteachr.github.io/glossary/b.html#barplot){class="glossary" target="_blank"}                       |A plot showing counts of categorical data where the height of each bar represents the count of that particular variable                                                                                                       |
|[boxplot](https://psyteachr.github.io/glossary/b.html#boxplot){class="glossary" target="_blank"}                       |A plot summarising distributions using five key values: the median, the upper and lower interquartile values, and the max and min value not considered and outlier. The length of the box represents the interquartile range. |
|[data visualisation](https://psyteachr.github.io/glossary/d.html#data-visualisation){class="glossary" target="_blank"} |Data Visualisation is the skill of creating and interpreting plots and figures from data.                                                                                                                                     |
|[descriptive](https://psyteachr.github.io/glossary/d.html#descriptive){class="glossary" target="_blank"}               |Statistics that describe an aspect of data (e.g., mean, median, mode, variance, range)                                                                                                                                        |
|[double](https://psyteachr.github.io/glossary/d.html#double){class="glossary" target="_blank"}                         |A data type representing a real decimal number                                                                                                                                                                                |
|[factor data type](https://psyteachr.github.io/glossary/f.html#factor-data-type){class="glossary" target="_blank"}     |A data type where a specific set of values are stored with labels                                                                                                                                                             |
|[inferential](https://psyteachr.github.io/glossary/i.html#inferential){class="glossary" target="_blank"}               |Statistics that allow you to make predictions about or comparisons between data (e.g., t-value, F-value, rho)                                                                                                                 |
|[numeric](https://psyteachr.github.io/glossary/n.html#numeric){class="glossary" target="_blank"}                       |A data type representing a real decimal number or integer.                                                                                                                                                                    |
|[violin](https://psyteachr.github.io/glossary/v.html#violin){class="glossary" target="_blank"}                         |A plot showing the probability density of data with a smoothed kernel function and look like a rotated and mirrored histogram                                                                                                 |

**End of Chapter**

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!

<!--chapter:end:07-data-viz.Rmd-->

# Probability

In this chapter we are going to bring in more ideas around <a class='glossary' target='_blank' title='A number between 0 and 1 where 0 indicates impossibility of the event and 1 indicates certainty' href='https://psyteachr.github.io/glossary/p#probability'>probability</a>. This is more of a reading chapter - in that we ask you to read more than try - but there are a few activities to try along the way and to think about to make sure you are getting the idea. Probability is really important in helping us make inference from our <a class='glossary' target='_blank' title='A subset of the population that you wish to make an inference about through your test.' href='https://psyteachr.github.io/glossary/s#sample'>sample</a> to our <a class='glossary' target='_blank' title='All members of a group that we wish to generalise our findings to. E.g. all students taking Psychology at the University of Glasgow. We draw our testing sample from the population.' href='https://psyteachr.github.io/glossary/p#population'>population</a> and, before we go on to look at different <a class='glossary' target='_blank' title='Statistics that allow you to make predictions about or comparisons between data (e.g., t-value, F-value, rho)' href='https://psyteachr.github.io/glossary/i#inferential'>inferential</a> tests, and now that we have a good handle on data wrangling and visualisation, now would seem an ideal time to recap and introduce some key aspects about probability.

Don't worry if this chapter does not make complete sense. It may take a few reads or it may take reading once to get the gist and then coming back to the ideas when we try out a few datasets ourselves. The main key concept that you want to take away from this chapter, if you get nothing else from this chapter, is that you can establish the probability of obtaining a value on any <a class='glossary' target='_blank' title='A probability distribution is way to describe the shape of data.' href='https://psyteachr.github.io/glossary/d#distribution'>distribution</a>, and from that probability you can make an inference about how likely or unlikely you were to obtain that value. Try to keep that in mind as we go through the next few sections and you should be ok.

The first half of this chapter doesn't contain any coding, instead, we're going to recap some core statistical concepts. If you need any additional resources beyond what has been discussed in the lectures, you may find the below useful. These are not essential and you can skip them but again they may just add that little bit you need to help you understand the ideas behind probability.

* Read [Statistical thinking (Noba Project)](https://nobaproject.com/modules/statistical-thinking#content){target="_blank"}
* Watch [Normal Distribution - Explained Simply](https://www.youtube.com/watch?v=tDLcBrLzBos){target="_blank"} (10 mins) 
* Watch [Probability explained](https://www.youtube.com/watch?v=uzkc-qNVoOk&list=PLC58778F28211FA19){target="_blank"} (8 mins)
* Watch [Binomial distribution](https://www.youtube.com/watch?v=WWv0RUxDfbs){target="_blank"} (12 minutes)

## Introduction to probability? 

Probability (*p*) is the extent to which an event is likely to occur and is represented by a number between 0 and 1. For example, the probability of flipping a coin and it landing on 'heads' would be estimated at *p = .5*, i.e., there is a 50% chance of getting a head when you flip a coin. 

In fact, calculating the probability of any individual event occurring can be formulated as:

$$p = \frac{number \  of  \ ways \ the \ event \ could \  arise}{number \ of \ possible \ outcomes}$$
For example, what is the probability of randomly drawing your name out of a hat of 12 names where one name is definitely yours? Well, if there are 12 possible outcomes, and only 1 way for your name to arise, then it the above formula becomes:

$$p = \frac{1}{12} = 0.0833333$$

Meaning that the probability is 0.0833333. Or, if you wanted to write that as a percentage then it would be 8.3333333%, meaning that out of every 100 draws from the hat you would expect your name to come out about 8.3 times.  And if there had been four names in the hat and one was yours then it would be:

$$p = \frac{1}{4} = 0.25$$

And if it had been 24 names in the hat and one was yours then it would have been:

$$p = \frac{1}{24} = 0.0416667$$

So you can see that the probability of an event occurring changes with the number of possible outcomes. Makes sense really! The more possible outcomes, the less likely any specific one outcome is going to happen. So far so good!

#### Activity 1: Probability {#prob-a1}

Try to answer these questions below to check your understanding.

1. What would be the probability of selecting your name from a hat when there are ten names in the hat and your name is one of them? <select class='webex-select'><option value='blank'></option><option value=''>0.25</option><option value='answer'>0.1</option><option value=''>0.0416666666666667</option><option value=''>0.0833333333333333</option></select>
2. What would be the probability of selecting your name from a hat when there are 100 names in the hat and your name is not one of them? Be careful on this one! <select class='webex-select'><option value='blank'></option><option value='answer'>0</option><option value=''>0.1</option><option value=''>0.01</option><option value=''>0.1</option></select>

## Types of data

How you tackle probability also depends on the type of data/variables you are working with  (i.e. <a class='glossary' target='_blank' title='Data that can only take certain values, such as integers.' href='https://psyteachr.github.io/glossary/d#discrete'>discrete</a> or <a class='glossary' target='_blank' title='Data that can take on any values between other existing values.' href='https://psyteachr.github.io/glossary/c#continuous'>continuous</a>). This is also referred to as `Level of Measurements` and here we will recap on those different types of data.

**Discrete** data can only take <a class='glossary' target='_blank' title='A data type representing whole numbers.' href='https://psyteachr.github.io/glossary/i#integer'>integer</a> values (whole numbers). For example, the number of  participants in an experiment would be discrete - we can't have half a participant! Discrete variables can also be further broken down into <a class='glossary' target='_blank' title='Categorical variables that don&#39;t have an inherent order, such as types of animal.' href='https://psyteachr.github.io/glossary/n#nominal'>nominal</a> and <a class='glossary' target='_blank' title='Discrete variables that have an inherent order, such as level of education or dislike/like.' href='https://psyteachr.github.io/glossary/o#ordinal'>ordinal</a> variables.

* **Ordinal** data is a set of ordered categories; you know which is the top/best and which is the worst/lowest, but not the difference between categories. For example, you could ask participants to rate the attractiveness of different faces based on a 5-item <a class='glossary' target='_blank' title='A rating scale with a small number of discrete points in order' href='https://psyteachr.github.io/glossary/l#likert'>Likert</a> scale (very unattractive, unattractive, neutral, attractive, very attractive). You know that very attractive is better than attractive but we can't say for certain that the difference between neutral and attractive is the same size as the distance between very unattractive and unattractive.
* **Nominal** data is also based on a set of categories but the ordering doesn't matter (e.g. left or right handed). Nominal is sometimes simply referred to as `categorical` data. 

**Continuous** data on the other hand can take any value. For example, we can measure age on a continuous scale (e.g. we can have an age of 26.55 years), other examples include reaction time or the distance you travel to university every day. Continuous data can be broken down into <a class='glossary' title='data which comes in the form of a numerical value where the difference between points is standardised and meaningful'>Interval</a> or <a class='glossary' title='data which comes in the form of a numerical value where the difference between points is standardised and meaningful but has a meaningful zero'>Ratio</a> data. 

* **Interval** data is data which comes in the form of a numerical value where the difference between points is standardised and meaningful. For example temperature, the difference in temperature between 10-20 degrees is the same as the difference in temperature between 20-30 degrees. 
* **Ratio** data is very like interval but has a true zero point. With our interval temperature example above, we have been experiencing negative temperatures (-1,-2 degrees) in Glasgow but with ratio data you don't see negative values such as these i.e. you can't be -10 cm tall. 

#### Activity 2: Types of data {#prob-a2}

Try to answer these questions below to check your understanding. What types of data are the below measurements?

* Time taken to run a marathon (in seconds): <select class='webex-select'><option value='blank'></option><option value=''>interval</option><option value=''>categorical</option><option value='answer'>ratio</option><option value=''>ordinal</option></select>
* Finishing position in marathon (e.g. 1st, 2nd, 3rd): <select class='webex-select'><option value='blank'></option><option value=''>categorical</option><option value=''>ratio</option><option value=''>interval</option><option value='answer'>ordinal</option></select>
* Which Sesame Street character a runner was dressed as: <select class='webex-select'><option value='blank'></option><option value=''>interval</option><option value=''>ratio</option><option value=''>ordinal</option><option value='answer'>categorical</option></select>
* Temperature of a runner dressed in a cookie monster outfit (in degrees Celsius): <select class='webex-select'><option value='blank'></option><option value='answer'>interval</option><option value=''>ordinal</option><option value=''>ratio</option><option value=''>categorical</option></select>

## Probability distributions

OK great. So we know a bit more about probability and a bit more about data types. Next thing we need to think about are probability distributions! A probability distribution is the theoretical counterpart to the observed frequency distribution. A frequency distribution simply shows how many times a certain event actually occurred. A probability distribution says how many times it should have occurred. Say for example you run a test on how many times different flips of a coin produce either heads or tails. What you count yourself is the frequency distribution. What was expected, based on <a class='glossary' target='_blank' title='Generating data, as opposed to collecting data, from summary parameters such as the mean and standard deviation' href='https://psyteachr.github.io/glossary/s#simulation'>simulations</a> by mathematicians, is the probability distribution. Mathematicians have actually simulated a number of different probability distributions, and we know that different types of data will tend to naturally fall into a known distribution. From this, we can use these distributions to help us calculate the probability of an event without having to run it ourselves. To say that in another way, we can determine the probability of an event by running a test many many times ourselves, or we can use one of these simulated probability distributions which would save us a lot of time and effort. And that is what we are going to show you here.

The three distributions we will look at, to help us understand probability, are:

1. The <a class='glossary' target='_blank' title='A distribution where all numbers in the range have an equal probability of being sampled' href='https://psyteachr.github.io/glossary/u#uniform-distribution'>uniform distribution</a>
2. The <a class='glossary' target='_blank' title='The distribution of data where each observation can have one of two outcomes, like success/failure, yes/no or head/tails. ' href='https://psyteachr.github.io/glossary/b#binomial-distribution'>binomial distribution</a>
3. The <a class='glossary' target='_blank' title='A symmetric distribution of data where values near the centre are most probable.' href='https://psyteachr.github.io/glossary/n#normal-distribution'>normal distribution</a>

## The uniform distribution

The uniform distribution is when each possible outcome has an equal chance of occurring. Let's take the example from above, pulling your name out of a hat of 12 names. Each individual name has an equal chance of being drawn (p = .08). If we visualised this distribution, it would look like this distribution below - each outcome, in this case each name, has the same chance of occurring:

<div class="figure" style="text-align: center">
<img src="08-probability_files/figure-html/unnamed-chunk-1-1.png" alt="The Uniform distribution, where every outcome has an equal probability of occurring." width="100%" />
<p class="caption">(\#fig:unnamed-chunk-1)The Uniform distribution, where every outcome has an equal probability of occurring.</p>
</div>

The uniform distribution does not feature that regularly in Psychology, except perhaps in experiments where you are randomising which block people get first or when performing a <a class='glossary' title='An inferential test used to compare observed frequencies with expected frequencies in categorical conditions'>chi-square</a> test, but it helps us start to understand that each outcome has a probability in a distribution.

## The binomial distribution

The next distribution we want to look at is the binomial distribution. The binomial (bi = two, nominal = categories) distribution, is used for **discrete** data, and is a probability distribution which calculates probabilities of success for situations where there are two possible outcomes e.g., flipping a coin; your outcomes are either heads or tails! A binomial distribution models the probability of any number of successes being observed (e.g. was it a heads when you wanted heads), given the probability of a success and the number of observations (e.g. how many times did you get heads (a success) over ten coin flips (the observations)). It is probably worth pointing out that you as the researcher determine what is the success (heads or tails) but for ease here we will try to stick to heads. 

Let’s say we flip a coin 10 times. Assuming the coin is fair (probability of heads = .5), how many heads should we expect to get? The below figure shows the results of a simulation for 10,000 coin flips (if you'd like to do this simulation yourself, you can see the code by clicking "Show the code"). However, what this distribution means is that we can use what we know about our data and the binomial distribution to work out the probability of different outcomes. For example, instead of running a whole bunch of tests, we could use the distribution to answer the question of what is the probability of getting at least 3 heads if you flip a coin 10 times?.

<div class="figure" style="text-align: center">
<img src="08-probability_files/figure-html/unnamed-chunk-2-1.png" alt="Probability of no. of heads from 10 coin tosses" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-2)Probability of no. of heads from 10 coin tosses</p>
</div>


<div class='webex-solution'><button>Show the code</button>


**Note that you are not expected to understand this code right now**


```r
heads10000 <- replicate(n = 10000, 
                        expr = sample(0:1, 
                                      10, 
                                      TRUE) %>%
                          sum())

data10000 <- tibble(heads = heads10000) %>%
                group_by(heads) %>%     
                summarise(n = n(),
                          p=n/10000)

ggplot(data10000, aes(x = heads,y = p)) + 
  geom_bar(stat = "identity") + 
  labs(x = "Number of Heads", 
       y = "Probability of Heads in 10 flips (p)") +
  theme_bw() +
  scale_x_continuous(breaks = c(0,1,2,3,4,5,6,7,8,9,10))
```

</div>


Again, the binomial distribution is not hugely common in Psychology but we are really starting to see how we can ask questions about outcomes based on probability distributions as opposed to running tests ourselves. Let's then look at this in a distribution that is very common in psychology - the normal distribution

## The normal distribution

The **normal distribution**, reflects the probability of any value occurring for a *continuous* variable. Examples of continuous variables include height or age, where a single person can score anywhere along a continuum. For example, a person could be 21.5 years old and 176 cm tall.

The normal distribution looks like this:

<div class="figure" style="text-align: center">
<img src="./images/norm_dist_height.PNG" alt="Normal Distribution of height. $\mu$ = the mean (average), $\sigma$ = standard deviation" width="100%" height="100%" />
<p class="caption">(\#fig:unnamed-chunk-4)Normal Distribution of height. $\mu$ = the mean (average), $\sigma$ = standard deviation</p>
</div>

Something to note is that the normal distribution is symmetrical, meaning there is an equal probability of observations above and below the mean occurring. This means that, if the mean in the above plot of heights is 170 cm, we could expect the number of people who have a height of 160 cm to be the same as the number of people who have a height of 180 cm. A second thing to note is that as the distribution is symmetrical, the mean, median, and mode of the distribution are all equal and in the middle of the distribution and have the highest probability of occurring. As you move away from the middle of the distribution, the probability of those outcomes occurring starts to reduce. This plays an important role in analyses as we will come on to see in later chapters.

Now, however, in the same way that we could with the coin flips, we can then use what we know about our data and the normal distribution to estimate the probability of certain outcomes, such as what's the probability that someone would be taller than 190cm?

As with any probabilities, real-world data will come close to the normal distribution, but will (almost certainly) never match it exactly. As we collect more observations from data that we might expect to be normally distributed, our data will get increasingly closer to a normal distribution. As an example, here's a simulation of an experiment in which we collect heights from 5000 participants. As you can see, as we add more observations, our data starts to look more and more like the normal distribution in the previous figure.

<div class="figure" style="text-align: center">
<img src="./images/normal_dist.gif" alt="A simulation of an experiment collecting height data from 2000 participants" width="75%" height="75%" />
<p class="caption">(\#fig:unnamed-chunk-5)A simulation of an experiment collecting height data from 2000 participants</p>
</div>

#### Activity 3: Normal distribution {#prob-a3}

Complete the sentences to make sure that you are understanding the above.

* In a normal distribution, the mean, median, and mode <select class='webex-select'><option value='blank'></option><option value=''>are always different</option><option value=''>sum to zero</option><option value='answer'>are all equal</option></select>.
* In a normal distribution, the further away from the mean an observation is <select class='webex-select'><option value='blank'></option><option value=''>the higher its probability of occuring</option><option value='answer'>the lower its probability of occuring</option></select>.
* Whereas the binomial distribution is based on situations in which there are two possible outcomes, the normal distribution is based on situations in which the data <select class='webex-select'><option value='blank'></option><option value=''>has three possible values</option><option value='answer'>is a continuous variable</option><option value=''>is a categorical variable</option></select>.

#### Activity 4: Distribution test {#prob-a4}

Which distribution is likely to be associated with the following?

* Scores on an IQ test <select class='webex-select'><option value='blank'></option><option value=''>Uniform distribution</option><option value=''>Binomial distribution</option><option value='answer'>Normal distribution</option></select>
* Whether a country has won or lost the Eurovision song contest <select class='webex-select'><option value='blank'></option><option value=''>Uniform distribution</option><option value='answer'>Binomial distribution</option><option value=''>Normal distribution</option></select>
* Picking a spade card out of a normal pack of playing cards<select class='webex-select'><option value='blank'></option><option value='answer'>Uniform distribution</option><option value=''>Binomial distribution</option><option value=''>Normal distribution</option></select>

## Using the binomial distribution

Now, we're going to calculate probabilities based on the binomial distribution. In this chapter, for the first time we don't need to load the tidyverse. All of the functions we need are contained in Base R. If you want a refresher on the difference between Base R and packages, see Programming Basics.

#### Activity 5: Getting Set-Up {#prob-a5}

* Open a new R Markdown document, call it "Probability" and save it in the relevant chapter folder, remembering to delete the default text which we do not need.

We're going to use three Base R functions to work with the binomial distribution:

* `dbinom()` - the density function: gives you the probability of x successes given the number of trials and the probability of success on a single trial (e.g., what's the probability of flipping 8/10 heads with a fair coin?).
* `pbinom()` - the probability distribution function: gives you the cumulative probability of getting a number of successes below a certain cut-off point (e.g. probability of getting 0 to 5 heads out of 10 flips), given the size and the probability. This is known as the cumulative probability distribution function or the cumulative density function.
* `qbinom()` - the quantile function: is the opposite of `pbinom()` in that it gives you the x axis value for a given probability p, plus given the size and prob, that is if the probability of flipping a head is .5, how many heads would you expect to get with 10 flips?

So let's try these functions out to answer two questions:

1. What is the probability of getting exactly 5 heads on 10 flips?
2. What is the probability of getting at most 2 heads on 10 flips?

#### Activity 6: `dbinom()` {#prob-a6}

Let's start with question 1, what is the probability of getting exactly 5 heads on 10 flips? 

We want to predict the **probability** of getting 5 heads in 10 trials (coin flips) where the probability of success on each flip is 0.5 (it'll either be heads or tails so you have a 50/50 chance which we write as 0.5). We will use `dbinom()` to work this out: 

The `dbinom()` (density) function has three arguments:  

* `x`: the number of ‘heads’ we want to know the probability of. Either a single value, 3, or a series of values, 0:10. In this case we want to know about 5 heads, so we write 5.
* `size`: the number of trials (flips) we are simulating; in this case, 10 flips.
* `prob`: the probability of ‘heads’ on one trial. Here chance is 50-50 which as a probability we state as 0.5 or .5

Type and run the below code in a new code chunk:


```r
dbinom(x = 5, size = 10, prob = 0.5)
```

Looking at the outcome, answer the following questions:

* To two decimal places, what is the probability of getting 5 heads out of 10 coin flips? <input class='webex-solveme nospaces' size='4' data-answer='["0.25",".25"]'/>  
* What is this probability expressed in percent? <select class='webex-select'><option value='blank'></option><option value=''>0.25%</option><option value=''>2.5%</option><option value='answer'>25%</option></select>

#### Activity 7: `pbinom()` {#prob-a7}

OK, question 2. What is the probability of getting at most 2 heads on 10 flips? 

This time we use `pbinom()` as we want to know the **cumulative probability** of getting a maximum of 2 heads from 10 coin flips. So we have set a cut-off point of 2 but we still have a probability of getting a heads of 0.5.

* **Note:** `pbinom()` takes the arguments `size` and `prob` argument just like `dbinom()`. However, the first input argument is `q` rather than `x`. This is because in dbinom `x` is a fixed number, whereas `q` is all the possibilities **up to and including** a given number (e.g. 0, 1, 2). 

Type and run the below code in a new code chunk:


```r
pbinom(q = 2, size = 10, prob = 0.5)
```

Looking at the outcome, answer the following question:

* What is the probability of getting a maximum of 2 heads on 10 coin flips to 2 decimal places? <input class='webex-solveme nospaces' size='4' data-answer='["0.05",".05"]'/>  
* What is this probability expressed in percent? <select class='webex-select'><option value='blank'></option><option value=''>0.05%</option><option value=''>0.5%</option><option value='answer'>5%</option></select>

#### Activity 8: `pbinom()` 2 {#prob-a8}

Let's try one more scenario with a cut-off point to make sure you have understood this. What is the probability of getting 7 or more heads on 10 flips?

We can use the same function as in the previous example, however, there's an extra argument if we want to get the correct answer. Let's try running the code we used above first but change `q = 2` to `q = 7` to see what we get.


```r
pbinom(q = 7, size = 10, prob = .5) 
```

```
## [1] 0.9453125
```

This tells us that the probability is .95 or 95% - that doesn't seem right does it? It seems very high for getting 7 or more heads out of 10 coin flips! Why is that? Well, the default behaviour for `pbinom()` is to calculate the cumulative probability for the lower tail of the curve, i.e., if you specify `q = 2` it calculates the probability of all outcomes **up to and including** 2. We specified `q = 7` which means that we have calculated the probability of getting an outcome of 0, 1, 2, 3, 4, 5, 6, or 7 - shown here in the blue area in the below figure - which is obviously very high.

<div class="figure" style="text-align: center">
<img src="08-probability_files/figure-html/unnamed-chunk-6-1.png" alt="Lower and upper tails" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-6)Lower and upper tails</p>
</div>

To get the right answer, we have to add `lower.tail = FALSE` to our code as we are interested in the upper tail of the distribution. Because we want the cumulative probability to include 7, and because we know `q` words as **up to and including**, in order to get 7 or more, we set `q = 6`. This will now calculate the cumulative probability of getting 7, 8, 9, or 10 heads out of 10 coin flips. Remember, if we set `q = 7` that would be up to including 7, and looking at the upper tail of the distribution would only give us 8, 9 and 10. We want 7, 8, 9 and 10, so we have to set up to and including 6, which leaves us 7 and more.

Try and run the below code in a new code chunk:


```r
pbinom(q = 6, size = 10, prob = .5, lower.tail = FALSE) 
```

Looking at the outcome, answer the following question:

* What is the probability of getting between 7 and 10 heads from 10 coin flips to 2 decimal places? <input class='webex-solveme nospaces' size='4' data-answer='["0.17",".17"]'/>  
* What is this probability expressed in percent? <select class='webex-select'><option value='blank'></option><option value=''>0.017%</option><option value=''>0.17</option><option value='answer'>17%</option></select> 

#### Activity 9: `qbinom()` {#prob-a9}

OK great! You are doing excellent as this is tricky stuff. Remember though the whole point is to show you that using probability distributions you can ask all sorts of questions about the probability of any outcome or series of outcomes. 

Now let's consider a scenario in which you'd use the quantile function `qbinom`. Imagine that you've been accosted by a street magician and they want to bet you that they can predict whether the coin will land on heads or tails. You suspect that they've done something to the coin so that it's not fair and that the probability of the coin landing on a head is no longer .5 or 50/50 - you suspect the coin is now very much more likely to land on tails. Your null hypothesis is that the coin is not a trick coin and that the probability of heads or tails should be even. You are going to run a single experiment to test your hypothesis, with 10 trials. What is the minimum number of heads that is acceptable if p really does equal .5?

You have used the argument `prob` in the previous two functions, `dbinom` and `pbinom`, and it represents the probability of success on a single trial (here it is the probability of 'heads' in one coin flip, .5). For `qbinom`, `prob` still represents the probability of success in one trial, whereas `p` represents the overall probability of success across all trials. When you run `pbinom`, it calculates the number of heads that would give that probability. 

We know from looking at the binomial distribution above that sometimes even when the coin is fair, we won't get exactly 5/10 heads. Instead, we want to set a cut-off, a probability that below which we'll say that it's so unlikely we'd get that result if the coin was fair and in this example we will use the default cut-off for statistical significance in psychology, .05, or 5%.

In other words, you ask for the minimum number of successes (e.g. heads) to maintain an overall probability of .05, in 10 flips, when the probability of a success on any one flip is .5. To do that we use the below code:


```r
qbinom(p = .05, size = 10, prob = .5)
```

```
## [1] 2
```

From the code we see that the answer is 2. That means that if the magician flipped fewer than two heads out of ten, you could conclude that there is a less than 5% probability that would happened if the coin was fair. You would reject the null hypothesis that the coin was unbiased against heads and very very politely ask the kind magician for your money back!

However, ten trials is probably far too few if you want to accuse the magician of being a bit dodge. Run the below code and then answer the following questions:


```r
qbinom(p = .05, size = c(100, 1000, 10000), prob = .5)
```

* What would your cut-off be if you ran 100 trials? <input class='webex-solveme nospaces' size='2' data-answer='["42"]'/>
* What would your cut-off be if you ran 1000 trials? <input class='webex-solveme nospaces' size='3' data-answer='["474"]'/>
* What would your cut-off be if you ran 10,000 trials? <input class='webex-solveme nospaces' size='4' data-answer='["4918"]'/>

Notice that the more trials you run, the more precise the estimates become, that is, the closer they are to the probability of success on a single flip (.5). Again this is a simplification, but think about how this relates to sample size in research studies, the more participants you have, the more precise your estimate will be.

We should also mention that `qbinom` also uses the lower.tail argument and it works in a similar fashion to pbinom. We won't try that out here but it is good to know in case you ever need it.

******

**Visualise it!**

Have a go at playing around with different numbers of coin flips and probabilities in our `dbinom()` and `pbinom()` app!

<div class="figure" style="text-align: center">
<iframe src="https://shannon-mcnee19.shinyapps.io/binomial_shiny/" width="100%" height="800px" data-external="1"></iframe>
<p class="caption">(\#fig:unnamed-chunk-7)Binomial distribution app</p>
</div>

******

## Using the normal distribution

A similar set of functions exist to help us work with other distributions, including the normal distribution and we're going to use three of these:

* `dnorm()`- the density function, for calculating the probability of a specific value
* `pnorm()`- the probability or distribution function, for calculating the probability of getting at least or at most a specific value
* `qnorm()`- the quantile function, for calculating the specific value associated with a given probability

As you can probably see, these functions are very similar to the functions that are used to work with the binomial distribution. We will use data about height in Scottish people to show you how the above functions work in the normal distribution

### Probability of heights

Data from the [Scottish Health Survey (2008)](http://www.scotland.gov.uk/Resource/Doc/286063/0087158.pdf) shows that:

* The average height of a 16-24 year old Scottish man is 176.2 centimetres, with a standard deviation of 6.748.
* The average height of a 16-24 year old Scottish woman is 163.8 cm, with a standard deviation of 6.931.
* At the time of writing, there is currently no data on Scottish trans and non-binary people.

The below figure is a simulation of this information - again, you can see the code used to run this simulation by clicking the "Show me the code" button but note that you are not asked to understand this right now.


<div class='webex-solution'><button>Show me the code</button>


```r
men <- rnorm(n = 100000, mean = 176.2, sd = 6.748)
women <- rnorm(n = 100000, mean = 163.8, sd = 6.931)

heights <- tibble(men, women) %>%
  pivot_longer(names_to = "sex", values_to = "height", men:women)

ggplot(heights, aes(x = height, fill = sex)) +
  geom_density(alpha = .6) +
  scale_fill_viridis_d(option = "E") +
  theme_minimal()
```

</div>


<div class="figure" style="text-align: center">
<img src="08-probability_files/figure-html/unnamed-chunk-9-1.png" alt="Simulation of Scottish height data" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-9)Simulation of Scottish height data</p>
</div>

So to test the normal distribution, and to round off this chapter, we will use the above information to calculate the probability of observing at least or at most a specific height with `pnorm()`, and the heights that are associated with specific probabilities with `qnorm()`.

#### Activity 10:`pnorm()` {#prob-a10}

`pnorm()` requires three arguments:

* `q` is the value that you want to calculate the probability of. Note however you set this as exactly the number you want and not 1 less than the number you want. This is because the data is continuous and not discrete as in the binomial distribution.
* `mean` is the mean of the data
* `sd` is the standard deviation of the data
* `lower.tail` works as above and depends on whether you are interested in the upper or lower tail,

Type the code below into a code chunk and replace the NULLs to calculate the probability of meeting a 16-24 y.o. Scottish woman who is as tall or taller than the average 16-24 y.o. Scottish man.

  * **hint:** You are asking about the female distribution so use that mean and sd
  * **hint:** the average male is 176.2
  * **hint:** tall or taller is upper.
  * **hint:** the solution is at the end of the chapter if you are stuck.


```r
pnorm(q = NULL, mean = NULL, sd = NULL, lower.tail = NULL)
```

Looking at your outcome, answer the following questions.

* What is the probability of meeting a 16-24 y.o. Scottish woman who is taller than the average 16-24 y.o. Scottish man? <input class='webex-solveme nospaces' size='4' data-answer='["0.04",".04"]'/>  
* What is this probability expressed in percent? <select class='webex-select'><option value='blank'></option><option value=''>0.04%</option><option value=''>0.4%</option><option value='answer'>4%</option></select>

#### Activity 11: `pnorm` 2 {#prob-a11}

Fiona is a very tall Scottish woman (181.12 cm) in the 16-24 y.o. range who will only date men who are taller than her.  

* Using `pnorm()` again, what is the proportion of Scottish men Fiona would be willing to date to 2 decimal places? <input class='webex-solveme nospaces' size='4' data-answer='["0.23",".23"]'/>
  * **hint:** you want to know about the male population
  * **hint:** Fiona is 181.12 cm tall and you want taller than her.
* What is this probability expressed in percent? <select class='webex-select'><option value='blank'></option><option value=''>0.23%</option><option value=''>2.3%</option><option value='answer'>23%</option></select>

#### Activity 12: `pnorm` 3 {#prob-a12}

On the other hand, Fiona is bisexual and will only date women who are shorter than her. 

* What is the proportion of Scottish women would Fiona be willing to date to 2 decimal places? <input class='webex-solveme nospaces' size='4' data-answer='["0.99",".99"]'/>
  * **hint:** female distribution, lower than Fiona.
* What is this probability expressed in percent? <select class='webex-select'><option value='blank'></option><option value=''>0.99%</option><option value=''>9.9%</option><option value='answer'>99%</option></select>

#### Activity 13: `qnorm()` {#prob-a13}

Finally, in the previous examples we calculated the probability of a particular outcome. Now we want to calculate what outcome would be associated with a particular probability and we can use `qnorm()` to do this.

`qnorm()` is very similar to `pnorm()` with one exception, rather than specifying `q` our known observation or quantile, instead we have to specify `p`, our known probability.


```r
qnorm(p = NULL, mean = NULL, sd = NULL, lower.tail = NULL)
```

Replace the NULLs in the above code to calculate how tall a 16-24 y.o. Scottish man would have to be in order to be in the top 5% (i.e., p = .05) of the height distribution for Scottish men in his age group. Remember the solutions are at the end of the chapter. You can confirm if you are right or not by answering this question:



The answer to this last question was: <div class='webex-radiogroup' id='radio_KTQTGXKRZQ'><label><input type="radio" autocomplete="off" name="radio_KTQTGXKRZQ" value=""></input> <span>176.2</span></label><label><input type="radio" autocomplete="off" name="radio_KTQTGXKRZQ" value="answer"></input> <span>187.299472274669</span></label><label><input type="radio" autocomplete="off" name="radio_KTQTGXKRZQ" value=""></input> <span>193.581696140348</span></label><label><input type="radio" autocomplete="off" name="radio_KTQTGXKRZQ" value=""></input> <span>175.352037231422</span></label></div>


*****

**Visualise it!**

Have a go at playing around with different distributions in our `dnorm()` and `pnorm()` app - [access it here](https://shiny.psy.gla.ac.uk/jackt/ShinyPsyTeachR/ug1/normal-distributions/){target="blank"}

******

## Finished

And that's it! The key concepts to take away from this chapter are that different types of data tend to follow known distributions, and that we can use these distributions to calculate the probability of particular outcomes. This is the foundation of many of the statistical tests that you will learn about in this course. For example, if you want to compare whether the scores from two groups are different, that is, whether they come from different distributions, you can calculate the probability that the scores from group 2 would be in the same distribution as group 1. If this probability is less than 5% (p = .05), you might conclude that the scores were significantly different. That's an oversimplification obviously, but if you can develop a good understanding of probability distributions it will stand you in good stead for the rest of the statistics content.  

This was a long read so there is no test yourself today but be sure to make notes and to check your understanding of different concepts. Please also remember to ask any questions you are unsure of.

## Activity solutions {#prob-sols}

#### Activity 6 {#prob-a6sol}

* To two decimal places, what is the probability of getting 5 heads out of 10 coin flips? 


```r
.25
```

#### Activity 7 {#prob-a7sol}

* What is the probability of getting a maximum of 2 heads on 10 coin flips to 2 decimal places? 


```r
.06
```


#### Activity 8 {#prob-a8sol}

* What is the probability of getting between 7 and 10 heads from 10 coin flips to 2 decimal places?


```r
.17
```


#### Activity 10 {#prob-a10sol}

* What is the probability of meeting a 16-24 y.o. Scottish woman who is taller than the average 16-24 y.o. Scottish man?


```r
pnorm(q = 176.2, mean = 163.8, sd = 6.931, lower.tail = FALSE)
```


#### Activity 11 {#prob-a11sol}

* Using `pnorm()` again, what is the proportion of Scottish men Fiona would be willing to date to 2 decimal places? 


```r
pnorm(q = 181.12, mean = 176.2, sd = 6.748, lower.tail = FALSE)
```


#### Activity 12 {#prob-a12sol}

* What is the proportion of Scottish women would Fiona be willing to date to 2 decimal places?


```r
pnorm(q = 181.12, mean = 163.8, sd = 6.931, lower.tail = TRUE)
```

#### Activity 13 {#prob-a13sol}

The answer to this last question was:


```r
qnorm(p = .05, mean = 176.2, sd = 6.748, lower.tail = FALSE)
```

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                         |definition                                                                                                                                                                           |
|:----------------------------------------------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|[binomial distribution](https://psyteachr.github.io/glossary/b.html#binomial-distribution){class="glossary" target="_blank"} |The distribution of data where each observation can have one of two outcomes, like success/failure, yes/no or head/tails.                                                            |
|[chi square](https://psyteachr.github.io/glossary/c.html#chi-square){class="glossary" target="_blank"}                       |An inferential test used to compare observed frequencies with expected frequencies in categorical conditions                                                                         |
|[continuous](https://psyteachr.github.io/glossary/c.html#continuous){class="glossary" target="_blank"}                       |Data that can take on any values between other existing values.                                                                                                                      |
|[discrete](https://psyteachr.github.io/glossary/d.html#discrete){class="glossary" target="_blank"}                           |Data that can only take certain values, such as integers.                                                                                                                            |
|[distribution](https://psyteachr.github.io/glossary/d.html#distribution){class="glossary" target="_blank"}                   |A probability distribution is way to describe the shape of data.                                                                                                                     |
|[inferential](https://psyteachr.github.io/glossary/i.html#inferential){class="glossary" target="_blank"}                     |Statistics that allow you to make predictions about or comparisons between data (e.g., t-value, F-value, rho)                                                                        |
|[integer](https://psyteachr.github.io/glossary/i.html#integer){class="glossary" target="_blank"}                             |A data type representing whole numbers.                                                                                                                                              |
|[interval](https://psyteachr.github.io/glossary/i.html#interval){class="glossary" target="_blank"}                           |data which comes in the form of a numerical value where the difference between points is standardised and meaningful                                                                 |
|[likert](https://psyteachr.github.io/glossary/l.html#likert){class="glossary" target="_blank"}                               |A rating scale with a small number of discrete points in order                                                                                                                       |
|[nominal](https://psyteachr.github.io/glossary/n.html#nominal){class="glossary" target="_blank"}                             |Categorical variables that don&#39;t have an inherent order, such as types of animal.                                                                                                |
|[normal distribution](https://psyteachr.github.io/glossary/n.html#normal-distribution){class="glossary" target="_blank"}     |A symmetric distribution of data where values near the centre are most probable.                                                                                                     |
|[ordinal](https://psyteachr.github.io/glossary/o.html#ordinal){class="glossary" target="_blank"}                             |Discrete variables that have an inherent order, such as level of education or dislike/like.                                                                                          |
|[population](https://psyteachr.github.io/glossary/p.html#population){class="glossary" target="_blank"}                       |All members of a group that we wish to generalise our findings to. E.g. all students taking Psychology at the University of Glasgow. We draw our testing sample from the population. |
|[probability](https://psyteachr.github.io/glossary/p.html#probability){class="glossary" target="_blank"}                     |A number between 0 and 1 where 0 indicates impossibility of the event and 1 indicates certainty                                                                                      |
|[ratio](https://psyteachr.github.io/glossary/r.html#ratio){class="glossary" target="_blank"}                                 |data which comes in the form of a numerical value where the difference between points is standardised and meaningful but has a meaningful zero                                       |
|[sample](https://psyteachr.github.io/glossary/s.html#sample){class="glossary" target="_blank"}                               |A subset of the population that you wish to make an inference about through your test.                                                                                               |
|[simulation](https://psyteachr.github.io/glossary/s.html#simulation){class="glossary" target="_blank"}                       |Generating data, as opposed to collecting data, from summary parameters such as the mean and standard deviation                                                                      |
|[uniform distribution](https://psyteachr.github.io/glossary/u.html#uniform-distribution){class="glossary" target="_blank"}   |A distribution where all numbers in the range have an equal probability of being sampled                                                                                             |


That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!






<!--chapter:end:08-probability.Rmd-->

# Correlations



So far in this book we have been building your skills and knowledge on data wrangling and you now have the basis for a lot of the work you will do in research. You may think that the tasks we ask you to do will get harder as this course progresses but that isn't true. The hardest part of working with data is at the very beginning, trying to learn the new terminology, figuring out how to load in data and wrangle it into the format you need. And whilst it may feel like you have not yet covered a lot, it is really worth reflecting on just how far you've come in a short time.

For instance, you can now:

* Understand what functions, arguments, objects, variables, and tibbles are.  
* Read data into your working environment for analysis.  
* Tidy data into an appropriate format.  
* Calculate a range of descriptive statistics.
* And Create plots of data.

That's amazing! And to be honest, as you will see, that actually covers a large percentage of what we will do. What we do now is start moving on to actually running some <a class='glossary' target='_blank' title='Statistics that allow you to make predictions about or comparisons between data (e.g., t-value, F-value, rho)' href='https://psyteachr.github.io/glossary/i#inferential'>inferential</a> statistics, where we make inferences about our population of interest from the sample we have collected. Specifically, in this chapter we are going to move on to performing a <a class='glossary' target='_blank' title='The relationship two vectors have to each other.' href='https://psyteachr.github.io/glossary/c#correlation'>correlation</a> and to create a plot to visualise the data. Correlation is a test that measures the relationship between two <a class='glossary' title='an aspect about your sample or population that can be measured'>variable</a>. In other words, you measure two variables and the correlation analysis tells you whether or not they are related in some manner, either <a class='glossary' title='a relationship between two variables where as one variable increases, the other variable also increases'>positively</a>  or <a class='glossary' title='a relationship between two variables where as one variable increases, the other variable also decreases'>negatively</a>, and how strong that relationship is - when you discuss a correlation you should always talk about the strength and the direction of the relationship. The figure below shows three examples of correlations just to give an idea:



<div class="figure" style="text-align: center">
<img src="09-correlation_files/figure-html/ch10-show-figure-1.png" alt="Schematic examples of extreme bivariate relationships" width="100%" />
<p class="caption">(\#fig:ch10-show-figure)Schematic examples of extreme bivariate relationships</p>
</div>

**Note:** When dealing with correlations you should always refer to relationships and not predictions. In a correlation, X does not predict Y, nor does X cause an effect in Y. We will look at different tests in this book where you can take about cause-and-effect and about prediction, but correlation all we can say is whether X and Y are related.

Now, as we said above, to actually carry out a correlation is fairly straightforward and we will show you that today in a little while. The hardest part of correlations is really wrangling the data and interpreting what the results mean. You are going to run a few correlations in this chapter to give you good practice at running and interpreting the relationships between two variables. 

In this chapter we will use the examples in [Miller and Haden (2013)](https://drive.google.com/file/d/0B1fyuTuvj3YoaFdUR3FZaXNuNXc/view){target="_blank"}, Chapter 11, looking at the relationship between four variables: reading ability, intelligence (IQ), the number of minutes per week spent reading at home (Home); and the number of minutes per week spent watching TV at home (TV). We will use this data across a series of tasks to help you understand correlations more. You do not need to read the chapter but hopefully from just the names of the variables you can see in this situation that it would be unethical to manipulate these variables so measuring them as they exist in the environment is most appropriate; hence the use of correlations. And for clarity, this is an example of observational research; all correlations are observational, but not all observational research uses correlations. 

Finally, there are two main types of correlations that people tend to think of (though there are more):

* Pearson's product-moment correlation (often shortened to the <a class='glossary' target='_blank' title='a standardised measure of the linear relationship between two variables' href='https://psyteachr.github.io/glossary/p#pearson'>Pearson</a> correlation) and symbolised by **r**
* Spearman's rank correlation coefficient (often shortened to the <a class='glossary' target='_blank' title='a standardised measure of the relationship between two variables that does not assume a linear relationship. Note that the relationship can be linear but it is not required.' href='https://psyteachr.github.io/glossary/s#spearman'>Spearman</a> correlation) and symbolised by **rho** or sometimes $r_s$ or sometimes $\rho$

We will talk a little bit about these two correlations in the work we do today. And we shall begin now!

## Set-up the Data

As always, the first activity is about getting ourselves ready to analyse the data so try out the steps and if you need help, consult the earlier chapters.

#### Activity 1: Set-up {#corr-a1}

* Open RStudio and set the working directory to your chapter folder. Ensure the environment is clear.
    * If you're using the Rserver, avoid a number of issues by restarting the session - click `Session` - `Restart R`
* Open a new R Markdown document and save it in your working directory. Call the file "Correlations".     
* Download <a href="MillerHadenData.csv" download>MillerHadenData.csv</a> and save it in your folder. Make sure that you do not change the file name at all.  
    * If you prefer you can download the data in a [zip folder by clicking here](data/chpt9/PsyTeachR_FQA_Chpt9-data.zip){target="_blank"}
    * Remember not to change the file names at all and that `data.csv` is not the same as `data (1).csv`.
* Delete the default R Markdown welcome text and insert a new code chunk that loads the following packages, in this specific order, using the `library()` function. Remember the solutions if needed.
  * Load the packages in this order, `car`,`correlation`, `report`, `psych`, and `tidyverse`
  * we have not used four of these packages before so you will likely need to install them using `install.packages()`. Remember though that you should only do this on your own machine and only in the console window. If you are using the RServer you will not need to install them.
* Finally, load the data into an object named `mh` using `read_csv()`. 


<div class='webex-solution'><button>Additional Hints</button>


* Each package requires using the `library()` function each time. For example, `library(car)`, `libary(correlation)`, etc, etc.
* mh <- read_csv("What_is_your_datafile_called.csv")

</div>


#### Activity 2: Look at your data {#corr-a2}

Excellent! If you have loaded in the data correctly then you should be able to have a look at it through one of the various methods we have looked at already.

* Look at your data using the `head()` function and you should see the following:

<div class="kable-table">

| Participant| Abil|  IQ| Home|  TV|
|-----------:|----:|---:|----:|---:|
|           1|   61| 107|  144| 487|
|           2|   56| 109|  123| 608|
|           3|   45|  81|  108| 640|
|           4|   66| 100|  155| 493|
|           5|   49|  92|  103| 636|
|           6|   62| 105|  161| 407|

</div>

As you can see, we have five columns and they are: 

* the participant number (`Participant`), 
* Reading Ability score (`Abil`), 
* Intelligence score (`IQ`), 
* the number of minutes spent reading at Home per week (`Home`), 
* and the number of minutes spent watching TV per week (`TV`). 

Here we will we will focus on Reading Ability and IQ but for further practice you can look at other relationships in your free time.  

A probable <a class='glossary' target='_blank' title='A proposed explanation made on the basis of limited evidence as a starting point for further investigation.' href='https://psyteachr.github.io/glossary/h#hypothesis'>hypothesis</a> for today could be that as Reading Ability increases so does Intelligence (remember there is no causality here). Or phrasing the <a class='glossary' title='the experimental hypothesis formed in Null Hypothesis Significance Testing and is the hypothesis that states that there will be a relationship between variables or an effect of one variable on the other'>alternative hypothesis</a> ($H_1$) more formally, we hypothesise that the reading ability of school children, as measured through a standardized test, and intelligence, again measured through a standardized test, show a positive relationship. This is the hypothesis we will test today but remember that we could always state the <a class='glossary' title='the defauly hypothesis in Null Hypothesis Significance Testing and is the hypothesis that states that there will be no effect or relationship in your study.'>null hypothesis</a> ($H_0$) that there is no relationship between reading ability and IQ.

## Assumptions of the test

Now before running an analysis we should check the <a class='glossary' title='requirements about your data and your design that must be held for your analysis to have meaning'>assumptions</a> of the test, where the assumptions are checks that the data must pass before we can use certain tests. The assumptions change on the test and you should only use a given test based on how well the data meets the assumptions of the test. In short, the Pearson correlation and the Spearman correlation have different assumptions and we need to check our data to see which test to use.

#### Activity 3: Assumptions {#corr-a3}

For correlations, the main assumptions we need to check are:

1. Is the data interval, ratio, or ordinal?
2. Is there a data point for each participant on both variables?
3. Is the data <a class='glossary' target='_blank' title='A symmetric distribution of data where values near the centre are most probable.' href='https://psyteachr.github.io/glossary/n#normal-distribution'>normally distributed</a> in both variables?
4. Does the relationship between variables appear linear?
5. Does the spread have <a class='glossary' title='that the spread of data around the line of best fit is equal on both side along the length of the line'>homoscedasticity</a>?

We will look at each of these assumptions in turn to see which correlation we should use.

**Assumption 1: Level of Measurement**

If we want to run a Pearson correlation then we need interval or ratio data; Spearman correlations can run with ordinal, interval or ratio data. What type of data do we have?  

* The type of data in this analysis is most probably <select class='webex-select'><option value='blank'></option><option value=''>ratio</option><option value='answer'>interval</option><option value=''>ordinal</option><option value=''>nominal</option></select> as the data is <select class='webex-select'><option value='blank'></option><option value='answer'>continuous</option><option value=''>discrete</option></select> and there is unlikely to be a true zero


<div class='webex-solution'><button>Hints on data type</button>


* Are the variables continuous? 
* Is the difference between 1 and 2 on the scale equal to the difference between 2 and 3?

</div>
  

**Assumption 2: Pairs of Data**

Great! So the data looks at least interval and continuous. Next, all correlations must have a data point for each participant in the two variables being correlated. This should make sense as to why - you can't correlate against an empty cell! So now go check that you have a data point in both columns for each participant. 

**Note:** You can check for missing data by visual inspection - literally using your eyes. A missing data point will show as a NA, which is short for not applicable, not available, or no answer. An alternative would be to use the `is.na()` function. This can be really handy when you have lots of data and visual inspection would just take too long. If for example you ran the following code:


```r
is.na(mh)
```

If you look at the output from that function, each FALSE tells you that there is a data-point in that cell. That is because `is.na()` asks is that cell a NA; is it empty. If the cell was empty then it would come back as TRUE. As all cells have data in them, they are all showing as FALSE. If you wanted to ask the opposite question, is their data in this cell, then you would write !is.na() which is read as "is not NA". Remember, the exclamation mark ! turns the question into the opposite.

However you have looked at the data, it looks like that everyone has data in all the columns but let's test our skills a little whilst we are here.  Answer the following questions:

1. How is missing data represented in a tibble? <select class='webex-select'><option value='blank'></option><option value=''>an empty cell</option><option value='answer'>NA</option><option value=''>a large number</option><option value=''>don't know</option></select>
2. Which code would leave you with just the participants who were missing Reading Ability data in mh: 
<select class='webex-select'><option value='blank'></option><option value=''>filter(mh, is.na(Ability)</option><option value='answer'>filter(mh, is.na(Abil)</option><option value=''>filter(mh, !is.na(Ability)</option><option value=''>filter(mh, !is.na(Abil)</option></select>
3. Which code would leave you with just the participants who were not missing Reading Ability data in mh: <select class='webex-select'><option value='blank'></option><option value=''>filter(mh, is.na(Ability)</option><option value=''>filter(mh, is.na(Abil)</option><option value=''>filter(mh, !is.na(Ability)</option><option value='answer'>filter(mh, !is.na(Abil)</option></select>


<div class='webex-solution'><button>Hints on removing missing data points</button>


* `filter(dat, is.na(variable))` versus `filter(dat, !is.na(variable))`

</div>
  

**Assumption 3-5: Normality, linearity, homoscedasticity**

Brilliant! We know our data type and we know we have no missing data. The remaining assumptions are all best checked through visualisations. You can use histograms and QQ-plots to check that the data (`Abil` and `IQ`) are both normally distributed, and you can use a scatterplot of `IQ` as a function of `Abil` to check whether the relationship is linear, with homoscedasticity, and without outliers. An alternative would be to use z-scores to check for outliers with the cut-off usually being set at around $\pm2.5SD$ or $\pm3SD$. You could do this using the mutate function (e.g. `mutate(z = (X - mean(X))/SD(X))`), but today we will just use visual checks.

We will now ask you to create a few figures and then we will look at them together, as a whole, to answer some questions about these last assumptions.

**Histograms for Normality**

* Type the below code in a new code chunk and run it to create a histogram for `Abil`.


```r
ggplot(data = mh, aes(x = Abil)) +
  geom_histogram()
```

This code should look very similar to the code you used to create a bar plot in Chapter 7. We have specified that we want to display `Abil` on the x-axis and that the shape we want to produce is a histogram, hence `geom_histogram()`. Just like `geom_bar()`, you do not need to specify the y-axis because if it's a histogram, it's always a count. The figure should look as shown here.

<div class="figure" style="text-align: center">
<img src="09-correlation_files/figure-html/abil-hist-1.png" alt="Histogram of Abil" width="100%" />
<p class="caption">(\#fig:abil-hist)Histogram of Abil</p>
</div>

* Now, in a new code chunk, write and run code to produce a histogram for the variable `IQ`. Remember the solutions are at the end of the chapter.

**Q-Q Plots for Normality**

As we said we will look at the figures in a minute but first we need a few more plots. One being the <a class='glossary' target='_blank' title='A scatterplot created by plotting two sets of quantiles against each other, used to check if data come from a specified distribution' href='https://psyteachr.github.io/glossary/q#q-q-plot'>Q-Q plot</a> which allows us to check normality. The Q-Q plot require us to use the package `car` rather than `ggplot2`. You can make Q-Q plots in `ggplot2` but they aren't as useful, however, the code is still very simple.

* In a new code chunk, type and run the below code to create a Q-Q plot for `Abil`.


```r
qqPlot(x = mh$Abil)
```

This code looks a little different to code you've used up until this point as it comes from Base R. It uses the notation `object$variable` so our x variable could be read as "use the variable `Abil` from the object `mh`. And the figure will look like this:

<div class="figure" style="text-align: center">
<img src="09-correlation_files/figure-html/qq-abil-1.png" alt="Q-Q plot for Abil" width="100%" />
<p class="caption">(\#fig:qq-abil)Q-Q plot for Abil</p>
</div>

```
## [1] 15  4
```

The Q-Q plot includes a **confidence envelope** (the blue dotted lines) around the data with  the understanding that if your data points fall within these dotted lines then you can assume normality. The `ggplot2` version of Q-Q plots make it more difficult to add on this confidence envelope, which is why we're using a different package. `qqPlot()` will also print the IDs of the most extreme data points. In this case, the 4th and 15th data point in `Abil` are flagged, although because they fall within the confidence envelope, they don't appear problematic. This also explains why you might see a message stating `## [1] 15 4`. The 15th and 4th value are worth considering!

* Now, in a new code chunk, write and run code to create a Q-Q plot for `IQ`.


**Information: Normality of the residuals**

One thing to note before we move on is that, in terms of normality, it is in fact the normality of the <a class='glossary' target='_blank' title='Defined as the deviation of an observation from a model&#39;s expected value.' href='https://psyteachr.github.io/glossary/r#residual'>residuals</a> that matters, where the residuals are the difference between the individual data points and the <a class='glossary' title='otherwise known as the regression line, it is the line drawn between data points in a scatterplot that best divides the data in half. It is in fact a prediction of where data would fall for a given relationship strength and direction'>line of best fit</a>. However, to fully understand this we need to cover more information first as introducing that concept at this stage would be confusing. One approach the field can use however is that if the data is normally distributed then it is highly likely that the residuals will also be normally distributed. We will look at residuals in the next chapter, but here we will instead use the normality of the raw data as a proxy for the normality of the residuals.

**Scatterplots for linearity and homoscedasticity**

Finally, in order to assess linearity and homoscedasticity, we can create a scatterplot using `ggplot2`.

* In a new code chunk, copy and run the below code to create a scatterplot of the relationship between IQ and Ability.


```r
ggplot(data = mh, aes(x = Abil, y = IQ)) +
  geom_point()+
  geom_smooth(method = lm)
```

The `ggplot2` code is very similar to what you have already encountered with the bar chart and violin-boxplot. 

* The first line of data sets up the base of the plot and we specify that we wish to display `Abil` on the x-axis, `IQ` on the y-axis, and use the dataset `mh`. 
* The first geom, `geom_point()`, adds in the data points, 
* the second geom, `geom_smooth`, adds in the line of best fit. The shaded area around the line is a **confidence interval** around the data. This can be turned off by setting `se = FALSE` as an additional argument.

The figure should look as follows:


```
## `geom_smooth()` using formula 'y ~ x'
```

<div class="figure" style="text-align: center">
<img src="09-correlation_files/figure-html/unnamed-chunk-5-1.png" alt="Scatterplot of scores" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-5)Scatterplot of scores</p>
</div>

**Note:** Do not worry if you see a message stating `## geom_smooth() using formula 'y ~ x'`. This is just letting you know how it is plotting the line of best fit (the blue line)

* Now, remembering that `ggplot2` works on layers and that you can customise each layer, edit the above code to add in a layer of `scale_x_continuous()` that changes the label `Abil` to `Reading Ability`.

**Checking the assumptions**

Now that we have all the figures we need we should be able to check the assumptions. Try to answer the following questions, based on the above visualisations:

* Is the assumption of normality met for both variables? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
* Is the assumption of linearity met? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
* Is the assumption of homoscedasticity met? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
* Based on the above, which correlation method would you use? <select class='webex-select'><option value='blank'></option><option value='answer'>Pearson</option><option value=''>Spearman</option></select>


<div class='webex-solution'><button>Explain these answers</button>

When assessing assumptions through the use of visualisations your decision will always be a judgement call. In this dataset, we only have data from 25 participants therefore it is very unlikely we would ever observe perfect normality and linearity in this dataset. It is likely that a researcher would assume that this data is approximately normal, that there is no evidence of a non-linear relationship, and that the spread of data points around the line is relatively even. Many students become fixated with needing a 'perfect' dataset that follows an exactly normal distribution. This is unlikely to ever happen with real data - learn to trust your instincts!

Finally, as the data is interval, continuous, normally distributed, and the relationship is linear and the assumption of homoscedasticity has been met, we would use a Pearson correlation.
    

</div>


## Descriptives of the Correlation

Now that we have checked our assumptions and have confirmed we will use the Pearson correlation, the next step is descriptives. A key thing to keep in mind is that the <a class='glossary' title='a visualisation where each individual data point shows the value of an observation on twi variables.'>scatterplot</a> is actually the descriptive of the correlation. Meaning that in an article, or in a report, you would not only use the scatterplot to determine which type of correlation to use but also to describe the potential relationship in regards to your hypothesis. So you would always expect to see a scatterplot in the write-up of this type of analysis. 

#### Activity 4: Descriptive statistics {#corr-a4}

* Looking at the scatterplot, spend a couple of minutes thinking about and describing the relationship between Ability and IQ in terms of your hypothesis. Remember this is a descriptive analysis at this stage, so nothing is confirmed. Does the relationship appear to be as we predicted in our hypothesis? A discussion is in the solutions at the end of the chapter.


<div class='webex-solution'><button>Hints on discussing descriptives</button>


* Hint 1: We hypothesised that reading ability and intelligence were positively correlated. Is that what you see in the scatterplot?
* Hint 2: Keep in mind it is subjective at this stage.
* Hint 3: Remember to only talk about a relationship and not a prediction. This is correlational work, not regression.
* Hint 4: Can you say something about both the strength (weak, medium, strong) and the direction (positive, negative)?

</div>


In addition to the scatterplot, it can sometimes be relevant to include means and standard deviations of scales in a correlation. It is not always relevant but, as an example, if you were measuring something like anxiety, or stress, or IQ, it can be informative to include this information to help demonstrate how your sample compares to population norms. As such we will calculate some descriptives here as it is also good practice of our data-wrangling skills.

* In a new code chunk, write and run code to calculate the mean score and standard deviation for `Abil` and `IQ` using `summarise()` and store the output of this function in an object called `descriptives`
  * Name the output of the calculations `Abil_mean`, `Abil_SD`, `IQ_mean`, and `IQ_SD`. Make sure to use these exact spellings otherwise later activities won't work.
  * **hint:** We have already seen how to calculate the `mean()`, the `median()`, the number of people (with `n()`), and the `sum()` within the `summarise()` function. Other descriptives such as the `sd()`, the `min()` and the `max()` can also be calculated in a similar way to using `mean()` and `median()`.

If you have performed this correctly, when you view `descriptives` should look similar to this:  


| Abil_mean | Abil_SD | IQ_mean | IQ_SD |
|:---------:|:-------:|:-------:|:-----:|
|   55.12   |  6.08   | 100.04  | 9.04  |

Answer the following questions to confirm your understanding of the output:

* What is the mean of Reading Ability? <select class='webex-select'><option value='blank'></option><option value=''>54.12</option><option value=''>56.12</option><option value='answer'>55.12</option></select>
* What is the mean of IQ? <select class='webex-select'><option value='blank'></option><option value=''>99.04</option><option value='answer'>100.04</option><option value=''>101.04</option></select>
* If the population norm mean of IQ is 100, how comparable is your sample to the population? <select class='webex-select'><option value='blank'></option><option value='answer'>the same</option><option value=''>very different</option></select>

## Inferentials of the correlation

Excellent! So we have checked our assumptions and our descriptives. Our data looks consistent with population norms and the scatterplot would suggest a positive relationship between the two variables. Finally we will run the correlation! 

There are often many different functions that can be used to achieve the same thing and we're actually going to show you two ways of running a correlation as some people prefer one approach over the other because of the data type the results come in and how easy it is to work with that output.

#### Activity 5: Run the correlation {#corr-a5}

First, we'll use the `correlation()` function from the `correlation` package. Remember that for help on any function you can type e.g., `?correlation` in the console window.  The `correlation()` function requires:

* The name of the data set you are using
* The name of the first variable you want to select for the correlation
* The name of the second variable you want to select for the correlation
* The type of correlation you want to run: e.g. `pearson`, `spearman`
* The type of NHST tail you want to run: e.g. `"less"`,`"greater"`, `"two.sided"`

For example, if your data is stored in `dat` and you want to do a two-sided pearson correlation of the variables (columns) `X` and `Y`, then you would do:


```r
correlation(data = dat, 
            select = "X", 
            select2 = "Y",  
            method = "pearson", 
            alternative = "two.sided")
```

Here we are wanting to run a Pearson correlation with a two-sided alternative.

* In a new code chunk, using the information about `correlation()` above, type and run a Pearson correlation between IQ and Ability and store the output in an object called `results`.
* View the output by typing `View(results)` in the console window

The second method is to use `cor.test()` which is a **`Base R`** function and uses similar code as `correlation()` except for how the variables are specified. `cor.test()` use the same `object$variable` syntax we saw in `qqPlot()`:

* In a new code chunk, type and run the below code and then view the output by typing `results2` in the console. 
  * not that we have specified `x = mh$IQ` meaning that the first variable, x, is the column `IQ` in the object `mh`. 


```r
results2 <-  cor.test(x = mh$IQ, 
                      y = mh$Abil, 
                      method = "pearson", 
                      alternative = "two.sided")
```

Look at how the output differs from `results`. We'll come back to why we've shown you two ways shortly.

## Interpreting output and writing up

Excellent work. As you can see, running the correlation is actually really quick, and the hard work was checking the assumptions and some data-wrangling. You should now have a tibble called `results` that gives you the output of the correlation between Reading Ability and IQ for the school children measured in Miller and Haden (2013) Chapter 11. All that is left to do now is interpret the output and write it up. 

#### Activity 6: Interpreting the correlation {#corr-a6}

Look at `results` and then answer the following questions:

1. What is the value of Pearson's *r* to 2 decimal places? <input class='webex-solveme nospaces' size='20' data-answer='[".45","0.45"]'/>
2. The direction of the relationship between Ability and IQ is: <select class='webex-select'><option value='blank'></option><option value='answer'>positive</option><option value=''>negative</option><option value=''>no relationship</option></select>
3. The strength of the relationship between Ability and IQ is: <select class='webex-select'><option value='blank'></option><option value=''>strong</option><option value='answer'>medium</option><option value=''>weak</option></select>
4. Assuming $\alpha = .05$ the relationship between Ability and IQ is: <select class='webex-select'><option value='blank'></option><option value='answer'>significant</option><option value=''>not significant</option></select>
5. The alternative hypothesis was that the reading ability of school children, as measured through a standardized test, and intelligence, again through a standardized test, are positively correlated. Based on the results we can say that the alternative hypothesis: <select class='webex-select'><option value='blank'></option><option value='answer'>is accepted</option><option value=''>is rejected</option><option value=''>is proven</option><option value=''>is not proven</option></select> 


<div class='webex-solution'><button>Explain these answers</button>


1. The test statistic, in this case the r value, is usually labelled as the `estimate`.
2. If Y increases as X increases then the relationship is positive. If Y increases as X decreases then the relationship is negative. If there is no change in Y as X changes then there is no relationship
3. Depending on the field most correlation values greater than .5 would be strong; .3 to .5 as medium, and .1 to .3 as small. 
4. The field standard says less than .05 is significant and our p-value is less than .05.
5. The alternative hypothesis can only be accepted or rejected, never proven. In this case, our results matched our alternative hypothesis and therefore it is accepted. Remember that the null hypothesis on the other hand can only be rejected or retained.

</div>
  

#### Activity 7: Write-up {#corr-a7}

Now we have interpreted the output we would want to write it up. Copy and paste the below **exactly** into **white space** in your R Markdown document and then knit the file. 


```r
As shown in Figure 7.5, there appeared to be a positive relationship between Reading Ability (M = `r round(pluck(descriptives$Abil_mean),2)`, SD = `r round(pluck(descriptives$Abil_SD),2)`) and IQ (M = `r round(pluck(descriptives$IQ_mean),2)`, SD = `r round(pluck(descriptives$IQ_SD),2)`), in line with the alternative hypothesis. A Pearson correlation found a significant, medium positive correlation between the two variables (r (`r results$df_error`) = `r round(results$r, 2)`, *p* = `r round(results$p, 3)`) and the alternative hypothesis is therefore accepted. 
```

When you knit the code, assuming you have done all of the above tasks correctly, the code you pasted will transform into a readable passage as follows:

As shown in Figure 7.5, there appeared to be a positive relationship between Reading Ability (M = 55.12, SD = 6.08) and IQ (M = 100.04, SD = 9.04), in line with the alternative hypothesis. A Pearson correlation found a significant, medium positive correlation between the two variables (r (23) = 0.45, *p* = 0.024) and the alternative hypothesis is therefore accepted. 

So you get a fairly ok start of a write-up. It isn't perfect but it is a good start. For instance, the r-value should not have the first 0 and just be r = .xx. Likewise, the p-value should not have the first 0 either. So you will always have to do a bit of tidying up.

**Note:** Remember that a relationship is said to be <a class='glossary' title='The conclusion where the p-value is lower than the critical alpha and at which the null hypothesis is rejected'>significant</a> if the p-value of the relationship is lower than the accepted level (normally called <a class='glossary' target='_blank' title='The cutoff value for making a decision to reject the null hypothesis' href='https://psyteachr.github.io/glossary/a#alpha'>alpha</a> and set at $\alpha = .05$). Alternatively, a relationship that has a p-value higher than the accepted level is said to be <a class='glossary' title='The conclusion where the p-value is greater than the critical alpha and at which the null hypothesis is retained'>non-significant</a>

**But why two approaches**

The reason that we have shown you two methods of performing correlations is because of the way each outputs the results. `correlation()` produces a tibble which means it is very easy to work with and pull out values or join to another table as needed because it is already in tidyverse format. `cor.test()` on the other hand produces a `list` type object, which is a harder to work with. However, the output of `cor.test()` also happens to work with functions from the `report` package, `report()` and `report_table()` that give you an automatic report of the analyses. For example, `report()` presents a fixed write-up of the correlation with all the available information. For correlations, this is perhaps less than useful, however, for more complex statistics this reporting function can really help when learning about data and output, and so we're introducing it now. `report()` doesn't currently work with the output of `correlation()` which is why we showed you both ways. Run the below in your console window and you will see what we mean - you will probably get an error. 


```r
report(results2)
```

**Note:** The write-up that comes out of report should not be considered as something to copy and paste into a report. It is a means of just obtaining an overview quickly to help you confirm your own thinking. There are issues again with the presentation of numbers and writing, and additional info that isn't needed. Basically, use these functions and approaches to start you off in your writing, but not as your write-up.

## Multiple Correlations

Finally, to round off this chapter, we want to briefly show you about running multiple correlations at one. Above we ran one correlation. However, when you have lots of variables in a dataset, to get a quick overview of patterns, you might want to run all the correlations at the same time or create a matrix of scatterplots at the one time. You can do this with functions from the `psych` and `correlation` packages (`cor.test()` only works for one correlation at a time). We will use the Miller and Haden data here again which you should still have in a tibble called `mh`. 

#### Activity 8: Scatterplot matrix {#corr-a8}

* In a new code chunk, type and run the following code. The `pairs.panels())` function comes from the `psych` library and creates a matrix of scatterplots, with the histograms, and correlation coefficients which you can then use to give you an overview of all the relationships at the one time. So it is useful for checking assumptions in one place.


```r
pairs.panels(mh)
```

<div class="figure" style="text-align: center">
<img src="09-correlation_files/figure-html/pairs-1.png" alt="Scatterplot matrix" width="100%" />
<p class="caption">(\#fig:pairs)Scatterplot matrix</p>
</div>

Notice something wrong? `pairs.panels()` will create plots for **all** variables in your data (as will `correlation()` below). This means that it has correlated the Participant ID number as well, which is totally meaningless.

Instead, we can use pipes to help us out here. The code below:

* Takes the dataset `mh` and then;
* Uses `select()` to get rid of the `Participant` column and then;
* Pipes the remaining data into the `pairs.panels()` function
* The additional arguments:
  * `ellipses = FALSE` turns off the [correlation ellipses](https://analyse-it.com/docs/user-guide/multivariate/scatter-plot#:~:text=If%20the%20association%20is%20a,more%20the%20variables%20are%20uncorrelated.){target="_blank"}, 
  * `lm = TRUE` use a linear line of best fit, 
  * `method = "pearson", specifies a Pearson correlation.

There are additional arguments to adjust the plot `pairs.panel` creates that you can look up in the help documentation if you are interested.


```r
mh %>%
  select(-Participant) %>%
  pairs.panels(ellipses = FALSE, 
               lm = TRUE, 
               method = "pearson")
```

Which produces:

<div class="figure" style="text-align: center">
<img src="09-correlation_files/figure-html/pairs-pipes-1.png" alt="Adjusted scatterplot matrix" width="100%" />
<p class="caption">(\#fig:pairs-pipes)Adjusted scatterplot matrix</p>
</div>

#### Activity 9: Running multiple correlations {#corr-a9}

To perform multiple correlations in one go, we will again use the `correlation()` function. package. Rather than specifying two variables to correlation, you can also provide a data frame that has multiple variables  and it will run all possible correlations between the variables. Similar to above, we want to remove the `Participant` column before we do this.   

* `method` controls which correlation is computed, the default is `pearson` but if you needed to run the non-parametric version you could change this to `spearman`.  
* `p_adjust` is the reason we are using the `correlation` package. In the lectures we discussed the problem of <a class='glossary' title='An issue of running mutlitple tests which results in an increase in the false positive rate making it more likely that you will incorrectly reject the null hypothesis and accept the alternative hypothesis. The issue is resolved through correction for multiple comparisons'>multiple comparisons</a> - the idea that if you run lots and lots of tests your false positive rate will increase and the probability of finding a significant result increase. 
  * This argument applies a correction to the p-value that adjusts for the number of correlations you have performed. There are several different methods which you can look up in the help documentation, but here we are setting <a class='glossary' title='A correction for multiple comparisons where the accepted alpha level is adjusted by dividing it by the number of comparisons made'>bonferroni</a>. The default setting is actually the less <a class='glossary' title='A conservative test is one that is more likely to result in more false negatives - i.e. missed findings - than a test considered less conservative'>conservative</a> <a class='glossary' title='A correction for multiple comparisons where an ordinal iterative approach is used comparing each individual test to an adjusted p-value based on the order of p-values. Generally said to be less conservative than Bonferroni'>holm</a> and you can read about why some might chose that instead in the help function by typing `?correlation` in the console window.
* **Note:** Because you're running multiple correlations and some may be positive and some may be negative, there is no option to specify a one or two-tailed test.   

* Run the below code to calculate then view the correlation results


```r
corr_results <- mh %>%
  select(-Participant) %>%
  correlation(method = "pearson", 
              p_adjust = "bonferroni")

corr_results
```

Which produces the following output:


```r
knitr::kable(corr_results)
```



|Parameter1 |Parameter2 |          r|   CI|     CI_low|    CI_high|          t| df_error|         p|Method              | n_Obs|
|:----------|:----------|----------:|----:|----------:|----------:|----------:|--------:|---------:|:-------------------|-----:|
|Abil       |IQ         |  0.4511699| 0.95|  0.0681965|  0.7182564|  2.4245212|       23| 0.1415557|Pearson correlation |    25|
|Abil       |Home       |  0.7443192| 0.95|  0.4946735|  0.8804938|  5.3451643|       23| 0.0001194|Pearson correlation |    25|
|Abil       |TV         | -0.2881974| 0.95| -0.6134691|  0.1206755| -1.4433874|       23| 0.9743671|Pearson correlation |    25|
|IQ         |Home       |  0.2016786| 0.95| -0.2102033|  0.5527604|  0.9875083|       23| 1.0000000|Pearson correlation |    25|
|IQ         |TV         |  0.2455425| 0.95| -0.1656610|  0.5840118|  1.2147699|       23| 1.0000000|Pearson correlation |    25|
|Home       |TV         | -0.6476572| 0.95| -0.8303052| -0.3393758| -4.0765523|       23| 0.0027905|Pearson correlation |    25|

`corr_results` is a tibble that lists the results of each correlation with its corresponding statistics. Look through the table and then answer the following questions:

1. Is the correlation between `Abil` and `Home` positive or negative? <select class='webex-select'><option value='blank'></option><option value='answer'>Positive</option><option value=''>Negative</option></select>
2. This means that as `Abil` scores increase, `Home` scores will <select class='webex-select'><option value='blank'></option><option value='answer'>Increase</option><option value=''>Decrease</option></select>
3. What is the strongest positive correlation? <select class='webex-select'><option value='blank'></option><option value=''>Abil * IQ</option><option value='answer'>Abil * Home</option><option value=''>Abil * TV</option></select>
4. What is the strongest negative correlation? <select class='webex-select'><option value='blank'></option><option value=''>Abil * TV</option><option value=''>IQ * TV</option><option value='answer'>Home * TV</option></select>
5. Is the correlation between `Abil` and `IQ` significant? <select class='webex-select'><option value='blank'></option><option value=''>Yes</option><option value='answer'>No</option></select>
6. Is the correlation between `Abil` and `Home` significant? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
7. How would you describe the strength of the correlation between `Home` and `TV`? <select class='webex-select'><option value='blank'></option><option value=''>Weak</option><option value=''>Medium</option><option value='answer'>Strong</option></select>
8. Think back to the lecture. Why are we not calculating an effect size?


<div class='webex-solution'><button>Explain these answers</button>

1. Negative correlations are denoted by a negative r value.  
    2. Positive correlations mean that as one score goes up so does the other, negative correlations mean that as one score goes up the other goes down.  
    3 & 4. Remember that correlations take values from -1 - 1 and that the nearer to one in either direction the stronger the correlation (i.e., an r value of 0 would demonstrate a lack of any relationship.  
    5 & 6. The traditional cut-off for significance is .05. Anything below .05 is considered significant. Be careful to pay attention to decimal places.  
    7. Cohen's guidelines recommend weak = 1. - .3, medium = .3 - .5, strong > .5.  
    8. Because r is an effect size.

</div>
  

Nice work! So it can be really easy to run a lot of correlations at once. However, you need to remember about what is appropriate in research. You should not just wildly run every correlation you can and then write up your favourite. PreRegistration of ideas, or Registered Reports, helps reduce Questionable Research Practices, and this is just another example of where setting out in advance, what you plan to do, will prevent bad practice!

## Finished! {#corr-fin}

Excellent work today! You can now add running, interpreting and writing up correlations to the list of knowledge and skills in your research methods toolbox. Remember that actually a lot of the work is in the preparation of the data and really running the correlation is just one more function. It might be worthwhile repeating the first few activities with two other variables to test your understanding. If you have any questions, please post them on Teams.

## Test Yourself




Look at this code and answer the following questions:


```r
results <- correlation(data = mh, 
                       select = "IQ", 
                       select2 = "Home",  
                       method = "pearson", 
                       alternative = "two.sided")
```

1. What would this analysis show? <div class='webex-radiogroup' id='radio_PYNXCDXWZY'><label><input type="radio" autocomplete="off" name="radio_PYNXCDXWZY" value=""></input> <span>the effect of IQ on time spent reading at Home</span></label><label><input type="radio" autocomplete="off" name="radio_PYNXCDXWZY" value="answer"></input> <span>the relationship between IQ and the time spent reading at home</span></label><label><input type="radio" autocomplete="off" name="radio_PYNXCDXWZY" value=""></input> <span>the relationship between IQ and Reading Ability</span></label><label><input type="radio" autocomplete="off" name="radio_PYNXCDXWZY" value=""></input> <span>the relationship between IQ and the time spent watching TV at home</span></label></div>

2. What type of correlation analysis is it? <div class='webex-radiogroup' id='radio_TTNNLYDDOG'><label><input type="radio" autocomplete="off" name="radio_TTNNLYDDOG" value=""></input> <span>two-tailed spearman analysis</span></label><label><input type="radio" autocomplete="off" name="radio_TTNNLYDDOG" value="answer"></input> <span>two-tailed pearson analysis</span></label><label><input type="radio" autocomplete="off" name="radio_TTNNLYDDOG" value=""></input> <span>one-tailed pearson analysis</span></label><label><input type="radio" autocomplete="off" name="radio_TTNNLYDDOG" value=""></input> <span>one-tailed spearman analysis</span></label></div>


Now try running the code and then answering the following questions.

3. To three decimal places, what is the r-value of the correlation between IQ and the time spent reading at Home? <div class='webex-radiogroup' id='radio_FVHWTNFPYA'><label><input type="radio" autocomplete="off" name="radio_FVHWTNFPYA" value=""></input> <span>0.988</span></label><label><input type="radio" autocomplete="off" name="radio_FVHWTNFPYA" value=""></input> <span>0.334</span></label><label><input type="radio" autocomplete="off" name="radio_FVHWTNFPYA" value=""></input> <span>0.553</span></label><label><input type="radio" autocomplete="off" name="radio_FVHWTNFPYA" value="answer"></input> <span>0.202</span></label></div>


4. To three decimal places, what is the p-value of the correlation between IQ and the time spent reading at Home? <div class='webex-radiogroup' id='radio_XISQPQXAHD'><label><input type="radio" autocomplete="off" name="radio_XISQPQXAHD" value=""></input> <span>0.553</span></label><label><input type="radio" autocomplete="off" name="radio_XISQPQXAHD" value=""></input> <span>0.202</span></label><label><input type="radio" autocomplete="off" name="radio_XISQPQXAHD" value=""></input> <span>0.988</span></label><label><input type="radio" autocomplete="off" name="radio_XISQPQXAHD" value="answer"></input> <span>0.334</span></label></div>


5. What is the degrees of freedom of the correlation between IQ and the time spent reading at Home? <div class='webex-radiogroup' id='radio_VDOAXUEBCC'><label><input type="radio" autocomplete="off" name="radio_VDOAXUEBCC" value=""></input> <span>25</span></label><label><input type="radio" autocomplete="off" name="radio_VDOAXUEBCC" value=""></input> <span>0.988</span></label><label><input type="radio" autocomplete="off" name="radio_VDOAXUEBCC" value="answer"></input> <span>23</span></label><label><input type="radio" autocomplete="off" name="radio_VDOAXUEBCC" value=""></input> <span>0.553</span></label></div>



<div class='webex-solution'><button>Explain these answers</button>


This analysis is a two-tailed pearson correlation looking at the relationship between IQ and the amount of time spent reading at home. You can tell this from the two variables in the code being IQ and Home, and the code stating pearson, and two-sided (another name for two-tailed). If you run the analysis you will find that the result would be r(23) = .202, p = .334.

</div>


## Activity solutions {#corr-sols}

Below you will find the solutions to the above questions. Only look at them after giving the questions a good try and trying to find help on Google or Teams about any issues.

#### Activity 1 {#corr-a1sol}


```r
library(car)
library(correlation)
library(report)
library(psych)
library(tidyverse)
mh <- read_csv("MillerHadenData.csv")
```
  
#### Activity 3 {#corr-a3sol}

**The histogram of IQ**


```r
ggplot(data = mh, aes(x = IQ)) +
  geom_histogram()
```

**The qqPlot of IQ**


```r
qqPlot(x = mh$IQ)
```

<img src="09-correlation_files/figure-html/unnamed-chunk-16-1.png" width="100%" style="display: block; margin: auto;" />

```
## [1]  3 14
```

**The scatterplot**


```r
ggplot(data = mh, aes(x = Abil, y = IQ)) +
  geom_point()+
  geom_smooth(method = lm)+
  scale_x_continuous(name = "Reading Ability")
```

```
## `geom_smooth()` using formula 'y ~ x'
```

<img src="09-correlation_files/figure-html/unnamed-chunk-17-1.png" width="100%" style="display: block; margin: auto;" />

#### Activity 4 {#corr-a4sol}

**The scatterplot**

Based on the scatterplot we might suggest that as reading ability scores increase, IQ scores also increase and as such it would appear that our data is inline with our hypothesis that the two variables are positively correlated. This appears to be a medium strength relationship.

**The means and standard deviations**


```r
descriptives <- summarise(mh, 
                          Abil_mean = mean(Abil),
                          Abil_SD = sd(Abil),
                          IQ_mean = mean(IQ),
                          IQ_SD = sd(IQ))

descriptives
```

<div class="kable-table">

| Abil_mean|  Abil_SD| IQ_mean|    IQ_SD|
|---------:|--------:|-------:|--------:|
|     55.12| 6.084954|  100.04| 9.043782|

</div>

#### Activity 5 {#corr-a5sol}

**The correlation using `correlation()`**


```r
results <- correlation(data = mh, 
                       select = "IQ", 
                       select2 = "Abil",  
                       method = "pearson", 
                       alternative = "two.sided")

results
```

<div class="kable-table">

|Parameter1 |Parameter2 |         r|   CI|    CI_low|   CI_high|        t| df_error|         p|Method              | n_Obs|
|:----------|:----------|---------:|----:|---------:|---------:|--------:|--------:|---------:|:-------------------|-----:|
|IQ         |Abil       | 0.4511699| 0.95| 0.0681965| 0.7182564| 2.424521|       23| 0.0235926|Pearson correlation |    25|

</div>

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                                           |definition                                                                                                                                                                                                                                                                      |
|:------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|[alpha](https://psyteachr.github.io/glossary/a.html#alpha){class="glossary" target="_blank"}                                   |The cutoff value for making a decision to reject the null hypothesis                                                                                                                                                                                                            |
|[alternative hypothesis](https://psyteachr.github.io/glossary/a.html#alternative-hypothesis){class="glossary" target="_blank"} |the experimental hypothesis formed in Null Hypothesis Significance Testing and is the hypothesis that states that there will be a relationship between variables or an effect of one variable on the other                                                                      |
|[assumptions](https://psyteachr.github.io/glossary/a.html#assumptions){class="glossary" target="_blank"}                       |requirements about your data and your design that must be held for your analysis to have meaning                                                                                                                                                                                |
|[bonferroni](https://psyteachr.github.io/glossary/b.html#bonferroni){class="glossary" target="_blank"}                         |A correction for multiple comparisons where the accepted alpha level is adjusted by dividing it by the number of comparisons made                                                                                                                                               |
|[conservative analysis](https://psyteachr.github.io/glossary/c.html#conservative-analysis){class="glossary" target="_blank"}   |A conservative test is one that is more likely to result in more false negatives - i.e. missed findings - than a test considered less conservative                                                                                                                              |
|[correlation](https://psyteachr.github.io/glossary/c.html#correlation){class="glossary" target="_blank"}                       |The relationship two vectors have to each other.                                                                                                                                                                                                                                |
|[holm bonferroni](https://psyteachr.github.io/glossary/h.html#holm-bonferroni){class="glossary" target="_blank"}               |A correction for multiple comparisons where an ordinal iterative approach is used comparing each individual test to an adjusted p-value based on the order of p-values. Generally said to be less conservative than Bonferroni                                                  |
|[homoscedasticity](https://psyteachr.github.io/glossary/h.html#homoscedasticity){class="glossary" target="_blank"}             |that the spread of data around the line of best fit is equal on both side along the length of the line                                                                                                                                                                          |
|[hypothesis](https://psyteachr.github.io/glossary/h.html#hypothesis){class="glossary" target="_blank"}                         |A proposed explanation made on the basis of limited evidence as a starting point for further investigation.                                                                                                                                                                     |
|[inferential](https://psyteachr.github.io/glossary/i.html#inferential){class="glossary" target="_blank"}                       |Statistics that allow you to make predictions about or comparisons between data (e.g., t-value, F-value, rho)                                                                                                                                                                   |
|[line of best fit](https://psyteachr.github.io/glossary/l.html#line-of-best-fit){class="glossary" target="_blank"}             |otherwise known as the regression line, it is the line drawn between data points in a scatterplot that best divides the data in half. It is in fact a prediction of where data would fall for a given relationship strength and direction                                       |
|[multiple comparisons](https://psyteachr.github.io/glossary/m.html#multiple-comparisons){class="glossary" target="_blank"}     |An issue of running mutlitple tests which results in an increase in the false positive rate making it more likely that you will incorrectly reject the null hypothesis and accept the alternative hypothesis. The issue is resolved through correction for multiple comparisons |
|[negative relationship](https://psyteachr.github.io/glossary/n.html#negative-relationship){class="glossary" target="_blank"}   |a relationship between two variables where as one variable increases, the other variable also decreases                                                                                                                                                                         |
|[non significant](https://psyteachr.github.io/glossary/n.html#non-significant){class="glossary" target="_blank"}               |The conclusion where the p-value is greater than the critical alpha and at which the null hypothesis is retained                                                                                                                                                                |
|[normal distribution](https://psyteachr.github.io/glossary/n.html#normal-distribution){class="glossary" target="_blank"}       |A symmetric distribution of data where values near the centre are most probable.                                                                                                                                                                                                |
|[null hypothesis](https://psyteachr.github.io/glossary/n.html#null-hypothesis){class="glossary" target="_blank"}               |the defauly hypothesis in Null Hypothesis Significance Testing and is the hypothesis that states that there will be no effect or relationship in your study.                                                                                                                    |
|[pearson](https://psyteachr.github.io/glossary/p.html#pearson){class="glossary" target="_blank"}                               |a standardised measure of the linear relationship between two variables                                                                                                                                                                                                         |
|[positive relationship](https://psyteachr.github.io/glossary/p.html#positive-relationship){class="glossary" target="_blank"}   |a relationship between two variables where as one variable increases, the other variable also increases                                                                                                                                                                         |
|[q q plot](https://psyteachr.github.io/glossary/q.html#q-q-plot){class="glossary" target="_blank"}                             |A scatterplot created by plotting two sets of quantiles against each other, used to check if data come from a specified distribution                                                                                                                                            |
|[residual](https://psyteachr.github.io/glossary/r.html#residual){class="glossary" target="_blank"}                             |Defined as the deviation of an observation from a model&#39;s expected value.                                                                                                                                                                                                   |
|[scatterplot](https://psyteachr.github.io/glossary/s.html#scatterplot){class="glossary" target="_blank"}                       |a visualisation where each individual data point shows the value of an observation on twi variables.                                                                                                                                                                            |
|[significant](https://psyteachr.github.io/glossary/s.html#significant){class="glossary" target="_blank"}                       |The conclusion where the p-value is lower than the critical alpha and at which the null hypothesis is rejected                                                                                                                                                                  |
|[spearman](https://psyteachr.github.io/glossary/s.html#spearman){class="glossary" target="_blank"}                             |a standardised measure of the relationship between two variables that does not assume a linear relationship. Note that the relationship can be linear but it is not required.                                                                                                   |
|[variable](https://psyteachr.github.io/glossary/v.html#variable){class="glossary" target="_blank"}                             |an aspect about your sample or population that can be measured                                                                                                                                                                                                                  |

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!

<!--chapter:end:09-correlation.Rmd-->

# t-tests

Experiments where you compare results from two conditions or two groups are very common within Psychology as often we want to know if there is an effect of a given variable.  One of the really confusing things however about research design is that there are many names for the same type of design. To clarify:

* <a class='glossary' title='A study to compare the mean and spread of one group against a known value or population norm.'>One-sample</a> are used to study one group of people against a known norm or criterion - for example, comparing the mean IQ of a sample against a known population norm such as an IQ of 100.
* Independent-samples and <a class='glossary' target='_blank' title='Not varying within unit of observation, such that each has only one value' href='https://psyteachr.github.io/glossary/b#between-subjects'>between-subjects</a> designs mean the same thing - different participants in different conditions.
* In contrast, <a class='glossary' target='_blank' title='Varying such that each unit of observation has more than one value' href='https://psyteachr.github.io/glossary/w#within-subjects'>within-subjects</a>, dependent-samples, paired-samples, and repeated-measures all tend to mean the same participants in all conditions
* Matched-pairs design means different people in different conditions but you have matched participants across the conditions so that they are effectively the same person (e.g. age, IQ, Social Economic Status, etc)
* <a class='glossary' target='_blank' title='An experimental design that has both within-subject and between-subject factors.' href='https://psyteachr.github.io/glossary/m#mixed-design'>Mixed-design</a> is when there is a combination of within-subjects and between-subjects designs in the one experiment. For example, say you are looking at attractiveness and dominance of male and female faces. Everyone might see both male and female faces (within) but half of the participants do ratings of attractiveness and half of the participants do ratings of trustworthiness (between).

To get a better understanding of how some of these tests run we will look at running an example of a between-subjects t-test and a within-subjects t-test through a series of activities. Remember that the solutions are at the bottom of the page if you are stuck, and please do ask questions on the forums.

## Between-Subjects t-tests (two-sample)

We will begin by looking at the between-subjects t-test which is used for comparing the outcome in two groups of different people. Here we will be using data from Schroeder and Epley (2015) on the perception of people from their job applications. You can take a look at the Psychological Science article here, [Schroeder, J. and Epley, N. (2015). The sound of intellect: Speech reveals a thoughtful mind, increasing a job candidate's appeal. Psychological Science, 26, 277--891.](https://doi.org/10.1177/0956797615572906){target="_blank"}, if you like but it is not essential for completing the activities. The abstract from this article explains more about the different experiments conducted, and we will be specifically looking at the data set from Experiment 4, based on information from the [Open Stats Lab](https://sites.trinity.edu/osl/data-sets-and-activities/t-test-activities){target="_blank"}. The abstract reads:

> A person's mental capacities, such as intellect, cannot be observed directly and so are instead inferred from indirect cues. We predicted that a person's intellect would be conveyed most strongly through a cue closely tied to actual thinking: his or her voice. Hypothetical employers (Experiments 1-3b) and professional recruiters (Experiment 4) watched, listened to, or read job candidates' pitches about why they should be hired. These evaluators (the employers) rated a candidate as more competent, thoughtful, and intelligent when they heard a pitch rather than read it and, as a result, had a more favourable impression of the candidate and were more interested in hiring the candidate. Adding voice to written pitches, by having trained actors (Experiment 3a) or untrained adults (Experiment 3b) read them, produced the same results. Adding visual cues to audio pitches did not alter evaluations of the candidates. For conveying one's intellect, it is important that one's voice, quite literally, be heard.

To summarise, 39 professional recruiters from Fortune 500 companies evaluated job pitches of M.B.A. candidates from the University of Chicago Booth School of Business. The methods and results appear on pages 887-889 of the article if you want to look at them specifically for more details and the original data, in **wide** format, can be found at the [Open Stats Lab](https://drive.google.com/open?id=0Bz-rhZ21ShvOei1MM24xNndnQ00){target="_blank"} website for later self-directed learning. Today however, we will be working with a modified version in "tidy" format which can be downloaded below and what we plan to do is reproduce the results from the article on Pg 887.

### Data and Descriptives

As always, the first activity is about getting ourselves ready to analyse the data so try out the steps and if you need help, consult the earlier chapters.

#### Activity 1: Set-up {#ttest-a1}

* Open RStudio and set the working directory to your chapter folder. Ensure the environment is clear.
    * If you're using the Rserver, avoid a number of issues by restarting the session - click `Session` - `Restart R`
* Open a new R Markdown document and save it in your working directory. Call the file "ttests".   
* Download <a href="evaluators.csv" download>evaluators.csv</a> and <a href="ratings.csv" download>ratings.csv</a> and save them in your t-test folder. Make sure that you do not change the file names at all.
  * If you prefer you can download the data in a [zip folder by clicking here](data/chpt10/PsyTeachR_FQA_Chpt10-data-between.zip){target="_blank"}
  * Remember not to change the file names at all and that `data.csv` is not the same as `data (1).csv`.
* Delete the default R Markdown welcome text and insert a new code chunk that loads the following packages, in this specific order, using the `library()` function. Remember the solutions if needed.
  * Load the packages in this order, `Hmisc`, `broom`, `car`,`effectsize`, `report`, and `tidyverse`
  * again we have not used some of these packages so you will likely need to install some of them using `install.packages()`. Remember though that you should only do this on your own machine and only in the console window. If you are using the RServer you will not need to install them.
* Finally, load the data held in `evaluators.csv` as a tibble into an object named `evaluators` using `read_csv()`. 



Remember to have a look at your data to help you understand the structure and the layout of the data. You can do this in whatever way you prefer. 

Now that we have our data, and have explored it, there is a few things we can do to make working with it a bit easier. If you look at the data, and in particular the `sex` column, you will see it is actually coded as <a class='glossary' target='_blank' title='A data type representing a real decimal number or integer.' href='https://psyteachr.github.io/glossary/n#numeric'>numeric</a> but we will want to treat it as <a class='glossary' target='_blank' title='Data that can only take certain values, such as types of pet.' href='https://psyteachr.github.io/glossary/c#categorical'>categorical</a>. Secondly, it can be tricky to work with 1s and 2s when you mean people, so we can "recode" the variables into labels that are easier to work with. That is what we will do here using a combination of `mutate()`, which we already know, and the `recode()` function from the `dplyr` package that is loaded in as part of the `tidyverse`, and the `as.factor()` function from `base`. Converting categorical data to factors will make it easier to work with in visualisations and analysis.

#### Activity 2: Explore the dataset {#ttest-a2}

In a new code chunk, copy the code below and see if you can follow it.

* First we use `mutate()` and `recode()` to recode `sex` into a new variable called `sex_labels` so that `1` = `male` and `2` = `female`. 
  * Be careful using `recode()` as there are multiple functions in different packages called with the same name so it is better to use the `package::function()` approach and specify `dplyr::recode()` to get the right one.
* Then we use `mutate()` and `as.factor()` to overwrite `sex_labels` and `condition` as factors.  


```r
evaluators <- evaluators %>%
  mutate(sex_labels = dplyr::recode(sex, "1" = "male", "2" = "female"),
         sex_labels = as.factor(sex_labels),
         condition = as.factor(condition))
```

Now see if you can create a count of the different sex labels to answer the following question. One approach would be `group_by() %>% count()` but what would you group by? Maybe store this tibble in an object called `eval_counts`.



* How many participants were noted as being female: <input class='webex-solveme nospaces' size='2' data-answer='["30"]'/>
* How many participants were noted as being male: <input class='webex-solveme nospaces' size='1' data-answer='["4"]'/>
* How many data points are missing for `sex`? <input class='webex-solveme nospaces' size='1' data-answer='["5"]'/>

#### Activity 3: Ratings {#ttest-a3}

Excellent work. Our evaluator data is ready to work with and we are now going to calculate what is called an "overall intellect rating" given by each evaluator, calculated by averaging the ratings of `competent`, `thoughtful` and `intelligent` from each evaluator; held within `ratings.csv`. This overall rating will measure how intellectual the evaluators thought candidates were, depending on whether or not the evaluators **read** or **listened** to the candidates' resume pitches. **Note**, however, we are not looking at ratings to individual candidates; we are looking at overall ratings for each evaluator. This is a bit confusing but makes sense if you stop to think about it a little. What we are interested in is how the medium they received the resume impacted their rating of the candidate. Once we have done that, we will then combine the overall intellect rating with the overall impression ratings and overall hire ratings for each evaluator, with the end goal of having a tibble called `ratings2` - which has the following structure:


| eval_id|Category   | Rating|condition |sex_labels |
|-------:|:----------|------:|:---------|:----------|
|       1|hire       |  6.000|listened  |female     |
|       1|impression |  7.000|listened  |female     |
|       1|intellect  |  6.000|listened  |female     |
|       2|hire       |  4.000|listened  |female     |
|       2|impression |  4.667|listened  |female     |
|       2|intellect  |  5.667|listened  |female     |

The following steps describe how to create the above tibble and it would be good practice to try this out yourself. Look at the table and think what do I need? The trick when doing data analysis and data wrangling is to first think about what you want to achieve - the end goal - and then think about what functions you need to use to get there. The solution is hidden just below the stpes of course if you want to look at it. Let's look at the steps. Steps 1, 2 and 3 calculate the new overall `intellect` rating. Steps 4 and 5 combine this rating to all other information.

1. Load the data found in `ratings.csv` as a tibble into an object called `ratings`. (e.g. read the csv)

2. `filter()` only the relevant variables (**thoughtful**, **competent**, **intelligent**) into a new tibble stored in an objected called something useful (we will call ours `iratings`), and then calculate a mean `Rating` for each evaluator (e.g. group_by & summarise).  

3. Add on a new column called `Category` where every entry is the word `intellect`. This tells us that every number in this tibble is an intellect rating.  (e.g. mutate)

4. Now create a new tibble called `ratings2` and filter into it just the "impression" and "hire" ratings from the original `ratings` tibble. 

5. Next, bind this tibble with the tibble you created in step 3 to bring together the intellect, impression, and hire ratings, in `ratings2`.  (e.g. `bind_rows(object1, object2)`)

6. Join `ratings2` with the `evaluator` tibble that we created in Task 1 (e.g. `inner_join()`). Keep only the necessary columns as shown above (e.g. `select()`) and arrange by Evaluator and Category (e.g. `arrange()`).


<div class='webex-solution'><button>Our approach to this</button>


```r
# 1. load in the data
ratings <- read_csv("book/ratings.csv")

# 2. first step: pull out the ratings associated with intellect
iratings <- ratings %>%
  filter(Category %in% c("competent", "thoughtful", "intelligent"))

# second step: calculate means for each evaluator
imeans <- iratings %>%
  group_by(eval_id) %>%
  summarise(Rating = mean(Rating))

# 3. add Category variable 
# this way we can combine with 'impression' and 'hire' into a single table, very useful!
imeans2 <- imeans %>%
  mutate(Category = "intellect")

# 4., 5. & 6. combine into a single table
ratings2 <- ratings %>%
  filter(Category %in% c("impression", "hire")) %>%
  bind_rows(imeans2) %>%
  inner_join(evaluators, "eval_id") %>%
  select(-age, -sex) %>%
  arrange(eval_id, Category)
```

</div>


* Finally, calculate the n, mean and SD for each condition and category to help with reporting the descriptive statistics.


```r
group_means <- ratings2 %>%
  group_by(condition, Category) %>%
  summarise(n = n(), m = mean(Rating), sd = sd(Rating))
```

```
## `summarise()` has grouped output by 'condition'. You can override using the `.groups` argument.
```

### Visualising two groups

Brilliant! Now that we have our data in a workable fashion, we are going to start looking at some visualisations and making figures. You should **always** visualise your data before you run a statistical analysis. Visualisations serve as part of the descriptive measures and they help you interpret the results of the test but they also give you an understanding of the spread of your data as part of the test assumptions. For data with a categorical IV, we are going to look at using the violin-boxplots that we saw in the introduction to visualisation chapter. In the past people would have tended to use barplots but as <a href="https://link.springer.com/article/10.3758/s13423-012-0247-5" target = "_blank">Newman and Scholl (2012)</a> point out, barplots are misleading to viewers about how the underlying data actually looks. You can read that paper if you like, for more info, but hopefully by the end of this section you will see why violin-boxplots are more informative.

#### Activity 4: Visualisation {#ttest-a4}

We will visualise the intellect ratings for the listened and the read conditions. The code we will use to create our figure is as follows with the explanation below. Put this code in a new code chunk and run it.


```r
ratings2 %>%
  filter(Category == "intellect") %>%
ggplot(aes(x = condition, y = Rating)) +
  geom_violin(trim = TRUE) +
  geom_boxplot(aes(fill = condition), width = .2, show.legend = FALSE) + 
  stat_summary(geom = "pointrange", fun.data = "mean_cl_normal")  +
  labs(x = "Condition", y = "Rating Score") +
  geom_jitter(height = .1, width = .2)
```

The first part of the code uses a pipe to filter the data to just the intellect rating:

* `ratings %>% filter(Category == "intellect)` is the same as `filter(ratings, Category == "intellect")`
* this code also reflects nicely the difference between pipes (`%>%`) used in wrangling and the `+` used in the visualisations with ggplot. Notice that we switch from pipes to plus when we start adding layers to our visualisation.

The main parts of the code to create the violin-boxplot above are:

* ggplot() which creates our base layer and sets our data and our x and y axes.
* `geom_violin()` which creates the density plot. The reason it is called a violin plot is because if your data are normally distributed it should look something like a violin.  
* `geom_boxplot()` which creates the boxplot, showing the median and inter-quartile range (see [here](https://towardsdatascience.com/understanding-boxplots-5e2df7bcbd51){target="_blank"} if you would like more information). The boxplot can also give you a good idea if the data are skewed - the median line should be in the middle of the box. The more the median is moved towards one of th extremities of the box, the more your data is likely to be skewed.  
* `geom_jitter()` can be used to show individual data points in your dataset and you can change the width and height of the jitter. Note that this uses a randomised method to display the points so you will get a different output each time you run it.
* And finally, we will use `stat_summary()` for displaying the mean and confidence intervals. Within this function, `fun.data` specifies the a summary function that gives us the summary of the data we want to plot, in this case, `mean_cl_normal` which will calculate the mean plus the upper and lower confidence interval limits. You could also specify `mean_se` here if you wanted standard error. Finally, `geom` specifies what shape or plot we want to use to display the summary, in this case we want a `pointrange` (literally a point (the mean) with a range (the CI)).

The figure will look like this:

<div class="figure" style="text-align: center">
<img src="10-t-tests_files/figure-html/plot1a-1.png" alt="Violin-boxplot of the evaluator data" width="100%" />
<p class="caption">(\#fig:plot1a)Violin-boxplot of the evaluator data</p>
</div>

An alternative version would be this shown below. Perhaps compare the two codes and see if you can see what makes the differences:


```r
ratings2 %>%
  filter(Category == "intellect") %>%
ggplot(aes(x = condition, y = Rating)) +
  geom_violin(trim = FALSE) +
  geom_boxplot(aes(fill = condition), width = .2, show.legend = FALSE) + 
  stat_summary(geom = "pointrange", fun.data = "mean_cl_normal") +
  labs(x = "Condition", y = "Rating Score")
```

<div class="figure" style="text-align: center">
<img src="10-t-tests_files/figure-html/plot2-1.png" alt="Violin-boxplot of the evaluator data" width="100%" />
<p class="caption">(\#fig:plot2)Violin-boxplot of the evaluator data</p>
</div>

Try to answer the following question:

* In which condition did the evaluators give the higher ratings overall? <select class='webex-select'><option value='blank'></option><option value='answer'>listened</option><option value=''>read</option></select>
* Would the descriptives (means, sds, figure) be inline with the hypothesis that evaluators favour resumes they have listened to more than resumes they have read? <select class='webex-select'><option value='blank'></option><option value='answer'>yes</option><option value=''>no</option></select>

Nice and informative figure huh? It gives a good representation of the data in the two conditions, clearly showing the spread and the centre points. If you compare this to Figure 7 in the original paper you see the difference. We actually get much more information with our approach. We even get a sense that maybe the data is questionable on whether it is skewed or not, but more on that below. 

The code is really useful as well so you know it is here if you want to use it again. But maybe have a play with the code to try out things to see what happens. For instance:

* Try setting `trim = TRUE`, `show.legend = FALSE`, and/or altering the value of `width` to see what these arguments do.
* change the `Category == "intellect"` to `Category == "hire"` or `Category == "impression"` to create visualisations of the other conditions.

### Assumptions

Great. We have visualised our data as well and we have been able to make some descriptive analysis about what is going on. Now we want to get ready to run the actual analysis. But one final thing we are going to decide is which t-test? But hang on you say, didn't we decide that? We are going to run a between-subjects t-test! Right? Yes! But, and you know what we are about to say, there is more than one between-subjects t-test you can run.  The two common ones are:

* Student's between-subjects t-test
* Welch's between-subjects t-test

We are going to recommend that, at least when doing the analysis by code, you should use Welch's between-subjects t-test for the reasons explained in this paper by [Delarce et al,m (2017)](https://www.rips-irsp.com/article/10.5334/irsp.82/){target="_blank"} Now you don't have to read that paper but effectively, the Welch's between-subjects t-test is better at maintaining the false positive rate of your test ($\alpha$, usually set at $\alpha$ = .05) at the requested level. So we will show you how to run a Welch's t-test here.

The assumptions for a Welch's between-subjects t-test are:

1. The data are continuous, i.e. interval/ratio
2. The data are independent
3. The residuals are normally distributed for each group

We know that 1 and 2 are true from the design of the experiment, the measures used, and by looking at the data. To test assumption 3, we can create a Q-Q plots of the **residuals**. For a between-subject t-test the residuals are the difference between the mean of each group and each data point. E.g., if the mean of group A is 10 and a participant in group A scores 12, the residual for that participant is 2.

* Thinking back to your lectures, if you ran a Student's t-test instead of a Welch t-test, what would the 4th assumption be? <select class='webex-select'><option value='blank'></option><option value='answer'>Homogeneity of variance</option><option value=''>Homoscedascity</option><option value=''>Nominal data</option></select>

#### Activity 5: Assumptions {#ttest-a5}

* Run the below code to calculate then plot the residuals for the "listened" condition on "intellect" ratings. 


```r
listened_intellect_residuals <- ratings2 %>%
  filter(condition == "listened", Category == "intellect") %>%
  mutate(group_resid = Rating - mean(Rating)) %>%
  select(group_resid)

qqPlot(listened_intellect_residuals$group_resid)
```

* Run the below code to calculate then plot the residuals for the "read" condition on "intellect" ratings. 


```r
read_intellect_residuals <- ratings2 %>%
  filter(condition == "read", Category == "intellect") %>%
  mutate(group_resid = Rating - mean(Rating)) %>%
  select(group_resid)

qqPlot(read_intellect_residuals$group_resid)
```

If we then look at our plots we get something that looks like this for the listened condition:

<div class="figure" style="text-align: center">
<img src="10-t-tests_files/figure-html/qqplot3-1.png" alt="Residual plots of listened condition. Each circle represents an indivudal rater. If data is normally distributed then it should fall close to or on the diagonal line." width="100%" />
<p class="caption">(\#fig:qqplot3)Residual plots of listened condition. Each circle represents an indivudal rater. If data is normally distributed then it should fall close to or on the diagonal line.</p>
</div>

```
## [1] 6 8
```

And something like this for the read condition.

<div class="figure" style="text-align: center">
<img src="10-t-tests_files/figure-html/qqplot4-1.png" alt="Residual plots of read intellect condition. Each circle represents an indivudal rater. If data is normally distributed then it should fall close to or on the diagonal line." width="100%" />
<p class="caption">(\#fig:qqplot4)Residual plots of read intellect condition. Each circle represents an indivudal rater. If data is normally distributed then it should fall close to or on the diagonal line.</p>
</div>

```
## [1] 11 18
```

What you are looking for is for the data to fall close to the diagonal line. Looking at the plots, maybe we could suggest that the "listened" condition is not so great as there is some data points moving away from the line at the far ends. The "read" condition seems a bit better, at least subjectively! There will always be some deviation from the diagonal line but at perhaps most of the data in both plots is relatively close to their respective diagonal lines.  

But in addition to the Q-Q plots we can also run a test on the residuals known as the **Shapiro-Wilk** test. The Shapiro-Wilk's test has the alternative hypothesis that the data is significantly different from normal. As such, if you find a significant result using the test then the interpretation is that your data is not normal. If you find a non-significant finding then the interpretation is that your data is not significantly different from normal. One technical point is that the test doesn't actually say your data is normal either but just that it is not significantly different from normal. Again, remember that assumptions have a degree of subjectivity to them. We use the `shapiro.wilk()` function from the base package to run the Shapiro-Wilk's test.

* In a new code chunk, run both lines of code below and look at their output. 


```r
shapiro.test(x = listened_intellect_residuals$group_resid)
shapiro.test(x = read_intellect_residuals$group_resid)
```

Try to answer the following questions:

* According to the Shapiro-Wilk's test, is the data normally distributed for the listened condition? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
* According to the Shapiro-Wilk's test, is the data normally distributed for the read condition? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>

So as you can see, the p-value for the listened condition is p = .174, and the p-value for the read condition is p = .445. So here we are in an interesting position that often happens. The figures for "listened" is a bit unclear, but the figure for "read" looks ok and both tests show a non-significant difference from normality. What do we do? Well we combine our knowledge of our data to make a reasoned decision. In this situation the majority of our information is pointing to the data being normal. However, there are known issues with the Shapiro-Wilks test when there are small sample sizes so we must always take results like this with some caution. It is never a good idea to run a small sample such as this and so in reality we might want to design a study that has larger sample groups. All that said, here it would not be unreasonable to take the assumption of normality as being held.

<div class="info">
<p>For info though, here are some options if you are convinced your data is nor normal.</p>
<ol style="list-style-type: decimal">
<li>Transform your data to try and normalise the distribution. We won't cover this but if you'd like to know more, <a href="https://www.researchgate.net/profile/Jason_Osborne2/publication/200152356_Notes_on_the_Use_of_Data_Transformations/links/0deec5295f1eb10df8000000.pdf">this page</a> is a good start. Not usually recommended these days but some still use it.</li>
<li>Use a non-parametric test. The non-parametric equivalent of the independent t-test is the Mann-Whitney and the equivalent of the paired-samples t-test is the Wilcoxon signed-ranks test. Though more modern permutation tests are better. Again we won't cover these here but useful to know if you read them in a paper.</li>
<li>Do nothing. <a href="https://www.rips-irsp.com/articles/10.5334/irsp.82/">Delacre, Lakens &amp; Leys, 2017</a> argue that with a large enough sample (&gt;30), the Welch test is robust to deviations from assumptions. With very large samples normality is even less of an issue, so design studies with large samples.</li>
</ol>
</div>

### Inferential analysis

Now that we have checked our assumptions and our data seems to fit our Welch's t-test we can go ahead and run the test. We are going to conduct t-tests for the Intellect, Hire and Impression ratings separately; each time comparing evaluators' overall ratings for the listened group versus overall ratings for the read group to see if there was a significant difference between the two conditions: i.e. did the evaluators who **listened** to pitches give a significant higher or lower rating than evaluators that **read** pitches.

#### Activity 6: Running the t-test {#ttest-a6}

* First, create separate objects for the intellect, hire, and impression data using `filter()`. We have completed intellect object for you so you should replace the NULLs in the below code to create one for `hire` and `impression`.




```r
intellect <- filter(ratings2, Category == "intellect")
hire <- NULL
impression <- NULL 
```

And we are finally ready to run the t-test. It is funny right, as you may have realised by now, most of the work in analysis involves the set-up and getting the data ready, running the tests is generally just one more function. To conduct the t-test we will use `t.test()` function from `base` which takes the following format called the **formula syntax**:


```r
t.test(DV_column_name ~ IV_column_name, 
       paired = FALSE,
       data = my_object)
```

* `~` is called a tilde. It can be read as 'by' as in "analyse the DV by the IV".  
* The variable on the left of the tilde is the dependent or outcome variable, `DV_column_name`.
* The variable(s) on the right of the tilde is the independent or predictor variable, `IV_column_name`.  
* and `paired = FALSE` indicates that we do not want to run a paired-samples test and that our data is from a between-subjects design.

So let's run our first test:

* In a new code chunk, type and run the below code, and thenview the output by typing `intellect_t` in the console.


```r
intellect_t <- t.test(Rating ~ condition, 
                      paired = FALSE, 
                      data = intellect,
                      alternative = "two.sided")
```

Similar to when we used `cor.test()` for correlations, the output of `t.test()` is a list type object which can make it harder to work with. This time, we are going to show you how to use the function `tidy()` from the `broom` package to convert the output to a tidyverse format.

* Run the below code. You can read it as "take what is in the object `intellect_t` and try to tidy it into a tibble".  
* View the object by clicking on `results_intellect` in the environment.  


```r
results_intellect <- intellect_t %>%
  tidy()
```

As you will see, `results_intellect` is now in a nice tibble format that makes it easy to extract individual values. It is worth looking at the values with the below explanations:

* `estimate` is the difference between the two means (alphabetically entered as mean 1 minus mean 2)
* `estimate1` is the mean of group 1
* `estimate2` is the mean of group 2  
* `statistic` is the t-statistic  
* `p.value` is the p-value  
* `parameter` is the degrees of freedom  
* `con.low` and `conf.high` are the confidence interval of the `estimate`
* `method` is the type of test, Welch's, Student's, paired, or one-sample
* `alternative` is whether the test was one or two-tailed  

And now that we know how to run the test and tidy it, try the below:



* Complete the code below in a new code chunk by replacing the NULLs to run the t-tests for the hire and impression ratings, don't tidy them yet.


```r
hire_t <- NULL
impression_t <- NULL
```

* And now tidy the data into the respective objects - `hire_t` into `results_hire`, etc.


```r
results_hire <- NULL
results_impression <- NULL
```

Be sure to look at each of your tests and see what the outcome of each was. To make that easier, we are going join all the results of the t-tests together using `bind_rows()` - which we can do because all the tibbles have the same column names after we passed them through `tidy()`. 

* Copy and run the below code. First, it specifies all of the individual tibbles you want to join and gives them a label (hire, impression, intellect), and then you specify what the ID column should be named (test).


```r
results <- bind_rows(hire = results_hire, 
                     impression = results_impression, 
                     intellect = results_intellect, 
                     .id = "test")
```

Which produces the below:


|    test    | estimate | estimate1 | estimate2 | statistic |  p.value  | parameter | conf.low  | conf.high |         method          | alternative |
|:----------:|:--------:|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|:-----------------------:|:-----------:|
|    hire    | 1.825397 | 4.714286  | 2.888889  | 2.639949  | 0.0120842 | 36.85591  | 0.4241979 | 3.226596  | Welch Two Sample t-test |  two.sided  |
| impression | 1.894333 | 5.968333  | 4.074000  | 2.817175  | 0.0080329 | 33.80061  | 0.5275086 | 3.261158  | Welch Two Sample t-test |  two.sided  |
| intellect  | 1.986722 | 5.635000  | 3.648278  | 3.478555  | 0.0014210 | 33.43481  | 0.8253146 | 3.148130  | Welch Two Sample t-test |  two.sided  |

And looking along the line at the p-values we might have some significant differences. However, we have to remember to consider multiple comparisons.

#### Activity 7: Correcting for multiple comparisons {#ttest-a7}

Because we have run three t-tests, we are actually increasing our false positive rate due to what is called familywise error - essentially, instead of a false positive rate of .05, we would have a false positive rate of 1-(1-.05)^3 = 0.142625, where the "3" in the formula is the number of tests we ran. To correct for this we can apply the multiple comparison correction just like we did with correlations when we ran a lot of correlations. So, we're going to add on a column to our `results` tibble that shows the adjusted p-values using `p.adj()` and `mutate()`. 

* Type and run the below code in a new code chunk and have a look at the output.
  * inside the `p.adjust()`, `p.value` says what column the p-values are in, and `bonferroni` says what adjustment to use.


```r
results_adj <- results %>%
  mutate(p.adjusted = p.adjust(p = p.value, 
                               method = "bonferroni"))
```

Looking at the adjusted p-values, try to answer the following questions:

* Listened is significantly more preferred in the `hire` condition after adjusting for multiple comparisons? <select class='webex-select'><option value='blank'></option><option value='answer'>TRUE</option><option value=''>FALSE</option></select>
* Listened is significantly more preferred in the `impression` condition after adjusting for multiple comparisons? <select class='webex-select'><option value='blank'></option><option value='answer'>TRUE</option><option value=''>FALSE</option></select>
* Listened is significantly more preferred in the `intellect` condition after adjusting for multiple comparisons? <select class='webex-select'><option value='blank'></option><option value='answer'>TRUE</option><option value=''>FALSE</option></select>

### Effect Size

As you can see, even after correcting for multiple comparisons, our effects are still significant and we have maintained our false positive rate. But one more thing we can add is the effect size. Remember that some effects are significant and large, some are significant and medium, and some are significant and small. The effect size tells us the magnitude of the effect size in a way we can compare across studies - it is said to be a standardised - and the common effect size for a t-test is called Cohen's D.

#### Activity 8: Effect size {#ttest-a8}

Whilst Cohen's D is relatively straightforward by hand, here we will use the function `cohens_d()` from the `effectsize` package. The code is similar to the syntax for `t.test()`. 



* The code to run the Cohen's D for intellect has been completed below.
  * The first argument should specify the formula, using the same syntax as `t.test()`, that is `dv ~ iv`.
  * `pooled_sd` should be `FALSE` if you ran a Welch test where the variances are not assumed to be equal and `TRUE` if you ran a regular Student's t-test.
* Run and complete the code below by replacing the NULLs to calculate the effect sizes for hire and impression


```r
intellect_d <- cohens_d(Rating ~ condition, 
                      pooled_sd = FALSE, 
                      data = intellect)
hire_d <- NULL
impression_d <- NULL
```

### Interpretation

Great Work!  But let's take a second to recap on our understanding of the data.

#### Activity 9: Interpreting the results {#ttest-a9}

* Were your results for `hire` significant? Enter the mean estimates and t-test results (means and t-value to 2 decimal places, p-value to 3 decimal places). Use the adjusted p-values:

    + Mean `estimate1` (listened condition) = <input class='webex-solveme nospaces' size='4' data-answer='["4.71"]'/>  
    
    + Mean `estimate2` (read condition) = <input class='webex-solveme nospaces' size='4' data-answer='["2.89"]'/>  
    
    + t(<input class='webex-solveme nospaces' size='5' data-answer='["36.86"]'/>) = <input class='webex-solveme nospaces' size='4' data-answer='["2.64"]'/>, p = <input class='webex-solveme nospaces' size='5' data-answer='["0.036",".036"]'/>  
    

* Were your results for `impression` significant? Enter the mean estimates and t-test results (means and t-value to 2 decimal places, p-value to 3 decimal places):

    + Mean`estimate1` (listened condition) = <input class='webex-solveme nospaces' size='4' data-answer='["5.97"]'/>  
    
    + Mean `estimate2` (read condition) = <input class='webex-solveme nospaces' size='4' data-answer='["4.07"]'/>  
    
    + t(<input class='webex-solveme nospaces' size='5' data-answer='["33.80","33.8"]'/>) = <input class='webex-solveme nospaces' size='4' data-answer='["2.82"]'/>, p = <input class='webex-solveme nospaces' size='5' data-answer='["0.024",".024"]'/> 

* According to Cohen's (1988) guidelines, the effect sizes for all three tests are <select class='webex-select'><option value='blank'></option><option value=''>Small</option><option value=''>Medium</option><option value='answer'>Large</option></select>

### Write-Up

And then finally on the between-subjects t-test, we should look at the write up.

#### Activity 10: Write-up {#ttest-a10}

If you refer back to the original paper on pg 887, you can see, for example, that the authors wrote:

**In particular, the recruiters believed that the job candidates had greater intellect—were more competent, thoughtful, and intelligent—when they listened to pitches (M = 5.63, SD = 1.61) than when they read pitches (M = 3.65, SD = 1.91), t(37) = 3.53, p < .01, 95% CI of the difference = [0.85, 3.13], d = 1.16.**

If we were to compare our findings, we would have something like the below:

**A bonferroni-corrected Welch t-test found that recruiters rated job candidates as more intellectual when they listened to resumes (M = 5.64, SD = 1.61) than when they read resumes (M = 3.65, SD = 1.91), t(33.43) = 3.48, p = 0.004, 95% CI of the difference = [0.83, 3.15], d = 1.12.**

You can create this same paragraph, using code, by copying and pasting the below **exactly** into **white space** in your R Markdown document and then knitting the file. 


```r
A bonferroni-corrected Welch t-test found that recruiters rated job candidates as more intellectual when they listened to resumes (M = `r results_intellect$estimate1%>% round(2)`, SD = `r round(group_means$sd[3], 2)`) than when they read resumes (M = `r results_intellect$estimate2%>% round(2)`, SD = `r round(group_means$sd[6], 2)`), t(`r round(results_intellect$parameter, 2)`) = `r round(results_adj$statistic[3],2)`, p = `r results_adj$p.adjusted[3] %>% round(3)`, 95% CI of the difference = [`r round(results_intellect$conf.low, 2)`, `r round(results_intellect$conf.high, 2)`], d = `r round(intellect_d$Cohens_d,2)`. 
```

Note that we haven't replicated the analysis exactly - the authors of this paper conducted Student's t-test whilst we have conducted Welch tests and we've also applied a multiple comparison correction. But you can look at the two examples and see the difference. It would also be worthwhile trying your own write-up of the two remaining conditions before moving on to within-subjects t-tests. 


## Within-subjects (paired-samples)

For the final activity we will run a paired-samples t-test for a within-subject design but we will go through this one more quickly and just point out the differences to the above. For this example we will again draw from the [Open Stats Lab](https://sites.trinity.edu/osl/data-sets-and-activities/t-test-activities) and look at data from the data in [Mehr, S. A., Song. L. A., & Spelke, E. S. (2016). For 5-month-old infants, melodies are social. Psychological Science, 27, 486-501.](https://journals.sagepub.com/stoken/default+domain/d5HcBHg85XamSXGdYqYN/full){target = "_blank"}. 

The premis of the paper is that parents often sing to their children and, even as infants, children listen to and look at their parents while they are sung to. The authors sought to explore the psychological function that music has for parents and infants, by examining the research question that particular melodies may convey important social information to infants. More specifically, that common knowledge of songs and melodies convey information about social affiliation. The authors argue that melodies are shared within social groups. Whereas children growing up in one culture may be exposed to certain songs as infants (e.g., “Rock-a-bye Baby”), children growing up in other cultures (or even other groups within a culture) may be exposed to different songs. Thus, when a novel person (someone who the infant has never seen before) sings a familiar song, it may signal to the infant that this new person is a member of their social group.

To test this the researchers recruited 32 infants and their parents to take part in the following experiment. During their first visit to the lab, the parents were taught a new lullaby (one that neither they nor their infants had heard before). The experimenters asked the parents to sing the new lullaby to their child every day for the next 1-2 weeks. Following this 1-2 week exposure period, the parents and their infant returned to the lab to complete the experimental portion of the study. Infants were first shown a screen with side-by-side videos of two unfamiliar people, each of whom were silently smiling and looking at the infant. The researchers recorded the looking behaviour (or gaze) of the infants during this ‘baseline’ phase. Next, one by one, the two unfamiliar people on the screen sang either the lullaby that the parents learned or a different lullaby (that had the same lyrics and rhythm, but a different melody). Finally, the infants saw the same silent video used at baseline, and the researchers again recorded the looking behaviour of the infants during this ‘test’ phase. For more details on the experiment’s methods, please refer to Mehr et al. (2016) Experiment 1. 

### The Data

#### Activity 11: Getting the data ready {#ttest-a11}

* First, download <a href="Mehr Song and Spelke 2016 Experiment 1.csv" download>Mehr Song and Spelke 2016 Experiment 1.csv</a> by clicking on the link and putting it into your working directory.
  * again if easier you can download the data as [a zip file by clicking this link](data/chpt10/PsyTeachR_FQA_Chpt10-data-between.zip).
* Next, type and run the below code in a new code chunk. The code loads in the data and then does some wrangling to get the data into a working format:
  * it filters so we just have the first experiment from the paper
  * selects the id and the preferential looking time of babies at the baseline stage and at the test stage.
  * finally it renames the two preferential looking time columns to have names that are easier to work with using the `rename()` function.
  

```r
gaze <- read_csv("Mehr Song and Spelke 2016 Experiment 1.csv") %>%
  filter(exp1 == 1) %>%
  select(id,
         Baseline_Proportion_Gaze_to_Singer,
         Test_Proportion_Gaze_to_Singer) %>%
  rename(baseline = Baseline_Proportion_Gaze_to_Singer,
         test = Test_Proportion_Gaze_to_Singer)
```

### Assumptions

So now that we have our data ready to work with, and be sure to look at it to get an understanding of the data, we want to consider the assumptions of the within-subjects t-test.

The assumptions for this t-test are a little different (although very similar) to the between-subjects t-tests above. They are

1. The data is continuous, i.e. interval/ratio 
2. All participants should appear in both conditions/groups. 
3. The residuals are normally distributed. 

Aside from the data being paired rather than independent, i.e. it is the same participants in two conditions, rather than two groups of people in different conditions, the key difference is that for the within-subjects test, the data is actually determined as the difference between the scores in the two conditions for each participant. So for example, say participant one scores 10 in condition 1 and 7 in condition 2, then there data is actually 3, and you do that for all participants. So it isn't looking at what they scored in either condition by itself, but what was the difference between conditions. And it is that data that must be continuous and that the residuals must be normally distributed for.


#### Activity 12: Assumptions {#ttest-a12}

* Type and run the below code to first calculate the difference scores (`diff`) and then the residuals (`group_resid`).
* next it plots the Q-Q plot of the residuals before carrying out a Shapiro-Wilk's test on the residuals


```r
gaze_residual <- gaze %>%
  mutate(diff = baseline - test) %>%
  mutate(group_resid = diff - mean(diff))

qqPlot(gaze_residual$group_resid)

shapiro.test(gaze_residual$group_resid)
```

And if we look at the plot we see:

<img src="10-t-tests_files/figure-html/unnamed-chunk-4-1.png" width="100%" style="display: block; margin: auto;" />

```
## [1] 22 29
```

and the Shapiro-Wilk's suggests:


```
## 
## 	Shapiro-Wilk normality test
## 
## data:  gaze_residual$group_resid
## W = 0.97818, p-value = 0.7451
```

Now as we saw above, with the Q-Q plot we want the data to fall approximately on the diagonal line, and with the Shapiro-Wilks test we are looking for a non-significant finding.  Based on those two tests, we can therefor say that our data meets the assumption of normality and so we can proceed.

### Descriptives

Now we are going to look at some descriptives. It made sense to keep the data in wide-form until this point to make it easy to calculate a column for the difference score, but now we will transform it to tidy data so that we can easily create descriptives and plot the data using `tidyverse` tools.

#### Activity 13: Descriptives and visualisations {#ttest-a13}

* Type and run the below code to gather the data using pivot_longer().
* Next create a violin-boxplot of the data using your knowledge (and code) from Activity 4 above. 
* Finally, create a descriptives table that contains the n, the mean, and the standard deviation of each condition.
  * If you prefer, you could actually work on the difference scores instead of the two different conditions. Whilst we analyse the difference, people plot either the difference or the two conditions as descriptives.


```r
gaze_tidy <- gaze %>%
  pivot_longer(names_to = "time", 
               values_to = "looking", 
               cols = c(baseline, test))
```

If you have done this step correctly, you should see a plot that looks like this:

<div class="figure" style="text-align: center">
<img src="10-t-tests_files/figure-html/unnamed-chunk-6-1.png" alt="Preferential Looking time for infants at baseline stage (left) and test stage (right)." width="100%" />
<p class="caption">(\#fig:unnamed-chunk-6)Preferential Looking time for infants at baseline stage (left) and test stage (right).</p>
</div>

And the descriptives:


|time     |  n| mean_looking| sd_looking|
|:--------|--:|------------:|----------:|
|baseline | 32|    0.5210967|  0.1769651|
|test     | 32|    0.5934912|  0.1786884|

Again you could look at the differences and if you know how you could plot the confidence interval of the difference, but it is not essential here.  But looking at what you have done it would be worth spending a few minutes to try and predict the outcome of the t-test if the null hypothesis is that there is no difference in preferential looking time in babies between the baseline and test conditions.

### Inferential Analysis

Which brings us on to running the t-test and the effect size. The code is almost identical to the independent code with two differences:

1. In `t.test()` you should specify `paired = TRUE` rather than `FALSE`
2. In `cohens_d()` you should specify `method = paired` rather than `pooled_sd`

#### Activity 14: Paired-samples t-test {#ttest-a14}

* Now have a go at running the within-subjects t-test based on your knowledge. The data you need is in `gaze_tidy()`. Store the output of the t-test as a tibble in the object `gaze_test`
  * i.e. pipe the output of the t-test into `tidy() in the one line of code.
* calculate the Cohen's D for the t-test and store it in `gaze_d`




```r
gaze_test <- NULL
gaze_d <- NULL
```

And if you have done that correctly, you should see in `gaze_test` something like this:


|   estimate| statistic|   p.value| parameter|  conf.low|  conf.high|method        |alternative |
|----------:|---------:|---------:|---------:|---------:|----------:|:-------------|:-----------|
| -0.0723946|  -2.41643| 0.0217529|        31| -0.133497| -0.0112922|Paired t-test |two.sided   |

### Write-Up and Interpretation

Looking at the output of the test, it is actually very similar to the between-subjects t-test, with one exception. Rather than providing the means of both conditions, there is a single `estimate`. This is the mean *difference* score between the two conditions and if you had calculated the descriptives on the `diff` we created above you would get the same answer.

* Enter the mean estimates and t-test results (means and t-value to 2 decimal places, p-value to 3 decimal places):

    + Mean `estimate` = <input class='webex-solveme nospaces' size='5' data-answer='["-0.07","0.07"]'/>  
    
    + t(<input class='webex-solveme nospaces' size='2' data-answer='["31"]'/>) = <input class='webex-solveme nospaces' size='4' data-answer='["2.42"]'/>, p = <input class='webex-solveme nospaces' size='5' data-answer='["0.022",".022"]'/> 

#### Activity 15: Write-up {#ttest-a15}

Now have a go at summarising this finding in a sentence using the standard APA formatting. We have hidden our version just below for you to look at when you have had a go.


<div class='webex-solution'><button>Show our write-up</button>


At test stage (M = .59, SD = .18), infants showed a significantly longer preferential looking time to the singer of the familiar melody than they had shown the same singer at baseline (M = .52, SD = .18), t(31) = 2.42, p = .022, d = .41.

Alternatively:

At test stage, infants showed a significantly longer preferential looking time to the singer of the familiar melody than they had shown the same singer at baseline (Mean Difference = 0.07, SD = 0.17), t(31) = 2.42, p = .022, d = .41.

</div>



## Finished! {#ttest-fin}

That was a long chapter but hopefully you will see that it really is true that the hardest part is the set-up and the data wrangling. As we've said before, you don't need to memorise lines of code - you just need to remember where to find examples and to understand which bits of them you need to change. Play around with the examples we have given you and see what changing the values does. There is no specific Test Yourself section for this chapter but make sure you check your understanding of the different sections before moving on.

## Activity solutions {#ttest-sols}

Below you will find the solutions to the above questions. Only look at them after giving the questions a good try and trying to find help on Google or Teams about any issues.

#### Activity 1 {#ttest-a1sol}


```r
library(broom)
library(car)
library(effectsize)
library(report)
library(tidyverse)
evaluators <- read_csv("evaluators.csv")
```
 

#### Activity 2 {#ttest-a2sol}

This was our code:


```r
evaluators <- evaluators %>%
  mutate(sex_labels = dplyr::recode(sex, "1" = "male", "2" = "female"),
         sex_labels = as.factor(sex_labels),
         condition = as.factor(condition))
```

and you could summarise as below to give an output:


```r
eval_counts <- group_by(evaluators, sex_labels) %>% count()
```

#### Activity 6 {#ttest-a6sol}



```r
intellect <- filter(ratings2, Category == "intellect")
hire <- filter(ratings2, Category == "hire")
impression <- filter(ratings2, Category == "impression")
```

#### Activity 8 {#ttest-a8sol}



```r
intellect_d <- cohens_d(Rating ~ condition, 
                      pooled_sd = FALSE, 
                      data = intellect)
hire_d <- cohens_d(Rating ~ condition, 
                      pooled_sd = FALSE, 
                      data = hire)
impression_d <- cohens_d(Rating ~ condition, 
                      pooled_sd = FALSE, 
                      data = impression)
```


#### Activity 13 {#ttest-a13sol}

For the plot:


```r
ggplot(gaze_tidy, aes(x = time, y = looking)) +
  geom_violin(trim = FALSE) +
  geom_boxplot(aes(fill = time), width = .2, show.legend = FALSE) + 
  stat_summary(geom = "pointrange", fun.data = "mean_cl_normal") +
  labs(x = "Experimental Stage", 
       y = "Preferential Looking Time (Proportion)")
```

For the descriptives:


```r
desc <- gaze_tidy %>% 
  group_by(time) %>% 
  summarise(n = n(), 
            mean_looking = mean(looking), 
            sd_looking = sd(looking))
```

#### Activity 14 {#ttest-a14sol}

For the t-test:


```r
gaze_test <- t.test(looking ~ time, 
                    paired = TRUE, 
                    data = gaze_tidy) %>% 
  tidy()
```

For the Cohen's D:


```r
gaze_d <- cohens_d(looking ~ time, 
                   method = "paired", 
                   data = gaze_tidy)
```

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.


|term                                                                                                               |definition                                                                                    |
|:------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------|
|[between subjects](https://psyteachr.github.io/glossary/b.html#between-subjects){class="glossary" target="_blank"} |Not varying within unit of observation, such that each has only one value                     |
|[categorical](https://psyteachr.github.io/glossary/c.html#categorical){class="glossary" target="_blank"}           |Data that can only take certain values, such as types of pet.                                 |
|[mixed design](https://psyteachr.github.io/glossary/m.html#mixed-design){class="glossary" target="_blank"}         |An experimental design that has both within-subject and between-subject factors.              |
|[numeric](https://psyteachr.github.io/glossary/n.html#numeric){class="glossary" target="_blank"}                   |A data type representing a real decimal number or integer.                                    |
|[one sample](https://psyteachr.github.io/glossary/o.html#one-sample){class="glossary" target="_blank"}             |A study to compare the mean and spread of one group against a known value or population norm. |
|[within subjects](https://psyteachr.github.io/glossary/w.html#within-subjects){class="glossary" target="_blank"}   |Varying such that each unit of observation has more than one value                            |

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!

<!--chapter:end:10-t-tests.Rmd-->

# Power and Effect Sizes

Up until now we have mainly spent time on data-wrangling, understanding probability, visualising our data, and more recently, running inferential tests, i.e. t-tests. In the lectures, however, you have also started to learn about additional aspects of inferential testing and trying to reduce certain types of error in your analyses. It is this balance of minimising error in our inferential statistics that we will focus on today. 

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
|small to medium| .2 to .5|
|medium to large| .5 to .8|
|large| > .8|

<br>

You may wish to read this paper later about different effect sizes in psychology - <a href="https://www.frontiersin.org/articles/10.3389/fpsyg.2019.00813/full" target = "_blank">Schafer and Schwarz (2019) The Meaningfulness of Effect Sizes in Psychological Research: Differences Between Sub-Disciplines and the Impact of Potential Biases</a>.

The thing to note is that the formula is slightly different depending on the type of t-test used and it can sometimes change depending on who you read. For this worksheet, let's go with the following formulas:

* One-sample t-test & paired-sample t-test:  

$$d = \frac{t}{\sqrt{N}}$$

* Independent t-test: 

$$d = \frac{2 \times t}{\sqrt{df}}$$

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
* According to Cohen (1988), the effect size for this t-test would probably be considered: <select class='webex-select'><option value='blank'></option><option value=''>small to medium</option><option value='answer'>medium to large</option><option value=''>large</option></select>  

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
* According to Cohen (1988), the effect size for this t-test would probably be considered: <select class='webex-select'><option value='blank'></option><option value=''>small to medium</option><option value=''>medium to large</option><option value='answer'>large</option></select>


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
* According to Cohen (1988), the effect size for this t-test would probably be described as: <select class='webex-select'><option value='blank'></option><option value=''>small to medium</option><option value='answer'>medium to large</option><option value=''>large</option></select>

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
  pluck("n") %>%
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

* Based on the information given, what will you set `type` as in the function? <div class='webex-radiogroup' id='radio_TPXFWLLUSI'><label><input type="radio" autocomplete="off" name="radio_TPXFWLLUSI" value=""></input> <span>one.sample</span></label><label><input type="radio" autocomplete="off" name="radio_TPXFWLLUSI" value="answer"></input> <span>two.sample</span></label></div>

* Based on the output, enter the minimum effect size you can reliably detect in this test, rounded to two decimal places: <input class='webex-solveme nospaces' size='4' data-answer='[".65","0.65"]'/>
* According to Cohen (1988), the effect size for this t-test is <div class='webex-radiogroup' id='radio_MYSECBNKIE'><label><input type="radio" autocomplete="off" name="radio_MYSECBNKIE" value=""></input> <span>small to medium</span></label><label><input type="radio" autocomplete="off" name="radio_MYSECBNKIE" value="answer"></input> <span>medium to large</span></label><label><input type="radio" autocomplete="off" name="radio_MYSECBNKIE" value=""></input> <span>large</span></label></div>

* Say you run the study and find that the effect size determined is d = 0.50. Given what you know about power, select the statement that is true: <div class='webex-radiogroup' id='radio_TEDSVJBCYG'><label><input type="radio" autocomplete="off" name="radio_TEDSVJBCYG" value=""></input> <span>the study is sufficiently powered as the analysis indicates you can detect only effect sizes smaller than d = 0.65</span></label><label><input type="radio" autocomplete="off" name="radio_TEDSVJBCYG" value="answer"></input> <span>the study is underpowered as the analysis indicates you can detect only effect sizes larger than d = 0.65</span></label></div>


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
* According to Cohen (1988), the effect size for this correlation is <select class='webex-select'><option value='blank'></option><option value=''>small to medium</option><option value='answer'>medium to large</option><option value=''>large</option></select>
* Say you run the study and find that the effect size determined is d = 0.24. Given what you know about power, select the statement that is true: <div class='webex-radiogroup' id='radio_LEUPGMZOIW'><label><input type="radio" autocomplete="off" name="radio_LEUPGMZOIW" value=""></input> <span>the study is sufficiently powered as the analysis indicates you can detect only effect sizes smaller than d = 0.24</span></label><label><input type="radio" autocomplete="off" name="radio_LEUPGMZOIW" value="answer"></input> <span>the study is underpowered as the analysis indicates you can detect only effect sizes larger than d = 0.34</span></label></div>


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

1. Assuming you were running a between-subjects t-test on secondary data ($\alpha = .05$, Power = .8, alternative = two-tailed) and that this secondary data has 100 participants in both groups. The smallest effect size, to three decimal places, you could determine with this data is: <div class='webex-radiogroup' id='radio_FLVDTWWCNU'><label><input type="radio" autocomplete="off" name="radio_FLVDTWWCNU" value=""></input> <span>d = 0.281</span></label><label><input type="radio" autocomplete="off" name="radio_FLVDTWWCNU" value=""></input> <span>d = 0.280</span></label><label><input type="radio" autocomplete="off" name="radio_FLVDTWWCNU" value=""></input> <span>d = 0.399</span></label><label><input type="radio" autocomplete="off" name="radio_FLVDTWWCNU" value="answer"></input> <span>d = 0.398</span></label></div>



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


2. Assuming you were running a between-subjects t-test on secondary data ($\alpha = .05$, Power = .8, alternative = two-tailed) and that this secondary data has 60 participants in Group 1 and 40 participants in Group 2. The smallest effect size, to three decimal places, you could determine with this data is: <div class='webex-radiogroup' id='radio_SUDVQJPXOH'><label><input type="radio" autocomplete="off" name="radio_SUDVQJPXOH" value=""></input> <span>d = 0.577</span></label><label><input type="radio" autocomplete="off" name="radio_SUDVQJPXOH" value=""></input> <span>r = .577</span></label><label><input type="radio" autocomplete="off" name="radio_SUDVQJPXOH" value=""></input> <span>r = .578</span></label><label><input type="radio" autocomplete="off" name="radio_SUDVQJPXOH" value="answer"></input> <span>d = 0.578</span></label></div>



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


3. Assuming you ran a correlation on secondary data ($\alpha = .05$, Power = .8, alternative = two-tailed) and that this secondary data has 50 observations. The smallest effect size, to three decimal places, you could determine with this data is: <div class='webex-radiogroup' id='radio_TQTYLDUJKD'><label><input type="radio" autocomplete="off" name="radio_TQTYLDUJKD" value=""></input> <span>r = .385</span></label><label><input type="radio" autocomplete="off" name="radio_TQTYLDUJKD" value="answer"></input> <span>r = .384</span></label><label><input type="radio" autocomplete="off" name="radio_TQTYLDUJKD" value=""></input> <span>r = .275</span></label><label><input type="radio" autocomplete="off" name="radio_TQTYLDUJKD" value=""></input> <span>r = .276</span></label></div>



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
  round(2)
```

[1] 0.65



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

<!--chapter:end:11-power.Rmd-->

# Screening Data 

In this chapter we're going to focus on how to screen datasets for potential issues and to reinforce the concept of tidy data. So far, we've given you complete datasets to work with, however, you will find that real data is often much messier than this, for example, participants may not answer some items in your questionnaire or there may be errors or implausible values in your dataset. We're also going to show you a different function to make calculating descriptive statistics easier. 

## The Set-Up and the Data

As always we first need to start with setting up our working environment, bringing in our data and looking at it.

#### Activity 1: Set-up {#screening-a1}

* Open RStudio and set the working directory to your chapter folder. Ensure the environment is clear.
    * If you're using the Rserver, avoid a number of issues by restarting the session - click `Session` - `Restart R`
* Open a new R Markdown document and save it in your working directory. Call the file "screeningdata".   
* Download <a href="messy.csv" download>messy.csv</a> and save it in your Screening Data folder. Make sure that you do not change the file name at all. 
  * If you prefer you can download the data in a [zip folder by clicking here](data/chpt12/PsyTeachR_FQA_Chpt12-data.zip){target="_blank"}
  * Remember not to change the file names at all and that `data.csv` is not the same as `data (1).csv`.
* Delete the default R Markdown welcome text and insert a new code chunk that loads the following packages, in this specific order, using the `library()` function. Remember the solutions if needed. 
    * Load the packages in this order, `psych` then `tidyverse`
  * again we have not used some of these packages so you will likely need to install some of them using `install.packages()`. Remember though that you should only do this on your own machine and only in the console window. If you are using the RServer you will not need to install them.
* Finally, load the data held in `messy.csv` as a tibble into an object named `messy` using `read_csv()`. If unsure, have a look at the solution at the end of the chapter



#### Activity 2: Look at the data {#screening-a2}

`messy` is simulated data for an experiment looking at the effect of note-taking on test performance and whether this is affected by being first language English. Participants are first given a pre-test to judge their baseline knowledge, then they watch a lecture and take notes. Immediately after the lecture is finished they take another test. Finally, they are tested after a week's delay. The maximum score for any test is 30. Participants lose marks for incorrect answers so minus scores are also possible. The dataset has six variables:

  * `id` showing the participant ID number
  * `age` showing the age of the participant
  * `speaker`showing if the participant are first language English or not  
  * `gender` showing if the participant is male, female, or non-binary  
  * `pre` showing pre-test score before any notes were taken  
  * `post` showing post-test score immediately after the lecture  
  * `delay` showing test score after one week delay

## Missing data

The first issue we will cover is missing data. There is a whole host of reasons that your data could have missing values. For example:

* Data can be missing because your participants accidentally didn't fill in a question.
* Data can be missing because participants intentionally didn't want to answer a question. 
* Data can be missing because participants didn't turn up to a final testing session. 
* Data can be missing because you did something wrong whilst setting up your questionnaire/experiment and it didn't save. 

In truth, real data frequently contains missing values and it's important that you know how to identify missing data and what you can do with it. Which is what we want to show you a little of in this chapter.

#### Activity 3: `summary()` and `is.na()` {#screening-a3}

Missing data is normally shown in your tibbles and objects as `NA` - usually taken to mean something like "Not Available". We have already seen a couple of approaches to find NAs in our data and we will quickly recap them.

The first approach is to use a pipeline of functions we have used before including `summarise()`, `is.na()`, `sum()`, and `pluck()`. For instance:


```r
messy_na <- messy %>% 
  summarise(find_nas = is.na(speaker)) %>%
  summarise(count_nas = sum(find_nas)) %>%
  pluck("count_nas")
```

Which reads as use `is.na()` to find all the NAs in messy (i.e the first `summarise()`) and then count up all those NAs (i.e. the second `summarise()` - which works because NAs are either TRUE, summed as 1, or FALSE, summed as 0), and then pluck out that number (i.e. the `pluck()`). And if you look at `messy_na` you see there are 20 NAs in `speaker`. That code looks quite long but it could actually be written as below if you prefer and you can follow the pipe inside the `summarise()`.


```r
messy_na <- messy %>% 
  summarise(count_nas = is.na(speaker) %>% sum()) %>% 
  pluck("count_nas")
```

This approach, using `is.na()`, is a good approach if you are only interested in one column or maybe a couple of columns, but if you want a snapshot of all your columns then we can use `summary()` which we have seen previously. First, however, because `speaker` and `gender` are character/text rather than numerical, in order to see how many values are missing we first need to convert these two columns into factors using the below code


```r
messy <- messy %>%
  mutate(speaker = as.factor(speaker), 
         gender = as.factor(gender))

summary(messy)
```

If you run the code, you can see, there are 20 data points missing (NAs) in each of `speaker`, `gender`, and `delay`. However, and the important part if you look at the actual data, the missing data is not in the same 20 participants and that gives us some issues about how to deal with these different participants. Fortunately, there are several different approaches to dealing with missing data and we will cover a few here.

## Listwise Deletion

One method for dealing with missing data is <a class='glossary' title='The removal of participants where they have missing data on any of the variables within the dataset'>listwise deletion</a>. This approach removes any participant who have a missing value (i.e. a NA) in **any** variable. So if there is missing data in any of the columns in the dataset, that participant will be removed and you will only be left with participants with complete datasets. For example the below participants would be removed along with all others with a similar profile:


|  id  | age | speaker | gender | pre | post | delay |
|:----:|:---:|:-------:|:------:|:---:|:----:|:-----:|
| S008 | 48  | english |   NA   | 12  |  15  |  17   |
| S009 | 22  |   NA    |  male  |  5  |  18  |   5   |
| S010 | 31  |   NA    | female | 13  |  35  |  17   |
| S011 | 26  | english |   NA   | 18  |  19  |  16   |

We can achieve this using the `drop_na()` function from the **`tidyr`** package that comes in as part of `tidyverse`.

#### Activity 4: Listwise deletion {#screening-a4}

* Run the below code and then view the tibble in the object called `messy_listwise`.  


```r
messy_listwise <- drop_na(messy)
```

As you can see `messy_listwise` now only contains data from participants with a complete set of data - i.e. responses in each column. 

Now, however, whilst this might seem like a good thing, and sometimes it is the most appropriate option, there are a couple of important points to consider. 

1. First, `gender` might not be part of our experiment; it might just be there as demographic information. So whilst we might not include `gender` in any of our analyses, because of the listwise deletion approach we have deleted experimental data if the participant was missing `gender` which means we are removing participants we could actual use. 
2. Relatedly, using a listwise deletion approach may result in the loss of a lot of data. Compare `messy` to `messy_listwise`. The original dataset had 200 participants. After using `drop_na()` we only have 143 participants meaning that we have lost over 25% of our data with this approach which is a lot of data. 
* **Note:** It is worth mentioning that if you do use a listwise approach you should check that the missing values are not coming from one particular group (i.e., non-random attrition).

To counter these issues, one option is to amend the use of `drop_na()` so that it doesn't include `gender`, or any column for that matter that we don't want to exclude people based on. We can do this using a similar approach to what we have seen when using `select()`. For example, run the below code, have a look at the output and then answer the question:


```r
messy_listwise2 <- drop_na(messy, -gender)
```

* How many observations does `messy_listwise2` have? <input class='webex-solveme nospaces' size='3' data-answer='["161"]'/>

So that approach says "remove participants with NAs from `messy` based on all columns **except** gender". Alternatively, you could do "remove participants with NAs from `messy` based on only the columns of speaker and delay" as follows:


```r
messy_listwise3 <- drop_na(messy, speaker, delay)
```

So you actually have a lot of control with `drop_na()` as long as you plan your approach in advance.

## Pairwise Deletion

The alternative to listwise deletion is <a class='glossary' title='The removal of participants for a given analysis only'>pairwise deletion</a>. This is when cases are removed depending upon the analysis. For example, if we were to calculate the correlations between `pre`, `post`, and `delay` without first removing participants with missing data, we would basically just use different numbers of participants in each correlation depending on missing data. For example, if you compare the degrees of freedom for the following two correlations:


```r
cor.test(messy$pre, messy$post)
```

```
## 
## 	Pearson's product-moment correlation
## 
## data:  messy$pre and messy$post
## t = 7.0493, df = 198, p-value = 2.924e-11
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  0.3296550 0.5523276
## sample estimates:
##       cor 
## 0.4479101
```


```r
cor.test(messy$pre, messy$delay)
```

```
## 
## 	Pearson's product-moment correlation
## 
## data:  messy$pre and messy$delay
## t = 7.9619, df = 178, p-value = 1.927e-13
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  0.3958642 0.6127887
## sample estimates:
##       cor 
## 0.5124561
```
 


You can see that the correlation of `pre` versus `post` has df = 198 whereas `pre` versus `delay` has df = 178. Meaning that the correlation is by default run only on the participants who have data in both columns - pairwise deletion. The problem here is remembering to write up the output accordingly as the dfs are changing and they may be different from the number of participants you stated in your methods section. Again it is about looking at your data!

## Summarising data with missing values 

So when running inferential tests like correlations, the analysis will usually know when to ignore missing values. However, if you're calculating descriptive statistics or if you want to calculate the average score of a number of different items, you need to explicitly state to ignore the missing values. We can do this through `na.rm = TRUE`

#### Activity 5: `na.rm = TRUE` {#screening-a5}

* Run the below code to calculate the mean score for each testing condition.


```r
summarise(messy, 
          pre_mean = mean(pre),
          post_mean = mean(post),
          delay_mean = mean(delay)
          )
```

This gives a table similar to below. We have rounded all the values to two decimal places but yours might have more decimal places.


| pre_mean | post_mean | delay_mean |
|:--------:|:---------:|:----------:|
|  10.02   |   17.27   |     NA     |

As you can see, the mean score for `delay` shows as `NA`. This is because we are trying to calculate an average of a variable that has missing data and that just isn't doable. As such we need to calculate the mean but ignoring the missing values by adding `na.rm = TRUE` - which you can read this as "remove the NAs? Yes".

* Run the below code and then answer the question. 


```r
summarise(messy, 
          pre_mean = mean(pre),
          post_mean = mean(post),
          delay_mean = mean(delay, na.rm = TRUE)
          )
```

* What is the mean score for the `delay` condition to 2 decimal places? <input class='webex-solveme nospaces' size='5' data-answer='["13.60"]'/>

<div class="danger">
<p>It's really important that you think about whether you want to calculate your descriptives from participants that have missing data. For example, if you are calculating the average reaction time from hundreds of trials, a few missing data points won't affect the validity of the mean. However, if you are using a standardised questionnaire that has been validated using complete responses but your participants didn't answer 3/10 questions, it may not be appropriate to calculate a mean score from the remaining data.</p>
</div>

## Implausible values

Along with looking for missing values, an additional crucial step of data screening is checking for implausible values - values that should not exist in your data. What is implausible depends on the data you've collected!

#### Activity 6: Implausible values {#screening-a6}

Additional functions we can put inside a `summarise()` function are `min()` and `max()`. 

* Run the below code and look at the output and answer the questions below:


```r
messy %>%
  summarise(max_age = max(age, na.rm = TRUE),
            min_age = min(age, na.rm = TRUE),
            max_pre = max(pre, na.rm = TRUE),
            min_pre = min(pre, na.rm = TRUE),
            max_post = max(post, na.rm = TRUE),
            min_post = min(post, na.rm = TRUE),
            max_delay = max(delay, na.rm = TRUE),
            min_delay = min(delay, na.rm = TRUE))
```

<div class="kable-table">

| max_age| min_age| max_pre| min_pre| max_post| min_post| max_delay| min_delay|
|-------:|-------:|-------:|-------:|--------:|--------:|---------:|---------:|
|     470|      18|      26|      -5|       40|        3|        29|        -3|

</div>

* Does the max value of `age` look plausible? <select class='webex-select'><option value='blank'></option><option value=''>Yes</option><option value='answer'>No</option></select>
* Does the max value of `pre` look plausible? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
* Do the max value of `post` look plausible? <select class='webex-select'><option value='blank'></option><option value=''>Yes</option><option value='answer'>No</option></select>
* Do the min value of `delay` look plausible? <select class='webex-select'><option value='blank'></option><option value=''>No</option><option value='answer'>Yes</option></select>


<div class='webex-solution'><button>Explain these answers</button>

The maximum value for age is 470, this is unlikely to be correct!
  
The maximum value for pre, post, and delay should be 30, as we described at the start of the chapter. However, for post, the maximum value is 40 so something is wrong. This is a very important check to do on your data, not just for the raw data but if you've calculated a total score.

The min value for delay is plausible, given the explanation at the start of the chapter. Remember that participants can be deducted points for incorrect answers, so negative values are possible.

</div>


That code above does look a bit long and could be written quicker as below. We won't go into detail as to how this works but see if you can figure it out by comparing the output to the version above:


```r
messy %>% 
  summarise_at(c("age","pre","post","delay"),
               c(max, min),
               na.rm = TRUE)
```

<div class="kable-table">

| age_fn1| pre_fn1| post_fn1| delay_fn1| age_fn2| pre_fn2| post_fn2| delay_fn2|
|-------:|-------:|--------:|---------:|-------:|-------:|--------:|---------:|
|     470|      26|       40|        29|      18|      -5|        3|        -3|

</div>

And there is always `summary(messy)` if you prefer. But the main point is that we should always check our values to make sure they are allowed in our data. But whilst looking at the values is useful, it can be easier to visualise the data.

#### Activity 7: Visualising implausible values {#screening-a7}

There are a number of different ways to visualise the data as you know and this depends on the data, and your preferences. You could produce violin-boxplots with the data points on top to check the distributions as follows:


```r
messy %>%
  pivot_longer(cols = c("pre", "post", "delay"), 
               names_to = "test", 
               values_to = "score") %>%
  ggplot(aes(x = test, y = score)) +
  geom_violin() +
  geom_boxplot() +
  geom_jitter(width = .2)
```

<div class="figure" style="text-align: center">
<img src="12-missing-data_files/figure-html/fig1-1.png" alt="Data screening plots" width="100%" />
<p class="caption">(\#fig:fig1)Data screening plots</p>
</div>

And if it helped, you could add some max and min lines to help spot issues using `geom_hline()` as follows:


```r
messy %>%
  pivot_longer(cols = c("pre", "post", "delay"), 
               names_to = "test", 
               values_to = "score") %>%
  ggplot(aes(x = test, y = score)) +
  geom_violin() +
  geom_boxplot() +
  geom_jitter(width = .2) +
  geom_hline(yintercept = c(0,30), color = "red", linetype = 2)
```

<div class="figure" style="text-align: center">
<img src="12-missing-data_files/figure-html/fig1a-1.png" alt="Data screening plots" width="100%" />
<p class="caption">(\#fig:fig1a)Data screening plots</p>
</div>

Alternatively you could also use a histogram to spot an outlier:


```r
ggplot(messy, aes(x = age)) +
  geom_histogram()
```

<div class="figure" style="text-align: center">
<img src="12-missing-data_files/figure-html/fig2-1.png" alt="Histogram of age for data screening" width="100%" />
<p class="caption">(\#fig:fig2)Histogram of age for data screening</p>
</div>

And we can make use of `facet_wrap()` which we have seen before to help split figures based on different conditions:


```r
messy %>%
  pivot_longer(cols = c("pre", "post", "delay"), 
               names_to = "test", 
               values_to = "score") %>%
  ggplot(aes(x = score)) +
  geom_histogram(binwidth = 1) +
  facet_wrap(~test)
```

<div class="figure" style="text-align: center">
<img src="12-missing-data_files/figure-html/fig3-1.png" alt="Histogram of the DVs for data screening" width="100%" />
<p class="caption">(\#fig:fig3)Histogram of the DVs for data screening</p>
</div>

Whatever method you choose, make sure that you look at your data before trying to work with it and that you know in advance what range your values should take (for example, if your Likert scale is 1-7, you shouldn't have a score of 8, for reaction times, 50ms is unlikely to reflect a real response). 

## Dealing with implausible values or missing data

Once we have spotted some implausible or missing values we then need to decide what to do with them. However, there is no hard and fast rule about what to do with missing data. You should review the missing data to see if there are any patterns, for example, is all the missing data from one condition? A pattern may indicate a problem with your design. Alternatively, does a single participant have a lot of missing data and should they be removed? This might indicate they were not paying attention.

One way of dealing with implausible values is to use the `replace()` and `mutate()` functions to change such values to Na.

* For `age`, we know that we have one very specific data point that is implausible, an age of 470 so we can specify just to replace this one value with NA.
* For `post`, there are multiple missing values so we specify to replace any data point that is over the maximum plausible value (30) with NA.


```r
messy_screen <-  messy %>% 
  mutate(age = replace(age, age == 470, NA),
         post = replace(post, post > 30, NA))
```

An alternative method for dealing with implausible data is to <a class='glossary' title='The replacement of missing values with a value such as the mean of the distribution'>impute</a> the data, i.e., to replace missing data with substituted values. There are many methods of doing this, for example, you can replace missing values with the mean value of the distribution. We won't go into which method you should choose this in this chapter but there's [more information available](https://www.theanalysisfactor.com/seven-ways-to-make-up-data-common-methods-to-imputing-missing-data/) online about the various options if you're interested. The code for imputing missing data is relatively simple and uses `mutate()` and `replace_na()`.

* You can read the below code as "create a new variable named `post_impute` that replaces the values of `post` if they're `NA` with the mean of the values in `post`.


```r
messy_impute <- messy_screen %>%
  mutate(post_impute = replace_na(post, 
                                  mean(post, na.rm = TRUE)))
```

And if we look at a participant who had a NA for `post` we can see the change:


|id   | age|speaker |gender | pre| post| delay| post_impute|
|:----|---:|:-------|:------|---:|----:|-----:|-----------:|
|S016 |  40|english |female |  21|   NA|    12|    16.71134|

So you can see that they have been given the value of the mean of the distribution in this new variable and then can be used in different analyses!

## Alternative function for descriptive statistics

And before we end this chapter we wanted to just add a small section on an alternative function for calculating some useful descriptives that you can use to check your data. So far in this book, we've calculated descriptive statistics using `summarise()` from the **`tidyverse`**. There's a good reason we've done this - the output of `summarise()` works well with `ggplot()` and the code is very flexible. However, it can be hard to calculate descriptives such as skew and kurtosis within `summarise()` and it can be useful to know of other functions that help create these descriptives. For example, the `psych` package contains many functions that are useful for psychology research. One of the functions of `psych` is `describe()`.

* Run the below code and look at the output as shown below.


```r
descriptives <- describe(messy)
descriptives
```

<table>
 <thead>
  <tr>
   <th style="text-align:left;">   </th>
   <th style="text-align:right;"> vars </th>
   <th style="text-align:right;"> n </th>
   <th style="text-align:right;"> mean </th>
   <th style="text-align:right;"> sd </th>
   <th style="text-align:right;"> median </th>
   <th style="text-align:right;"> trimmed </th>
   <th style="text-align:right;"> mad </th>
   <th style="text-align:right;"> min </th>
   <th style="text-align:right;"> max </th>
   <th style="text-align:right;"> range </th>
   <th style="text-align:right;"> skew </th>
   <th style="text-align:right;"> kurtosis </th>
   <th style="text-align:right;"> se </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> id* </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 100.500000 </td>
   <td style="text-align:right;"> 57.8791845 </td>
   <td style="text-align:right;"> 100.5 </td>
   <td style="text-align:right;"> 100.500000 </td>
   <td style="text-align:right;"> 74.1300 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 199 </td>
   <td style="text-align:right;"> 0.0000000 </td>
   <td style="text-align:right;"> -1.2180144 </td>
   <td style="text-align:right;"> 4.0926764 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> age </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 36.075000 </td>
   <td style="text-align:right;"> 32.3102015 </td>
   <td style="text-align:right;"> 34.0 </td>
   <td style="text-align:right;"> 33.931250 </td>
   <td style="text-align:right;"> 13.3434 </td>
   <td style="text-align:right;"> 18 </td>
   <td style="text-align:right;"> 470 </td>
   <td style="text-align:right;"> 452 </td>
   <td style="text-align:right;"> 12.0951922 </td>
   <td style="text-align:right;"> 159.6718805 </td>
   <td style="text-align:right;"> 2.2846763 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> speaker* </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 180 </td>
   <td style="text-align:right;"> 1.511111 </td>
   <td style="text-align:right;"> 0.5012709 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:right;"> 1.513889 </td>
   <td style="text-align:right;"> 0.0000 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> -0.0440855 </td>
   <td style="text-align:right;"> -2.0091259 </td>
   <td style="text-align:right;"> 0.0373625 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> gender* </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 180 </td>
   <td style="text-align:right;"> 1.688889 </td>
   <td style="text-align:right;"> 0.7268889 </td>
   <td style="text-align:right;"> 2.0 </td>
   <td style="text-align:right;"> 1.611111 </td>
   <td style="text-align:right;"> 1.4826 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 0.5452331 </td>
   <td style="text-align:right;"> -0.9643153 </td>
   <td style="text-align:right;"> 0.0541791 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> pre </td>
   <td style="text-align:right;"> 5 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 10.015000 </td>
   <td style="text-align:right;"> 5.0039959 </td>
   <td style="text-align:right;"> 10.0 </td>
   <td style="text-align:right;"> 9.987500 </td>
   <td style="text-align:right;"> 4.4478 </td>
   <td style="text-align:right;"> -5 </td>
   <td style="text-align:right;"> 26 </td>
   <td style="text-align:right;"> 31 </td>
   <td style="text-align:right;"> 0.0555773 </td>
   <td style="text-align:right;"> 0.2559528 </td>
   <td style="text-align:right;"> 0.3538359 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> post </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 17.270000 </td>
   <td style="text-align:right;"> 6.3386110 </td>
   <td style="text-align:right;"> 17.0 </td>
   <td style="text-align:right;"> 16.968750 </td>
   <td style="text-align:right;"> 5.9304 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 40 </td>
   <td style="text-align:right;"> 37 </td>
   <td style="text-align:right;"> 0.5802699 </td>
   <td style="text-align:right;"> 0.7133158 </td>
   <td style="text-align:right;"> 0.4482075 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> delay </td>
   <td style="text-align:right;"> 7 </td>
   <td style="text-align:right;"> 180 </td>
   <td style="text-align:right;"> 13.600000 </td>
   <td style="text-align:right;"> 5.1563271 </td>
   <td style="text-align:right;"> 14.0 </td>
   <td style="text-align:right;"> 13.645833 </td>
   <td style="text-align:right;"> 4.4478 </td>
   <td style="text-align:right;"> -3 </td>
   <td style="text-align:right;"> 29 </td>
   <td style="text-align:right;"> 32 </td>
   <td style="text-align:right;"> -0.0462551 </td>
   <td style="text-align:right;"> 0.4985955 </td>
   <td style="text-align:right;"> 0.3843299 </td>
  </tr>
</tbody>
</table>

As you can see `describe()` produces a full set of descriptive statistics, including skew, kurtosis and standard error for the entire dataset! Run `?describe` to see a full explanation of all the statistics it calculates.

You may notice that `id`, `speaker` and `gender` all have a star next to their name. This star signifies that these variables are factors, and so it is not really appropriate to calculate these statistics, but we asked it to apply `describe()` to the entire dataset so it's done what you asked. However, we could `describe()`with `select()` to remove these variables and just get the data we want:


```r
descriptives2 <- messy %>%
  select(-id, -speaker, -gender) %>%
  describe()

descriptives2
```

<table>
 <thead>
  <tr>
   <th style="text-align:left;">   </th>
   <th style="text-align:right;"> vars </th>
   <th style="text-align:right;"> n </th>
   <th style="text-align:right;"> mean </th>
   <th style="text-align:right;"> sd </th>
   <th style="text-align:right;"> median </th>
   <th style="text-align:right;"> trimmed </th>
   <th style="text-align:right;"> mad </th>
   <th style="text-align:right;"> min </th>
   <th style="text-align:right;"> max </th>
   <th style="text-align:right;"> range </th>
   <th style="text-align:right;"> skew </th>
   <th style="text-align:right;"> kurtosis </th>
   <th style="text-align:right;"> se </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> age </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 36.075 </td>
   <td style="text-align:right;"> 32.310201 </td>
   <td style="text-align:right;"> 34 </td>
   <td style="text-align:right;"> 33.93125 </td>
   <td style="text-align:right;"> 13.3434 </td>
   <td style="text-align:right;"> 18 </td>
   <td style="text-align:right;"> 470 </td>
   <td style="text-align:right;"> 452 </td>
   <td style="text-align:right;"> 12.0951922 </td>
   <td style="text-align:right;"> 159.6718805 </td>
   <td style="text-align:right;"> 2.2846763 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> pre </td>
   <td style="text-align:right;"> 2 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 10.015 </td>
   <td style="text-align:right;"> 5.003996 </td>
   <td style="text-align:right;"> 10 </td>
   <td style="text-align:right;"> 9.98750 </td>
   <td style="text-align:right;"> 4.4478 </td>
   <td style="text-align:right;"> -5 </td>
   <td style="text-align:right;"> 26 </td>
   <td style="text-align:right;"> 31 </td>
   <td style="text-align:right;"> 0.0555773 </td>
   <td style="text-align:right;"> 0.2559528 </td>
   <td style="text-align:right;"> 0.3538359 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> post </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 200 </td>
   <td style="text-align:right;"> 17.270 </td>
   <td style="text-align:right;"> 6.338611 </td>
   <td style="text-align:right;"> 17 </td>
   <td style="text-align:right;"> 16.96875 </td>
   <td style="text-align:right;"> 5.9304 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 40 </td>
   <td style="text-align:right;"> 37 </td>
   <td style="text-align:right;"> 0.5802699 </td>
   <td style="text-align:right;"> 0.7133158 </td>
   <td style="text-align:right;"> 0.4482075 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> delay </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 180 </td>
   <td style="text-align:right;"> 13.600 </td>
   <td style="text-align:right;"> 5.156327 </td>
   <td style="text-align:right;"> 14 </td>
   <td style="text-align:right;"> 13.64583 </td>
   <td style="text-align:right;"> 4.4478 </td>
   <td style="text-align:right;"> -3 </td>
   <td style="text-align:right;"> 29 </td>
   <td style="text-align:right;"> 32 </td>
   <td style="text-align:right;"> -0.0462551 </td>
   <td style="text-align:right;"> 0.4985955 </td>
   <td style="text-align:right;"> 0.3843299 </td>
  </tr>
</tbody>
</table>

The output of `describe()` is a little harder to work with in terms of manipulating the table and using the data in subsequent plots and analyses, so we still strongly recommend that you use `summarise()` and `group_by()` for these operations, however, for getting a comprehensive overview of your data, `describe()` is a good function to know about.

## Finished! {#screening-fin}

And you're done! Excellent work today! This isn't a comprehensive tutorial on every type of dataset you will come across and the concept of tidy data will take practice but hopefully this should give you a good starting point for when you have your own real, messy data.

## Activity solutions {#screening-sols}

### Activity 1 {#screening-a1sol}


```r
library(psych)
library(tidyverse)
messy <- read_csv("messy.csv")
```

## Words from this Chapter

Below you will find a list of words that were used in this chapter that might be new to you in case it helps to have somewhere to refer back to what they mean. The links in this table take you to the entry for the words in the [PsyTeachR Glossary](https://psyteachr.github.io/glossary/){target="_blank"}. Note that the Glossary is written by numerous members of the team and as such may use slightly different terminology from that shown in the chapter.

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> term </th>
   <th style="text-align:left;"> definition </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> [impute](https://psyteachr.github.io/glossary/i.html#impute){class="glossary" target="_blank"} </td>
   <td style="text-align:left;"> The replacement of missing values with a value such as the mean of the distribution </td>
  </tr>
  <tr>
   <td style="text-align:left;"> [listwise](https://psyteachr.github.io/glossary/l.html#listwise){class="glossary" target="_blank"} </td>
   <td style="text-align:left;"> The removal of participants where they have missing data on any of the variables within the dataset </td>
  </tr>
  <tr>
   <td style="text-align:left;"> [pairwise](https://psyteachr.github.io/glossary/p.html#pairwise){class="glossary" target="_blank"} </td>
   <td style="text-align:left;"> The removal of participants for a given analysis only </td>
  </tr>
</tbody>
</table>

That is end of this chapter. Be sure to look again at anything you were unsure about and make some notes to help develop your own knowledge and skills. It would be good to write yourself some questions about what you are unsure of and see if you can answer them later or speak to someone about them. Good work today!


<!--chapter:end:12-missing-data.Rmd-->

# Visualisation



In this chapter we are going to focus on visualising data using `ggplot2`. You've already created a number of different plots including bar charts, scatterplots, histograms, qq-plots, and violin-boxplots, but now we will show you how to customise your plots further to give you a better idea of the range and flexibility of visualising data in R. 

In this chapter, you won't be asked to write any code yourself, we will give you all the example code. Instead, play with the arguments, change TRUE to FALSE and vice-versa, change the values and colours. This will help you learn what each bit does. 

For all of the activities in this chapter we are going to use data from  Experiment 3 of [Zhang, T., Kim, T., Brooks, A. W., Gino, F., & Norton, M. I. (2014). A "present" for the future: The unexpected value of rediscovery. Psychological Science, 25, 1851-1860.](https://journals.sagepub.com/doi/abs/10.1177/0956797614542274).

To help you understand the data we're visualising, here is the abstract:

> Although documenting everyday activities may seem trivial, four studies reveal that creating records of the present generates unexpected benefits by allowing future rediscoveries. In Study 1, we used a time-capsule paradigm to show that individuals underestimate the extent to which rediscovering experiences from the past will be curiosity provoking and interesting in the future. In Studies 2 and 3, we found that people are particularly likely to underestimate the pleasure of rediscovering ordinary, mundane experiences, as opposed to extraordinary experiences. Finally, Study 4 demonstrates that underestimating the pleasure of rediscovery leads to time-inconsistent choices: Individuals forgo opportunities to document the present but then prefer rediscovering those moments in the future to engaging in an alternative fun activity. Underestimating the value of rediscovery is linked to people’s erroneous faith in their memory of everyday events. By documenting the present, people provide themselves with the opportunity to rediscover mundane moments that may otherwise have been forgotten.

## Activity 1: Set-up Visualisation {#viz-a1}

* Open R Studio and set the working directory to your chapter folder. Ensure the environment is clear.   
* Open a new R Markdown document and save it in your working directory. Call the file "Visualisation".    
* Download <a href="Zhang et al. 2014 Study 3.csv" download>Zhang et al. 2014 Study 3.csv</a> and save it in your chapter folder. Make sure that you do not change the file name at all.
* If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Delete the default R Markdown welcome text and insert a new code chunk that loads the package `tidyverse` using the `library()` function. 
* Run the below code to load and wrangle the data into tidy data.


```r
library(tidyverse)
zhang_data <- read_csv("Zhang et al. 2014 Study 3.csv")%>%
  select(Gender, Age,Condition, T1_Predicted_Interest_Composite, T2_Actual_Interest_Composite)%>%
  mutate(subject = row_number())%>%
  pivot_longer(names_to = "time",values_to = "interest",
               cols = T1_Predicted_Interest_Composite:T2_Actual_Interest_Composite)%>%
  mutate(Condition = recode(Condition, "1" = "Ordinary", "2" = "Extraordinary"))%>%
  mutate(time = recode(time, "T1_Predicted_Interest_Composite" = "time1_interest", "T2_Actual_Interest_Composite" = "time2_interest"),
         Gender = recode(Gender, "1" = "male", "2" = "female")) %>%
  filter(Gender %in% c("male", "female"))
```

## Activity 2: Histograms {#viz-a2}

First, let's create histograms for `interest` to check the distribution. 
The first line of code creates the `ggplot()` object and specifies which dataset is being used, and what should be represented on the x and y-axis. Because this is a histogram, you only need to specify the variable on the x-axis because y is always frequency

### Basic histogram

The code below will create a simple histogram with default appearance and no customisation. You wouldn't use this graph in a paper, but if you just want to quickly check your distributions, for e.g., normality, this code might be enough. 


```r
ggplot(zhang_data, aes(interest))+ 
  geom_histogram()
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/hist1-1.png" alt="Basic histogram" width="100%" />
<p class="caption">(\#fig:hist1)Basic histogram</p>
</div>

### Colour and fill

The next section of code will change the appearance. Plots in ggplot2 are highly customisable - [R for Data Science](https://r4ds.had.co.nz/data-visualisation.html) has an excellent chapter on `ggplot` if you would like additional information. 

Adding `binwidth` to `geom_histogram()` changes the bins of the histogram, i.e., how wide the bars are. The default is 30. Sometimes this may be appropriate but often you will want to change the binwidth. What value you give will depend upon your data.

`colour()` changes the colour of the line around the bars. `fill()` changes the fill of the bars. 


```r
ggplot(zhang_data, aes(x = interest))+ 
  geom_histogram(binwidth = .3, 
                 colour = "black",  
                 fill = "grey") 
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/hist2-1.png" alt="Histogram with colour changes" width="100%" />
<p class="caption">(\#fig:hist2)Histogram with colour changes</p>
</div>

### Axis labels

The next section of code changes the labels on the graphs. Note that the labels are an additional layer (i.e., it comes after an `+`, rather than being an argument to `geom_histogram()`).

The function you use will depend on your data, the most common are `scale_x/y_continuous` and `scale_x/y_discrete` depending on whether you are displaying continuous or categorical data. Again, each axis is a separate layer. 

These scale functions control all the information about the axis, from the label to the breaks, to the minimum and maximum values. For more information use the help documentation. 

For our labelling purposes, there are two main arguments:

1. `name()` controls the main name of the axis
2. `labels()` controls the name of the breaks  

For our histogram we will just change the main axis labels. 


```r
ggplot(zhang_data, aes(x = interest))+ 
  geom_histogram(binwidth = .3, 
                 colour = "black",  
                 fill = "grey") + 
  scale_x_continuous(name = "Mean interest score (1-7)") +
  scale_y_continuous(name = "Count") 
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/hist3-1.png" alt="Histogram with label changes" width="100%" />
<p class="caption">(\#fig:hist3)Histogram with label changes</p>
</div>

### Density curve

The following section adds a normal density curve to the histogram, which can be useful for checking the assumption of normality.

To add the line you must change the `geom_histogram()` to use density on the y-axis (the default is count) and add a `stat_function()` layer that draws the line.


```r
ggplot(zhang_data, aes(interest))+ 
  geom_histogram(binwidth = .3, 
                 colour = "black", 
                 fill = "grey",
                 aes(y = ..density..))+ # change y-axis to density
  scale_x_continuous(name = "Mean interest score (1-7)") +
  scale_y_continuous(name = "Count") +
  stat_function(fun = dnorm, # this adds a normal density function curve
                colour = "red", # this makes it red
                args = list(mean = mean(zhang_data$interest, na.rm = TRUE),
                           sd = sd(zhang_data$interest, na.rm = TRUE)))
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/hist4-1.png" alt="Histogram with normal density curve" width="100%" />
<p class="caption">(\#fig:hist4)Histogram with normal density curve</p>
</div>

## Activity 3: Scatterplots {#viz-a3}

### Basic scatterplot

Now let's make a scatterplot plotting `Age` and `interest` to see if there is any relationship between the two. We need to specify both the x and y-axis variables. The following code will produce a very simple scatterplot. Again, you wouldn't use this graph in a paper, but for eye-balling your data it would suffice. 


```r
ggplot(zhang_data, aes(x = interest,y = Age))+
       geom_point()
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/scat1-1.png" alt="Basic scatterplot" width="100%" />
<p class="caption">(\#fig:scat1)Basic scatterplot</p>
</div>

### Axis labels

From this plot it doesn't look like there is much of a relationship between age and interest ratings. We can now change the labels using the same scale functions as before. 


```r
ggplot(zhang_data, aes(x = interest,y = Age))+
       geom_point()+
  scale_x_continuous(name = "Mean interest score (1-7)") + 
  scale_y_continuous(name = "Age")
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/scat2-1.png" alt="Scatterplot with label changes" width="100%" />
<p class="caption">(\#fig:scat2)Scatterplot with label changes</p>
</div>

### Adding a regression line

It's often useful to add a regression line or line of best fit to a scatterplot. The regression line is added with `geom_smooth()` and by default will also provide a 95% confidence interval. You can specify what type of line you want to draw, most often you will need `method = lm`, i.e., a linear model or a straight line. Look up the help documentation for `geom_smooth()` and see what other methods you can use. 


```r
ggplot(zhang_data, aes(x = interest,y = Age))+
  geom_point()+
  scale_x_continuous(name = "Mean interest score (1-7)") + 
  scale_y_continuous(name = "Age")+
  geom_smooth(method=lm) # if you don't want the shaded CI, add se = FALSE to this
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/scat3-1.png" alt="Scatterplot with regression line" width="100%" />
<p class="caption">(\#fig:scat3)Scatterplot with regression line</p>
</div>

### Grouped scatterplots

We can use ggplot to show how the relationship might differ for different populations within our data. We do this by adding `colour()` to `aes()` and setting it as whatever variable we would like to distinguish between. In this case, we will see how the relationship between age and interest differs for the male and female participants. There are a few participants with missing gender so we will first filter them out.



```r
zhang_data %>%
  filter(Gender %in% c("male", "female")) %>%
           ggplot(aes(x = interest,y = Age, colour = Gender))+
  geom_point()+
  scale_x_continuous(name = "Mean interest score (1-7)") + 
  scale_y_continuous(name = "Age")+
  geom_smooth(method=lm)
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/scat4-1.png" alt="Grouped scatterplot" width="100%" />
<p class="caption">(\#fig:scat4)Grouped scatterplot</p>
</div>

And here's that plot with the labels tidied up. Notice the use of `scale_color_discrete()` to adjust the labels for Gender. 

<div class="warning">
<p>When you change the <code>labels</code>, R will simply overwrite the names in the dataset. If you wanted to actually change the order of the categories (e.g., have male as the red line) you need to change the order of the factor. We will do this later, for now, just be sure that you're changing the name of the right category (i.e., female comes first))</p>
</div>


```r
ggplot(zhang_data, aes(x = interest,y = Age, colour = Gender))+
  geom_point()+
  scale_x_continuous(name = "Mean interest score (1-7)") + 
  scale_y_continuous(name = "Age")+
  geom_smooth(method=lm)+
  scale_color_discrete(name = "Gender",
                       labels = c("Female", "Male"))
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/scat5-1.png" alt="Grouped scatterplot with adjusted labels" width="100%" />
<p class="caption">(\#fig:scat5)Grouped scatterplot with adjusted labels</p>
</div>

## Activity 4: Boxplots {#viz-a4}

### Basic boxplot

The following code will produce a simple boxplot for eye-balling your data.


```r
ggplot(zhang_data, aes(x = Condition, y = interest))+
  geom_boxplot()
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bp1-1.png" alt="Basic boxplot" width="100%" />
<p class="caption">(\#fig:bp1)Basic boxplot</p>
</div>

### Adding data points

If we add another layer `geom_point()` we can add our raw data points to our boxplots to make them more informative.


```r
ggplot(zhang_data, aes(x = Condition, y = interest))+
  geom_boxplot()+
  geom_point()
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bp2-1.png" alt="Boxplot with overplotting" width="100%" />
<p class="caption">(\#fig:bp2)Boxplot with overplotting</p>
</div>

However, this plot suffers from **over-plotting**, that is, there are multiple data points on top of each other. We can change this by using `geom_jitter()`, which adds a layer of points that are jittered so that each one is visible.

`height` and `width` affect how much each point is jittered. Play around with the values to see how it affects the data points. 


```r
ggplot(zhang_data, aes(x = Condition, y = interest))+
  geom_boxplot()+
  geom_jitter(height = 0, width = .1)
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bp3-1.png" alt="Boxplot with jittered data" width="100%" />
<p class="caption">(\#fig:bp3)Boxplot with jittered data</p>
</div>

### Adding colour

We may want to add colour to our graph (and for consistency, we'll sort out the labels). We do this by adding the 'fill' argument to the ggplot aesthetic by specifying which variable the colour of the fill should be organised by. 


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = Condition))+
  geom_boxplot()+
  geom_jitter(height = 0, width = .1)+
  scale_x_discrete(name = "Condition") + # note the x-axis is discrete
  scale_y_continuous(name = "Mean interest rating (1-7)")+
  scale_fill_discrete(guide = FALSE) # this suppresses the legend because we don't need it
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bp4-1.png" alt="Boxplot with colour" width="100%" />
<p class="caption">(\#fig:bp4)Boxplot with colour</p>
</div>

### Boxplots for multiple factors

When you only have one IV, using the fill command to change the colour is a little redundant, as the colours don't add any additional information. It makes more sense to use colour to represent an additional IV. 

For this example, we'll use `Condition` and `time` as IVs. `fill()` now specifies a second IV, rather than repeating the IV on the x-axis as in the previous plot. 

With multiple IVs the command to overlay the raw data points changes as the data points also need dodged (try running the code with the previous geom_jitter function to see what happens)


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = time))+
  geom_boxplot()+
  geom_point(position=position_jitterdodge(jitter.width = .1))
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bp5-1.png" alt="Boxplot for two factors" width="100%" />
<p class="caption">(\#fig:bp5)Boxplot for two factors</p>
</div>

### Colour-blind friendly options

There is one more fill option that we can use. Rather than specifying `scale_fill_discrete()`, we can use `scale_fill_viridis_d()`. This function does exactly the same thing but it uses a colour-blind friendly palette (which also prints in black and white). There are 5 different options for colours and you can see them by changing `option` to A, B, C, D or E. Personally I like option E with `alpha = .6` (to control transparency) but that's not an official School position.


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = time))+
  geom_boxplot(alpha = .6)+
  geom_point(position=position_jitterdodge(jitter.width = .1)) +
  scale_fill_viridis_d(option = "E")
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/unnamed-chunk-2-1.png" alt="Boxplots with friendly colours" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-2)Boxplots with friendly colours</p>
</div>

## Activity 5: Reordering factors {#viz-a5}

R orders categorical variables alphabetically. For gender it didn't really matter whether male or female was represented first and for time 1 and 2 it makes sense for them to be in this order but we may want to change the order of Condition (in my mind it makes more sense for Ordinary to come first, but that may just be me).

To do this we can use `mutate()` and `fct_level()` to change the factor levels to the order we want.


```r
zhang_data <- zhang_data %>%
  mutate(Condition = fct_relevel(Condition, c("Ordinary", "Extraordinary")))
```

Now we can re-run the boxplot. That's better. 


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = time))+
  geom_boxplot(alpha = .6)+
  geom_point(position=position_jitterdodge(jitter.width = .1)) +
  scale_fill_viridis_d(option = "E")
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bp6-1.png" alt="Boxplot with reordered factors" width="100%" />
<p class="caption">(\#fig:bp6)Boxplot with reordered factors</p>
</div>

## Activity 6: Bar Charts {#viz-a6}

### Basic bar chart

Bar charts should only be used for counts because they can distort your understanding of the data if you use them to represent means (see [here for a great example](https://www.autodeskresearch.com/publications/samestats). 

First, we'll do a bar chart for the count of male and females in our sample.


```r
ggplot(zhang_data, aes(x=Gender))+
  geom_bar()
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bc1-1.png" alt="Basic bar chart" width="100%" />
<p class="caption">(\#fig:bc1)Basic bar chart</p>
</div>

### Bar charts with two factors

We can also use `fill()` to separate gender by Condition


```r
ggplot(zhang_data, aes(x=Gender, fill = Condition))+
  geom_bar(position = "dodge", alpha = .6) + # the position argument places the bars next to each other, rather than on top of each other, try removing this
  scale_fill_viridis_d(option = "E")
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/bc2-1.png" alt="Bar chart with two factors" width="100%" />
<p class="caption">(\#fig:bc2)Bar chart with two factors</p>
</div>

## Activity 7: Violin plots {#viz-a7}

### Basic violin plot

Violin plots are so-called because with a normal distribution the shape would look something like a violin. They show density, i.e., the fatter the violin the more data points there are for that value.


```r
ggplot(zhang_data, aes(x = Condition, y = interest))+
  geom_violin()
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/vp1-1.png" alt="Basic violin plot" width="100%" />
<p class="caption">(\#fig:vp1)Basic violin plot</p>
</div>

### Violin plots with raw data points

Like the boxplot, we can also add the raw data points to our violin plot, making sure to use jitter  to avoid over-plotting.


```r
ggplot(zhang_data, aes(x = Condition, y = interest))+
  geom_violin()+
  geom_jitter(height = 0, width = .1)
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/vp2-1.png" alt="Violin plot with data points" width="100%" />
<p class="caption">(\#fig:vp2)Violin plot with data points</p>
</div>

<div class="warning">
<p>It's important to remember that R is very literal. <code>ggplot2</code> works on a system of layers. It will add new geoms on top of existing ones and it won't stop to think whether this is a good idea. Try running the above code but put <code>geom_jitter()</code> first and then add <code>geom_violin()</code>. The order of your layers matters.</p>
</div>

## Activity 8: Violin-boxplots {#viz-a8}

One increasingly common graph is a violin + boxplot + summary plot that shows a huge amount of information about your data in a single plot. 

* This code uses two calls to `stat_summary()` that was introduced during the t-test chapter. The first draws a `point` to represent the mean, and the second draws an `errorbar` that represents standard error (`mean_se`).  
* `guides` is a new function and can be used to adjust whether legends are displayed. This has the same effect as specifying `show.legend = FALSE` in both `geom_violin()` and `geom_boxplot()` but it uses less code to do so.  
* `fatten = NULL` removes the median line from the boxplots. This can be useful if you're running a test where you're comparing means as it makes it easier to see the point range. 
* You may get warning messages telling you that R has removed rows containing missing values, you do not need to worry about this.


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = Condition))+
  geom_violin(alpha = .6, trim = FALSE)+
  geom_boxplot(width = .2, alpha = .7, fatten = NULL)+
  stat_summary(fun = "mean", geom = "point") +
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = .1) +
  scale_fill_viridis_d(option = "E", label = c("Ordinary", "Extraordinary"))+
  scale_y_continuous(name = "Mean interest rating (1-7)") +
  guides(fill = FALSE)
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/vbp1-1.png" alt="Violin-boxplot with summary data" width="100%" />
<p class="caption">(\#fig:vbp1)Violin-boxplot with summary data</p>
</div>

## Activity 9: Faceting {#viz-a9}

`ggplot2` contains a facet function that produces different plots for each level of a grouping variable which can be very useful when you have more than two factors, for example, for a three-way ANOVA. The following code displays produces violin-boxplots for Condition ~ interest, but separately for male and female participants. 

* This code adds an extra argument `position = position_dodge(.9)` to align the layers with the violin plots. Try removing this argument from each layer to see what happens, and also try adjusting the value from `.9` to another number.


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = time))+
  geom_violin(alpha = .6, trim = FALSE)+
  geom_boxplot(width = .2, 
               alpha = .6, 
               fatten = NULL,
               position = position_dodge(.9))+
  stat_summary(fun = "mean", geom = "point",
               position = position_dodge(.9)) +
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = .1,
               position = position_dodge(.9))+
  scale_fill_viridis_d(option = "E") +
  facet_wrap(~Gender)
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/facet1-1.png" alt="Violin-boxplot facetted by gender" width="100%" />
<p class="caption">(\#fig:facet1)Violin-boxplot facetted by gender</p>
</div>

### Facet labelling

Finally, changing the labels within the facets is a little more complicated - there's no additional scale layer, instead, you adjust this inside `facet_wrap()` using `labeller`. This has always felt unintuitive to me and I have to look it up every single time so don't worry if it is confusing - just remember where to look for the example. 


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = time))+
  geom_violin(alpha = .6, trim = FALSE)+
  geom_boxplot(width = .2, 
               alpha = .6, 
               fatten = NULL,
               position = position_dodge(.9))+
  stat_summary(fun = "mean", geom = "point",
               position = position_dodge(.9)) +
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = .1,
               position = position_dodge(.9))+
  scale_fill_viridis_d(option = "E") +
  facet_wrap(~Gender, labeller = labeller(Gender = (c(female = "Female", male = "Male"))))
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/facet2-1.png" alt="Facetted plot with updated labels" width="100%" />
<p class="caption">(\#fig:facet2)Facetted plot with updated labels</p>
</div>

## Activity 10: Split-violins and raincloud plots {#viz-a10}

Finally, we're going to do something a bit snazzy. As well as the functions that are included in packages, anyone can also write custom functions and share the code. One such custom function allows us to create **raincloud plots** which are highly informative and very pretty. See [here](https://wellcomeopenresearch.org/articles/4-63) for more information about their creation and function (and to cite them if you use them in a publication or report).

In order to use this custom function code you will need to install the `plyr` package, although crucially, don't load it like you normally would using `library()`. The custom function code will just use one very specific function, if you load the entire package you risk creating a function conflict.


```r
install.packages("plyr")
```


### Split-violin plots

Because the functions we need don't exist in a package we can load, we need to create them. Copy and paste all  the below code without changing anything. You do not need to understand this code. I certainly don't. When you run this, you should see `geom_split_violin` appear in the Environment pane under Functions. 


```r
GeomSplitViolin <- ggproto(
  "GeomSplitViolin", 
  GeomViolin, 
  draw_group = function(self, data, ..., draw_quantiles = NULL) {
    data <- transform(data, 
                      xminv = x - violinwidth * (x - xmin), 
                      xmaxv = x + violinwidth * (xmax - x))
    grp <- data[1,'group']
    newdata <- plyr::arrange(
      transform(data, x = if(grp%%2==1) xminv else xmaxv), 
      if(grp%%2==1) y else -y
    )
    newdata <- rbind(newdata[1, ], newdata, newdata[nrow(newdata), ], newdata[1, ])
    newdata[c(1,nrow(newdata)-1,nrow(newdata)), 'x'] <- round(newdata[1, 'x']) 
    if (length(draw_quantiles) > 0 & !scales::zero_range(range(data$y))) {
      stopifnot(all(draw_quantiles >= 0), all(draw_quantiles <= 1))
      quantiles <- ggplot2:::create_quantile_segment_frame(data, draw_quantiles)
      aesthetics <- data[rep(1, nrow(quantiles)), setdiff(names(data), c("x", "y")), drop = FALSE]
      aesthetics$alpha <- rep(1, nrow(quantiles))
      both <- cbind(quantiles, aesthetics)
      quantile_grob <- GeomPath$draw_panel(both, ...)
      ggplot2:::ggname("geom_split_violin", 
                       grid::grobTree(GeomPolygon$draw_panel(newdata, ...), quantile_grob))
    } else {
      ggplot2:::ggname("geom_split_violin", GeomPolygon$draw_panel(newdata, ...))
    }
  }
)

geom_split_violin <- function (mapping = NULL, 
                               data = NULL, 
                               stat = "ydensity", 
                               position = "identity", ..., 
                               draw_quantiles = NULL, 
                               trim = TRUE, 
                               scale = "area", 
                               na.rm = FALSE, 
                               show.legend = NA, 
                               inherit.aes = TRUE) {
  layer(data = data, 
        mapping = mapping, 
        stat = stat, 
        geom = GeomSplitViolin, 
        position = position, 
        show.legend = show.legend, 
        inherit.aes = inherit.aes, 
        params = list(trim = trim, 
                      scale = scale, 
                      draw_quantiles = draw_quantiles, 
                      na.rm = na.rm, ...)
  )
}
```

The split-violin is a version of the violin-boxplot that is good for visualising interactions. If you look at the faceted graph we made, there's actually quite a lot of unnecessary space used up because we only need half of the violin to see the distribution - the other half is just repeating the same information. 


```r
ggplot(zhang_data, aes(x = Condition, y = interest, fill = Gender))+
  geom_split_violin(trim = FALSE, alpha = .4)+
  geom_boxplot(width = .2, alpha = .6,
               position = position_dodge(.25))+
  scale_fill_viridis_d(option = "E") +
  stat_summary(fun = "mean", geom = "point",
               position = position_dodge(width = 0.25)) +
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = .1,
               position = position_dodge(width = 0.25))
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/sv1-1.png" alt="Split-violin plot" width="100%" />
<p class="caption">(\#fig:sv1)Split-violin plot</p>
</div>

### Raincloud plots

The second custom function is `geom_flat_violin`. Copy and paste all of this code and again you should see it appear in your Environment pane. 


```r
"%||%" <- function(a, b) {
  if (!is.null(a)) a else b
}

geom_flat_violin <- function(mapping = NULL, data = NULL, stat = "ydensity",
                             position = "dodge", trim = TRUE, scale = "area",
                             show.legend = NA, inherit.aes = TRUE, ...) {
  layer(
    data = data,
    mapping = mapping,
    stat = stat,
    geom = GeomFlatViolin,
    position = position,
    show.legend = show.legend,
    inherit.aes = inherit.aes,
    params = list(
      trim = trim,
      scale = scale,
      ...
    )
  )
}

GeomFlatViolin <-
  ggproto("Violinist", Geom,
          setup_data = function(data, params) {
            data$width <- data$width %||%
              params$width %||% (resolution(data$x, FALSE) * 0.9)
            
            # ymin, ymax, xmin, and xmax define the bounding rectangle for each group
            data %>%
              group_by(group) %>%
              mutate(ymin = min(y),
                     ymax = max(y),
                     xmin = x,
                     xmax = x + width / 2)
            
          },
          
          draw_group = function(data, panel_scales, coord) {
            # Find the points for the line to go all the way around
            data <- transform(data, xminv = x,
                              xmaxv = x + violinwidth * (xmax - x))
            
            # Make sure it's sorted properly to draw the outline
            newdata <- rbind(plyr::arrange(transform(data, x = xminv), y),
                             plyr::arrange(transform(data, x = xmaxv), -y))
            
            # Close the polygon: set first and last point the same
            # Needed for coord_polar and such
            newdata <- rbind(newdata, newdata[1,])
            
            ggplot2:::ggname("geom_flat_violin", GeomPolygon$draw_panel(newdata, panel_scales, coord))
          },
          
          draw_key = draw_key_polygon,
          
          default_aes = aes(weight = 1, colour = "grey20", fill = "white", size = 0.5,
                            alpha = NA, linetype = "solid"),
          
          required_aes = c("x", "y")
  )
```

This plot is similar to the split-violin, but it adds in the raw data points and looks a bit like a raincloud as a result. 
  
First, we will run the plot for just one variable, Condition. Again, try changing the arguments (adjust any numbers and change FALSE to TRUE) to see how you can control different aspects of the plot, in particular, try removing `coord_flip()` to see what happens.


```r
ggplot(zhang_data, aes(x = Condition, y = interest))+
  geom_flat_violin(position = position_nudge(x = .25, y = 0), 
                   trim=FALSE, alpha = 0.75) +
  geom_jitter(aes(color = Condition), 
             width = .2, size = .5, alpha = .75, show.legend = FALSE)+
  geom_boxplot(width = .1, alpha = 0.5, fatten = NULL)+
  stat_summary(fun = "mean", geom = "point",
               position = position_dodge(width = 0.25)) +
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = .1,
               position = position_dodge(width = 0.3)) +
  coord_flip()
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/rc1-1.png" alt="Raincloud plot for one factor" width="100%" />
<p class="caption">(\#fig:rc1)Raincloud plot for one factor</p>
</div>

### Raincloud plots with multiple factors

Now we can run the code for a 2 x 2 plot, adding in Gender to `fill` argument. This is quite a complicated plot, do not worry if you are struggling to understand the code but remember, you just need to understand which bits to change. 
  

```r
ggplot(zhang_data, 
       aes(x = Condition, y = interest, fill = Gender))+
  geom_flat_violin(position = position_nudge(x = .25, y = 0), 
                   trim=FALSE, 
                   alpha = 0.6) +
  geom_point(position = position_jitter(width = .05, height = 0.05), 
             size = .5, 
             alpha = .7, 
             show.legend = FALSE, 
             aes(colour = Gender))+
  geom_boxplot(width = .3, 
               alpha = 0.5, 
               position = "dodge")+
  stat_summary(fun = "mean", geom = "point",
               position = position_dodge(width = 0.3)) +
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = .1,
               position = position_dodge(width = 0.3)) +
  scale_fill_viridis_d(option = "E") +
  scale_colour_viridis_d(option = "E")
```

<div class="figure" style="text-align: center">
<img src="13-visualisation_files/figure-html/rc2-1.png" alt="Raincloud plot for two factors" width="100%" />
<p class="caption">(\#fig:rc2)Raincloud plot for two factors</p>
</div>

### Finished! {#viz-fin}

And you're done! As we've said throughout this chapter, you do not need to remember all of this code, you just need to remember what's possible and where to find the examples that you can modify. 


<!--chapter:end:13-visualisation.Rmd-->

# One-way ANOVA

### Background: Intrusive memories

In the lecture reading materials you have worked through calculating an ANOVA by hand in order to gain a conceptual understanding. However, when you run an ANOVA, typically the computer does all of these calculations for you. In this chapter we'll show you how to run a one-factor and factorial ANOVA using the `afex` package and post-hoc tests using a package called `emmeans`. 

In this example we will be using data from experiment 2 of [James, E. L., Bonsall, M. B., Hoppitt, L., Tunbridge, E. M., Geddes, J. R., Milton, A. L., & Holmes, E. A. (2015). Computer game play reduces intrusive memories of experimental trauma via reconsolidation-update mechanisms. Psychological Science, 26, 1201-1215](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4526368/).

The abstract for the paper is as follows:

> Memory of a traumatic event becomes consolidated within hours. Intrusive memories can then flash back repeatedly into the mind's eye and cause distress. We investigated whether reconsolidation - the process during which memories become malleable when recalled - can be blocked using a cognitive task and whether such an approach can reduce these unbidden intrusions. We predicted that reconsolidation of a reactivated visual memory of experimental trauma could be disrupted by engaging in a visuospatial task that would compete for visual working memory resources. We showed that intrusive memories were virtually abolished by playing the computer game Tetris following a memory-reactivation task 24 hr after initial exposure to experimental trauma. Furthermore, both memory reactivation and playing Tetris were required to reduce subsequent intrusions (Experiment 2), consistent with reconsolidation-update mechanisms. A simple, non-invasive cognitive-task procedure administered after emotional memory has already consolidated (i.e., > 24 hours after exposure to experimental trauma) may prevent the recurrence of intrusive memories of those emotional events.

### Activity 1: Set-up {#anova-a1}  

Do the following:

* Open R Studio and set the working directory to your chapter folder. Ensure the environment is clear.    
* Open a new R Markdown document and save it in your working directory. Call the file "One-way ANOVA".  
* Download <a href="James Holmes_Expt 2_DATA.csv" download>James Holmes_Expt 2_DATA.csv</a> and save it in your chapter folder.  
* If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R`   
* In a new code chunk, type and run the code that loads `pwr`, `lsr`, `car`, `broom`, `afex`, `emmeans`, `performance` and `tidyverse` using the `library()` function and loads the data into an object named `dat` using `read_csv()`. If you are working on your own machine you may need to install `afex` and `emmeans` but as always **do not install packages on university machines**.    
* Add (hint: mutate) a column to `dat` called `subject`that equals `row_number()` to act as a participant ID which is currently missing from the data set.  





### Activity 2: Data wrangling {#anova-a2}  

There are a lot of columns in this data set that we don't need for this analysis and the names of the variable are also long and difficult to work with. 

* Create a new object called `dat2` that just has the three columns we need - use `select()` to select the columns `subject`, `Condition`, and  `Days_One_to_Seven_Image_Based_Intrusions_in_Intrusion_Diary`
* Use `rename()` to rename `Days_One_to_Seven_Image_Based_Intrusions_in_Intrusion_Diary` to `intrusions`
* See if you can do this all in one pipeline
* Hint: in rename, `new_name = old_name`



### Activity 3: Numbers and factors {#anova-a3}

In addition to the names of the variables being too long, the levels of `Condition` are named 1,2,3,4 which R will think is a number rather than a category. We're going to overwrite the column `Condition` with a column that recodes these numbers as a factor. Copy and paste the code below into your Markdown and then run it.


```r
dat2 <- dat2 %>%
  mutate(Condition = as.factor(Condition))
```

**This is a really important step**. If you forget to recode variables as factors and R treats them as numbers, a lot of things won't work. Trust us, we've spent a lot of time trying to figure out what was wrong because we forgot to do this step!

### Activity 4: Create summary statistics {#anova-a4}

Next we want to calculate some descriptive statistics. We're really interested in the scores from each experimental group rather than overall.

* Create an object called `sum_dat`that contains the mean, standard deviation and standard error for the number of intrusions grouped by `Condition`  
* Use the pipe to achieve this in one pipeline  
* Your table should have four columns, `Condition`, `mean`, `sd`, and `se`.  



<div class='webex-solution'><button> Hint</button>


```
## 
## * Use group_by(some_grouping_variable) %>% summarise(...)
## * standard error = sd/sqrt(n) =  sd/sqrt(length(some_variable_name)
```

</div>




### Activity 5: Visualisation {#anova-a5}

Now we can visualise the data. In the original paper they use a bar plot, which we will reproduce later but for now let's use a better plot that gives us more information about the data. 

* Create the below violin-boxplot with number of intrusions on the y-axis and condition on the x-axis (see the Visualisation chapter for more info). 
* Change the labels on the x-axis to something more informative (hint: `scale_x_discrete(labels = c("label names")`)  

<div class="figure" style="text-align: center">
<img src="14-anova_files/figure-html/violin-plot-1.png" alt="Number of intrusions by condition" width="100%" />
<p class="caption">(\#fig:violin-plot)Number of intrusions by condition</p>
</div>

We can see from this plot that there are outliers in each of the groups. This information isn't present in the bar plot, which is why it's not a good idea to use them but we will reproduce it anyway.The below code shows you how to produce the bar plot that is presented in the paper. Try and figure out what each bit of code is doing in the plot (remember to use the help documentation for each function) and see what happens when you change the values for each argument.



```r
ggplot(sum_dat, aes(x = Condition, y = mean, fill = Condition))+
  stat_summary(fun = "mean", geom = "bar", show.legend = FALSE)+
  geom_errorbar(aes(ymin = mean - se, ymax = mean + se), width = 0.25)+
  scale_y_continuous(limits = c(0,7), 
                     breaks = c(0,1,2,3,4,5,6,7), 
                     name = "Intrusive-Memory Frequency (Mean for the Week")+
  scale_x_discrete(labels = c("No-task control", "Reactivation plus Tetris", "Tetris only",
                                "Reactivation only"))
```

<div class="figure" style="text-align: center">
<img src="14-anova_files/figure-html/bar-plot-1.png" alt="Bar plot of instrusions by condition" width="100%" />
<p class="caption">(\#fig:bar-plot)Bar plot of instrusions by condition</p>
</div>

### Activity 6: One-way ANOVA {#anova-a6}

Now we can run the one-way ANOVA using `aov_ez` from the `afex` package and save it to the object `mod`. As well as running the ANOVA, the `aov_ez` function also conducts a Levene's test for homogeneity of variance so that we can test our final assumption.

`aov_ez()` will likely produce some messages that look like errors, do not worry about these, they are just letting you know what it's done. 

* Copy and paste the below code to run and then view the results of the ANOVA using `anova(mod)`.


```r
mod <- aov_ez(id = "subject", # the column containing the subject IDs
              dv = "intrusions", # the DV 
              between = "Condition", # the between-subject variable
              es = "pes", # sets effect size to partial eta-squared
              type = 3, # this affects how the sum of squares is calculated, set this to 3
              include_aov = TRUE,
              data = dat2)

anova(mod)
```

Just like with the t-tests and correlations, we can use `tidy()` to make the output easier to work with.

* Run the below code to transform the output. Don't worry about the warning message, it is just telling you it doesn't know how to automatically rename the columns so it will keep the original names.


```r
mod_output <- (mod$anova_table) %>% tidy()
```

```
## Warning in tidy.anova(.): The following column names in ANOVA output were not
## recognized or transformed: num.Df, den.Df, MSE, ges
```

* `term` = the IV  
* `num.Df` = degrees of freedom effect
* `den.Df` = degrees of freedom residuals
* `MSE` = Mean-squared errors
* `statistic` = F-statistic
* `ges` = effect size  
* `p.value` = p.value

You should refer to the lecture for more information on what each variable means and how it is calculated.

* Is the overall effect of Condition significant? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
* What is the F-statistics to 2 decimal places? <input class='webex-solveme nospaces' size='4' data-answer='["3.79"]'/>
* According to the rules of thumb, the effect size is <select class='webex-select'><option value='blank'></option><option value=''>Small</option><option value=''>Medium</option><option value='answer'>Large</option></select>


### Activity 7: Assumption checking {#anova-a7}

You may be wondering why we haven't yet checked the assumptions. Well, unlike the t-tests and correlations, in order to test the assumptions we need to use the model we created with `aov_ez()`, so we couldn't assess them all until this point. For a one-way independent ANOVA, the assumptions are the same as for a Student's t-test:

1. The DV is interval or ratio data
2. The observations should be independent
3. The residuals should be normally distributed
4. There should be homogeneity of variance between the groups

We know that 1 and 2 are met because of the design of our study. To test 3, we can look at the QQ-plot of the residuals and test for normality with the Shapiro-Wilk test. The residuals have been stored as one of the components of `mod`. To access them we specify `mod$aov$residuals`.


```r
qqPlot(mod$aov$residuals)
```

<div class="figure" style="text-align: center">
<img src="14-anova_files/figure-html/fig-qq-1.png" alt="qq-plot for model residuals" width="100%" />
<p class="caption">(\#fig:fig-qq)qq-plot for model residuals</p>
</div>

```r
shapiro.test(mod$aov$residuals)
```

```
## [1] 11 60
## 
## 	Shapiro-Wilk normality test
## 
## data:  mod$aov$residuals
## W = 0.87739, p-value = 4.252e-06
```

There are a few things to note about the assumption test results. First, look at the p-value for the Shapiro-Wilk test - `4.252e-06`. Whenever you see the `e` at the end of a number it means that R is using **scientific notation**. Scientific notation is a way of writing very large or very small numbers. Because the number after the `e` is negative it means the number should be divided by 10 to the power of six. Put simply, move the decimal place six places to the left and you will get the standard number. When reporting p-values in your results section, you should not use scientific notation, instead you should round to 3 decimal places.

* What is the value of `4.252e-06`? <select class='webex-select'><option value='blank'></option><option value=''>.004252</option><option value=''>42.52</option><option value='answer'>.000004252</option></select>

If you want R to round this for you to make it easier to read, you could use the below code to save it to an object, tidy it and then round the p.value. Just remember that in APA style you should never write "p = 0", instead, you should write "p < .001" (because p will never equal actual zero, it can just be very, very, very small).


```r
shapiro <- shapiro.test(mod$aov$residuals) %>% #run the test
  tidy() %>% # tidy the output
  mutate(p.value = round(p.value, digits = 3)) # overwrite the p-value with one rounded to 3 decimal places
```

If you find scientific notation difficult to read, you can paste and run the following code in your console to turn it off

```r
options(scipen=999)
```


The second thing to note is that from both the qq-plot and the Shapiro-Wilk test it is clear that the assumption of normality has not been met. Is this a problem? Well, Field et al. (2009) say that if the sample sizes for each group are equal then ANOVA is robust to violations of both normality and of homogeneity of variance. There's also a good discussion of this [here](https://link.springer.com/article/10.3758/s13428-017-0918-2) but it is a bit technical. We can check how many participants are in each condition using `count()`:


```r
dat2 %>% count(Condition)
```


| Condition | n  |
|:---------:|:--:|
|     1     | 18 |
|     2     | 18 |
|     3     | 18 |
|     4     | 18 |

Thankfully the sample sizes are equal so we should be OK to proceed with the ANOVA. It is not clear whether normality was checked in the original paper.

For the last assumption, we can test homogeneity of variance with Levene's test and the function `test_levene()` from `performance`. The code for this is very simple, you just need to supply the ANOVA model we created earlier `mod`.


```r
test_levene(mod)
```

```
## Warning: Functionality has moved to the 'performance' package.
## Calling 'performance::check_homogeneity()'.
```

```
## Warning: Variances differ between groups (Levene's Test, p = 0.039).
```

The results from Levene's test show that the assumption of homogeneity of variance has also not been met. The paper does indicate this might be the case as it specifies that the ANOVAs do not assume equal variance, however, the results of the ANOVA that are reported are identical to our results above where no correction has been made although the post-hoc tests are Welch tests (you can tell this because the degrees of freedom have been adjusted and are not whole numbers).

Whilst all of this might seem very confusing - we imagine you might be wondering what the point of assumption testing is given that it seems to be ignored - we're showing you this for three reasons: 

1. To reassure you that sometimes the data can fail to meet the assumptions and it is still ok to use the test. To put this in statistical terms, many tests are **robust** to mild deviations of normality and unequal variance, particularly with equal sample sizes. 
2. As a critical thinking point, to remind you that just because a piece of research has been published does not mean it is perfect and you should always evaluate whether the methods used are appropriate. 
3. To reinforce the importance of pre-registration where these decisions could be made in advance, and/or open data and code so that analyses can be reproduced exactly to avoid any ambiguity about exactly what was done. In this example, given the equal sample sizes and the difference in variance between the groups isn't too extreme, it looks like it is still  appropriate to use an ANOVA but the decisions and justification for those decisions could have been more transparent.


### Activity 8: Post-hoc tests {#anova-a8}

For post-hoc comparisons, as mentioned, the paper appears to have computed Welch t-tests but there is no mention of any multiple comparison correction. We could reproduce these results by using `t.test` for each of the contrasts.

For example, to compare condition 1 (the control group) with condition 2 (the reactivation plus tetris group) we could run:


```r
dat2 %>%
  filter(Condition %in% c("1", "2")) %>%
  droplevels() %>% 
  t.test(intrusions ~ Condition, data = .)
```

<div class="info">
<p>Because <code>Condition</code> has four levels, we can’t just specify <code>intrustion ~ Condition</code> because a t-test compares two groups and it wouldn’t know which of the four to compare so first we have to filter the data and use a new function <code>droplevels()</code>. It's important to remember that when it comes to R there are two things to consider, the data you can see and the underlying structure of that data. In the above code we use <code>filter()</code> to select only conditions 1 and 2 so that we can compare them. However, that doesn't change the fact that R "knows" that <code>Condition</code> has four levels - it doesn't matter if two of those levels don't have any observations any more, the underlying structure still says there are four groups. <code>droplevels()</code> tells R to remove any unused levels from a factor. Try running the above code but without <code>droplevels()</code> and see what happens.</p>
</div>

However, a quicker and better way of doing this that allows you apply a correction for multiple comparisons easily is to use `emmeans()` which computes all possible pairwise comparison t-tests and applies a correction to the p-value. 

First, we use `emmeans()` to run the comparisons and then we can pull out the contrasts and use `tidy()` to make it easier to work with.

* Run the code below. Which conditions are significantly different from each other? Are any of the comparisons different from the ones reported in the paper now that a correction for multiple comparisons has been applied?


```r
mod_pairwise <-emmeans(mod, pairwise ~ Condition, adjust = "bonferroni")
mod_contrasts <- mod_pairwise$contrasts %>% tidy()
```

<div class="warning">
<p>The inquisitive amongst you may have noticed that <code>mod</code> is a list of 5 and seemingly contains the same thing three times: <code>anova_table</code>, <code>aov</code> and <code>Anova</code>. The reasons behind the differences are too complex to go into detail on this course (see <a href="https://rcompanion.org/rcompanion/d_04.html">here</a> for more info) but the simple version is that <code>anova_table</code> and <code>Anova</code>use one method of calculating the results (type 3 sum of squares) and <code>aov</code> uses a different method (type 1 sum of squares). What's important for your purposes is that you need to use <code>anova_table</code> to view the overall results (and replicate the results from papers) and <code>aov</code>to run the follow-up tests and to get access to the residuals (or <code>lm()</code> for factorial ANOVA). As always, precision and attention to detail is key.</p>
</div>

### Activity 9: Power and effect size {#anova-a9}

Finally, we can replicate their power analysis using `pwr.anova.test`.

> On the basis of the effect size of d = 1.14 from Experiment 1, we assumed a large effect size of f = 0.4. A sample size of 18 per condition was required in order to ensure an 80% power to detect this difference at the 5% significance level.


```r
pwr.anova.test(k = 4, f = .4, sig.level = .05, power = .8)
```

```
## 
##      Balanced one-way analysis of variance power calculation 
## 
##               k = 4
##               n = 18.04262
##               f = 0.4
##       sig.level = 0.05
##           power = 0.8
## 
## NOTE: n is number in each group
```

We've already got the effect size for the overall ANOVA, however, we should also really calculate Cohen's D using `cohensD` from `lsr` for each of the pairwise comparisons. This code is a little complicated because you need to do it separately for each comparison, bind them all together and then add them to `mod_contrasts` - just make sure your understand which bits of the code you would need to change to run this on different data.


```r
d_1_2 <- cohensD(intrusions ~ Condition, 
                 data = filter(dat2, Condition %in% c(1,2)) %>% 
                   droplevels())

d_1_3 <- cohensD(intrusions ~ Condition, 
                 data = filter(dat2, Condition %in% c(1,3)) %>%
                   droplevels()) 

d_1_4 <- cohensD(intrusions ~ Condition, 
                 data = filter(dat2, Condition %in% c(1,4)) %>%
                   droplevels())

d_2_3 <- cohensD(intrusions ~ Condition, 
                 data = filter(dat2, Condition %in% c(2,3)) %>% 
                   droplevels())

d_2_4 <- cohensD(intrusions ~ Condition, 
                 data = filter(dat2, Condition %in% c(2,4)) %>% 
                   droplevels())

d_3_4 <- cohensD(intrusions ~ Condition, 
                 data = filter(dat2, Condition %in% c(3,4)) %>%
                   droplevels())

pairwise_ds <- c(d_1_2,d_1_3,d_1_4,d_2_3,d_2_4,d_3_4)

mod_contrasts <- mod_contrasts %>%
  mutate(eff_size = pairwise_ds)
```


<div class="warning">
<p>What are your options if the data don't meet the assumptions and it's really not appropriate to continue with a regular one-way ANOVA? As always, there are multiple options and it is a judgement call.</p>
<ol style="list-style-type: decimal">
<li>You could run a non-parametric test, the Kruskal-Wallis for between-subject designs and the Friedman test for within-subject designs.</li>
<li>If normality is the problem, you could try transforming the data. Field et al. (2009) has a good section on data transformation.</li>
<li>You could use bootstrapping, which is not something we will cover in this course at all. Again, Field et al. (2009) covers this although it is a little complicated.</li>
</ol>
</div>

### Activity 10: Write-up {#anova-a10}

The below code replicates the write-up in the paper, although has changed the Welch t-test to the pairwise comparisons from `emmeans`.


```r
Second, and critically, for the 7-day diary postintervention, there was a significant difference between groups in overall intrusion frequency in daily life, F(`r mod_output$num.Df`, `r mod_output$den.Df`) = `r mod_output$statistic %>% round(2)`, p = `r mod_output$p.value %>% round(3)`, ηp2 = .`r mod_output$ges %>% round(2)`. Planned comparisons demonstrated that relative to the no-task control group, only those in the reactivation-plus-Tetris group, t(`r mod_contrasts$df[1]`) = `r mod_contrasts$statistic[1] %>% round(2)`, p = `r mod_contrasts$adj.p.value[1] %>% round(2)`, d = `r mod_contrasts$eff_size[1] %>% round(2)`, experienced significantly fewer intrusive memories; this finding replicated Experiment 1. The reactivation-plus-Tetris group had significantly fewer intrusive thoughts than the reactivation-only group, t(`r mod_contrasts$df[5]`) = `r mod_contrasts$statistic[5] %>% round(2)`, p = `r mod_contrasts$adj.p.value[5] %>% round(2)`, d = `r mod_contrasts$eff_size[5] %>% round(2)`. Further, there were no significant differences between the reactivation-plus-Tetris group and the Tetris-only group, t(`r mod_contrasts$df[4]`) = `r mod_contrasts$statistic[4] %>% round(2)`, p = `r mod_contrasts$adj.p.value[4] %>% round(2)`, d = `r mod_contrasts$eff_size[4] %>% round(2)`, the no-task control group and the reactivation-only group, t(`r mod_contrasts$df[3]`) = `r mod_contrasts$statistic[3] %>% round(2)`, p = `r mod_contrasts$adj.p.value[3] %>% round(2)`, or between the no-task control group and the Tetris-only group, t(`r mod_contrasts$df[2]`) = `r mod_contrasts$statistic[2] %>% round(2)`, p = `r mod_contrasts$adj.p.value[2] %>% round(2)`
```

Second, and critically, for the 7-day diary postintervention, there was a significant difference between groups in overall intrusion frequency in daily life, F(3, 68) = 3.79, p = 0.014, ηp2 = .0.14. Planned comparisons demonstrated that relative to the no-task control group, only those in the reactivation-plus-Tetris group, t(68) = 3.04, p = 0.02, d = 1, experienced significantly fewer intrusive memories; this finding replicated Experiment 1. Critically, as predicted by reconsolidation theory, the reactivation-plus-Tetris group had significantly fewer intrusive memories than the Tetris-only group, t(68) = -1.89, p = 0.38, d = 0.84, as well as the reactivation-only group, t(68) = -2.78, p = 0.04, d = 1.11. Further, there were no significant differences between the no-task control group and the reactivation-only group, t(68) = 0.26, p = 1, or between the no-task control group and the Tetris-only group, t(68) = 1.15, p = 1

### Activity solutions {#anova-sols}

Below this line you will find the solutions to the above tasks. Only look at them after giving the tasks a good try yourself!

#### Activity 1 {#anova-1sol}


<div class='webex-solution'><button>Solution</button>


```r
library("pwr")
library("lsr")
library("car")
library("broom")
library("afex")
library("emmeans")
libr\ry("performance")
library("tidyverse")

dat <- read_csv("James Holmes_Expt 2_DATA.csv")%>%
  mutate(subject = row_number())
```

</div>


** Click tab to see solution **

#### Activity 2 {#anova-a2sol}


<div class='webex-solution'><button>Solution</button>


```r
dat2 <- dat%>%
  select(subject,Condition,Days_One_to_Seven_Image_Based_Intrusions_in_Intrusion_Diary)%>%
  rename(intrusions = Days_One_to_Seven_Image_Based_Intrusions_in_Intrusion_Diary)
```

</div>


** Click tab to see solution **


#### Activity 4 {#anova-a4sol}


<div class='webex-solution'><button>Solution</button>


```r
sum_dat<-dat2%>%
  group_by(Condition)%>%
  summarise(mean = mean(intrusions),
            sd = sd(intrusions),
            se = sd/sqrt(length(intrusions)))
```

</div>


** Click tab to see solution **

#### Activity 5 {#anova-a5sol}


<div class='webex-solution'><button>Solution</button>


```r
ggplot(dat2, aes(x = Condition, y = intrusions))+
  geom_violin(trim = FALSE)+
  geom_boxplot(width = .2)
```

</div>


** Click tab to see solution **

<!--chapter:end:14-anova.Rmd-->

# Factorial ANOVA

For this chapter, we're going to look at an example of a factorial ANOVA. You'll learn more about interpreting these in the lectures, but for now, we'll just focus on the code. 

We're going to reproduce the analysis from Experiment 3 of [Zhang, T., Kim, T., Brooks, A. W., Gino, F., & Norton, M. I. (2014). A "present" for the future: The unexpected value of rediscovery. Psychological Science, 25, 1851-1860.](https://journals.sagepub.com/doi/abs/10.1177/0956797614542274). You may remember this study from the Chapter Visualisation chapter. 

This experiment has a 2 x 2 mixed design:

* The first IV is time (time1, time2) and is within-subjects 
* The second IV is type of event (ordinary vs. extraordinary) and is a between-subjects factor 
* The DV we will use is `interest` 

### Activity 1: Set-up {#factorial-a1}

* Open R Studio and set the working directory to your chapter folder. Ensure the environment is clear. 
* Open a new R Markdown document and save it in your working directory. Call the file "Factorial ANOVA". 
* Download <a href="Zhang et al. 2014 Study 3.csv" download>Zhang et al. 2014 Study 3.csv</a> and extract the files in to your Chapter 15 folder. 
* If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* If you are working on your own computer, install the package `rcompanion`. Remember **do not install packages on university computers, they are already installed**.
* Type and run the code that loads `pwr`, `rcompanion`, `lsr`, `car`, `broom`, `afex`, `emmeans` and `tidyverse` using the `library()` function.



Run the below code to load the data and wrangle it into the format we need. You don't need to write this code yourself but do make sure you can understand what each line is doing - a good way to do this when the code uses pipes (`%>%`) is to highlight and run each line progressively so you can see how it builds up. Line-by-line the code:

* Reads in the data file
* Select the three columns we need  
* Adds on a column of subject IDs  
* Tidies the data
* Recodes the values of `Condition` from numeric to text labels
* Recodes the values of `time` to be easier to read/write


```r
factorial <- read_csv("Zhang et al. 2014 Study 3.csv")%>%
  select(Condition, T1_Predicted_Interest_Composite, T2_Actual_Interest_Composite)%>%
  mutate(subject = row_number())%>%
  pivot_longer(names_to = "time",values_to = "interest", cols =       c("T1_Predicted_Interest_Composite","T2_Actual_Interest_Composite"))%>%
  mutate(Condition = dplyr::recode(Condition, "1" = "Ordinary", "2" = "Extraordinary"))%>%
  mutate(time = dplyr::recode(time, "T1_Predicted_Interest_Composite" = "time1_interest",
                       "T2_Actual_Interest_Composite" = "time2_interest")) %>%
  mutate(Condition = as.factor(Condition)) %>% 
  mutate (time= as.factor(time))
```

### Activity 2: Descriptive statistics {#factorial-a2}

* Calculate descriptive statistics (mean and SD) for `interest`  for each `Condition` for each `time` (hint: you will need to `group_by()` two variables) and store it in an object named `sum_dat_factorial`. These are known as the cells means.




### Activity 3: Violin-boxplots {#factorial-a3}

We're going to produce two kinds of plots to visualise our data. First, we'll produce violin-boxplots so that we can see the distribution of our data.

* Write the code that produces the below violin-boxplots for the scores in each group. 
  * Hint 1: you will need to add in the second IV in the first call to ggplot as a fill argument (aes(x,y,fill)). 
  * Hint 2: you will need to add `position = position_dodge(.9)` to geom_boxplot to get the plots to align. 

You don't need to replicate the exact colour scheme used below, see if you can play around with the settings to whatever colour scheme you think works best.

<div class="figure" style="text-align: center">
<img src="15-factorial-anova_files/figure-html/plt1-1.png" alt="Violin-boxplot by condition and time" width="100%" />
<p class="caption">(\#fig:plt1)Violin-boxplot by condition and time</p>
</div>

### Activity 4: Interaction plots {#factorial-a4}

Now we're going to produce an interaction plot that makes it easier to see how the IVs are interacting, which requires some ggplot2 functions we haven't come across yet. Rather than using the raw data in `dat_factorial`, we use the means that we produced in `sum_dat_factorial`. This type of plot requires two geoms, one to draw the points, and one to draw the lines that connect them. 

This plot reproduces the plot used in the paper.

* Run the code and then play around with how it looks by changing the arguments for e.g., colour, line-type, and the theme.


```r
ggplot(sum_dat_factorial, aes(x = time, y = mean, group = Condition, shape = Condition)) +
  geom_point(size = 3) +
  geom_line(aes(linetype = Condition))+
  scale_x_discrete(labels = c("Time 1", "Time 2"))+
  theme_classic()
```

<div class="figure" style="text-align: center">
<img src="15-factorial-anova_files/figure-html/plot2-1.png" alt="Interaction plot" width="100%" />
<p class="caption">(\#fig:plot2)Interaction plot</p>
</div>

### Activity 5: ANOVA {#factorial-a5}

* Complete the below code to run the factorial ANOVA. Remember that you will need to specify both IVs and that one of them is between-subjects and one of them is within-subjects. Look up the help documentation for `aov_ez` to find out how to do this. 

* Save the ANOVA model to an object called `mod_factorial`
* Pull out the anova table, you can either do this with `mod_factorial$anova_table` or `anova(mod_factorial)` both have the same result. Save this to an object named `factorial_output` and make sure you have used `tidy()`.





```r
mod_factorial <- aov_ez(id = "NULL",
               data = NULL, 
               between = "NULL", 
               within = "NULL",
               dv = "NULL", 
               type = 3,
               es = "NULL") 

factorial_output <- NULL
```

Look at the results. Remember the pre-class information about how to read p-values in scientific notation.

* Is the main effect of condition significant? <select class='webex-select'><option value='blank'></option><option value=''>Yes</option><option value='answer'>No</option></select>
* Is the main effect of time significant? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>
* Is the two-way interaction significant? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>

### Activity 6: Assumption checking {#factorial-a6}

The assumptions for a factorial ANOVA are the same as the one-way ANOVA.

1. The DV is interval or ratio data
2. The observations should be independent
3. The residuals should be normally distributed
4. There should be homogeneity of variance between the groups

As before, we know assumption 2 is met from the design of the study. Assumption 1 throws up an interesting issue which is the problem of ordinal data. Ordinal data are the kind of data that come from Likert scales and are very common in psychology. The problem is that ordinal data aren't interval or ratio data, there's a fixed number of values they can take (the values of the Likert scale) and you can't claim that the distance between the values is equal (is the difference between strongly agree and agree the same as the difference between agree and neutral?). 

Technically, we shouldn't use an ANOVA to analyse ordinal data - *but almost everyone does*. Most people would argue that if there are multiple Likert scale items that are averaged (which is the case in our study) and this averaged data are normally distributed, then it is not a problem. There is a minority (who are actually correct) that argue you should use non-parametric methods or more complicated tests such as ordinal regression for this type of data. Whichever route you choose, you should understand the data you have and you should be able to justify your decision.

* To test assumption 3, extract the residuals from the model (`mod_factorial$lm$residuals`), create a qq-plot and conduct a Shapiro-Wilk test.

* Are the residuals normally distributed? <select class='webex-select'><option value='blank'></option><option value=''>Yes</option><option value=''>No</option><option value='answer'>No, but given the sample it is probably acceptable to proceed</option></select> 

For the final assumption, we can again use `test_levene()` to test homogeneity of variance.

* Conduct Levene's test. Is assumption 4 met? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>


### Activity 7: Post-hoc tests {#factorial-a7}

Because the interaction is significant, we should follow this up with post-hoc tests using `emmeans()` to determine which comparisons are significant. If the overall interaction is not significant, you should not conduct additional tests.

`emmeans()` requires you to specify the `aov` object, and then the factors you want to contrast. For an interaction, we use the notation `pairwise ~ IV1 | IV2` and you specify which multiple comparison correction you want to apply. Finally, you can use `tidy()` to tidy up the output of the contrasts and save it into a tibble.

* Run the below code and view the results. 


```r
# run the tests
posthoc_factorial <- emmeans(mod_factorial, 
                             pairwise ~ time| Condition, 
                             adjust = "bonferroni")

# tidy up the output of the tests
contrasts_factorial <- posthoc_factorial$contrasts %>%
  tidy()
```

Note that because there are two factors, we could also reverse the order of the IVs. Above, we get the results contrasting time 1 and time 2 for each event condition. Instead, we could look at the difference between ordinary and extraordinary events at each time point.

* Run the below code and look at the output of `contrast_factorial` and `contrasts_factorial2` carefully making sure you understand how to interpret the results. You will find it useful to refer to the interaction plot we made earlier.


```r
posthoc_factorial2 <- emmeans(mod_factorial, 
                             pairwise ~ Condition| time, 
                             adjust = "bonferroni") 

contrasts_factorial2 <- posthoc_factorial2$contrasts %>%
  tidy()
```

Because our main effects (condition and time) only have two levels, we don't need to do any post-hoc tests to determine which conditions differ from each other, however, if one of our factors had three levels then we could use `emmeans()` to calculate the contrast for the main effects, like we did for the one-way ANOVA. 

Finally, to calculate effect size for the pairwise comparisons we again need to do this individually using 'cohensD()` from `lsr`. 

* Run the below code to add on effect sizes to `contrasts_factorial` and `contrasts_factorial2`.


```r
d_extra_t1_t2 <- cohensD(interest ~ time, 
                         data = (filter(factorial, Condition == "Extraordinary") %>% droplevels())) 

d_ord_t1_t2 <- cohensD(interest ~ time, 
                         data = (filter(factorial, Condition == "Ordinary") %>% droplevels())) 


Condition_ds <- c(d_extra_t1_t2, d_ord_t1_t2)

contrasts_factorial <- contrasts_factorial %>%
  mutate(eff_size = Condition_ds)

d_time1_extra_ord <- cohensD(interest ~ Condition, 
                         data = (filter(factorial, time == "time1_interest") %>% droplevels())) 

d_time2_extra_ord <- cohensD(interest ~ Condition, 
                         data = (filter(factorial, time == "time2_interest") %>% droplevels()))


time_ds <- c(d_time1_extra_ord, d_time2_extra_ord)

contrasts_factorial2 <- contrasts_factorial2 %>%
  mutate(eff_size = time_ds)
```

### Activity 8: Write-up {#factorial-a8}

* p-values of < .001 have been entered manually. There is a way to get R to produce this formatting but it's overly complicated for our purposes. If you want to push yourself, look up the [papaja](https://github.com/crsh/papaja) package. 
* The values of partial eta-squared do not match between our analysis and those reported in the paper. I haven't figured out why this is yet - if you know, please get in touch!
* We have replaced the simple effects in the main paper with our pairwise comparisons. 

First we need to calculate descriptives for the main effect of time as we didn't do this earlier.


```r
time_descrip <- factorial %>% 
  group_by(time) %>%
  summarise(mean_interest = mean(interest, na.rm = TRUE),
            sd_interest = sd(interest, na.rm = TRUE))
```

Copy and paste the below into **white-space**.


```r
We conducted the same repeated measures ANOVA with interest as the dependent measure and again found a main effect of time, F(`r factorial_output$num.Df[2]`, `r factorial_output$den.Df[2]`) = `r factorial_output$statistic[2] %>% round(2)`, p < .001, ηp2 = `r factorial_output$ges[2] %>% round(3)`; anticipated interest at Time 1 (M = `r time_descrip$mean_interest[1] %>% round(2)`), SD = `r time_descrip$sd_interest[1]%>% round(2)`)) was lower than actual interest at Time 2 (M = `r time_descrip$mean_interest[2]%>% round(2)`, SD = `r time_descrip$sd_interest[2]%>% round(2)`).We also observed an interaction between time and type of experience, F(`r factorial_output$num.Df[3]`, `r factorial_output$den.Df[3]`) = `r factorial_output$statistic[3] %>% round(3)`, p = `r factorial_output$p.value[3] %>% round(2)`, ηp2 = `r factorial_output$ges[3] %>% round(3)`. Pairwise comparisons revealed that for ordinary events, predicted interest at Time 1 (M = `r sum_dat_factorial$mean[3]%>% round(2)`, SD = `r sum_dat_factorial$sd[3]%>% round(2)`) was lower than experienced interest at Time 2 (M = `r sum_dat_factorial$mean[4]%>% round(2)`, SD = `r sum_dat_factorial$sd[4]%>% round(2)`), t(`r contrasts_factorial$df[2]%>% round(2)`) = `r contrasts_factorial$statistic[2]%>% round(2)`, p < .001, d = `r contrasts_factorial$eff_size[2]%>% round(2)`. Although predicted interest for extraordinary events at Time 1 (M = `r sum_dat_factorial$mean[1]%>% round(2)`, SD = `r sum_dat_factorial$sd[1]%>% round(2)`) was lower than experienced interest at Time 2 (M = `r sum_dat_factorial$mean[2]%>% round(2)`, SD = `r sum_dat_factorial$sd[2]%>% round(2)`), t(`r contrasts_factorial$df[1]%>% round(2)`) = `r contrasts_factorial$statistic[1]%>% round(2)`, p < .001, d = `r contrasts_factorial$eff_size[1]%>% round(2)` , the magnitude of underestimation was smaller than for ordinary events.
```

> We conducted the same repeated measures ANOVA with interest as the dependent measure and again found a main effect of time, F(1, 128) = 25.88, p < .001, ηp2 = 0.044; anticipated interest at Time 1 (M = 4.2), SD = 1.12)) was lower than actual interest at Time 2 (M = 4.69, SD = 1.19).We also observed an interaction between time and type of experience, F(1, 128) = 4.445, p = 0.04, ηp2 = 0.008. Pairwise comparisons revealed that for ordinary events, predicted interest at Time 1 (M = 4.04, SD = 1.09) was lower than experienced interest at Time 2 (M = 4.73, SD = 1.24), t(128) = -5.05, p < .001, d = 0.59. Although predicted interest for extraordinary events at Time 1 (M = 4.36, SD = 1.13) was lower than experienced interest at Time 2 (M = 4.65, SD = 1.14), t(128) = -2.12, p < .001, d = 0.25 , the magnitude of underestimation was smaller than for ordinary events.

### Activity 9: Transforming data {#factorial-a9}

In this chapter we decided that the violation of the assumption of normality was ok so that we could replicate the results in the paper. But what if we weren't happy with this or if the violation had been more extreme? One option to deal with normality is to **transform your data**. If you want more information on this you should consult the Appendix chapter on data transformation.

There are various options for how you can transform data but we're going to use Tukeys Ladder of Powers transformation. This finds the power transformation that makes the data fit the normal distribution as closely as possible with this type of transformation.

* Run the below code. This will use `mutate()` to add a new variable to the data-set, `interest_tukey` which is going to be our transformed DV. The function `transformTukey()` is from the `rcompanion` package. Setting `plotit = TRUE` will automatically create qqPlots and histograms so that we can immediately visualise the new variable. 



```r
factorial <- factorial %>%
  mutate(interest_tukey = transformTukey(interest, plotit=TRUE))
```



Now that you've transformed the DV we can re-run the ANOVA with this new variable.


```r
tukey_factorial <- aov_ez(id = "subject",
               data = factorial, 
               between = "Condition", 
               within = "time",
               dv = "interest_tukey", 
               type = 3)

tukey_factorial
```

Notice that doing this hasn't changed the pattern of the ANOVA results, the p-values for the main effects and interactions are very slightly different but the overall conclusions remain the same. This is likely because the violations of normality was quite mild and there is a large sample size, however, with the transformation we can be more confident in our results and it may not always be the case that the transformed ANOVA is the same if the violations were more extreme. 

#### Finished! {#factorial-fin}


### Activity solutions {#factorial-sols}

#### Activity 1 {#factorial-a1sol}


<div class='webex-solution'><button>Activity 1</button>


```r
library("pwr")
library("rcompanion")
library("car")
library("lsr")
library("broom")
library("afex")
library("emmeans")
library("tidyverse")
```

</div>


** Click tab to see solution **


#### Activity 2 {#factorial-a2sol}


<div class='webex-solution'><button>Solution</button>


```r
sum_dat_factorial<-factorial%>%
  group_by(Condition, time)%>%
  summarise(mean = mean(interest, na.rm = TRUE),
            sd = sd(interest, na.rm = TRUE)
            )
```

</div>


** Click tab to see solution **


#### Activity 3 {#factorial-a3sol}


<div class='webex-solution'><button>Solution</button>


```r
ggplot(factorial, 
       aes(x = time , y = interest, fill = Condition))+
  geom_violin(trim = FALSE, 
              alpha = .4)+
  geom_boxplot(position = position_dodge(.9), 
               width = .2, 
               alpha = .6)+
  scale_x_discrete(labels = c("Time 1", "Time 2"))+
  scale_fill_viridis_d(option = "E")+
  stat_summary(fun = "mean", geom = "point",
               position = position_dodge(width = 0.9)) +
  stat_summary(fun.data = "mean_se", geom = "errorbar", width = .1,
               position = position_dodge(width = 0.9)) +
  theme_minimal()
```

</div>


** Click tab to see solution **

#### Activity 5 {#factorial-a5sol}


<div class='webex-solution'><button>Solution</button>


```r
mod_factorial <- aov_ez(id = "subject",
               data = factorial, 
               between = "Condition", 
               within = "time",
               dv = "interest", 
               type = 3) 

factorial_output <- anova(mod_factorial) %>% tidy()

# OR

factorial_output <- mod_factorial$anova_table %>% tidy()
```

</div>


** Click tab to see solution **

#### Activity 6 {#factorial-a6sol}


<div class='webex-solution'><button>Solution</button>


```r
# normality testing
qqPlot(mod_factorial$lm$residuals)
shapiro.test(mod_factorial$lm$residuals)

# levene's test
test_levene(mod_factorial)
```

</div>


** Click tab to see solution **

<!--chapter:end:15-factorial-anova.Rmd-->

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


<!--chapter:end:16-regression.Rmd-->

# Multiple regression

There is currently much debate (and hype) surrounding smartphones and their effects on well-being, especially with regard to children and teenagers.  We'll be looking at data from this recent study of English adolescents:

> Przybylski, A. & Weinstein, N. (2017). A Large-Scale Test of the Goldilocks Hypothesis. *Psychological Science*, *28*, 204--215.

This was a large-scale study that found support for the "Goldilocks" hypothesis among adolescents: that there is a "just right" amount of screen time, such that any amount more or less than this amount is associated with lower well-being.  This was a huge survey study: the data contain responses from over 120,000 participants! 

Fortunately, the authors made the data from this study openly available, which allows us to dig deeper into their results. In this exercise, we will look at whether the relationship between screen time and well-being is modulated by participants' (self-reported) gender.

The dependent measure used in the study was the [Warwick-Edinburgh Mental Well-Being Scale (WEMWBS)](https://warwick.ac.uk/fac/med/research/platform/wemwbs/). This is a 14-item scale with 5 response categories, summed together to form a single score ranging from 14-70.

At [Przybylski & Weinstein's page for this study on the Open Science Framework](https://osf.io/82ybd/), you can find the [participant survey](https://osf.io/82ybd/) which asks a large number of additional questions (see page 14 for the WEMWBS questions and pages 4-5 for the questions about screen time). Within the same page you can also find the [raw data](https://osf.io/82ybd/); however, for the purpose of this exercise, you will be using local pre-processed copies of the data which we will provide.

Przybylski and Weinstein looked at multiple measures of screen time, but we will be focusing on smartphone use.  They found that decrements in well-being started to appear when respondents reported more than one hour of weekly smartphone use.  Our question: Does the negative association between hours of use and well-being (beyond the one-hour point) differ for boys and girls?

Note that in this analysis, we have:

- a continuous$^*$ DV, well-being;

- a continuous$^*$ predictor, screen time;

- a categorical predictor, gender.

$^*$these variables are only quasi-continuous, inasmuch as only discrete values are possible. However, there are a sufficient number of discrete categories that we can treat them as effectively continuous.

We want to estimate two slopes relating screen time to well-being, one for girls and one for boys, and then statistically compare these slopes. So this problem seems simultaneously like a situation where you would run a regression (to estimate the slopes) but also one where you would need a t-test (to compare two groups).

But the expressive power of regression allows us to do this all within a single model. As the [Bishop blog showed](http://deevybee.blogspot.com/2017/11/anova-t-tests-and-regression-different.html), *an independent groups t-test is just a special case of ordinary regression with a single categorical predictor; ANOVA is just a special case of regression where all predictors are categorical.*  So although we can express any ANOVA design using regression, the converse is not true: we cannot express every regression design in ANOVA. Regression allows us to have any combination of continuous and categorical predictors in the model. The only inconvenience with running ANOVA models as regression models is that you have to take care in how you numerically code the categorical predictors.

## Activity 1: Set-up {#mulregression-a1}

* Open R Studio and set the working directory to your chapter folder. Ensure the environment is clear.    
* Open a new R Markdown document and save it in your working directory. Call the file "Multiple Regression".    
* Download <a href="wellbeing.csv" download>wellbeing.csv</a>, <a href="participant_info.csv" download>participant_info.csv</a> and <a href="screen_time.csv" download>screen_time.csv</a> and save them in your Chapter folder. Make sure that you do not change the file names at all.    
* If you're on the server, avoid a number of issues by restarting the session - click `Session` - `Restart R` 
* Delete the default R Markdown welcome text and insert a new code chunk that loads `pwr`, `see`, `performance`, `report`, and `tidyverse` using the `library()` function.
* Load the CSV datasets into variables called `pinfo`, `wellbeing` and `screen` using `read_csv()`.


```
## Warning: package 'see' was built under R version 4.1.2
```

```
## Warning: package 'performance' was built under R version 4.1.2
```

```
## Warning: package 'report' was built under R version 4.1.2
```

## Activity 2: Look at the data {#mulregression-a2}

Take a look at the resulting tibbles `pinfo`, `wellbeing`, and `screen`.  The `wellbeing` tibble has information from the WEMWBS questionnaire; `screen` has information about screen time use on weekends (variables ending with `we`) and weekdays (variables ending with `wk`) for four types of activities: using a computer (variables starting with `Comph`; Q10 on the survey), playing video games (variables starting with `Comp`; Q9 on the survey), using a smartphone (variables starting with `Smart`; Q11 on the survey) and watching TV (variables starting with `Watch`; Q8 on the survey).  If you want more information about these variables, look at the items 8-11 on pages 4-5 of the the [PDF version of the survey on the OSF website](https://osf.io/82ybd/).

* The variable corresponding to *gender* is located in the table named <select class='webex-select'><option value='blank'></option><option value='answer'>pinfo</option><option value=''>wellbeing</option><option value=''>screen</option></select> and this variable is called <input class='webex-solveme nospaces' size='6' data-answer='["male"]'/>.

* The WEMWBS data is in <select class='webex-select'><option value='blank'></option><option value=''>long</option><option value='answer'>wide</option></select> format, and contains observations from <input class='webex-solveme nospaces' size='10' data-answer='["102580","102,580"]'/> participants on <input class='webex-solveme nospaces' size='2' data-answer='["15"]'/> items.

* Individual participants in this dataset are identified by the variable named <input class='webex-solveme nospaces' size='9' data-answer='["Serial"]'/> [be sure to type the name *exactly*, including capitalization].  This variable will allow us to link information across the three tables.

* Run `summary()` on the three data-sets. Are there any missing data points? <select class='webex-select'><option value='blank'></option><option value=''>Yes</option><option value='answer'>No</option></select>


## Activity 3: Compute the well-being score for each respondent {#mulregression-a3}

The WEMWBS well-being score is simply the *sum* of all the items. 

* Write the code to create a new table called `wemwbs`, with two variables: `Serial` (the participant ID), and `tot_wellbeing`, the total WEMWBS score.


<div class='webex-solution'><button>Hint</button>

- "pivot" the table from wide to long

</div>



<div class='webex-solution'><button>Another Hint</button>

- `group_by()`; `summarise(tot_wellbeing = ...)`

</div>




**Sanity check:** Verify for yourself that the scores all fall in the 14-70 range.  Przybylski and Weinstein reported a mean of 47.52 with a standard deviation of 9.55. Can you reproduce these values?


<div class='webex-solution'><button>Hint</button>

- `summarise()`, `min()`, `max()`

</div>

<br>

* Now visualise the distribution of `tot_wellbeing` in a histogram using ggplot2.  


<div class='webex-solution'><button>Hint</button>

- `geom_histogram()`

</div>



<div class='webex-solution'><button>Solution</button>


```r
ggplot(wemwbs, aes(tot_wellbeing)) + geom_histogram() 
```

```
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

<img src="17-multiple-regression_files/figure-html/wemwbs_histogram-1.png" width="100%" style="display: block; margin: auto;" />


</div>


The distribution of well-being scores is <select class='webex-select'><option value='blank'></option><option value=''>symmetric</option><option value='answer'>negatively skewed</option><option value=''>positively skewed</option></select>.

## Activity 4: Visualise the relationship {#mulregression-a4}

Let's take a quick look at the relationship between screen time (for the four different technologies) and measures of well-being.  Here is code to do this. 

* Run the below code and try and explain in words what each line of code is doing (remember, pronounce `%>%` as "and then"). You may find it easier to look at each of the tables that are produced.


```r
screen_long <- screen %>%
  pivot_longer(names_to = "var", values_to = "hours", -Serial) %>%
  separate(var, c("variable", "day"), "_")

screen2 <- screen_long %>%
  mutate(variable = dplyr::recode(variable,
               "Watch" = "Watching TV",
               "Comp" = "Playing Video Games",
               "Comph" = "Using Computers",
               "Smart" = "Using Smartphone"),
     day = dplyr::recode(day,
              "wk" = "Weekday",
              "we" = "Weekend"))

dat_means <- inner_join(wemwbs, screen2, "Serial") %>%
  group_by(variable, day, hours) %>%
  summarise(mean_wellbeing = mean(tot_wellbeing))

ggplot(dat_means, aes(hours, mean_wellbeing, linetype = day)) +
  geom_line() +
  geom_point() +
  facet_wrap(~variable, nrow = 2)
```

<div class="figure" style="text-align: center">
<img src="17-multiple-regression_files/figure-html/combined-1.png" alt="Relationship between wellbeing and screentime usage by technology and weekday" width="100%" />
<p class="caption">(\#fig:combined)Relationship between wellbeing and screentime usage by technology and weekday</p>
</div>

The graph makes it evident that smartphone use of more than 1 hour per day is associated with increasingly negative well-being.  Note that we have combined the tables using an `inner_join()`, such that we only include data for which we have observations across the `wemwbs` and `screen2` tables.

In the next step, we are going to focus in on the smartphone/well-being relationship.

## Activity 5: Smartphone and well-being for boys and girls {#mulregression-a5}

For this analysis, we are going to collapse weekday and weekend use for smartphones.

* Create a new table, `smarttot`, that has the that has mean number of hours per day of smartphone use for each participant, averaged over weekends/weekdays. 
* You will need to filter the dataset to only include smartphone use and not other technologies. 
* You will also need to group the results by the participant ID (i.e., `serial`). 
* The final data-set should have two variables: `Serial` (the participant) and `tothours`.
* You will need to use the data-set `screen2` to do this.


<div class='webex-solution'><button>Hint</button>

- `filter()` then `group_by()` then `summarise()`

</div>


* Next, create a new tibble called `smart_wb` that only includes (filters) participants from `smarttot` who used a smartphone for more than one hour per day each week, and then combine (join) this table with the information in `wemwbs` and `pinfo`.**


<div class='webex-solution'><button>Hint</button>

- `filter()` then `inner_join()` then another `inner_join()`

</div>




## Activity 6: Mean-centering variables {#mulregression-a6}

As discussed in the lecture, When you have continuous variables in a regression, it is often sensible to transform them by *mean centering*.  You mean center a predictor `X` simply by subtracting the mean (`X_centered = X - mean(X)`). This has two useful consequences:

- the model intercept reflects the prediction for $Y$ at the mean value of the predictor variable, rather than at the zero value of the unscaled variable;

- if there are interactions in the model, any lower-order effects can be given the same interpretation as they receive in ANOVA (main effects, rather than simple effects).

For categorical predictors with two levels, these become coded as -.5 and .5 (because the mean of these two values is 0).

* Use `mutate` to add two new variables to `smart_wb`: `tothours_c`, calculated as a mean-centered version of the `tothours` predictor; and `male_c`, recoded as -.5 for female and .5 for male.
* To create `male_c` you will need to use `if_else(male == 1, .5, -.5)` You can read this code as "if the variable `male` equals 1, recode it as .5, if not, recode it as -.5".
* Finally, recode `male` and `male_c` as factors, so that R knows not to treat them as a real numbers.




## Activity 7: Visualise the relationship {#mulregression-a7}

* Reverse-engineer the below plot. Calculate mean well-being scores for each combination of `male` and `tothours`, and then create a scatterplot plot that includes separate regression lines for each gender.
* You may find it useful to refer to the Visualisation chapter.


<div class='webex-solution'><button>Hint</button>

- `group_by()` both variables then `summarise()`
- `colour = variable_you_want_different_colours_for`

</div>


<div class="figure" style="text-align: center">
<img src="17-multiple-regression_files/figure-html/plots-1.png" alt="Relationship between mean wellbeing and smartphone use by gender" width="100%" />
<p class="caption">(\#fig:plots)Relationship between mean wellbeing and smartphone use by gender</p>
</div>

Write an interpretation of the above plot in plain English.


<div class='webex-solution'><button>Possible solution</button>

Girls show lower overall well-being compared to boys.  In addition, the slope for girls appears more negative than that for boys; the one for boys appears relatively flat.  This suggests that the negative association between well-being and smartphone use is stronger for girls.

</div>


## Activity 8: Running the regression {#mulregression-a8}

Now we're going to see if there is statistical support for our above interpretation of the graph.

For the data in `smart_wb`, use the `lm()` function to calculate the multiple regression model:

$Y_i = \beta_0 + \beta_1 X_{1i}  + \beta_2 X_{2i}  + \beta_3 X_{3i} + e_i$

where

- $Y_i$ is the well-being score for participant $i$;
- $X_{1i}$ is the mean-centered smartphone use variable for participant $i$;
- $X_{2i}$ is gender (-.5 = female, .5 = male);
- $X_{3i}$ is the interaction between smartphone use and gender ($= X_{1i} \times X_{2i}$)

Then use `summary()` to view the results and store this in an object called `mod_summary()`.


<div class='webex-solution'><button>Hint</button>

- R formulas look like this: `y ~ a + b + a:b` where `a:b` means interaction

</div>




* The interaction between smartphone use and gender is shown by the variable <select class='webex-select'><option value='blank'></option><option value=''>thours_c</option><option value=''>male_c</option><option value='answer'>thours_c:male_c</option></select>, and this interaction was <select class='webex-select'><option value='blank'></option><option value='answer'>significant</option><option value=''>nonsignificant</option></select> at the $\alpha = .05$ level.

* To 2 decimal places, what proportion of the variance in well-being scores does the overall model explain? <input class='webex-solveme nospaces' size='4' data-answer='["9.38"]'/>

* The p-value for the overall model fit is `< 2.2e-16`. Is this significant? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>

* What is the most reasonable interpretation of these results? <select class='webex-select'><option value='blank'></option><option value=''>smartphone use harms girls more than boys</option><option value=''>smartphone use harms boys more than girls</option><option value=''>there is no evidence for gender differences in the relationship between smartphone use and well-being</option><option value='answer'>smartphone use was more negatively associated with wellbeing for girls than for boys</option></select>

## Activity 9: Assumption checking {#mulregression-a9}

Now it's time to test those pesky assumptions. The assumptions for multiple regression are the same as simple regression but there is one additional assumption, that of multicollinearity, the idea that predictor variables should not be too highly correlated.

1. The outcome/DV is a interval/ratio level data 
2. The predictor variable is interval/ratio or categorical (with two levels)
3. All values of the outcome variable are independent (i.e., each score should come from a different participant)
4. The predictors have non-zero variance
5. The relationship between outcome and predictor is linear
6. The residuals should be normally distributed
7. There should be homoscedasticity (homogeneity of variance, but for the residuals)
8. Multicollinearity: predictor variables should not be too highly correlated

From the work we've done so far we know that assumptions 1 - 4 are met and we can use the functions from the `performance` package again to check the rest, like we did with the simple linear regression chapter.

One difference from when we used `check_model()` previously is that rather than just letting it run all the tests it wants, we're going to specify which tests, to stop it throwing an error. A word of warning - these assumptions tests will take longer than usual to run, because it's such a big dataset. The first line of code will run the assumption tests and save it to an object, calling the object name will then display the plots.


```r
assumptions <- check_model(mod, check = c("vif", "qq", "normality", "linearity", "homogeneity"))

assumptions
```

<div class="figure" style="text-align: center">
<img src="17-multiple-regression_files/figure-html/unnamed-chunk-1-1.png" alt="Assumption plots" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-1)Assumption plots</p>
</div>

For assumption 5, linearity, we already know from looking at the scatterplot that the relationship is linear, but the residual plot also confirms this.

For assumption 6, normality of residuals, again the residuals look good in both plots and this provides an excellent example of why it's often better to visualise than rely on statistics because if we use `check_normality()` which calls the Shapiro-Wilk test:


```r
check_normality(mod)
```

```
## Warning: Non-normality of residuals detected (p < .001).
```

It tells us that the residuals are not normal, despite the fact that the plots look almost perfect. And that's because with large sample sizes, any deviation from perfect normality can be flagged as non-normal.

For assumption 7, homoscedasticity, the plot is missing the reference line - fun fact, this took us several days of our lives and asking for help on Twitter to figure out. The reason the line isn't there is because the dataset is so large that is creates a memory issue so we need to create the plot ourselves using code the developers of the package `see` provided to us on Twitter. The default code would try to draw confidence intervals around the line which is what causes the memory issue, this code removes that with `se = FALSE`.

Please note that with most datasets you wouldn't have to do this extra step, but it's a good example that when it comes to programming, it doesn't matter how long you've been doing it, there will always be a problem you haven't come across and that asking for help is part of the process.


```r
ggplot(assumptions$HOMOGENEITY, aes(x, y)) +
    geom_point2() +
    stat_smooth(
      method = "loess",
      se = FALSE,
      formula = y ~ x,
    ) +
    labs(
      title = "Homogeneity of Variance",
      subtitle = "Reference line should be flat and horizontal",
      y = expression(sqrt("|Std. residuals|")),
      x = "Fitted values"
    ) 
```

<div class="figure" style="text-align: center">
<img src="17-multiple-regression_files/figure-html/unnamed-chunk-3-1.png" alt="Adjusted homogeneity plot that will produce reference line" width="100%" />
<p class="caption">(\#fig:unnamed-chunk-3)Adjusted homogeneity plot that will produce reference line</p>
</div>

Again like normality, the plot isn't perfect but it is pretty good and another example of why visualisation is better than running statistical tests as we see the same significant result if we run:


```r
check_homogeneity(mod)
```

```
## Warning: Variances differ between groups (Bartlett Test, p = 0.000).
```


For assumption 8, linearity, again the plot looks fine, and we could also have used the grouped scatterplots above to look at this. 

Finally, for assumption 9, multicollinearity, the plot also indicates no issues but we can also test this statistically using `check_collinearity()`.

Essentially, this function estimates how much the variance of a coefficient is “inflated” because of linear dependence with other predictors, i.e., that a predictor isn't actually adding any unique variance to the model, it's just really strongly related to other predictors. [You can read more about this here](https://statisticalhorizons.com/multicollinearity). Thankfully, VIF is not affected by large samples like the other tests.

There are various rules of thumb, but most converge on a VIF of above 2 - 2.5 for any one predictor being problematic.


```r
check_collinearity(mod)
```

<div class="kable-table">

|Term            |      VIF| SE_factor|
|:---------------|--------:|---------:|
|thours_c        | 1.721968|  1.312238|
|male_c          | 1.035552|  1.017621|
|thours_c:male_c | 1.716349|  1.310095|

</div>

## Activity 10: Power and effect size {#mulregression-a10}

Finally, we'll calculate power and effect size as usual.

* Using the code from Power and Effect Size calculate the minimum effect size we could reliably observe given our sample size and design but for 99% power. Report this to 2 decimal places <input class='webex-solveme nospaces' size='0.00' data-answer='[".00"]'/>







* What is the observed effect size for the study to 2 decimal places? <input class='webex-solveme nospaces' size='0.10' data-answer='[".10"]'/>  
* Is the study sufficiently powered? <select class='webex-select'><option value='blank'></option><option value='answer'>Yes</option><option value=''>No</option></select>

## Activity 11: Write-up {#mulregression-a11}

Same as the simple regression, we can use inline coding or the `report()` function to help with the write-up. First, copy and paste the below code into **white-space** and then knit the document. Note that the p-values are entered manually because of the APA `p < .001` formatting.


```r
All continuous predictors were mean-centered and deviation coding was used for categorical predictors. The results of the regression indicated that the model significantly predicted course engagement (F(`r mod_summary$fstatistic[2]`, `r mod_summary$fstatistic[3] %>% round(2)`) = `r mod_summary$fstatistic[1] %>% round(2)`, p < .001, Adjusted R2 = `r mod_summary$adj.r.squared %>% round(2)`, f^2^ = .63), accounting for `r (mod_summary$adj.r.squared %>% round(2))*100`% of the variance. Total screen time was a significant negative predictor of wellbeing scores (β = `r mod$coefficients[2] %>% round(2)`, p < .001, as was gender (β = `r mod$coefficients[3] %>% round(2)`, p < .001, with girls having lower wellbeing scores than boys. Importantly, there was a significant interaction between screentime and gender (β = `r mod$coefficients[4] %>% round(2)`, p < .001), smartphone use was more negatively associated with wellbeing for girls than for boys. 
```

> All continuous predictors were mean-centered and deviation coding was used for categorical predictors. The results of the regression indicated that the model significantly predicted course engagement (F(3, 7.1029\times 10^{4}) = 2450.89, p < .001, Adjusted R2 = 0.09, f2 = .63), accounting for 9% of the variance. Total screen time was a significant negative predictor of well-being scores (β = -0.77, p < .001, as was gender (β = 5.14, p < .001, with girls having lower well-being scores than boys. Importantly, there was a significant interaction between screen time and gender (β = 0.45, p < .001), smartphone use was more negatively associated with well-being for girls than for boys.

Now, we can use `report()` to produce an automated summary. Again, it would need some editing but may be useful to aid interpretation and reporting.


```r
report(mod)
```

```
## We fitted a linear model (estimated using OLS) to predict tot_wellbeing with thours_c and male_c (formula: tot_wellbeing ~ thours_c * male_c). The model explains a statistically significant and weak proportion of variance (R2 = 0.09, F(3, 71029) = 2450.89, p < .001, adj. R2 = 0.09). The model's intercept, corresponding to thours_c = 0 and male_c = -0.5, is at 44.87 (95% CI [44.78, 44.96], t(71029) = 1001.87, p < .001). Within this model:
## 
##   - The effect of thours c is statistically significant and negative (beta = -0.77, 95% CI [-0.82, -0.73], t(71029) = -32.96, p < .001; Std. beta = -0.15, 95% CI [-0.16, -0.15])
##   - The effect of male c [0 5] is statistically significant and positive (beta = 5.14, 95% CI [5.00, 5.28], t(71029) = 72.25, p < .001; Std. beta = 0.54, 95% CI [0.52, 0.55])
##   - The interaction effect of male c [0 5] on thours c is statistically significant and positive (beta = 0.45, 95% CI [0.38, 0.52], t(71029) = 12.24, p < .001; Std. beta = 0.09, 95% CI [0.08, 0.11])
## 
## Standardized parameters were obtained by fitting the model on a standardized version of the dataset. 95% Confidence Intervals (CIs) and p-values were computed using the Wald approximation.
```

## Finished! {#mulregression-fin}

And you're done! Not just with this week but with the R component of RM2!  The progress that you have made is truly astonishing. Even if you struggled with R and haven't quite understood every single line of code we've shown, what you're capable of with data wrangling and visualisation alone makes you some of the most highly competitive psychology graduates in the world. 

Regardless of whether you continue with quantitative methods and using R, remember the more important critical skills that you have learned as part of this process. The next time you see a dataset or you see data being talked about in the news, think about all work that was put into getting the data into the final format. More importantly, think about all the decisions that the researcher needed to make along the way and how that might have affected the outcome. 

![](https://media.giphy.com/media/ujGfBmVppmgEg/giphy.gif) 


## Activity solutions {#mulregression-sols}

### Activity 3 {#mulregression-a3sol}


<div class='webex-solution'><button>Solution</button>


```r
wemwbs <- wellbeing %>%
  pivot_longer(names_to = "var", values_to = "score", -Serial) %>%
  group_by(Serial) %>%
  summarise(tot_wellbeing = sum(score))

# sanity check values

wemwbs %>% summarise(mean = mean(tot_wellbeing),
                     sd = sd(tot_wellbeing),
                     min = min(tot_wellbeing), 
                     max = max(tot_wellbeing))
```

</div>


### Activity 5 {#mulregression-a5sol}


<div class='webex-solution'><button>Solution</button>


```r
smarttot <- screen2 %>%
  filter(variable == "Using Smartphone") %>%
  group_by(Serial) %>%
  summarise(tothours = mean(hours))

smart_wb <- smarttot %>%
  filter(tothours > 1) %>%
  inner_join(wemwbs, "Serial") %>%
  inner_join(pinfo, "Serial") 
```

</div>


### Activity 6 {#mulregression-a6sol}


<div class='webex-solution'><button>Solution</button>


```r
smart_wb <- smarttot %>%
  filter(tothours > 1) %>%
  inner_join(wemwbs, "Serial") %>%
  inner_join(pinfo, "Serial") %>%
  mutate(thours_c = tothours - mean(tothours),
         male_c = ifelse(male == 1, .5, -.5),
         male_c = as.factor(male_c),
         male = as.factor(male))
```

</div>


### Activity 7 {#mulregression-a7sol}


<div class='webex-solution'><button>Solution</button>


```r
smart_wb_gen <- smart_wb %>%
  group_by(tothours, male) %>%
  summarise(mean_wellbeing = mean(tot_wellbeing))

ggplot(smart_wb_gen, aes(tothours, mean_wellbeing, color = male)) +
  geom_point() +
  geom_smooth(method = "lm") +
  scale_color_discrete(name = "Gender", labels = c("Female", "Male"))+
  scale_x_continuous(name = "Total hours smartphone use") +
  scale_y_continuous(name = "Mean well-being score")
```

</div>


### Activity 8 {#mulregression-a8sol}


<div class='webex-solution'><button>Solution</button>


```r
mod <- lm(tot_wellbeing ~ thours_c * male_c, smart_wb)
# alternatively: 
# mod <- lm(tot_wellbeing ~ thours_c + male_c + thours_c:male_c, smart_wb)

mod_summary <- summary(mod)
```

</div>


### Activity 9 {#mulregression-a9sol}


<div class='webex-solution'><button>Solution</button>


```r
qqPlot(mod$residuals)
```

</div>


### Activity 10 {#mulregression-a10sol}


<div class='webex-solution'><button>Solution</button>


```r
pwr.f2.test(u = 3, v = 71029, f2 = NULL, sig.level = .05, power = .99)
f2 <- mod_summary$adj.r.squared/(1 - mod_summary$adj.r.squared)
```

</div>


<!--chapter:end:17-multiple-regression.Rmd-->

# (APPENDIX) Appendices {-} 

<!--chapter:end:appendix-0.Rmd-->

# Installing `R` {#installing-r}

Installing R and RStudio is usually straightforward. The sections below explain how and [there is a helpful YouTube video here](https://www.youtube.com/watch?v=lVKMsaWju8w){target="_blank"}.

## Installing Base R

[Install base R](https://cran.rstudio.com/){target="_blank"}. Choose the download link for your operating system (Linux, Mac OS X, or Windows).

If you have a Mac, install the latest release from the newest `R-x.x.x.pkg` link (or a legacy version if you have an older operating system). After you install R, you should also install [XQuartz](http://xquartz.macosforge.org/){target="_blank"} to be able to use some visualisation packages.

If you are installing the Windows version, choose the "[base](https://cran.rstudio.com/bin/windows/base/)" subdirectory and click on the download link at the top of the page. After you install R, you should also install [RTools](https://cran.rstudio.com/bin/windows/Rtools/){target="_blank"}; use the "recommended" version highlighted near the top of the list.

If you are using Linux, choose your specific operating system and follow the installation instructions.

## Installing RStudio

Go to [rstudio.com](https://www.rstudio.com/products/rstudio/download/#download){target="_blank"} and download the RStudio Desktop (Open Source License) version for your operating system under the list titled **Installers for Supported Platforms**.

## RStudio Settings

There are a few settings you should fix immediately after updating RStudio. Go to **`Global Options...`** under the **`Tools`** menu (&#8984;,), and in the General tab, uncheck the box that says **`Restore .RData into workspace at startup`**.  If you keep things around in your workspace, things will get messy, and unexpected things will happen. You should always start with a clear workspace. This also means that you never want to save your workspace when you exit, so set this to **`Never`**. The only thing you want to save are your scripts.

You may also want to change the appearance of your code. Different fonts and themes can sometimes help with visual difficulties or [dyslexia](https://datacarpentry.org/blog/2017/09/coding-and-dyslexia){target="_blank"}. 

<div class="figure" style="text-align: center">
<img src="images/rstudio_settings_general_appearance.png" alt="RStudio General and Appearance settings" width="100%" />
<p class="caption">(\#fig:settings-general)RStudio General and Appearance settings</p>
</div>

You may also want to change the settings in the Code tab. Foe example, Lisa prefers two spaces instead of tabs for my code and likes to be able to see the <a class='glossary' target='_blank' title='Spaces, tabs and line breaks' href='https://psyteachr.github.io/glossary/w#whitespace'>whitespace</a> characters. But these are all a matter of personal preference.

<div class="figure" style="text-align: center">
<img src="images/rstudio_settings_code.png" alt="RStudio Code settings" width="100%" />
<p class="caption">(\#fig:settings-code)RStudio Code settings</p>
</div>


## Installing LaTeX

You can install the LaTeX typesetting system to produce PDF reports from RStudio. Without this additional installation, you will be able to produce reports in HTML but not PDF. This course will not require you to make PDFs. To generate PDF reports, you will additionally need to install <code class='package'>tinytex</code> [@R-tinytex] and run the following code:


```r
tinytex::install_tinytex()
```

<!--chapter:end:appendix-a-installing-r.Rmd-->

# Updating packages

Package developers will occasionally release updates to their packages. This is typically to add in new functions to the package, or to fix or amend existing functions. **Be aware that some package updates may cause your previous code to stop working**. This does not tend to happen with minor updates to packages, but occasionally with major updates, you can have serious issues if the developer has made fundamental changes to how the code works. For this reason, we recommend updating all your packages once at the beginning of each academic year (or semester) - don't do it before an assessment or deadline just in case!

To update an individual package, the easiest way is to use the `install.packages()` function, as this always installs the most recent version of the package.


```r
install.packages("tidyverse")
```

To update multiple packages, or indeed all packages, RStudio provides helpful tools. Click `Tools - Check for Package Updates`. A dialogue box will appear and you can select the packages you wish to update. Be aware that if you select all packages, this may take some time and you will be unable to use R whilst the process completes.

<div class="figure" style="text-align: center">
<img src="images/update_packages.jpg" alt="Updating packages with RStudio" width="100%" />
<p class="caption">(\#fig:img-updateall)Updating packages with RStudio</p>
</div>

Occasionally, you might have a few problem packages that seemingly refuse to update, for me, `rlang` and `vctrs` cause me no end of trouble. These aren't packages that you will likely ever explicitly load, but they're required beneath the surface for R to do things like knit your Markdown files etc.

If you try to update an existing package and get an error message that says something like `Warning in install.packages : installation of package ‘vctrs’ had non-zero exit status` or perhaps `Error in loadNamespace(i, c(lib.loc, .libPaths()), versionCheck = vI[[i]]) :  namespace 'rlang' 0.4.9 is being loaded, but >= 0.4.10 is required` one solution I have found is to manually uninstall the package, restart R, and then install the package new, rather than trying to update an existing version. The `installr` package also has a useful function for uninstalling packages.


```r
# Load installr
library(installr)

# Uninstall the problem package
uninstall.packages("package_name")

# Then restart R using session - restart R
# Then install the package fresh

install.packages("package")
```

## Updating R

Finally, you may also wish to update R itself. The key thing to be aware of is that when you update R, if you just download the latest version from the website, you will lose all your packages. The easiest way to update R and not cause yourself a huge headache is to use the `installr` package. When you use the `updateR()` function, a series of dialogue boxes will appear. These should be fairly self-explanatory but there is a [full step-by-step guide available](https://www.r-statistics.com/2015/06/a-step-by-step-screenshots-tutorial-for-upgrading-r-on-windows/) for how to use `installr`, the important bit is to select "Yes" when it asked if you would like to copy your packages from the older version of R.


```r
# Install the installr package
install.packages("installr")

# Load installr
library(installr)

# Run the update function
updateR()
```

As always, if you're having issues, please ask on Teams or book into a GTA session.

<!--chapter:end:appendix-a1-updating-packages.Rmd-->

# Additional Resources

<div class="figure" style="text-align: center">
<img src="images/kitteh.png" alt="The truth about programming" width="100%" />
<p class="caption">(\#fig:img-kitteh)The truth about programming</p>
</div>

If you would like additional practice, you can check out the other UofG PsyTeachR course books. 

* [Level 1](https://psyteachr.github.io/ug1-practical/) - Intro to R (overlaps with Msc Conv book), data wrangling, data viz, descriptive statistics  
* [Level 2](https://psyteachr.github.io/ug2-practical/) - Our second-year undergraduate course introduces statistical concepts such as permutation tests,t-tests, NHST, alpha, power, effect size, and sample size. Semester 2 focusses on correlations and the general linear model. 
* [Level 3](https://psyteachr.github.io/ug3-stats/): This third-year undergraduate course teaches students how to specify, estimate, and interpret statistical models corresponding to various study designs, using a General Linear Models approach.
* [MSc Data Skills](https://psyteachr.github.io/msc-data-skills/): This course provides an overview of skills needed for reproducible research and open science using the statistical programming language R. Students will learn about data visualisation, data tidying and wrangling, archiving, iteration and functions, probability and data simulations, general linear models, and reproducible workflows.

We also highly recommend the following, they will help practice your data wrangling skills but also they're great options if you're enjoying R and want to stretch yourself:

* [Open Stats Lab](https://sites.trinity.edu/osl) - this wonderful resource gives you practice at running statistical tests by providing you with datasets from published papers.
* [R for Data Science](https://r4ds.had.co.nz/) - written by the authors of the tidyverse, this is a great resource for additional data wrangling practice and more depth on many of the tidyverse functions.
* [Text Mining with R](https://www.tidytextmining.com/) - Shows you how to use R to work with text. This isn't something we cover in this course, but it uses the same data wrangling skills and be a very useful additional skill to have.
* [How to make BBC style graphics](https://bbc.github.io/rcookbook/#how_to_create_bbc_style_graphics) - Ever wondered how the BBC News makes their data visualisation? Well, now you can make your own!
* [Data Vizualisation](https://socviz.co/) - this is an entire book on data visualisation and goes into detail on how to take `ggplot` to its limits. 

<!--chapter:end:appendix-a2-additional-learning-resources.Rmd-->

# Citing R and RStudio {#citing-r-rstudio}

How to cite R and RStudio

You may be some way off writing a scientific report where you have to cite and reference R, however, when the time comes it is important to do so to give the people who built it (most of them for free!) credit. You should provide separate citations for R, RStudio, and the packages you use.

To get the citation for the version of R you are using, simply run the `citation()` function which will always provide you with the most recent citation.


```r
citation()
```

```
## 
## To cite R in publications use:
## 
##   R Core Team (2021). R: A language and environment for statistical
##   computing. R Foundation for Statistical Computing, Vienna, Austria.
##   URL https://www.R-project.org/.
## 
## A BibTeX entry for LaTeX users is
## 
##   @Manual{,
##     title = {R: A Language and Environment for Statistical Computing},
##     author = {{R Core Team}},
##     organization = {R Foundation for Statistical Computing},
##     address = {Vienna, Austria},
##     year = {2021},
##     url = {https://www.R-project.org/},
##   }
## 
## We have invested a lot of time and effort in creating R, please cite it
## when using it for data analysis. See also 'citation("pkgname")' for
## citing R packages.
```

To generate the citation for any packages you are using, you can also use the `citation()` function with the name of the package you wish to cite.


```r
citation("tidyverse")
```

```
## 
##   Wickham et al., (2019). Welcome to the tidyverse. Journal of Open
##   Source Software, 4(43), 1686, https://doi.org/10.21105/joss.01686
## 
## A BibTeX entry for LaTeX users is
## 
##   @Article{,
##     title = {Welcome to the {tidyverse}},
##     author = {Hadley Wickham and Mara Averick and Jennifer Bryan and Winston Chang and Lucy D'Agostino McGowan and Romain François and Garrett Grolemund and Alex Hayes and Lionel Henry and Jim Hester and Max Kuhn and Thomas Lin Pedersen and Evan Miller and Stephan Milton Bache and Kirill Müller and Jeroen Ooms and David Robinson and Dana Paige Seidel and Vitalie Spinu and Kohske Takahashi and Davis Vaughan and Claus Wilke and Kara Woo and Hiroaki Yutani},
##     year = {2019},
##     journal = {Journal of Open Source Software},
##     volume = {4},
##     number = {43},
##     pages = {1686},
##     doi = {10.21105/joss.01686},
##   }
```

To generate the citation for the version of RStudio you are using, you can use the `RStudio.Vesion()` function:


```r
RStudio.Version()
```

Finally, here's an example of how that might look in the write-up of your method section:

> Analysis was conducted using R (R Core Team, 2020), RStudio (Rstudio Team, 2020), and the tidyverse package (Wickham, 2017).

As noted, you may not have to do this for a while, but come back to this when you do because it's important to give the open-source community credit for their work.

<!--chapter:end:appendix-a3-How-to-cite-R.Rmd-->

# Symbols {#symbols}

| Symbol | psyTeachR Term    | Also Known As     |
|:------:|:------------------|:------------------|
| ()     | (round) brackets  | parentheses       |
| []     | square brackets   | brackets          |
| {}     | curly brackets    | squiggly brackets |
| <>     | chevrons          | angled brackets / guillemets |
| <      | less than         |                   |
| >      | greater than      |                   |
| &      | ampersand         | "and" symbol      |
| #      | hash              | pound / octothorpe|
| /      | slash             | forward slash     |
| \\     | backslash         |                   |
| -      | dash              | hyphen / minus    |
| _      | underscore        |                   |
| *      | asterisk          | star              |
| ^      | caret             | power symbol      |
| ~      | tilde             | twiddle / squiggle|
| =      | equal sign        |                   |
| ==     | double equal sign |                   |
| .      | full stop         | period / point    |
| !      | exclamation mark  | bang / not        |
| ?      | question mark     |                   |
| '      | single quote      | quote / apostrophe|
| "      | double quote      | quote             |
| %>%    | pipe              | magrittr pipe     |
| \|     | vertical bar      | pipe              |
| ,      | comma             |                   |
| ;      | semi-colon        |                   |
| :      | colon             |                   |
| @      | "at" symbol       | [various hilarious regional terms](https://www.theguardian.com/notesandqueries/query/0,5753,-1773,00.html) |
| ...    | `glossary("ellipsis")`| dots     |


<div class="figure" style="text-align: center">
<img src="images/soundimals_hash.png" alt="[Image by James Chapman/Soundimals](https://soundimals.tumblr.com/post/167354564886/chapmangamo-the-symbol-has-too-many-names)" width="100%" />
<p class="caption">(\#fig:img-soundimals-hash)[Image by James Chapman/Soundimals](https://soundimals.tumblr.com/post/167354564886/chapmangamo-the-symbol-has-too-many-names)</p>
</div>





<!--chapter:end:appendix-b-symbols.Rmd-->

# Conventions

This book will use the following conventions:

* Generic code: `list(number = 1, letter = "A")`
* Highlighted code: <code><span class='fu'>dplyr</span><span class='fu'>::</span><span class='fu'><a target='_blank' href='https://dplyr.tidyverse.org/reference/slice.html'>slice_max</a></span><span class='op'>(</span><span class='op'>)</span></code>
* File paths: <code class='path'>data/sales.csv</code>
* R Packages: <code class='package'>tidyverse</code>
* Functions: <code><span class='fu'><a target='_blank' href='https://rdrr.io/r/base/paste.html'>paste</a></span><span class='op'>(</span><span class='op'>)</span></code>
* Strings: <code><span class='st'>"psyTeachR"</span></code>
* Numbers: <code><span class='fl'>100</span></code>, <code><span class='fl'>3.14</span></code>
* Logical values: <code><span class='cn'>TRUE</span></code>, <code><span class='cn'>FALSE</span></code>
* Glossary items: <a class='glossary' target='_blank' title='Discrete variables that have an inherent order, such as level of education or dislike/like.' href='https://psyteachr.github.io/glossary/o#ordinal'>ordinal</a>
* Citations: @R-tidyverse
* Internal links: Chapter\ \@ref(intro)
* External links: [R for Data Science](https://r4ds.had.co.nz/){target="_blank"}
* Menu/interface options: **`New File...`**
* Quiz question: I am going to learn a lot: <select class='webex-select'><option value='blank'></option><option value='answer'>TRUE</option><option value=''>FALSE</option></select>


<div class='webex-solution'><button>Hidden Solutions</button>
You found it!
</div>

::: {.info data-latex=""}
Informational asides.
:::

::: {.warning data-latex=""}
Notes to warn you about something.
:::

::: {.dangerous data-latex=""}
Notes about things that could cause serious errors.
:::

::: {.try data-latex=""}
Try it yourself.
:::


```r
# code chunks
paste("Applied", "Data", "Skills", 1, sep = " ")
```

```
## [1] "Applied Data Skills 1"
```


<div class='verbatim'><pre class='sourceCode r'><code class='sourceCode R'>&#96;&#96;&#96;{r setup, message = FALSE}</code></pre>

```r
# code chunks with visible r headers
library(tidyverse)
```

<pre class='sourceCode r'><code class='sourceCode R'>&#96;&#96;&#96;</code></pre></div>

<!--chapter:end:appendix-c-conventions.Rmd-->

# License {-}

This book is licensed under Creative Commons Attribution-ShareAlike 4.0 International License [(CC-BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/){target="_blank"}. You are free to share and adapt this book. You must give appropriate credit, provide a link to the license, and indicate if changes were made. If you adapt the material, you must distribute your contributions under the same license as the original. 

## Citation

Nordmann, E., & McAleer, P. (2021). Fundamentals of Quantitative Analysis (Version 2.0). https://psyteachr.github.io/quant-fun-v2/

<!--chapter:end:appendix-y-license.Rmd-->

# References {-}


<!--chapter:end:appendix-z-refs.Rmd-->

