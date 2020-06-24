
## Set up 
- H0: assume to be true before we collect data 
- H1: what we want to prove to be true 
## Types of Error 
- Type I: FP choosing the `\(H_a\)` when `\(H_0\)` is true 
- Type II: FN
## P value 
- probability of observing data in favor of alternative 
  when`\(H_0\)` is true
- if  `\(p-val <= \alpha \)` then reject the null and choose alternative
## Alternative 
- get CI from boostrapping samples 
## Paradox 
- 1-when sample sizes are large, everything appears statistically 
significant (end up reject every null) but these results may not 
be practically significant 
- 2-when performing multiple hypothesis tests, the error will compound
  correction: Bonferroni correction `\(\frac{\alpha}{m}\)`