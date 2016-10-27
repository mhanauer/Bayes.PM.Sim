# Bayes.PM.Sim
# This version gets the values into the empty list kappa.mean.output by
# making sure they are type consistent 
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
#To get the mean from the prior data
#Produces the choice of 1 or 0 for a piece of evidence
x = c(1,0)
#Samples from x 10 and replicates this ten times with prob of 1 = .3 and 0 = .7
#It produces 10 sets of data with 10 data points each
#It produces a different set of numbers each time
x.sample = replicate(10, sample(x, 10, replace = TRUE, prob = c(.4, .6))); x.sample
x.sample.m = matrix(x.sample, 10, 10); x.sample.m
#Gets the means for the columns
x.sample.m.a = apply(x.sample.m, 2, mean); x.sample.m.a
# Changing the name for convience 
mean.prior = x.sample.m.a; mean.prior
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
n.rep.m = matrix(n.rep, 10, 10); n.rep
#Gets the means for the columns
n.rep.m.a = round(apply(n.rep.m, 2, mean), 0); n.rep.m.a
# Changing the name for convience
n.prior = n.rep.m.a; n.prior
###########################################################################################################
# Here I am changing the shape parameters 
a = mean.prior*n.prior; mean.prior; a
b = (1-mean.prior)*n.prior; n.prior; b
###############################################################################################################
# Here is code for calculating the posterior mean that is correct
a = 5
b = 5
Data = c(rep(1,1),rep(0,9)); Data
z = sum( Data ) # number of 1's in Data
N = length( Data ) 
Theta = seq(0.001,0.999,by=0.001) # points for plotting
pThetaGivenData = dbeta( Theta , a+z , b+N-z ); pThetaGivenData  # posterior for plotting
post.mean = (z+a)/(N +a+b); post.mean
