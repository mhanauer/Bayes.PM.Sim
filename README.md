# Bayes.PM.Sim
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
#Produces a 10,000 1's and 0's with probability .3 for 1's and .7 for zeros
kappa.mean = function(){ 
  x = c(1,0)
  x.sample = sample(x, 10, replace = TRUE, prob = c(.3, .7))
  x.sample.rep = rep(x.sample, 1000)
  x.sample.rep
  } 
}
kappa.mean()
