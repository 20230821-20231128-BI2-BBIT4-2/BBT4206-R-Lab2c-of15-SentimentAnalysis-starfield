Business Intelligence Lab Submission Markdown
================
<Specify your group name here>
<Specify the date when you submitted the lab>

- [Student Details](#student-details)
- [Setup Chunk](#setup-chunk)
- [\<Provide an Appropriate Title
  Here\>](#provide-an-appropriate-title-here)
- [\<You can Provide Another Appropriate Title
  Here\>](#you-can-provide-another-appropriate-title-here)

# Student Details

|                                                                                                                                                                                                                                                                |                                                              |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| **Student ID Numbers and Names of Group Members** \| \| \| \| 1.135232- Starfield - Sadiki Hamisi \| \| \| 2.134782 - Starfield - Yasmin Choma \| \| \| 3.134783- Starfield - Moses Mbugua \| \| \| 4. ID -Starfield- Glenn Oloo \| \| \| 5. ID - Group - Name |                                                              |
| **GitHub Classroom Group Name**                                                                                                                                                                                                                                |                                                              |
| **Course Code**                                                                                                                                                                                                                                                | BBT4206                                                      |
| **Course Name**                                                                                                                                                                                                                                                | Business Intelligence II                                     |
| **Program**                                                                                                                                                                                                                                                    | Bachelor of Business Information Technology                  |
| **Semester Duration**                                                                                                                                                                                                                                          | 21<sup>st</sup> August 2023 to 28<sup>th</sup> November 2023 |

# Setup Chunk

**Note:** the following “*KnitR*” options have been set as the
defaults:  
`knitr::opts_chunk$set(echo = TRUE, warning = FALSE, eval = TRUE, collapse = FALSE, tidy.opts = list(width.cutoff = 80), tidy = TRUE)`.

More KnitR options are documented here
<https://bookdown.org/yihui/rmarkdown-cookbook/chunk-options.html> and
here <https://yihui.org/knitr/options/>.

**Note:** the following “*R Markdown*” options have been set as the
defaults:

> output:  
>   
> github_document:  
> toc: yes  
> toc_depth: 4  
> fig_width: 6  
> fig_height: 4  
> df_print: default  
>   
> editor_options:  
> chunk_output_type: console

# \<Provide an Appropriate Title Here\>

      LOAD STUDENT DATASET

``` this

library(readr)
student_performance_dataset <-
  read_csv("data/20230412-20230719-BI1-BBIT4-1-StudentPerformanceDataset.CSV",
           col_types =
           cols(
                class_group = col_factor(levels = c("A", "B", "C")),
                gender = col_factor(levels = c("1", "0")),
                YOB = col_date(format = "%Y"),
                regret_choosing_bi = col_factor(levels = c("1", "0")),
                drop_bi_now = col_factor(levels = c("1", "0")),
                motivator = col_factor(levels = c("1", "0")),
                read_content_before_lecture =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                anticipate_test_questions =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                answer_rhetorical_questions =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                find_terms_I_do_not_know =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                copy_new_terms_in_reading_notebook =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                take_quizzes_and_use_results =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                reorganise_course_outline =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                write_down_important_points =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                space_out_revision =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                studying_in_study_group =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                schedule_appointments =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                goal_oriented = col_factor(levels = c("1", "0")),
                spaced_repetition =
                col_factor(levels = c("1", "2", "3", "4")),
                testing_and_active_recall =
                col_factor(levels = c("1", "2", "3", "4")),
                interleaving = col_factor(levels = c("1", "2", "3", "4")),
                categorizing = col_factor(levels = c("1", "2", "3", "4")),
                retrospective_timetable =
                col_factor(levels = c("1", "2", "3", "4")),
                cornell_notes = col_factor(levels = c("1", "2", "3", "4")),
                sq3r = col_factor(levels = c("1", "2", "3", "4")),
                commute = col_factor(levels = c("1", "2", "3", "4")),
                study_time = col_factor(levels = c("1", "2", "3", "4")),
                repeats_since_Y1 = col_integer(),
                paid_tuition = col_factor(levels = c("0", "1")),
                free_tuition = col_factor(levels = c("0", "1")),
                extra_curricular = col_factor(levels = c("0", "1")),
                sports_extra_curricular = col_factor(levels = c("0", "1")),
                exercise_per_week = col_factor(levels = c("0", "1", "2", "3")),
                meditate = col_factor(levels = c("0", "1", "2", "3")),
                pray = col_factor(levels = c("0", "1", "2", "3")),
                internet = col_factor(levels = c("0", "1")),
                laptop = col_factor(levels = c("0", "1")),
                family_relationships =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                friendships = col_factor(levels = c("1", "2", "3", "4", "5")),
                romantic_relationships =
                col_factor(levels = c("0", "1", "2", "3", "4")),
                spiritual_wellnes =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                financial_wellness =
                col_factor(levels = c("1", "2", "3", "4", "5")),
                health = col_factor(levels = c("1", "2", "3", "4", "5")),
                day_out = col_factor(levels = c("0", "1", "2", "3")),
                night_out = col_factor(levels = c("0", "1", "2", "3")),
                alcohol_or_narcotics =
                col_factor(levels = c("0", "1", "2", "3")),
                mentor = col_factor(levels = c("0", "1")),
                mentor_meetings = col_factor(levels = c("0", "1", "2", "3")),
                `Attendance Waiver Granted: 1 = Yes, 0 = No` =
                col_factor(levels = c("0", "1")),
                GRADE = col_factor(levels = c("A", "B", "C", "D", "E"))),
           locale = locale())

View(student_performance_dataset)
```

Contractions of Words From the Student Perfomance Dataset

``` r
library(readr)
expand_contractions <- function(doc) {
    doc <- gsub("I'm", "I am", doc, ignore.case = TRUE)
    doc <- gsub("you're", "you are", doc, ignore.case = TRUE)
    doc <- gsub("he's", "he is", doc, ignore.case = TRUE)
    doc <- gsub("she's", "she is", doc, ignore.case = TRUE)
    doc <- gsub("it's", "it is", doc, ignore.case = TRUE)
    doc <- gsub("we're", "we are", doc, ignore.case = TRUE)
    doc <- gsub("they're", "they are", doc, ignore.case = TRUE)
    doc <- gsub("I'll", "I will", doc, ignore.case = TRUE)
    doc <- gsub("you'll", "you will", doc, ignore.case = TRUE)
    doc <- gsub("he'll", "he will", doc, ignore.case = TRUE)
    doc <- gsub("she'll", "she will", doc, ignore.case = TRUE)
    doc <- gsub("it'll", "it will", doc, ignore.case = TRUE)
    doc <- gsub("we'll", "we will", doc, ignore.case = TRUE)
    doc <- gsub("they'll", "they will", doc, ignore.case = TRUE)
    doc <- gsub("won't", "will not", doc, ignore.case = TRUE)
    doc <- gsub("can't", "cannot", doc, ignore.case = TRUE)
    doc <- gsub("n't", " not", doc, ignore.case = TRUE)
    return(doc)
}
```

Loading the required lexicons

``` r
# file is rendered using knitR
library(tidytext)
afinn <- get_sentiments(lexicon = "afinn")
View(afinn)

bing <- get_sentiments("bing")
View(bing)

loughran <- get_sentiments("loughran")
View(loughran)
```

# \<You can Provide Another Appropriate Title Here\>

Describe the code chunk here:

``` r
# Fill this with R related code that will be executed when the R markdown file
# is rendered using knitR
library(readr)
```

**etc.** as per the lab submission requirements.
