How Minimalist Design Affects Information Delivery
==================================================

Goal:
-----

The goal of this experiment is to evaluate readers acceptance of the
minimalist data visualization and their average preference between a
standard graph and a minimalist version.

We also explore if a minimalist approach can be more effective in
delivering a message to the audience and if it has an effect on the
ability of the reader to recall specific features of the data once the
visualization is no longer available.

Experimental Data:
------------------

We aimed at 80 participants divided into two experimental conditions and
we successfully collected data of 79 participants on their preference
for two different graphs displaying the identical information, one is
designed with the minimalist elements, while the other involves both
more text information and aesthetics (due to the budget reason, sample
size is limited to 79).

The survey was designed using Qualtrics and administered using Amazon
Mechanical Turk. The only filtered required to answer the survey was to
be located in the US. This would ensure that the respondents speak
English. We randomized whether the participant would be provided with a
minimalist or non-minimalist visualization.

Visualizations:
---------------

#### Data presented in the visualizations:

The data used in the visualization is the Health Survey data collected
by The National Institute of Statistics and Geography during 2012 in
Mexico. The data cleaning process includes variable selection and data
aggregation: since the main goal of our project is to provide one
minimalist and one non-minimalist graphs with the basic information of
Body Mass Index (BMI) by age and gender, we cleaned the original data
set and only maintained variables BMI, diets indicators, and basic
demographic information. Meanwhile, in order to maintain the privacy of
individual cases in public reports while also being able to have a
???cleaner??? data, we believe that there is of less sense of fully
tapping into details of all disparate age. We removed observations whose
age is higher than 100 year-old and gathered and expressed information
of age by aggregating them into twenty age groups ( 0 - 4, 5 - 9,10 -14,
and etc.). We calculate the mean Body Mass Index (BMI) within each age
group by male and female.

#### Visualization Design

We used ggplot2 package in RStudio. For both minimalist and
non-minimalist visualization, BMI and Age group are mapped respectively
to x-axis and y-axis, while variable gender (only two categories in this
case: male and female) is mapped to the aesthetics of shape. Note that
variable BMI is mapped to the x-axis since this way the vertical space
is guaranteed for future use in the non-minimalist graph. Because this
element needs to be controlled and the only difference between two
scenarios is the minimalism, it is mapped to a-axis in both
visualizations.

For the minimalist graph (Exhibit 1), in order to improve the simplicity
of design and reduce non-data ink, any special effects are avoided:
there is no color-mapping by gender, and x-, y- axis as well as borders
and gridlines have been removed. In addition, the color of labels and
titles are lightened from black to grey, tick marks are only
regularly-spaced at logical intervals of 50-year for age (10-year for
age group) so we only have three tick marks on the y-axis. Same for BMI
on the x-axis, only the value of threshold of each group are maintained
and there are only three tick marks. Accordingly, background are divided
into four groups (underweight, normal, overweight, and obese) with three
vertical grey dash-line with x-axis intercept of each tick mark 18.5,
25.0, and 30.0, placed between each two adjacent BMI groups. Besides,
the borders has been removed and background color as well as label
color, instead of grey, are set to white. However, in order to keep the
clarity of the visualization, the title, label of axes, and legends are
all kept in the graph. We used scatterplot to present the BMI for male
and female respectively in each age group: circle represents female and
triangle represents male.

For the non-minimalist or more complex visualization (Exhibit 2), the
ink color is set back to the default setting black. The title Prevalence
of Overweight and Obesity, Mexico 2012 also has bigger font size. Under
the title, we briefly describe the graph and add one paragraph to tell
readers a short story of the background that Mexico ranks the most obese
country in the world in adult obesity by 2012. Meanwhile, at the bottom
of the graph, we provide two formulas used to calculate BMI for readers
who have different preferences of unit of measurement. In considering
the users possible expectations of detailed tick marks that can be used
to calculate their own BMI and understand if they are underweight,
normal, overweight, or obese, tick labels are defined to contain more
blocks and less spacing: x-axis has ten tick marks with spacing of 2 and
y-axis now has 20 tick mark labels, each standing for one age group.
Other than the words placed on the top of each BMI group, in this
non-minimalist graph, the range of BMI under each group is marked under
the group, such as underweight &lt;18.5, normal 18.5 - 23.0 and etc. In
the background, contours of different body shapes are placed in each
group. We believe that in this way readers can get a more
straightforward impression of how each body weight group looks like
approximately. Most importantly, one more aesthetics color is mapped to
the grouping variable gender: now pink circles represent female while
blue triangles represent males. At the same time, we added one more
layer to the graph with geom\_line and linked the point of male to the
point of female within each group.

#### Exhibit 1: Non-minimalist Visualization

<img src="Assignment2_Final_Version_files/figure-markdown_strict/unnamed-chunk-4-1.png" width="80%" />

#### Exhibit 2 - Minimalist Visualization

<img src="Assignment2_Final_Version_files/figure-markdown_strict/unnamed-chunk-5-1.png" width="80%" />

Survey Design:
--------------

Now it comes to the survey designing process. When a reader is provided
with the graph, they will be asked to provide their evaluations of two
visualizations on the dimension of major information, effectiveness,
beauty, and simplicity. Instead of being guided to decide if he/she is
healthy, underweight, or overweight, the reader is expected to only get
a general sense of the information: Obesity is a serious issue in Mexico
now. Readers do not necessarily need to calculate the exact BMI of
themselves or locate which group they belong to.

The survey includes 5 questions:

Questions 1 and 2 are be used to determine the effectiveness of
visualization. In these firsts questions, readers are randomized to
receive either the minimalist graph or the non-minimalist visualization.
Note that in Qualtrics, design is set successfully for randomization,
which means that participants had equal chance to receive either
visualization.

Question 1 asks if the reader think Mexican government should implement
a policy to reduce obesity. It is meant to evaluate from which graph,
the reader can better capture the main information of the critical
situation of obesity in Mexico. If the reader chooses yes, we consider
the graph presented to have successfully passed the essential
information. In contrast, if the answer is no or unsure, the graph is
considered to be not clear for this reader.

Question 2 asks readers to decide which age group on average has the
problem of overweight, which requires readers to look a bit more into
the graph and would be used to determine which graph actually enhance
readers understanding.

In Question 3, the visual is no longer displayed and the reader is asked
to judge if a statement about the data displayed in the visualization is
right and choose either true or false. This question allows testing for
differences in recallability and attention associated with each type of
visual.

For Questions 4 and 5, both graphs are presented to readers (since they
cannot go back and modify their answers in the previous questions, the
presentation of the two graphs will not affect randomization or cause
selection bias). In this section, the reader is asked about her
preferred design.Question 4 explicitly asks the reader which graph is
preferred and the Question 5 asks the reasons of their preference of one
over another with options color, information, images, simplicity, and
other. This last question will be used to determine which factor is
considered to be a more important contributor to a good visualization.

The survey is shown in Appendix A. Additionally, the survey can be
accessed at this link
<http://ssd.az1.qualtrics.com/jfe/form/SV_1HW8jXQeiGcZqxD>

Results
-------

Question 1
----------

In the data we collected from the survey, for the first question, as
shown in table 1, 36 participants were randomly presented the
non-minimalist graph and 47% choose yes for a policy for obesity issue
in Mexico, while 43 participants received the treatment of minimalist
graph and 67% of them choose the same answer. The percentage of
participants who choose unsure for if the government should draft a
policy of each group is very close.

**Survey Answers**
<img src="Assignment2_Final_Version_files/figure-markdown_strict/unnamed-chunk-7-1.png" width="80%" style="display: block; margin: auto;" />

**Permutation Test**

Since the sample size is too small for significance test for two-sample
mean difference, we use permutation method by re-randomizing the sample
data of the survey and conducted significance test on the mean of
difference of getting the answer yes for the first question of if the
government should implement a policy. The results indicate a two-tailed
p-value of 5.4% and we failed to reject the null hypothesis at 5%
significance level; in other words, the test show that with given
sample, we are not able to conclude any significant difference at the
rate of getting the right answer between participants who were shown the
minmalist graph and those who were shown the non-minimalist one.

    Too many permutations to use exact method.
    Defaulting to approximate method.
    Increase maxiter to at least 3.98066761451243e+22 to perform exact estimation.

<img src="Assignment2_Final_Version_files/figure-markdown_strict/unnamed-chunk-8-1.png" width="80%" style="display: block; margin: auto;" />

    $two.tailed.p.value
    [1] 0.054

    $two.tailed.p.value.abs
    [1] 0.081

    $greater.p.value
    [1] 0.027

    $lesser.p.value
    [1] 0.973

    $quantile
          2.5%      97.5% 
    -0.2092985  0.2495636 

    $sd
    [1] 0.1143493

    $exp.val
    [1] 3.740835e-05

**Logistic Regression**

The logistic regression analysis shows that those individuals in the
minimalistic group have a higher probability than those in the
non-minimalistic group to respond in favor of implementing a policy to
reduce obesity. However, the estimated coefficient for the dummy
variable indicating the group of the respondent is not statistically
significant. This results can be driven by the low number of
observations in the data.


    Call:
    glm(formula = Q1_dummy ~ bw_dummy, family = binomial(link = "logit"), 
        data = exp_DT_Q1)

    Deviance Residuals: 
        Min       1Q   Median       3Q      Max  
    -1.4981  -1.1306   0.8876   0.8876   1.2250  

    Coefficients:
                Estimate Std. Error z value Pr(>|z|)  
    (Intercept)  -0.1112     0.3338  -0.333   0.7390  
    bw_dummy      0.8395     0.4662   1.801   0.0718 .
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    (Dispersion parameter for binomial family taken to be 1)

        Null deviance: 107.37  on 78  degrees of freedom
    Residual deviance: 104.06  on 77  degrees of freedom
    AIC: 108.06

    Number of Fisher Scoring iterations: 4

Question 2
----------

For question 2, which age group/groups have on average a BMI indicating
overweight, participants do not differentiate much in their answers. To
better analyze this question, we constructed a score to rank the
answers. The correct answer for this question would be young adults,
middle age, and elder; if the answer includes one of the mentioned
aforementioned, the answer scores 1, if two the answer scores 2, and if
all of them are mentioned, the participant get the full score of 3.
However, if the answer does not mention any of them, the score is 0. For
both groups, 38%-39% of them score 2 or 3.

\begin{table}[h]
\centering
\caption{Which age group(s) have BMI indicating overweight}
\label{my-label}
\begin{tabular}{llll}
score & Non-minimalist & Minimalist & Interpretation of Score                    \\
0     & 11\%           & 9\%        & did not get any of the three right answers \\
1     & 50\%           & 51\%       & get one right answer                       \\
2     & 19\%           & 30\%       & get two right answers                      \\
3     & 19\%           & 9\%        & get all right answers                      \\
total & 100\%          & 100\%      &                                           
\end{tabular}
\end{table}
**Linear Regression**

The linear regression analysis shows that those individuals in the
minimalistic group have on average a lower score than those in the
non-minimalistic group. The estimated coefficient for the dummy variable
indicatin the group of the respondent, however, is not statistically
significant. This results can also be driven by the low number of
observations in the data.


    Call:
    lm(formula = score ~ bw_dummy, data = exp_DT_Q2)

    Residuals:
        Min      1Q  Median      3Q     Max 
    -1.4722 -0.4722 -0.3953  0.6047  1.6046 

    Coefficients:
                Estimate Std. Error t value Pr(>|t|)    
    (Intercept)  1.47222    0.14371  10.244 4.96e-16 ***
    bw_dummy    -0.07687    0.19479  -0.395    0.694    
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    Residual standard error: 0.8623 on 77 degrees of freedom
    Multiple R-squared:  0.002019,  Adjusted R-squared:  -0.01094 
    F-statistic: 0.1557 on 1 and 77 DF,  p-value: 0.6942

Question 3
----------

For the third question, 75% of non-minimalist readers answered the
question correctly and chose True, while only 57% of minimalist readers
get the right answer.

<img src="Assignment2_Final_Version_files/figure-markdown_strict/unnamed-chunk-12-1.png" width="80%" style="display: block; margin: auto;" />

Question 4
----------

It is interesting that when readers are presented both graphs and asked
to choose one they prefer, 81% chose the more complex design and only
19% chose the minimalist design. Out of the readers who at the beginning
were only shown the non-minimalist graph, 83% of them stick with their
initial visualization; however, 79% of participants who for the first
question were given the high-ink ratio chart, rather chose the more
complex one as their preferred option.

\begin{table}[]
\centering
\caption{Which Figure Do You Prefer?}
\label{my-label}
\begin{tabular}{lll}
Figure Preferred & Frequency & Proportion \\
Non-minimalist   & 64        & 81\%       \\
Minimalist       & 15        & 19\%       \\
Total            & 79        & 100\%     
\end{tabular}
\end{table}
<img src="Assignment2_Final_Version_files/figure-markdown_strict/unnamed-chunk-13-1.png" width="80%" style="display: block; margin: auto;" />

**Logistic Regression**

As shown in the previous graph, most individuals prefer the
non-minimalistic plot over the minimalistic one. The logistic regression
analysis shows that there is no significant difference between each
experimental group.


    Call:
    glm(formula = Q4_dummy ~ bw_dummy, family = binomial(link = "logit"), 
        data = exp_DT_Q4)

    Deviance Residuals: 
        Min       1Q   Median       3Q      Max  
    -1.8930   0.6039   0.6039   0.6853   0.6853  

    Coefficients:
                Estimate Std. Error z value Pr(>|z|)    
    (Intercept)   1.6094     0.4472   3.599  0.00032 ***
    bw_dummy     -0.2803     0.5835  -0.480  0.63098    
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

    (Dispersion parameter for binomial family taken to be 1)

        Null deviance: 76.794  on 78  degrees of freedom
    Residual deviance: 76.561  on 77  degrees of freedom
    AIC: 80.561

    Number of Fisher Scoring iterations: 4

Question 5
----------

The results of the last question show that among readers who prefer the
non-minimalist visualization, 67% of them mentioned color as the reason
of their preference, 62% mentioned amount of information, and 59% values
the design of image in the background, while only 17% chose the
simplicity. For those who express more affection to the minimalist
design, while color and information are only mentioned 13% out of all,
image 20%, 70% of them like the low-ink ratio chart is because of the
simplicity of design.

    # A tibble: 2 x 8
      Q4                     n  freq Color Information Images Simplicity Other
      <fct>              <int> <dbl> <dbl>       <dbl>  <dbl>      <dbl> <dbl>
    1 Figure A (color)      64 0.810 0.670       0.620  0.590      0.170    0.
    2 Figure B (black a~    15 0.190 0.130       0.130  0.200      0.730    0.

**Distribution for all the respondents**
<img src="why.png" width="80%" style="display: block; margin: auto;" />
\#\#Conclusions:

The main finding of this experiment is that, on average, the
minimalistic plot was not preferred over the non-minimalistic plot. We
also get to recover some insights on why people prefer the
non-minimalistic plot.

Regarding the efficacy to transmit a message and recallability of
minimalistic graphs, with this amount of data and small sample size,
there is as yet insufficient data for any meaningful answer, and we are
just too powerless to address any conclusion.

However, at least within this sample we study, it is obvious that much
more participants prefer the design with a relatively lower-ink ratio.
The reason for the preference of non-minimalist chart can give fast
interest to capture potential readers and draw more attention to
important facts. Sometimes readers do not have time to sit there and
decode the number; rather they prefer a quick and easy access to get
information.

While minimalist design with extremely high data-ink ratio can provide
information in a cleaner and more straightforward way, sometimes the
omission of aesthetics factors and deliberate cutoff of information can
backfire: readers are likely to get bored reading and extracting
important information from a too-simple chart. A correct use of
complexity can match readers visual preferences and enhance the
effectiveness of a graph

Citation
--------

Inbar, Ohad & Tractinsky, Noam & Meyer, Joachim. (2007). Minimalism in
information visualization: Attitudes towards maximizing the data-ink
ratio. ACM International Conference Proceeding Series. 250. 185-188.
10.1145/1362550.1362587.

Appendix A. Survey Design for minimalist group
----------------------------------------------

**Page 1 (Question 1)** <img src="Q1min.png" width="70%" />

**Page 2 (Question 2)** <img src="Q2min.png" width="70%" />

**Page 3 (Question 3)** <img src="Q3.png" width="70%" />

**Page 4 (Questions 4 and 5)**
<img src="max.png" width="70%" /><img src="min.png" width="70%" /><img src="Q4Q5.png" width="70%" />

\newpage
Appendix B. Survey Design for non-minimalist group
--------------------------------------------------

**Page 1 (Question 1)** <img src="Q1max.png" width="70%" />

**Page 2 (Question 2)** <img src="Q2max.png" width="70%" />

**Page 3 (Question 3)** <img src="Q3.png" width="70%" />

**Page 4 (Questions 4 and 5)**
<img src="max.png" width="70%" /><img src="min.png" width="70%" /><img src="Q4Q5.png" width="70%" />
