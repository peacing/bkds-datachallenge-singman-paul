# Brooklyn Data Science Stats Test
### 3/25/16
### Paul Singman

#### Q1

**a: Calculate the Five Number Summary:**
* Min: 150
* Q1: 164
* Median: 167.5
* Q3: 169.5
* Max: 178

**b: Calculate the Sample Mean**
mean = 166

**c: Calculate the Inter quartile Range**
IQR = Q3 - Q1 = 5.5

**d: Which, if any, of the observations are possible outliers?**
What is considered an outlier is subjective, though commonly
a point greater than two standard deviations from the mean
are considered as possible outliers. We have a mean of 166 and
a sample s.d. of 9.27, meaning any point outside the range:
166 +- 2* 9.27 = [147.45 184.55] could be considered an outlier.

None of the heights of the six people are possible outliers

**e: Create a boxplot of the observations**
See accompanying Ipython notebook for image (or perhaps it will load here)
![Image](../static/boxplotq1.png?raw=True)

Notice that the box plot considers the 178 cm data point
a potential outlier

**f: Calculate the sample variance and sample s.d.:**
As mentioned in part d, the sample std dev is 9.27.
The sample variance is the square of that, 86.0.


#### Q2

**i: All real numbers:**
The set of all reals are metric and continuous (by definition)

**ii: {first, second, third}:**
I would argue this is in between metric and non-metric. Yes, you can
calculate a "distance" between coming in first and second (1) or 
first and third (2) but it requires an implicit conversion from
the text to the numerical equivalent.

It is also an interval/discrete data type since it is ordinal with
equally spaced intervals between the values.

**iii: {Green, Blue, Yellow. Brown}:**
This is a clear example of a non-metric, nominal data type.

**iv: (1,2,3,4,5):**
This is a metric data type, and is interval/discrete

** v: 5 point scale of strongly disagree to strongly agree:**
I would argue this is in between metric and non-metric based on the same logic
used for part ii. I would consider this to be an ordinal data type since it
gives a clear ordering of the variables, though the scale used to calculate a 
"distance" could be arbitrary.


#### Q3: What is the 68, 95, 99.7 rule for the normal distribution?

This rule means that, given normally distributed data, you expect 68%
of the data points to fall within plus/minus one standard deviation of the mean,
95% of the data points to fall within a two std. dev range, and 99.7%
to fall within a three std. dev range.

#### Q4

**a: Given N(100, 16) data, what percentile is 116?**
The z-score for 116 is: (116 - 100)/16 = 1
Looking up this z-score in a normal distribution table
shows that this score is in the 84th percentile.

#### Q5
If we find a silver coin in the first drawer, we know that we opened a drawer
in either cabinet B or C. If it was cabinet B, we will find a silver coin in the
other drawer. If it was cabinet C, we will find a gold coin in the other drawer.

Therefore we have a 1/2, or 50% chance that the other
drawer contains a silver coin.

#### Q6
The longer piece will be twice the length of the shorter piece
if we make the cut anywhere outside the middle third of the segment.
Assuming a uniform distribution of where the cut occurs, that means there's
a 66.6% chance the resulting longer piece is more than twice the length
of the short piece (anywhere int he first third, or last third of the segment).

#### Q7

This is a classic Bayes Theorem set up.

P(A|B) = P(B|A)*P(A)/P(B)

I will define:
* A as having the flu
* B as testing positive

We are trying to solve the probability of having the flu given a positive test

We need to solve for P(A), P(B) and P(B|A)

We are given P(A) = 0.1
We are also given the False Positive Rate (FPR) = 0.01
and the False Negative Rate (FNR) = 0.0003

To make the problem easier to intuit, I'm going to assign actual numbers to these rates.
Assume there are 100,000 people. With what we are given, we know 10,000 people have the flu
and 90,000 do not.

The FNR = FN/(FN + TP), which can be interpreted as the percent of
times a negative test results from someone positive with the condition.
We know that (FN + TP) = 10,000 (in the 100k population), so we can solve for FN:

0.0003 = FN/10000. FN = 3. If FN + TP = 10,000, we know TP = 9,997.

We use the same logic on the FPR to solve for FP = 900 & TN = 89,100.

We can use these numbers to solve for the P(B), the probability
of getting a positive test. There are two ways to get a positive test result:
1) a true positive or 2) a false positive. With TP = 9,997 and FP = 900 in a
population of 100k, the probability of getting a positive test result is:
(9,997 + 900)/100,000 = P(B) = 0.10897

Lastly, we interpret the P(B|A) as the probability of getting a positive test
given that you have the flu. This can also be called the True Positive Rate (TPR) and
TPR = 1 - FNR = .9997.

Plugging these values into the equation we get:
P(A|B) = 0.9997 * 0.1 / 0.10897 = 91.74%

To summarize, there is a 91.74% chance that given a positive test result,
a person has the flu.

#### Q8

We have a Poisson distribution with a mean of 2 failures per year. This means we would expect
an average of 100 failures over 50 years. The Probability Distribution Function (PDF) for 
the Poisson is (excuse the lack of mathematical notation):

P(k events) = (mu^k * e^-mu)/k!

To calculate the probability of 100 or more failures, we would do:

1 - P(k), for all k 0 to 99. I've utilized a Poisson distribution calculator and found
the answer to be: P(k >= 100) = 51.33%

#### Q9

* The estimated standard error of the sample mean is the standard deviation of
the sample, which is given to be 0.8

* To calculate a 95% confidence interval for the population average, we need to calculate
the estimated population standard deviation. The formula is:

s.d.(population) = s.d(sample)/sqrt(n), where n is the size of the sample.
s.d.(population) = 0.8/sqrt(100) = 0.08.

A 95% confidence interval covers the range 1.96* +/- the mean.
Therefore the 95% confidence interval is 1.6 +- 1.96 * 0.08.
95% CI = [1.44 1.76]

* An estimate for the total No. of umbrellas is simply the sample mean * population size.
U = 1.6 * 8000 = 12,800.

* Estimated standard error of U is the estimated standard deviation of the population,
multiplied by the square root of the size of the population:
SE(U) = 0.08 * sqrt(8000) = 7.155

* Lastly then the 95% CI for the total No. of umbrellas is:
12,800 +- 1.96 * 7.155 = [12,785 12,814]

#### Q10

To use the Monte Carlo method to simulat the standard normal density on the interval [0, 1],
we need to generate many random numbers with the pdf of the normal distribution. We will keep track
of the percent of the generated numbers that fall in the [0,1] range.

See the code in the Jupyter Notebook for details of simulation implementation
I used NumPy's random normal method to generate the random numbers.
The result I got for the density in the [0,1] range is 34.46%.
This is very close to the actual value of 34% you would expect since
68% of values lie within 1 standard deviation, and the range [0,1] is half of that.

#### Q11



