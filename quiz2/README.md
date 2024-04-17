# Quiz 2 materials for 432 Spring 2024

## If changes are necessary...

Dr. Love will email them to you, and post them here.

Current version of [the main PDF](https://github.com/THOMASELOVE/432-quizzes-2024/blob/main/quiz2/432_quiz2_2024_for_students.pdf) - is `2024-04-17 at 12:32 PM`.

## All Five Things you need ares available NOW.

1. The [Google Form Answer Sheet](https://bit.ly/432-2024-quiz2-answer-form) for Quiz 2 will be found at <https://bit.ly/432-2024-quiz2-answer-form>. It will open at 5 PM on Thursday 2024-04-18.
    - All of your answers must go into that sheet, which will close **15 minutes** after the Quiz deadline on the [Calendar](https://thomaselove.github.io/432-2024/calendar.html).

2. We are providing you with seven Quiz 2 data sets [at this link on our 432-data page](https://github.com/THOMASELOVE/432-data/tree/master/data/quiz2), and in the **Quiz 2 Materials ... data** folder on our Shared Drive. Here are the details on those data sets:

Data Set | Type of File | # observations | # variables | Quiz 2 items
:-------: | :-------: | :----: | :----: | :---------:
`dataB` | Rds | 4593 | 3 | Q09 - Q10
`dataD` | csv | 1111 | 4 | Q16 - Q23
`dataE` | Rds | 432 | 8 | Q25 - Q30
`dataH` | csv | 1515 | 6 | Q01 - Q03
`dataN` | Rds | 2640 | 9 | Q31 - Q34
`dataS` | Rds | 600 | 7 | Q04 - Q06
`dataT` | csv | 360 | 5 | Q11 - Q12

3. Here is a copy of section 0.12 of the main PDF, in a format that lets you easily copy and paste Dr. Love's code chunk for **R packages and setup** into your Quarto file.

## Code Chunk for R Packages and Setup (from section 0.12 of the Main Document on page 4)

```{r}
#| message: false

knitr::opts_chunk$set(comment = NA)

library(bayestestR); library(bestglm)
library(car); library(caret); library(countreg); library(cutpointr)
library(Epi)
library(GGally); library(glmnet); library(gt)
library(insight)
library(janitor)
library(lme4)
library(MASS); library(mice); library(mosaic)
library(naniar); library(nnet)
library(patchwork); library(pROC); library(pscl)
library(quantreg)
library(ROCR); library(rstanarm)
library(survey); library(survival); library(survminer)
library(topmodels) ## students do not need this but I did

library(conflicted)
library(rms)
library(tidymodels)
library(tidyverse)

conflicts_prefer(dplyr::filter, dplyr::select, dplyr::summarize, dplyr::count, 
                 base::mean, base::sum, base::max,
                 car::vif, Matrix::update, rms::Predict)

options(dplyr.summarise.inform = FALSE)

theme_set(theme_bw())
```

4. Here is a copy of the relevant code from the two pages leading up to Items Q25-30, working with `dataE` to create imputations.

## Code Setting Up Items Q25-30 (from pp. 33-34 of the Main PDF)

```{r}
dataE <- read_rds("data/dataE.Rds") 

## first we remove the subject ID codes from dataE
dataE_noid <- dataE |> select(-person)

## we next set our seed then perform 20 imputations
set.seed(25)
dataE_20imps <- mice(dataE_noid, m = 20, printFlag = FALSE)

## use the 17th of those imputations to form dataE_s
dataE_s <- complete(dataE_20imps, 17) |> tibble()

## add back in the subject ID codes to finish dataE_s
dataE_s$person <- dataE$person
```

5. The Main PDF document is [now available](https://github.com/THOMASELOVE/432-quizzes-2024/blob/main/quiz2/432_quiz2_2024_for_students.pdf).
    - It contains the instructions and all 34 questions for Quiz 2.
    - Be sure you have all 47 pages in the PDF, and that you carefully read the document as you do the Quiz.




