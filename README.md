Download Link: https://assignmentchef.com/product/solved-gu4206-gr5206-lab1-the-normal-distribution
<br>
<h1>Background: The Normal Distribution</h1>

Recall from your probability class that a random variable <em>X </em>is normally-distributed with mean <em>µ </em>and variance <em>σ</em><sup>2 </sup>(denoted <em>X ∼ N</em>(<em>µ,σ</em><sup>2</sup>)) if it has a probability density function, or <em>pdf</em>, equal to

<em>f</em><em>.</em>

In <em>R </em>we can simulate <em>N</em>(<em>µ,σ</em><sup>2</sup>) random variables using the rnorm() function. For example,

<strong>rnorm</strong>(n = 5, mean = 10, sd = 3)

## [1] 8.120639 10.550930 7.493114 14.785842 10.988523

outputs 5 normally-distributed random variables with mean equal to 10 and standard deviation (this is <em>σ</em>) equal to 3. If the second and third arguments are ommited the default rates are <strong>mean = 0 </strong>and <strong>sd = 1</strong>, which is referred to as the “standard normal distribution”.

<h1>Tasks</h1>

<h2>Sample means as sample size increases</h2>

1) Generate 100 random draws from the standard normal distribution and save them in a vector named <strong>normal100</strong>. Calculate the mean and standard deviation of <strong>normal100</strong>. In words explain why these values aren’t exactly equal to 0 and 1.

<em># You’ll want to type your response here. Your response should look like:</em>

<em># normal100 &lt;# Of course, your answer should not be commented out. </em>2) The function <strong>hist() </strong>is a base <em>R </em>graphing function that plots a histogram of its input. Use <strong>hist() </strong>with your vector of standard normal random variables from question (1) to produce a histogram of the standard normal distribution. Remember that typing <strong>?hist </strong>in your console will provide help documents for the <strong>hist() </strong>function. If coded properly, these plots will be automatically embedded in your output file.

<ul>

 <li>Repeat question (1) except change the number of draws to 10, 1000, 10,000, and 100,000 storing the results in vectors called <strong>normal10</strong>, <strong>normal1000</strong>, <strong>normal10000</strong>, <strong>normal100000</strong>.</li>

 <li>We want to compare the means of our four random draws. Create a vector called <strong>sample_means </strong>that has as its first element the mean of <strong>normal10</strong>, its second element the mean of <strong>normal100</strong>, its third element the mean of <strong>normal1000</strong>, its fourth element the mean of <strong>normal10000</strong>, and its fifth element the mean of <strong>normal100000</strong>. After you have created the <strong>sample_means </strong>vector, print the contents of the vector and use the <strong>length() </strong>function to find the length of this vector. (it should be five). There are, of course, multiple ways to create this vector. Finally, explain in words the pattern we are seeing with the means in the <strong>sample_means </strong></li>

</ul>

<h2>Sample distribution of the sample mean</h2>

<ul>

 <li>Let’s push this a little farther. Generate 1 million random draws from a normal distribution with <em>µ </em>= 3 and <em>σ</em><sup>2 </sup>= 4 and save them in a vector named <strong>normal1mil</strong>. Calculate the mean and standard deviation of <strong>normal1mil</strong>.</li>

 <li>Find the mean of all the entries in <strong>normal1mil </strong>that are greater than 3. You may want to generate a new vector first which identifies the elements that fit the criteria.</li>

 <li>Create a matrix <strong>normal1mil_mat </strong>from the vector <strong>normal1mil </strong>that has 10,000 columns (and therefore should have 100 rows).</li>

 <li>Calculate the mean of the 1234<em><sup>th </sup></em></li>

 <li>Use the <strong>colSums() </strong>functions to calculate the <em>means </em>of each column of <strong>normal1mil_mat</strong>. Remember, <strong>?colSums </strong>will give you help documents about this function. Save the vector of column means with an appropriate name as it will be used in the next task.</li>

 <li>Finally, produce a histogram of the column means you calculated in task (9). What is the distribution that this histogram approximates (i.e. what is the distribution of the sample mean in this case)?</li>

 <li>Let’s push this even farther. Generate 10 million random draws from an exponential distribution with rate parameter <em>λ </em>= 3 (<strong>Hint: ?rexp</strong>). Save the simulated draws in a vector named <strong>exp_10mil</strong>. Calculate the mean and standard deviation of <strong>exp_10mil</strong>. How do these numbers compare to <em>E</em>(<em>X</em>) = 1<em>/</em>3 and <em>sd</em>(<em>X</em>) = 1<em>/</em>3?</li>

 <li>Create a matrix <strong>exp10mil_mat </strong>from the vector <strong>exp_10mil </strong>that has 10,000 columns (and therefore should have 100 rows). Use the <strong>colMeans() </strong>function to calculate the <em>means </em>of each column of <strong>exp_mil_mat</strong>. Show the first 10 computed means.</li>

 <li>Finally, produce a histogram of the column means you calculated in task (12). What is the approximate distribution that this histogram displays (i.e. what is the distribution of the sample mean in this case)? Overlay the true approximate density function over the histogram. <strong>Note: </strong>the correct code is displayed below.</li>

</ul>

<em># hist(exp_means,</em>

<em>#                     main=”Histogram of Exponential Means”,</em>

<em>#                     xlab=expression(bar(X)),</em>

<em>#                 prob = T,</em>

<em>#                breaks=20)</em>

<em># n &lt;- nrow(exp10mil_mat)</em>




<table width="632">

 <tbody>

  <tr>

   <td width="632"><em># mean_exp &lt;- 1/3</em><em># mean_exp</em><em># sd_exp &lt;- 1/(3*sqrt(n))</em><em># sd_exp</em><em># x &lt;- seq(0,1,by=.0001)</em><em># my_density &lt;- dnorm(x,mean=mean_exp,sd=sd_exp)</em><em># lines(x,my_density,col=”purple”)</em></td>

  </tr>

 </tbody>

</table>


