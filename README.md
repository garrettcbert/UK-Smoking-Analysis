# UK Smoking Data Analysis

(In Progress) Project: [/uk_smoking_analysis/uk_smoking.html](https://github.com/garrettcbert/uk_smoking_analysis/blob/main/uk_smoking.html)

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

<div style="max-width: 800px; margin: 0 auto; font-family: Arial, sans-serif; line-height: 1.6;">

  <h2 style="color: #4CAF50; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">Hypothesis Testing</h2>
  
  <p style="font-size: 18px; font-weight: bold; margin-top: 10px;">
    Using a significance level of \( \alpha = 0.05 \)
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 1: Model Statement</h3>
  <p style="text-align: center; font-size: 20px; margin: 10px 0;">
    \( X_\text{Single} \sim \text{Binomial}(158, p_\text{Single}) \)
  </p>
  <p style="text-align: center; font-size: 20px; margin: 10px 0;">
    \( X_\text{Married} \sim \text{Binomial}(143, p_\text{Married}) \)
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 2: State Hypotheses</h3>
  <p style="text-align: center; font-size: 20px; margin: 10px 0;">
    \( H_0: p_\text{Single} = p_\text{Married} \)
  </p>
  <p style="text-align: center; font-size: 20px; margin: 10px 0;">
    \( H_\alpha: p_\text{Single} > p_\text{Married} \)
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 3: Test Statistic and Null Distribution</h3>
  <p style="text-align: center; font-size: 18px;">
    <b>Test Statistic and Null Distribution for Difference of Proportions:</b>
  </p>
  <p style="text-align: center; font-size: 22px; color: #555;">
    \( Z = \frac{(\hat{p_1} - \hat{p_2}) - (0)}{\sqrt{\frac{\bar{p}(1-\bar{p})}{n_1} + \frac{\bar{p}(1-\bar{p})}{n_2}}} \sim N(0, 1) \)
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 4: Identify Relevant Outcomes</h3>
  <p style="text-align: center; font-size: 20px;">
    \(\text{Single vs. Married Test Statistic} = 7.564\)
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 5: Calculate a P-Value</h3>
  <p style="text-align: center; font-size: 18px; color: #555;">
    \( \text{P-Value} = P(Z \geq |z|) \)
  </p>
  <p style="text-align: center; font-size: 20px; font-weight: bold;">
    \( \text{Single vs. Married P-Value} = 1.953993 \times 10^{-14} \)
  </p>

  <h3 style="color: #4CAF50; text-align: left; margin-top: 20px;">Step 6: Interpret in Context</h3>
  <p style="font-size: 18px;">
    Our calculated P-Value is much smaller than our significance level of \( 0.05 \), providing significant evidence that the true proportion of single people who smoke in the UK is not equal to the proportion of married people who smoke. 
  </p>
  <p style="font-size: 18px;">
    Although it may already be clear which proportion is likely larger, we can confirm this using a confidence interval.
  </p>

  <h2 style="color: lightblue; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">Confidence Interval (C = 0.95)</h2>
  
  <p style="font-size: 18px; font-weight: bold;">General Formula for Confidence Interval:</p>
  <p style="text-align: center; font-size: 22px; color: lightblue;">
    \( \text{Point Estimate} \pm \text{Quantile Confidence Score * Standard Error of PE} \)
  </p>

  <p style="font-size: 18px; font-weight: bold;">Confidence Interval for Difference in Proportions:</p>
  <p style="font-size: 18px;">
    Using the <b>Agresti-Coull Adjustment:</b>
  </p>
  <p style="text-align: center; font-size: 22px; color: lightblue;">
    \( \hat{p_{1AC}} - \hat{p_{2AC}} \pm \text{qnorm}(C + (1-C)/2) \cdot \sqrt{\frac{\hat{p}_{1AC}(1-\hat{p}_{1AC})}{n_1+2} + \frac{\hat{p}_{2AC}(1-\hat{p}_{2AC})}{n_2+2}} \)
  </p>
  <p style="text-align: center; font-size: 22px; color: lightblue;">
    \( \frac{158 + 2}{427 + 4} - \frac{143 + 2}{812 + 4} \pm \text{qnorm}(0.95 + (1-0.95)/2) \cdot \sqrt{\frac{\frac{158 + 2}{427 + 4}(1-\frac{158 + 2}{427 + 4})}{427+2} + \frac{\frac{143 + 2}{812 + 4}(1-\frac{143 + 2}{812 + 4})}{812+2}} \)
  </p>

  <p style="text-align: center; font-size: 20px; font-weight: bold;">
    Left Bound: \( 0.141 \) &nbsp;&nbsp; | &nbsp;&nbsp; Right Bound: \( 0.246 \)
  </p>

  <h2 style="color: purple; text-align: left; border-bottom: 2px solid #ddd; padding-bottom: 5px;">Conclusion:</h2>
  <p style="font-size: 18px;">
    The confidence interval created using a 95% confidence level is heavily shifted to the right and does not include zero. This provides strong evidence that the true proportion of single smokers in the UK is greater than the true proportion of married smokers in the UK.
  </p>

</div>
