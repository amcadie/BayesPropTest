BayesPropTest
=============

simple Bayesian version of R's prop.test

## Bayesian Test of the Difference Between Proportions  

### usage  
<code>bayes.prop.test(n1, d1, n2, d2, a=1, b=1, rep=10000)</code>


### arguments
<code>n1</code>  The numerator of the first group. Required.  

\item{d1}{The denominator of the first group. Required. The
proportion \emph{n1/d1} should be greater than or equal to \emph{n2/d2}.}

\item{n2}{The numerator of the second group. Required.}

\item{d2}{The denominator of the second group. Required. The
proportion \emph{n2/d2} should be less than or equal to \emph{n1/d1}.}

\item{a}{Alpha prior parameter. Defaults to 1.}

\item{b}{Beta prior parameter. Defaults to 1.}

\item{rep}{Number of replications for the \code{rbeta} function. Defaults to 10,000.}
}
\description{
This function provides a simple way to perform a Bayesian
version of \code{prop.test} using the beta distribution.

The default prior distributional parameters are \emph{a} = 1 and \emph{b} = 1.
The prior can be adjusted if you have reasonable information to work with.
If you set \emph{a} < \emph{b}, the density will be weighted toward the lower
half of the distribution, and setting \emph{a} > \emph{b} would weight it
toward the upper half. If \emph{a} = 0.5, much more weight is given to values
near 0, while if \emph{b} = 0.5, weight is stacked up near 1. Examples of
different shapes of the beta distribution based on different parameter values
can be seen at Rocscience: \url{http://bit.ly/1hOWChG}.
}
\examples{
bayes.prop.test(n1=50, d1=100, n2=20, d2=50)
# difference       p-hat        2.5\%       97.5\% prob.diff>0
# 0.10000000  0.09695006 -0.07072376  0.25873452  0.87380000
}
\keyword{Bayesian}
\keyword{beta}
\keyword{differences}
\keyword{prop.test}
\keyword{proportions}
