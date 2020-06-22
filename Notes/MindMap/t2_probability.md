# Probability 

## Binomial Distribution  
- Like flip coin
  `\( P \left( X=x \right) = \frac{n!}{x! \left( n-x \right) !}p^{x} \left( 1-p \right) ^{n-x} \)`
- Code Func
    `np.random.randint()`
    `np.random.choice()`
    `np.random.binomial()` 
 
## Conditional probability 
- `\(P\left(A |B \right) = \frac{P(A\bigcap{B}) }{P(B)}\)`

## Bayes Rule 
- Review[[v1](https://www.youtube.com/watch?time_continue=85&v=b8M9CWxRyQ4&feature=emb_logo),[v2](https://www.youtube.com/watch?time_continue=10&v=aUFWZ2uJuBE&feature=emb_logo), [v3](https://www.youtube.com/watch?v=RgXQ8GRsjfc&feature=emb_logo), [v4](https://www.youtube.com/watch?time_continue=5&v=SdMk3aROgSc&feature=emb_logo)]
- **Total probability** rule 
  `\(P(A)=P(A∩B)+P(A∩ \bar B)\) `
  `\(\downarrow\)`
  `\(P(A)=P(A|B)P(B)+P(A|\bar B)P(\bar B)\)`
  `\(\downarrow\downarrow\downarrow\)`
  `\(P(A)=∑iP(A∩Bi)=∑iP(A|Bi)P(Bi)\)`

## Normal Distribution 
- Review[[v1](https://www.youtube.com/watch?time_continue=58&v=mQ_IjrtmmAk&feature=emb_logo), [v2](https://www.youtube.com/watch?time_continue=6&v=zqo1RJEHT_0&feature=emb_logo), [CLT](https://www.youtube.com/watch?time_continue=7&v=36KLIHioAvA&feature=emb_logo)]
- `\(f(x) = \frac{1}{\sqrt{2\pi\sigma^2}}e^\left[-\frac{\left(x-\mu \right)^2}{2\sigma^2}\right]\)`
