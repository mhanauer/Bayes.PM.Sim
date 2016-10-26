# Bayes.PM.Sim
# This version generalizes the sampling function for the 1,0 to selecting N's
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
#######################################################################################################
# Here we are creating the N matrix
# Currently I am just randomly sampling them and will come up with a more meaning way later
typeof(kappa.mean.output)
#Produces the choice of the total N for priors (must be at least 2)
# one value for A and one value for B
n = c(2:11)
#Samples from x 10 and replicates this ten times with prob of .1 for each N 
#It produces 10 sets of N's with 10 N's each
#It produces a different set of numbers each time
n.rep = replicate(10, sample(n, 10, replace = TRUE, prob = c(rep(.1,10)))); n.rep 
x.sample.m = matrix(n.rep, 10, 10); n.rep
#Gets the means for the columns
x.sample.m.a = round(apply(x.sample.m, 2, mean), 0); x.sample.m.a
###########################################################################################################


