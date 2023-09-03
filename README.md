# ANA515_R_Markdown-
R Markdown Assignment for Week One 
---
title: "Diamond sizes"
author: Antonio Tabash
date: 2023
output: word_document
---

``` {r, echo = FALSE}
#Note, Each gray box below is a code chunk. You need to insert a code chunk and put your R code in it. By setting echo = FALSE. this comment and any code will not show in my output document. If it were TRUE, the comment and code would appear. 
```

```{r setup, include = FALSE}
#The include = FALSE function hides both the code and output in my output document

#You need to install these packages first to be able to use the functions within them. You can install them from the Tools tab or write a new code chunk: install.packages("package_name"). 
#(AT Comment: I used the Tool tab to install both packages)
library(ggplot2)
library(dplyr)
```

```{r, include = FALSE}
#this next line is creating a subset called 'small' of the diamonds data
small <- diamonds %>% 
  filter(carat <= 2)
```

```{r, echo = FALSE}
#This next chunk is inline code. Inline code puts the text with the output of the function in my document.
```

We have data about `r nrow(diamonds)` diamonds. Only 
`r nrow(diamonds) - nrow(small)` are larger than
2 carats. The distribution of the remainder is shown
below:

``` {r, echo = FALSE}
#This next code chunk will make a plot in our output doc
```

```{r, echo = FALSE}
small %>% 
  ggplot(aes(carat)) + 
  geom_freqpoly(binwidth = 0.01)
```
