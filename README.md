# Bayes.PM.Sim
# This version produces a matrix of mean values randomly sampled from a 
# vector of 1,0 for ten students
# making sure they are type consistent 
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
#To get the mean from the prior data
#Create a set of data points of 1's and 0's and take the mean
kappa.mean.output = as.vector(kappa.mean.output); kappa.mean.output
typeof(kappa.mean.output)
#Produces the choice of 1 or 0 for a piece of evidence
x = c(1,0)
#Samples from x 10 and replicates this ten times with prob of 1 = .3 and 0 = .7
#It produces 10 sets of data with 10 data points each
#It produces a different set of numbers each time
x.sample = replicate(10, sample(x, 10, replace = TRUE, prob = c(.4, .6))); x.sample
mean(x.sample)
x.sample.m = matrix(x.sample, 10, 10); x.sample.m
#Gets the means for the columns
x.sample.m.a = apply(x.sample.m, 2, mean); x.sample.m.a 
#Need to create a matrix with the same length filled with values of N
#To get it into the prior function a loop with two commands one for the mean and the other for n
#If you can get the values into a data.frame then create a matrix of them
#that this 100*10 and then apply for the median over the columns
