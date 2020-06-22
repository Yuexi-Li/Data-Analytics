# Practical Statistics 
**Outline**
<ul>
<li><a href="#L1">Descriptive Statistics</a></li>
<li><a href="#L2">Probability</a></li>
<li><a href="#L3">Probability</a></li>

****

<a id='L1'></a>
## Descriptive Statistics
Descriptive Statistics is about describing our collected data. 
- mindmap as below ([Link](Notes/MindMap/t1_descriptvie_statictics.html)) 

![mindmap_descriptive](Pics/mindmap_descriptive_statistics.jpeg)
****

<a id='L2'></a>
## Probability
- mindmap as below ([Link](Notes/MindMap/t2_probability.html)) 
![mindmap_probability](Pics/mindmap_probability.png)

**Additional**
- porbability generator: 
  - 1M test of three fair coin `np.random.randint(2, size=(int(1e6), 3))` 
  - 1M test of 3 unfaired coin `np.random.choice([0, 1], size=(int(1e6), 3), p=[0.6, 0.4])`
  * **Binomial Generator** each number of the results represents for the number of heads that resulted from each test of 10 coin flips. `np.random.binomial(n = 10, p = 0.5, size =20)` 

- Bayes rule  ([v1](https://www.youtube.com/watch?time_continue=85&v=b8M9CWxRyQ4&feature=emb_logo),[v2](https://www.youtube.com/watch?time_continue=10&v=aUFWZ2uJuBE&feature=emb_logo), [v3](https://www.youtube.com/watch?v=RgXQ8GRsjfc&feature=emb_logo), [v4](https://www.youtube.com/watch?time_continue=5&v=SdMk3aROgSc&feature=emb_logo))

- Normal Distribution ([v1](https://www.youtube.com/watch?time_continue=58&v=mQ_IjrtmmAk&feature=emb_logo), [v2](https://www.youtube.com/watch?time_continue=6&v=zqo1RJEHT_0&feature=emb_logo), [CLT](https://www.youtube.com/watch?time_continue=7&v=36KLIHioAvA&feature=emb_logo))

****
<a id='L3'></a>
## 