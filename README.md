# Data science in practice

<div align="justify">

A living repository on how to analyze data in medicine. Most books on medical data analysis now available recommend practices that were state-of-the-art 25-35 years ago. This repo will illustrate how to analyze data now and users will be able to use GitHub's version control to observe previous recommendations.

## Observational data

### Data analysis

* I would have recommended to split the data in two and use honest estimation ([Wager and Athey, 2016](https://amstat-tandfonline-com.stanford.idm.oclc.org/doi/full/10.1080/01621459.2017.1319839?src=recsys)). However, I would now recommend a very compelling new alternative called cross-screening ([Zhao et al., 2018](https://amstat.tandfonline.com/doi/abs/10.1080/01621459.2017.1407770?journalCode=uasa20#.W0W2NS3wd24)): "Cross-screening splits the data in half at random, uses the first half to plan a study carried out on the second half, then uses the second half to plan a study carried out on the first half, and reports the more favorable conclusions of the two studies correcting using the Bonferroni inequality for having done two studies. If the two studies happen to concur, then they achieve Bogomolov–Heller replicability; however, importantly, replicability is not required for strong control of the family-wise error rate, and either study alone suffices for firm conclusions. In randomized studies with just a few null hypotheses, cross-screening is not an attractive method when compared with conventional methods of multiplicity control. However, cross-screening has substantially higher power when hundreds or thousands of hypotheses are subjected to sensitivity analyses in an observational study of moderate size."

* Only explore a small subset of your data, design all of your analytic approaches within that small sample and then discard that sample and apply all of what you did, but in the large sample, without changing anything in your analysis.

* Create p-values using the bootstrap to include, not only the uncertainty introduced by the sampling procedure, but to also include ALL analytic decisions made. For example, if you are removing outliers, run bootstrap procedures to include decisions related to outliers. This is the true p-value for your study.

* Do not report the analysis of your preference, but all analyses done. Use as many analytic approaches as you think apply and certainly at least three. For example, instead of merely using matching, use inverse-probability weighting, a matching procedure (e.g. propensity and Mahalanobis-distance matching) and double machine learning.

* Use s-values alongside p-values to help readers understand what a p-value means

* Always report p-values calculated 4 ways: using likelihood, using quasi-likelihood, using sandwich estimation and using the bootstrap.

* Always report SMD in Table 1 and always consider whether the distribution of p-values makes sense.

* Always consider what others before you have done and capture as many as you can of the data that they captured to help provide a bridge between your data and their data - this will help us appreciate the true heterogeneity between the two studies.

* Causal inference. As of March 2019, the recommended procedure is to use doubly robust machine learning with cross-fitting and trimming. To do so, fit the machine learning model (using your favorite algorithm and by optimizing for out of sample performance, i.e. NOT overfitting) fit within n-1 folds and predict within the last fold (usually 5-fold cross-fitting) with trimming (trimming adjusts for overfitting). Then, add up the 5 estimates and divide by 5 for an unbiased estimator of the ATE.

* Run as many analyses of as many associations as possible - exhaust your data. This will allow us to correctly adjust for the p-value and achieve a better false-discovery rate, rather than creating many publications for each association you want to test.

### Data reporting

* Provide forest plots to illustrate the confidence intervals associated to each association tested - do not provide the p-values and do not provide the confidence intervals without this forest plot.

* Always think of your analytic tasks as either descriptive, predictive or causal inference and clearly denote which one you are working on.

* Make your code and data available on OSF, GitHub, etc.

* Report ALL data - the p-value should play NO role in whether you choose to report your data or not.

</div>
