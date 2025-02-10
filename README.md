# UK Smoking Data Analysis

(In Progress) Project: [/uk_smoking_analysis/uk_smoking (1).html](https://github.com/garrettcbert/uk_smoking_analysis/blob/main/uk_smoking.html)

Data pulled from <a href = https://www.stem.org.uk/resources/elibrary/resource/28452/large-datasets-stats4schools>Stem.org.uk</a> and published by Stats4Schools

## Introduction
We have worked hard as a society to abolish smoking as a socially accepted tool. That being said, many still struggle with a smoking addiction, creating lasting effects on population health, and potentially drastically shortening lifespans. Our surroundings often play a large role in determining the type of lifestyle that we choose to live. Your gender, your marital status, and even your education level may heavily impact your decisions and habits. For better or for worse, the opinions of those around us and the surroundings that we find ourselves in can certainly influence us. What factor of life plays the most substantial role in pushing someone towards this habit and what can we do with this information to get people out of a lifetime of smoking?


In this report, I make a statistical conclusion about the effects that marital status, gender, and education level can have on the probability that someone smokes. This data was exclusively collected from a sample of people who live in the UK, so any conclusions made are made exclusively about the population of people who live in the United Kingdom.

## Background
This data was put together by Stats4Schools and was collected from <a href = "https://www.stem.org.uk/resources/elibrary/resource/28452/large-datasets-stats4schools">stem.org.uk</a>. The dataset includes many variables that potentially play a role in determining the probability that someone smokes tobacco. The variables used in this investigation include:

<ul>
    <li><b>marital_status:</b> Marital Status (Divorced, Married, Single, etc.)</li>
    <li><b>gender:</b> (Male, Female)</li>
    <li><b>highest_qualification:</b> Highest Level of Education</li>
    <li><b>smoke: </b> Whether or not the person smokes (Yes, No)</li>
</ul>

The `smoke` column will be modified to contain ones and zeros. (1 = Yes, 0 = No)

<p align="center">
  <img src="Graphs/marital_status_graph.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

# Inference on Difference of Proportion of Smokers

## **Part 1:** Married vs. Single

For the sake of simplicity, and drawing real conclusions, we will just focus on the single and the married people in the `marital_status` column. At least from our sample and as you can see from the graph above, these two groups have the greatest difference in proportions. To conclude the respective percentages from the population, we can conduct a hypothesis test as well as a confidence interval.

The graph below shows the number of smokers and non-smokers we have in our dataset from the `Single` and `Married` categories. The total number of smokers in both is very similar but the percentage of the total number is much different. 

<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>total</th>
<th>total_smoke</th>
<th>non_smoke</th>
<th>perc_smoke</th>
</tr>
<tr>
<th>marital_status</th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<th>Married</th>
<td>812</td>
<td>143</td>
<td>669</td>
<td>17.610837</td>
</tr>
<tr>
<th>Single</th>
<td>427</td>
<td>158</td>
<td>269</td>
<td>37.002342</td>
</tr>
</tbody>
</table>

<p align="center">
  <img src="Graphs/single_vs_married.png" style="max-width: 70%; height: auto; display: block;"/>
</p>
<p align="center">

<div style="max-width: 800px; margin: 0 auto; font-family: Arial, sans-serif; line-height: 1.6;">

  <h2 style="color: #4CAF50; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">Hypothesis Testing</h2>
  
  <p style="font-size: 18px; font-weight: bold; margin-top: 10px;">
    Using a significance level of 0.05
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 1: Model Statement</h3>
<p align="center">
  <img src="math/single_married_binom.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 2: State Hypotheses</h3>
<p align="center">
  <img src="math/hypo_single_married.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 3: Test Statistic and Null Distribution</h3>
  <p style="text-align: center; font-size: 18px;">
    <b>Test Statistic and Null Distribution for Difference of Proportions:</b>
  </p>
<p align="center">
  <img src="math/Z-stat.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 4: Identify Relevant Outcomes</h3>
<p align="center">
  <img src="math/single_married_t_stat.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 5: Calculate a P-Value</h3>
<p align="center">
  <img src="math/single_married_p_value.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 6: Interpret in Context</h3>
  <p style="font-size: 18px;">
    Our calculated P-Value is much smaller than our significance level of 0.05, providing significant evidence that the true proportion of single people who smoke in the UK is not equal to the proportion of married people who smoke. 
  </p>
  <p style="font-size: 18px;">
    Although it may already be clear which proportion is likely larger, we can confirm this using a confidence interval.
  </p>

  <h2 style="color: lightblue; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">Confidence Interval (C = 0.95)</h2>
  
  <p style="font-size: 18px; font-weight: bold;">General Formula for Confidence Interval:</p>
<p align="center">
  <img src="math/stand_conf_equation.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <p style="font-size: 18px; font-weight: bold;">Confidence Interval for Difference in Proportions:</p>
  <p style="font-size: 18px;">
    Using the <b>Agresti-Coull Adjustment:</b>
  </p>
<p align="center">
  <img src="math/conf_equation.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

<p align="center">
  <img src="math/conf_bounds.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h2 style="color: purple; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">Conclusion:</h2>
  <p style="font-size: 18px;">
    The confidence interval created using a 95% confidence level is heavily shifted to the right and does not include zero. This provides strong evidence that the true proportion of single smokers in the UK is greater than the true proportion of married smokers in the UK.
  </p>

</div>

## **Part 2:** Male vs. Female 

An argument could be made that gender plays a role in determining whether someone might take up smoking. Certain societal pressures could provoke an addiction based on sex, but by looking at the sample data the percentages look similar enough for an argument to be made for the difference to be negligable. That being said we can perform the same kind of statistical hypothesis testing to create evidence to point towards the population proportions.

<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>total_smoke</th>
<th>total</th>
<th>perc_smoke</th>
<th>non_smoke</th>
</tr>
<tr>
<th>gender</th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<th>Female</th>
<td>234</td>
<td>965</td>
<td>0.242487</td>
<td>731</td>
</tr>
<tr>
<th>Male</th>
<td>187</td>
<td>726</td>
<td>0.257576</td>
<td>539</td>
</tr>
</tbody>
</table>
</div>
</div>

<p align="center">
  <img src="Graphs/male_vs_female.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

<div style="max-width: 800px; margin: 0 auto; font-family: Arial, sans-serif; line-height: 1.6;">

  <h2 style="color: #4CAF50; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">Hypothesis Testing</h2>
  
  <p style="font-size: 18px; font-weight: bold; margin-top: 10px;">
    Using a significance level of 0.05
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 1: Model Statement</h3>
<p align="center">
  <img src="math/gender_binom.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 2: State Hypotheses</h3>
<p align="center">
  <img src="math/hypo_gender.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 3: Test Statistic and Null Distribution</h3>
  <p style="text-align: center; font-size: 18px;">
    <b>Test Statistic and Null Distribution for Difference of Proportions:</b>
  </p>
<p align="center">
  <img src="math/Z-stat.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 4: Identify Relevant Outcomes</h3>
<p align="center">
  <img src="math/gender_t.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 5: Calculate a P-Value</h3>
<p align="center">
  <img src="math/gender_p_value.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 6: Interpret in Context</h3>
  <p style="font-size: 18px;">
    Our calculated P-Value is much larger than our significance level. This means that there is strong evidence for the null hypothesis that gender has no impact on the proportion of smokers in the UK. A confidence is not necessary and we can safely disregard the idea of a difference in population proportion based on gender.
  </p>

## **Part 3:** Education Levels

Conventional wisdom may tell you that the higher education level someone has attained, the more likley they would be to maintain good health, whether that be because they know more about healthy habits or they simply have more money and time to invest into getting rid of habits such as smoking. In order to make a conclusion about how exactly education may impact the probaility of someone smoking in the UK, I have mutated the data to help find more of a concrete conclusion about this question.

`No Formal Education`:
<ul>
    <li>No Qualification</li>
</ul>

`Basic Education`:
<ul>
    <li>GCSE/O Level</li>
    <li>GCSE/CSE</li>
</ul>

`Intermediate Education`:
<ul>
    <li>A Levels</li>
    <li>ONC/BTEC</li>
    <li>Higher/Sub Degree</li>
</ul>

`Higher Education`:
<ul>
    <li>Degree</li>
</ul>

<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>total_smoke</th>
<th>total</th>
<th>perc_smoke</th>
<th>non_smoke</th>
</tr>
<tr>
<th>highest_qualification</th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<th>No Formal Education</th>
<td>137</td>
<td>586</td>
<td>0.233788</td>
<td>449</td>
</tr>
<tr>
<th>Basic Education</th>
<td>143</td>
<td>410</td>
<td>0.348780</td>
<td>267</td>
</tr>
<tr>
<th>Intermediate Education</th>
<td>71</td>
<td>306</td>
<td>0.232026</td>
<td>235</td>
</tr>
<tr>
<th>Higher Education</th>
<td>39</td>
<td>262</td>
<td>0.148855</td>
<td>223</td>
</tr>
</tbody>
</table>
</div>
</div>

<p align="center">
  <img src="Graphs/education_graph.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

This graph shows something I would not have expected. `Basic Education`, atleast according to our sample percentages has far and away the greatest fraction of smokers. `Higher Education` people, as I would expect has the lowest percentage of smokers, but `No Formal Education` people do not have the highest as I would have predicted. Students in the `Basic Education` levels of GCSE/O Level and GCSE/CSE have passed what is really the bear minumum for people who want to pursue a well-paying job. People with `No Formal Education` likely ended their schooling after the compulsory education ended at around the age of 16. Because `Intermediate Education` and `No Formal Education` appears to have a similar sample proportion this is not worth testing to apply to the population, however, we can perform a series of tests to find conclusions about how some of the education levels relate to smoking rates.

<div style="max-width: 800px; margin: 0 auto; font-family: Arial, sans-serif; line-height: 1.6;">

  <h2 style="color: #4CAF50; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">3a. No Formal Education vs. Basic Education Hypothesis Testing</h2>
  
  <p style="font-size: 18px; font-weight: bold; margin-top: 10px;">
    Using a significance level of 0.05
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 1: Model Statement</h3>
<p align="center">
  <img src="math/binom_education.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 2: State Hypotheses</h3>
<p align="center">
  <img src="math/hypo_education.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 3: Test Statistic and Null Distribution</h3>
  <p style="text-align: center; font-size: 18px;">
    <b>Test Statistic and Null Distribution for Difference of Proportions:</b>
  </p>
<p align="center">
  <img src="math/Z-stat.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 4: Identify Relevant Outcomes</h3>
<p align="center">
  <img src="math/education_t_stat.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 5: Calculate a P-Value</h3>
<p align="center">
  <img src="math/education_p_val.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 6: Interpret in Context</h3>
  <p style="font-size: 18px;">
    A P-Value of 3.548652e-5 is much smaller than our significance level of 0.05 so we have enough evidence to refute the null hypothesis that the real proportion of people with a Basic Education is equal to the real proportion of people with No Formal Education. There is strong evidence that the true proportion of people with a Basic Education that smoke is greater than the true proportion of people with No Formal Education that smoke. 
  </p>

It is difficult to properly hypothesize about why this might be the case. Students that never pass their GCSE or never obtain any other equivilant qualification might experience different stresses and use different coping mechanisms. Whether a proportion of people smoke or not is largely determined by the societal norms put in place in that area. If someone leaves school early to enter a field with less smokers overall then they would not be as likely to smoke themselves. The lesson that we should take from these results should not be to discourage getting these types of qualifications but stop dangerous norms like smoking from appearing in a setting such as a school, where young people are more easily influenced and addictions are more easily created.

<div style="max-width: 800px; margin: 0 auto; font-family: Arial, sans-serif; line-height: 1.6;">

  <h2 style="color: #4CAF50; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">3b. Basic Education vs. Higher Education</h2>
  
  <p style="font-size: 18px; font-weight: bold; margin-top: 10px;">
    Using a significance level of 0.05
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 1: Model Statement</h3>
<p align="center">
  <img src="math/basic_higher_binom.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 2: State Hypotheses</h3>
<p align="center">
  <img src="math/basic_higher_hypo.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 3: Test Statistic and Null Distribution</h3>
  <p style="text-align: center; font-size: 18px;">
    <b>Test Statistic and Null Distribution for Difference of Proportions:</b>
  </p>
<p align="center">
  <img src="math/Z-stat.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 4: Identify Relevant Outcomes</h3>
<p align="center">
  <img src="math/basic_higher_t_stat.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 5: Calculate a P-Value</h3>
<p align="center">
  <img src="math/basic_higher_p_val.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 6: Interpret in Context</h3>
  <p style="font-size: 18px;">
    Our P-Value is yet again extremely small meaning that we have strong evidence that the true proportion of people that smoke with a basic education level is greater than the true proportion of people that smoke with a degree. These results are not particularly surprising considering we can easily relate having a higher education level to being more healthy. 
  </p>

# Relavant Heatmap

We have collected a solid amount of information about the true proportion of smokers within our dataset in certain groups. To recap the results:

<ol>
    <li>True proportion of single smokers in the UK is very likley larger than the true proportion of married smokers</li>
    <li>There is no statistical significance between the true proportion of males and females in the UK that smoke</li>
    <li>True proportion of people with a basic education level that smoke in the UK is surprisingly likely greater than the true proportion of people with no formal education that smoke in the UK</li>
    <li>True proportion of people with a basic education level that smoke in the UK is likley greater than the true proportion of people with a higher education level that smoke in the UK</li>
</ol>

To start to understand what economic and social climate breeds the largest true proportion of smokers in the UK, we can compare these factors against each other using a heatmap.

<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html" tabindex="0">
<div>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th>highest_qualification</th>
<th>Basic Education</th>
<th>Higher Education</th>
<th>Intermediate Education</th>
<th>No Formal Education</th>
</tr>
<tr>
<th>marital_status</th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<th>Married</th>
<td>0.315789</td>
<td>0.111111</td>
<td>0.218182</td>
<td>0.170543</td>
</tr>
<tr>
<th>Single</th>
<td>0.500000</td>
<td>0.240964</td>
<td>0.162162</td>
<td>0.321429</td>
</tr>
</tbody>
</table>
</div>
</div>

<p align="center">
  <img src="Graphs/heatmap.png" style="max-width: 70%; height: auto; display: block;"/>
</p>

## Heatmap Conclusions

This heatmap gives us a good idea of where the highest proportion of smokers in the UK seem to lie. The area corresponding to `Basic Education` and `Single` is far and away the highest proportion of 50% of those in those categories in our sample identifying as smokers. This agrees with our earlier conclusion that between `Single` and `Married`, `Single` has a statistically significant greater proportion of smokers. As well as our other conclusion that among our distinct education levels, `Basic Education` has a statistically greater real proportion of smokers in the UK

# Overall Conclusions

Although only three factors were tested of many possible factors that could play into whether someone smokes, this information is still useful in understanding why some people are pushed into forming bad habits. Being single, of course, is not an inherently bad thing, but having a partner evidently may be a contributing factor into pursuing a healthy lifestyle. Another worthwhile conclusion that was made is that gender does not seem to have a real effect on smoking habits. Men in the UK have just as good of a chance to take up smoking as women. Education levels is where some very surprising findings were made. I have been made to assume, that the more education someone has access to, the more likley they will be to pursue good habits, whether that be because they are more educated regarding what is healthy and what is not or because they simply have the access/money required to build better habits. The statistical conclusions made mostly followed this pattern, but the discovery that the true UK smoking percentage of those with a `Basic Education` level is very likley greater than the true proportion of those with `No Formal Education` changed by perception on this topic.

Finally, the heatmap connected some of the other findings that were made prior and gave strong evidence that those in the `Single` and `Basic Education` categories have the greatest probability of identifying as a smoker (50%). Perhaps unsurprisingly, on the other side of the spectrum, only 11% of those in the `Married` and `Higher Education` categories in the sample data identify as smokers. 
