# This produces a values for mean.priors from .2, .5, .8 and from n values 5, 10, 15 
# I should do this for all combinations 
output.a = NULL
output.b = NULL
mean.prior = c(.2, .5, .8); mean.prior
length(mean.prior)
n.prior = c(5, 10, 15)
length(n.prior)
for (i in seq_along(mean.prior)){
  for (j in seq_along(n.prior) ){
  a = mean.prior*n.prior
  b = (1-mean.prior)*n.prior
  output.a[[i]] = a[[i]] 
  output.b[[j]] = b[[j]] 
  }
}
output.a
output.b
