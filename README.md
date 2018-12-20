# Is the salary of female developers lower than that of male?
![avatar](./title.jpg)
Last month I read 'Man Disconnected:How technology has sabotaged what it means to be male' , a book written by  Philip Zimbardo / Nikita D. Coulombe.The book tell us that manhood is in crisis. So I want to find out if the salary of female developers is higher than that of male at present.<br>
StackOverflow has published the results of their 2017 and 2018 Developer Survey. <br>
Let's take a look at the difference in wages between male and female developers in 2 years.
We have 12891 salary data in 2017 and 50578 salary data in 2018 <br>
A quartile is a type of quantile. The first quartile (Q1) is defined as the middle number between the smallest number and the median of the data set. The second quartile (Q2) is the median of the data. The third quartile (Q3) is the middle value between the median and the highest value of the data set. <br>
So I choose the salary from Q1 to Q3 in order to avoid extreme values.


We will investigate this issue in three steps.
## Question 1:Is wages increased?
![avatar](./q1_bar.png)
![avatar](./q1_line.png)
<br>
The answer is very clear.Low-income developers’ wages fall.Middle-income developers are basically flat.High-income developer income has increased significantly.

## Question 2:Does female developer salary increase?
![avatar](./q2_bar.png)
<br>
 We can see that the average annual income of female developers has increased by more than 11.2% this year.

## Question 3:Is women’s wages are higher than men’s?
![avatar](./q3_2017.png)
<center>2017</center>

![avatar](./q3_2018.png)
<center>2018</center>
<br>
Looking at the data from these two years,The average income of female developers is basically the same as that of men, but there is a slight overshoot.
<br>
If the data can represent the current income of all developers,we can answer the question of the title.  The answer is direct negative.But the survey_results_public of stackoverflow is not enough, and there is a lack of data from many countries, such as China,so only as a reference.<br>
[Code source](https://github.com/xueweiyema/xueweiyema.github.io/blob/master/SalaryTrend.ipynb) 