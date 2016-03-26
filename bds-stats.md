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
in either cabinet B or C. If it was cabinet B we will find a silver coin in the
other drawer. If it was cabinet C, we will find a gold coin in the other drawer.

Therefore we have a 1/2, or 50% chance that the other
drawer contains a silver coin.






