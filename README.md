# This get the values in the vector into the output variable for the length of the vector.
# Try to generalize this to the sample and replicate functions
foo = c(4,5); foo
Bayes.Sim.output.n.5 = NULL

for (i in seq_along(foo)) {
  Bayes.Sim.output.n.5[i] = foo[i]
}
Bayes.Sim.output.n.5

