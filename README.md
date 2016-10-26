# Bayes.PM.Sim
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
# This version puts the previous version into a function
kappa.mean.output = as.list(c(rep(NULL, 10000)); kappa.mean.output)
kappa.mean.output = as.list(kappa.mean.output)
typeof(kappa.mean.output)
function(){
  x = c(1,0)
  x.sample = sample(x, 10, replace = TRUE, prob = c(.3, .7))
  x.sample.rep = as.list(rep(x.sample, 1000))
  typeof(x.sample.rep)
  for(i in 1:length(x.sample.rep)){
    kappa.mean.output[i] = x.sample.rep[i]
  }
}  
kappa.mean()
kappa.mean.output
