# 2020-02_GBNERR_RWorkshop_Day1Challenge

## 01 Read in data

You are reading in a file that contains oyster data collected from the Guana Tolomato Matanzas NERR. This .xlsx data file contains two sheets: "SPAT" and "OYSTER". For your first task, we are going to be looking at the spat data. (*Spat are oyster larvae that have permanently attached themselves to a surface*)

After reading in the data and creating the `oyster` object, be sure to inspect your data. *What kind of variables are you given? How many observations are there? Can you tell if this is a wide or long dataset? Does it appear tidy?*

```{r data}
oyster <- read_xlsx(here::here('oysters_gtm.xlsx'), sheet = 'SPAT') %>%
  janitor::clean_names()
```

***

1.   What does the `janitor::clean_names()` function do? 

*     [YOUR ANSWER HERE]

2.   Why is it recommended that you use the `here` package? 

*     [YOUR ANSWER HERE]

3.   Identify three functions you can use to inspect your data. 

*     [YOUR ANSWER HERE]


This dataset contains date (`year`, `month`, `deployment_date`, `retrieval_date`), location (`region`, `reef`), identification (`rep`, `shell_id`), and count information (`spat_count`). 


***

## 02 Wrangle

Create a new dataset where you summarize by calculating the mean number of spat per `region`. Remember, with the `mean()` function you will need to specify `na.rm = TRUE`.

```{r wrangle}


  
```

## 03 Make it pretty

1.   Using your `ggplot2` cheatsheet, determine what `geom_` would be the best for using on a timeseries. Make a plot of `mean_spat` by `deployment_date` and color by region. Depending on your `geom_` you may either use `color` and/or `fill` aesthetics. 

2.   Remove the label on the legend. (*Hint: think about what scale this is representing. Are the variables continuous or discrete?*)

3.   Assign a theme. `ggplot2` has several good defaults.

4.   Relabel the axes to something more suitable than the variable names. 

*EXTRA CHALLENGE*

5.   Adjust the scale of the y-axis to break by 50s.

6.   Adjust the scale of the x-axis to display every year. **Hint: use `?scale_x_datetime` for help. The year label will be `%Y`.**



NOTE:  `gglot2` defaults where it does not have the data start **ON** the x-axis. If this bothers you, you could try adding `expand = c(0,0)` to the `scale_y_continuous()` function in your plot.

```{r}



```

## 04 Do it all in one step

Steps 02 and 03 wrangled and then plotted your data. Now, combine both steps into one using pipes `%>%`, starting with the `oyster` dataset without creating new datasets. (Hint: remember to think of pipes as *"...and then..."* and write your code in a step-wise way.)

```{r final}



```

***
1.   How might "working within the data frame" be more beneficial than creating new objects each step?

*     [YOUR ANSWER HERE]

A great explanation for this: https://github.com/jennybc/row-oriented-workflows/blob/master/ex01_leave-it-in-the-data-frame.md 
