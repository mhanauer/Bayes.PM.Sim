# Here is a for loop that places values into an empty vector. 
# I want to get this to work for the sampling and replication of the data for one data length
foo = seq(1, 100); foo
Bayes.Sim.output.n.5 = NULL

for (i in foo ) {
  Bayes.Sim.output.n.5[i] = foo[i]
}
Bayes.Sim.output.n.5
