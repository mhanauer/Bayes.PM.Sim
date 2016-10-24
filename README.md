# Bayes.PM.Sim
#Need to source all three of these things
source("DBDA2E-utilities.R") # Load definitions of graphics functions etc.
source("BernBeta.R") # Load the definition of the BernBeta function
#To get the mean from the prior data
#This is just a mean value to put into the kapp.example
#So simulate these values and create a matrix of mean values
#Need to produce a second variable that has the total N for the samples
#because the kappa needs to match the total N for the mean (i.e. kappa.example)
kappa.example = mean(c(rep(1,8), rep(0,3))); kappa.example
#Will need to randomly select Kappas which need to be intervals and non-negative
#They need to match whatever the 
prior = betaABfromMeanKappa( mean=kappa.example, kappa=11); prior
#To run the actual analysis
openGraph()
post.informed = BernBeta( priorBetaAB=c(8,3) , Data=c(rep(1,6),rep(0,3)) ,showHDI=TRUE , showCentTend="Mode")
