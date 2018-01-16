# Gendered Success in Developer Careers

## Problem
While women have been shown to make vital contributions to the collective intelligence of teams, to collective intelligence of a team (Wooley-Williams et al., 2010), they are also marginalized in many respects. (Gill, 2002; Terrell et al., 2016) In project-based creative fields investing in social capital by sharing knowledge with other experts is an important aspect of a successful career, and men seem to do a better job at it. (Lutter, 2015) To test this hypothesis in IT, we analyzed the paths to success for men and women using their activity traces on GitHub. 

## Data Collection
Our primary data source is GitHub  the most popular online Open Source community, which is a modern platform for the development of social and knowledge capital (Bonaccorsi and Rossi, 2003). The empirical basis of this work is a data set acquired via githubarchive.org about the activities on the social coding platform GitHub, encompassing the various types of events that took place between 2009 and 2016. 
To collect information about users’ name, e-mail address, location, organizations, number of followers, number of people they follow, number of public repositories and the date they joined GitHub, we sent calls to the official GitHub  users API  

## Gender Recognition
Since users do not list their gender directly, we infer each person's gender using their first names. This is a commonly and successfully used method in Western societies (Hannak et al, 2017) In this work, we relied on the US baby name dataset (SSA 2016).  Due to some names being used for both males and females, we assign a probability of being male to each candidate based on the fraction of times their first name was assigned to a male baby in the name dataset. The bimodal shape of this probability distribution, sharply peaking at 0 and 1, allows us to binaries the values using the thresholds 0.1 and 0.9: If the probability is less than 0.1 or equal we assign the user as female, if it is higher than 0.9 or equal we assign as male, otherwise unknown. 

### Gender Recognition Summary

| Probability                        | Gender   | Sample Size  |
| ---------------------------------- | -------- | ------------ |
| P <= 0.1                           | female   | 180 000      |
| No name available or 0.1 < P < 0.9 | unknown  | 6.2 million  |
| P >= 0.9                           | male     | 1.4 million  |

## Results
We used collaboration activity to conceptualize individual careers. After filtering for users with at least 10 actions we created stratified samples of each gender group, With 10,000 male, female, and unknown users.

We adapted an approach pioneered by Wachs and co-authors (Wachs et al. 2017) to operationalize the extent to which someone’s behavior follows a gendered pattern, using the resulting continuous variable to consider a continuum, rather than binary, notion of gendered behavior. To gender behaviors, we used a logistic regression to predict the gender of a user using their collaboration history, activity, and programming language use. The resulting coefficients give us a measure of how gendered a given kind of activity or programming language is.


## Gender Prediction
We use an odds ratio to calculate represents the odds that the user is male and having a given attribute (e.g.: having intra-gender collaborations) compared to the odds of being man in the absence of that given attribute (not having intra-gender collaborations). SE indicates standard error significance stars in the table below denote p<0.05.

### Logit Table and ROC Curve

<img src="Logit.png" alt="hi" class="inline"/>

Gender homophily is more likely among women (OR=0.322, p=0.002), women are more likely to collaborate with each other. (See Logit Model, Collaborations) Women have more followers (OR=0.813, p<0.001) but men use more different languages (versatility, OR=1.028, p=0.000). 

### Gender and Success

<img src="Gender_Success.png" alt="hi" class="inline"/>

Success is defined as the number of stars on users’ own repositories. We used the gender prediction results (maleness) to understand the correlation between success and gendered behavior. Success is defined as the number of stars on users' repositories.

Maleness is positively related with success (# repository stars), but female developers are systematically less successful, even if they have highly male behaviors. (Red line is always under the blue one.) We ca conclude that women are more likely to collaborate with each other But are more likely to succeed if they adopt a collaboration and activity behavior that is typical of men. For instance, they are more likely to be successful if they collaborate less with other women.

## Closure
Research shows that in a majority-minority setting the marginalized group should avoid closing itself into cohesive groups, and needs to invest into diverse collaborations to be successful in long term (Lutter, 2015). An important reason why this work is innovative is that it is the result of an interdisciplinary collaboration between a physicist, sociologist, and data scientist. We worked together to understand causes and consequences of female marginalization in technology. We are also able to distill our findings and offer practical advice for young professionals. 

## References
*	Bonaccorsi, A. and Rossi, C. (2003). Why Open Source software can succeed. Res. Policy, 32:1243–1258. 
*	Gill, R. (2002). Cool, Creative and Egalitarian? Exploring Gender in Project-Based New Media Work in Euro. Information, Commun. Soc., 5(1):70–89. 
*	Hannak, A., Wagner, C., Garcia, D., Mislove, A., Strohmaier, M., and Wilson, C. 2017. Bias in Online Freelance Marketplaces: Evidence from TaskRabbit and Fiverr. In 20th ACM Conference on Computer-Supported Cooperative Work and Social Computing (CSCW 2017).
*	Lutter, M. (2015). Do Women Suffer from Network Closure? The Moderating Effect of Social Capital on Gender Inequality in a Project-Based Labor Market, 1929 to 2010. Am. Sociol. Rev., 80(2):329–358. 
*	Terrell, J., Kofink, A., Middleton, J., Rainear, C., Murphy-Hill, E., and Parnin, C. (2016). Gender bias in open source: Pull request acceptance of women versus men. PeerJ Prepr. 
*	Wachs, J., Hannakm A., Voros, A., Daroczy, B. (2017) Why Do Men Get More Attention? Exploring Factors Behind Success in an Online Design Community
Proceedings of the 11th International AAAI Conference on Weblogs and Social Media (ICWSM'17), Montreal, May, 2017.
*	Wooley-Williams, A., Chabris, C. F., Pentland, A., Hashmi, N., and Malone, T. M. (2010). Evidence for a Collective Intelligence Factor in the Performance of Human Groups. Science (80-. )., 330. 


