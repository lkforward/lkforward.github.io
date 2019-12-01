# 1. Three Key Elements in Bayesian Inference

# 2. Interpret Your Posterior Samples: The Theorem of Large Numbers

# 3. Choose a Prior Properly
## (1) Is the prior “objective” or “subjective”?
The prior distribution about the unknown parameters is the weakest and the strongest point of Bayesian inference. It is a weak point because the choice of prior distribution depends on the user and is sort of subjective; but it is also a strong point as users can bring in their domain knowledge into the model. 
In general, we can divide the priors into two categories: objective priors and subjective priors. Objective priors refer to those “naive” assumptions that do not involve any bias (?) towards any part of the possible range of the parameter value. In contrast, subjective priors usually indicate that certain part of the domain will be more “probable” than the rest of the range. 

## (2) How to be “objective”?
In most cases, a uniform distribution is the most objective prior as it basically assumes that all the values in the range of definition are equally possible. However, is being objective the same as always using a uniform distribution?
For example, the mu in a Bernoulli distribution is around 0.5. What is a good example to discuss this point? 

## (3) The “empirical Bayesian” trick
Sometimes people use the so-called “empirical Bayesian” trick in Bayesian inference, but in some sense, it double-counts the data in the modeling process and thus violates the definition of “prior” information (which means the distribution without seeing the data). 
The empirical Bayesian trick takes the following steps: 
frequentists’ method - > parameter value as the prior - > Bayesian method - > distribution of the parameter values 

## (4) When N is large enough
Although a good prior will lead you to the “true” distribution of the parameter more efficiently, we should keep in mind that the ultimate posterior distribution will not depend on the choice of the prior. 
From the Bayesian theorem, we can show that (we can show from the equation) the likelihood term will dominate as more and more data is given, and thus the effect of the prior distribution on the posterior distribution will be eventually be very small when the N is large enough.  

# 4. Loss function in Bayesian Inference and Apply B.I. in Machine Learning Problems

If a machine learning model has an explicit expression (for example, linear regression, logistic regression, SVM, etc), we can consider using Bayesian method instead of optimization. 
To be specific, if we have a model in the format of y = f(x; alpha, beta), where alpha and beta are parameters we are interested, we can use the same formula y = f(x; alpha, beta) to build a data model in Bayesian language. We can assign a prior to parameters alpha and beta, and then use MCMC to get the posterior distribution of alpha/beta. 
Just us usual, we choose alpha/beta to minimize the pre-defined loss 
function. But unlike other machine learning methods, the Bayesian inference (MCMC) does not rely on the specific format of loss function. Recall that a linear regression usually involves minimize the root-mean-square or similar error definition. 
Using Bayesian method takes two steps in learning the parameter: 
    • a. Build up the data model; 
    • b. get the posterior distribution of unknown parameters; 
    • c. select the prediction to minimize the loss function. 
NOTE: We can use an example from the book to illustrate the diffference. 
