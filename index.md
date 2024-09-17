---

layout: col-sidebar
title: OWASP WAF Advanced Ruleset Management
tags: example-tag
level: 2
type: code
pitch: A very brief, one-line description of your project

---

The project addresses the challenge of optimizing the performances of the rulesets used by Web Application Firewalls (WAFs) to stop attack instances against applications and APIs.
Rulesets generally consist of regular expressions that are matched against the traffic incoming toward applications and services. Such rules are based on well-known attack instances and are standard; thus, they are not prepared considering how the application to be protected has been written and works (e.g., which kind of inputs it is expected to receive). Additionally, rules might also be associated with a "score" that represents how critical the attack detected by the rule is. This score is assigned based on the experience of the ruleset developer. It again does not take into account the features of the web application in front of which the ruleset will be deployed. 
Thus, before putting the ruleset into production, a tuning phase is necessary to reduce the risk of false alarms. This result is achieved with a set of combined actions, which are 1) the progressive disabling of all the rules that might trigger a false positive, 2) the adjustment of the threshold used by the WAF to decide between legitimate and malicious requests, and, even, 3) adjusting the "score" assigned with the rules. 
Unfortunately, this process is typically the outcome of a manual, trial-and-error process that, while ensuring that no false positives are triggered, may significantly deteriorate the detection rate ensured by the ruleset, yielding a suboptimal tradeoff between false positives and application security.

The goal of this project is to overcome these limitations by leveraging machine learning to automate and improve the aforementioned manual tuning process.
Machine learning can indeed provide a substantial advantage in optimizing the selection and the combination of the available rules, based on the available traffic/data, by simply training a linear model. In particular, a linear model can do the same work systematically and exhaustively, considering all the possible options, and identify an optimal setting of the parameters that ensures, based on the ruleset at the end, the traffic incoming to the application to protect, and a dataset of attacks, the best tradeoff possible between false positives and detection rate. 
Thus, the project will focus on how to use machine learning effectively to optimize the ruleset in a living environment where web applications and APIs are actually deployed.
The OWASP Core Rule Set will represent the primary reference ruleset for the project. Nevertheless, the approach developed will be general and thus eventually adaptable also to other rulesets. 

### Road Map
Within the first 12 months, the project is expected to deliver:
•	The documentation provides the background on the problem and the way the project intends to address it;
•	Datasets to use to replicate the tests already documented in the referenced research work (ModSec-Learn: Boosting ModSecurity with Machine Learning)
•	A first dataset of legitimate traffic;
•	A first dataset of malicious traffic. This latter will focus on the optimization against the SQLi attacks;
•	The source code to run the optimization process. It will be a set of scripts enabling the update of the scores assigned to the SQLi rules used by an OWASP Core Rule Set in a production environment.
Over the years, the project is expected to cover:
•	attack categories different from SQLi, for which the datasets will be provided in the initial stage of the project. Thismeans substantially collecting examples of attack instances to use in the learning process different from SQLi samples.
•	the code, script, or reference tools to run the process in a production environment. The components provided shall be such to allow one to run the optimization process against the real traffic incoming to the application and to deploy easily the ruleset produced as an outcome of the process in the production environment.
•	performance evaluation for the reference environments (i.e. the datasets made available by the project)
The project documentation will be progressively updated as the project evolves.
