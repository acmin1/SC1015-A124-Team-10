# SC1015 A124 Team 10: Sleep Efficiency Project:

## About
---
Our mini project for SC1015 *(Introduction to Data Science and Artificial Intelligence)* aims to explore the <u>factors that affect Sleep Efficiency</u>.
<br/><br/>
## Background
---
Studies show that more than one-third of adults in the US do not get enough sleep on a regular basis and are sleep deprived. Given the importance of sleep for our overall health and wellbeing, it's crucial that we understand the <u>factors that affect Sleep Efficiency</u>.
<br/><br/>

## Contributors
---

|Name:| Contribution:|
|---|---|
|Borkar Nitika Prasad|Outlier Removal, Model 3, Presenter 1|
|Chan Min Adeline Alyssa|Data Cleaning, EDA, Model 1, Model 2, Presenter 2|
|G R Devansh Rao| Dataset Scaling, Model 3, Presenter 3|
<br/><br/>
## Problem Definition
---

* <u>Identify key factors</u> that impact sleep efficiency using the Sleep Efficiency metric

* Sleep Efficiency: Measure of quality of sleep, % of time spent asleep while in bed.
<br/><br/>

## Data Set
---
The dataset used for this project was retrieved from [here](https://www.kaggle.com/datasets/equilibriumm/sleep-efficiency)
<br/><br/>

## Our Process
---

<details>
<summary>1. Data Cleaning & Outlier Removal</summary>
<ul>
<li> Checking for duplicates and missing values</li>
<li> Converting string variables to integers (Label Encoding)</li>
<li> Conversion to Unix timestamps </li>
<li> Filled in NaN values using 10% Trimmed Mean</li>
</ul>
</details>

<details>
<summary>2. Exploratory Data Analysis</summary>
<ul>
<li> Identified potential Sleep Efficiency Predictors</li>
<ul>
<li> Categorical Variables Boxplot & Violin Plot: Smoking Status</li>
<li> Numerical Variables PairPlots: Deep Sleep Percentage, Light Sleep Percentage
 </li>
 </ul>
<li> Correlation Heat Map: Deep sleep percentage, Light sleep percentage, Awakenings, Alcohol consumption, Smoking Status, Exercise Frequency
</li>
<li>Used T-Test for Smoking Status
</li>
<li>
Random Sampling for Splitting 80% Train & 20% Test Dataset
</li>
<li>Dataset Scaling using StandardScaler()
</li>
<ul><li>Normalized Features
</li></ul>
</ul>
</details>

<details>
<summary>3. Model 1 & 2: Multi-Variate Linear & Lasso Regression</summary>
<ul>
<li> Model 1: Multivariate Linear Regression</li>
<ul>
<table><tbody>
    <tr>
      <th>Dataset:</th>
      <th align="center">Explained Variance:</th>
      <th align="right">Root Mean Squared Error:</th>
    </tr>
        <tr>
      <td>Train</td>
      <td align="center">0.80</td>
      <td align="right">0.0592</td>
    </tr>
    <tr>
      <td>Test</td>
      <td align="center">0.81</td>
      <td align="right">0.0626</td>
    </tr>
</tbody></table>
</ul><ul>
<li> Key Features: Bedtime, Wakeup Time, Light Sleep Percentage</li></ul>


<li> Model 2: Lasso Regression</li>
<ul>
<table><tbody>
    <tr>
      <th>Dataset:</th>
      <th align="center">Explained Variance:</th>
      <th align="right">Root Mean Squared Error:</th>
    </tr>
        <tr>
      <td>Train</td>
      <td align="center">0.77</td>
      <td align="right">0.0592</td>
    </tr>
    <tr>
      <td>Test</td>
      <td align="center">0.79</td>
      <td align="right">0.0626</td>
    </tr>
</tbody></table>
</ul><ul>
<li> Key Features: Light Sleep Percentage, Awakenings, Age</li></ul>

</ul>
</details>
<details>
<summary>4. Model 3: XGBoost</summary>
<ul>
<table><tbody>
    <tr>
      <th>Dataset:</th>
      <th align="center">Explained Variance:</th>
      <th align="right">Root Mean Squared Error:</th>
    </tr>
        <tr>
      <td>Train</td>
      <td align="center">0.99</td>
      <td align="right">0.0024</td>
    </tr>
    <tr>
      <td>Test</td>
      <td align="center">0.88</td>
      <td align="right">0.048</td>
    </tr>
</tbody></table>
</ul><ul>
<li> Key Features: Deep Sleep Percentage, Awakenings, Smoking Status</li></ul>
</details>
<br/><br/>

## Conclusions
----

*   All 3 models identified important features; however, <u>each set was not the same</u>.

*    In our Lasso & Multi-Variate Linear Regression Models, features such as Age, Gender, Sleep Duration, REM Sleep Percentage, Deep Sleep Percentage, Caffeine Consumption, Alcohol Consumption & Exercise Frequency, were considered less important.

*  Since the model of XGBoost also had the <u>best fit and outcome with the data</u>, we trust the model and the features that played a role.
    *   For XGBoost, Deep Sleep Percentage, Light Sleep Percentage, Awakenings, Alcohol Consumption, Smoking Status, and Exercise Frequency were more prominent. This shows that <u>external habits can affect sleep quality</u>.
    * So to have better sleep and an improved quality of life, people should refrain from smoking and drinking while also exercising more frequently. They should also not make mid-sleep awakenings as a habit and remove any loud distractors that could potentially awaken them at night.
<br></br>

## What Did We Learn During This Project?
---
<details>
<summary>Key Learning Points:</summary>
<ul>
<li> Z Score</li>
<li> 10% Trimmed Mean to fill in NAN</li>
<li> T-Test</li>
<li> Multivariate Linear Regression</li>
<li> Lasso Regression</li>
<li> XGBoost</li>

</ul>
</details>
<br></br>

## References
---
* https://www.sleepfoundation.org/how-sleep-works/how-much-sleep-do-we-really-need
* https://www.cdc.gov/sleep/data_statistics.html
* https://www.kaggle.com/code/unmoved/regress-sleep-efficiency-xgb
* https://www.statology.org/z-score-python/
* https://www.mygreatlearning.com/blog/understanding-of-lasso-regression/
* https://www.analyticsvidhya.com/blog/2017/06/a-comprehensive-guide-for-linear-ridge-and-lasso-regression/
* https://machinelearningmastery.com/lasso-regression-with-python/
* https://www.scribbr.com/statistics/multiple-linear-regression/
* https://www.analyticsvidhya.com/blog/2021/05/multiple-linear-regression-using-python-and-scikit-learn/
