# This version takes produces a matrix of means for a length of 5 for the evidence
x = c(1,0)
# 500 replications, because you have you have 100 replications of a length of 5
# This produces 500 data points.  seq_along inputs each value of i for the length of 
# of the dataset 
Bayes.Sim.n  = replicate(500,5); Bayes.Sim.n
x.sample = replicate(100, sample(x, 5, replace = TRUE, prob = c(.5, .5)))
length(x.sample)

Bayes.Sim.output.n.5 = NULL

for (i in seq_along(Bayes.Sim.n)) {
  x.sample = replicate(100, sample(x, i, replace = TRUE, prob = c(.5, .5)))
  Bayes.Sim.output.n.5[[i]] = x.sample[[i]]
  Bayes.Sim.output.n.5.matrix = matrix(Bayes.Sim.output.n.5, 100, 5)
  Bayes.Sim.output.n.5.matrix.apply = apply(Bayes.Sim.output.n.5.matrix, 1, mean)
}
Bayes.Sim.output.n.5.matrix.apply
