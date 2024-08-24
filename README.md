# Normalizacija podataka stepenim transformacijama: Box-Cox  i Yeo-Johnson 
U ovom projektu istražujemo tehnike normalizacije podataka kroz primenu stepenih transformacija, sa fokusom na Box-Cox i Yeo-Johnson metode. 

Normalizacija podataka je ključna za pripremu podataka za analizu i modelovanje, jer omogućava da se podaci prilagode pretpostavkama koje su neophodne za mnoge statističke metode i algoritme mašinskog učenja. Ovaj proces je naročito važan danas, kada tačnost i efikasnost analiza, baziranih na modelima masinskog ucenja, igraju ključnu ulogu u donošenju odluka.

Poseban naglasak stavljamo na primere primene Box-Cox i Yeo-Johnson transformacija. Pružićemo konkretne primere kako se ove transformacije primenjuju na različite skupove podataka i uporediti njihove efekte na distribuciju podataka. Diskutovaćemo prednosti i ograničenja svakog pristupa, kao i situacije u kojima su određene transformacije posebno korisne.

## Normalizacija podataka (normalna raspodela)
Normalization is the process of scaling in respect to the entire data range so that the data has a range from 0 to 1.

In machine learning, data normalization is a common technique used to preprocess data before training a model. The goal is to transform the data in a way that improves the performance and accuracy of the model.
There are many data transformation techniques that can be used to normalize or alter the distribution of a dataset. These include Log transformation, Square root transformation, Power transformation, Exponential transformation e.t.c. The Box-Cox transformation is useful in data normalization because it can help to reduce the impact of outliers, and can make the data more consistent and comparable.

The pattern of values obtained when a variable is measured in large number of individuals is called a distribution. The normal distribution, also known as the Gaussian distribution, is a continuous probability distribution that is widely used in Machine Learning and statistical modeling. It is a bell-shaped curve that is symmetrical around its mean and is characterized by its mean and standard deviation. This is called normal distribution as most of the biological parameters (such as weight, height and blood sugar) follow it. 

The aim of normalization is to change the distribution of the observation such that it resembles a Normal or Gaussian distribution. A Gaussian distribution is a probability distribution that is symmetric and bell-shaped. Most of the data is concentrated near the mean, with fewer and fewer data points as you move away from the mean.

Maybe this skewed data is not good for model training, why?  Machines learn from patterns, and extreme values can mess up their understanding. We want to make sure the model sees the full story, not just a part of it. So, we often tweak the data to make it more balanced and fair, helping the machine learn better. So these transformations will help you achieve balanced data.

The sole purpose  of  normalization of  the data is to ensure 
that the variation in the expression values is indeed due to biological differences and not 
due to experimental artifacts (noises).  (https://www.researchgate.net/publication/256005221_A_Note_on_Transformation_Standardization_and_Normalization)

variance - refers to how much is the data varying with respect to the mean

# Stepene transformacije - uvod


# Box-Cox transformacija
The Box-Cox transformation (Box & Cox, 1964) represents a family of power transformations that incorporates and
extends the traditional options to help researchers easily find the optimal normalizing transformation
for each variable. Box-Cox represents a potential best practice where normalizing data or
equalizing variance is desired.
The Box-Cox transformation is a type of power transformation, but other powers can also be used. It is commonly used in statistical analysis, particularly in the field of econometrics, where it is often used to transform non-normal data to improve the performance of linear regression models.
It is important to note that the Box-Cox transformation is not intended to normalize the distribution of the data to a Gaussian (normal) distribution, but rather to transform the data to a distribution that is closer to normality.

A Box cox transformation is defined as a way to transform non-normal dependent variables in our data to a normal shape through which we can run a lot more tests than we could have
https://www.geeksforgeeks.org/box-cox-transformation-using-python/

