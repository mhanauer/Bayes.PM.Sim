# Bayes.PM.Sim
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
#To get the mean from the prior data
kappa.example = mean(c(rep(1,8), rep(0,3))); kappa.example
#To get the shape values
betaABfromMeanKappa( mean=kappa.example, kappa=11)
#To run the actual analysis
openGraph()
post.informed = BernBeta( priorBetaAB=c(8,3) , Data=c(rep(1,6),rep(0,3)) ,showHDI=TRUE , showCentTend="Mode")
