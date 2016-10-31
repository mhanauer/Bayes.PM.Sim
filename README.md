# I am going to make a seperate dataset manually for each condition
# The parameters are evidence length = 5,10,15; priors = .2, .5, .8
# Here is the list of combinations: 5.2.8; 5 .8 .2; 10 .2 .8; 10 .8 .2; 15 .2 .8; 15 .8 .2; 5 .5 .5; 10 .5 .5; 15 .5 .5  
# Bayes.Sim.output.n.5.2.8
x = c(1,0)
Bayes.Sim.output.n.5.2.8 = replicate(100, sample(x, 5, replace = TRUE, prob = c(.2, .8))); Bayes.Sim.output.n.5.8.2
Bayes.Sim.output.n.5.2.8.matrix = matrix(Bayes.Sim.output.n.5.2.8, 100, 5); Bayes.Sim.output.n.5.2.8.matrix
Bayes.Sim.output.n.5.2.8.matrix.apply = apply(Bayes.Sim.output.n.5.2.8.matrix, 1, mean); Bayes.Sim.output.n.5.2.8.matrix.apply 
