# Data science in practice

<div align="justify">

A living repository on how to analyze data in medicine. Most books on medical data analysis now available recommend practices that were state-of-the-art 25-35 years ago. This repo will illustrate how to analyze data now and users will be able to use GitHub's version control to observe previous recommendations.

## Observational data

### Data

I would have recommended to split the data in two and use honest estimation ([Wager and Athey, 2016](https://amstat-tandfonline-com.stanford.idm.oclc.org/doi/full/10.1080/01621459.2017.1319839?src=recsys)). However, I would now recommend a very compelling new alternative called cross-screening ([Zhao et al., 2018](https://amstat.tandfonline.com/doi/abs/10.1080/01621459.2017.1407770?journalCode=uasa20#.W0W2NS3wd24)): "Cross-screening splits the data in half at random, uses the first half to plan a study carried out on the second half, then uses the second half to plan a study carried out on the first half, and reports the more favorable conclusions of the two studies correcting using the Bonferroni inequality for having done two studies. If the two studies happen to concur, then they achieve Bogomolov–Heller replicability; however, importantly, replicability is not required for strong control of the family-wise error rate, and either study alone suffices for firm conclusions. In randomized studies with just a few null hypotheses, cross-screening is not an attractive method when compared with conventional methods of multiplicity control. However, cross-screening has substantially higher power when hundreds or thousands of hypotheses are subjected to sensitivity analyses in an observational study of moderate size."

</div>
