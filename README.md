# This produces a values for mean.priors from .3, .5, .7 and from n values 5, 10, 15 
# This only produces A's and B's for the each value matched with each other (.3 with 5, .5 with 5, and .7 with 15)
# This needs to be done for all possible combinations
output.a = NULL
output.b = NULL
a.b = NULL
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
a.b. = cbind(output.a, output.b)
########################################################################################################################
# This takes the vectors of a's and b's and runs them through a for loop that produces posteior means for the combination
# above.  
a = output.a # This is the prior for a
b = output.b # This is the prior for b
mean.data = c(.3, .5, .7) # number of 1's in Data
n.data = c(5, 10, 15) # number of total data points
output.post = NULL # Empty vector to place posterior means in
for(i in seq_along(mean.data)){
    Theta = seq(0.001,0.999,by=0.001) # points for plotting
    pThetaGivenData = dbeta( Theta , a+mean.data , b+n.data-mean.data ); pThetaGivenData  # posterior for plotting
    post.mean = (mean.data+a)/(n.data +a+b)
    output.post[[i]] = post.mean[[i]]
}
output.post
