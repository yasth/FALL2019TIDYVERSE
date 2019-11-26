# CUNY DATA 607 Fall 2019 Tidyverse recipes

I am using the Avengers dataset from FiveThirtyEight and using the dplyr package to demonstrate the filter and full_join function.
Avengers dataset: https://github.com/fivethirtyeight/data/tree/master/avengers

---
title: "Data 607 TidyVerse Assignment Part 1"
author: "Bryan Persaud"
date: "11/26/2019"
output: html_document
---

```{r}
library(tidyverse)
```

# I chose to work with the Avengers dataset 

```{r}
# Get dataset from URL from FiveThirtyEight github
Avengers <- read.csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/avengers/avengers.csv")
```

# I chose to demonstrate the dplyr package

```{r}
# Use filter to extract an individual avenger
Captain_America <- filter(Avengers, Name.Alias == "Steven Rogers")
Iron_Man <- filter(Avengers, Appearances == "3068")
Thor <- filter(Avengers, Name.Alias == "Thor Odinson")
Black_Widow <- filter(Avengers, Name.Alias == "Natalia Alianovna Romanova")
The_Hulk <- filter(Avengers, Name.Alias == "Robert Bruce Banner")
Hawkeye <- filter(Avengers, Name.Alias == "Clinton Francis Barton")
```

```{r}
# Use full_join to combine everything into one data frame
Avengers_2012 <- list(Captain_America, Iron_Man, Thor, Black_Widow, The_Hulk, Hawkeye) %>%
  reduce(full_join, by.x = "URL", by.y = "Appearances")
Avengers_2012
```

For my Tidyverse example I used the Avengers dataset from FiveThirtyEight. The dataset contains a list of members of the Avengers group from the Marvel comics. The list shows appearances of when they were first introduced in the comics and if/when they died and/or returned. I used the filter function from the dplyr package to extract every avenger from the 2012 Avengers film. I then put them into a list and used the full_join function from the dplyr function to put every avenger that I got from using the filter function into one data frame.

**Extend an Existing Example**  Using one of your classmate’s examples (as created above), extend his or her example with additional annotated code. (15 points)
