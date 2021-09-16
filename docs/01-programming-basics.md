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

When you install R you will have access to a range of functions including options for data wrangling and statistical analysis. The functions that are included in the default installation of R are typically referred to as **<a class='glossary' target='_blank' title='The set of R functions that come with a basic installation of R, before you add external packages' href='https://psyteachr.github.io/glossary/b#base-r'>Base R</a>** and there is a useful cheat sheet that shows many Base R functions [here](https://www.rstudio.com/wp-content/uploads/2016/05/base-r.pdf).

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
age <- 16 + 19 
today <- Sys.Date()
new_year <- as.Date("2021-01-01")
data <- rnorm(n = 10, mean = 15, sd = 3)
```

<div class="figure" style="text-align: center">
<img src="images/objects-enviro.png" alt="Objects in the environment" width="100%" />
<p class="caption">(\#fig:img-objects-enviro)Objects in the environment</p>
</div>

Note that in these examples, `name`,`age`, and `new_year` would always contain the values `emily`, `35`, and the date of New Year's Day 2021, however, `today` will draw the date from the operating system on the day you are using the computer, and `data` will be a randomly generated set of data - as we saw earlier - so the values of these objects will not be static. 

* Why don't you try changing the name to your name and the age to your age, and seeing if they update in the environment window.

Importantly, for what we will learn in future chapters, objects can be involved in calculations and can interact with each other. For example:


```r
age + 10
```

```
## [1] 45
```


```r
new_year - today
```

```
## Time difference of -258 days
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
<img src="images/global_options.jpg" alt="Global options" width="100%" />
<p class="caption">(\#fig:img-options)Global options</p>
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
|[base r](https://psyteachr.github.io/glossary/b.html#base-r){class="glossary" target="_blank"}                           |The set of R functions that come with a basic installation of R, before you add external packages                                                                |
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
