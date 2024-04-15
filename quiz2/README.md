# Quiz 2 materials for 432 Spring 2024

## What is available now?

A fairly complete draft of [the instructions for Quiz 2 is now available](https://github.com/THOMASELOVE/432-quizzes-2024/blob/main/quiz2/432_quiz2_2024_instructions_only.pdf).

- This "instructions only" draft will disappear when we provide the final main PDF file of instructions and questions.
- **NEW!** I updated the "instructions only" document again on Sunday `2024-04-14` to reflect a more complete list of packages and setup, and increases in (1) the length of the PDF file to 47 pages, and (2) the number of footnotes to 14, as we add additional output and hints in revising the questions.

## What will become available here?

All of this material will appear by the time specified on the [Calendar](https://thomaselove.github.io/432-2024/calendar.html).

- The main (**47-page**) PDF containing the instructions and all 34 questions for Quiz 2.
    - This document will also include the list of R packages and settings I used to create and answer the Quiz.
- A link to the Google Form Answer Sheet for Quiz 2.
    - All of your answers must go into that sheet, which will close **15 minutes** after the Quiz deadline on the [Calendar](https://thomaselove.github.io/432-2024/calendar.html).
- A link to the folder on our Shared Drive where you'll find the seven Quiz 2 data sets we are providing to you, specifically...
    - `dataB.rds`, `dataD.csv`, `dataE.rds`, `dataH.csv`, `dataN.rds`, `dataS.rds`, and `dataT.csv`.     
- A copy of Dr. Love's code chunk for **R packages and setup** that you can easily copy and paste into your Quarto file when building your responses to the Quiz. (see [below for a preliminary version](#code-chunk-for-r-packages-and-setup-this-is-not-yet-guaranteed-to-be-the-final-version).)
- A copy of Dr. Love's code chunk for **setting up Items Q25 - Q30**, so that you can copy and paste it more easily than the PDF will allow.

## Code Chunk for R Packages and Setup (this is not yet guaranteed to be the final version.)

```
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


