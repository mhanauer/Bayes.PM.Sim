# This get the values in the vector into the output variable for the length of the vector.
# Try to generalize this to the sample and replicate functions
# What I want to do here is get it the loop to place each value of the x.sample which is the replication 
# of choosing i from x which is just 1 and 0.  
x = c(1,0)
Bayes.Sim.n  = c(4,5)
x.sample = replicate(100, sample(x, i, replace = TRUE, prob = c(.5, .5)))

Bayes.Sim.output.n.5 = NULL


for (i in seq_along(foo)) {
  Bayes.Sim.output.n.5[i] = foo[i]
}
Bayes.Sim.output.n.5

