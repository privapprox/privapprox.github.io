---
layout: page-fullwidth
show_meta: false
title: "Micro-benchmarks Evaluation"
subheadline:
teaser:
header: no
permalink: "/benchmarks/"
---

<div class="row">
<div class="medium-4 medium-push-8 columns" markdown="1">
<div class="panel radius" markdown="1">
**Table of Contents**
{: #toc }
*  TOC
{:toc}
</div>
</div><!-- /.medium-4.columns -->

{% include mathjax_support %}
<div class="medium-8 medium-pull-4 columns" markdown="1">

We evaluate PrivApprox using a series of microbenchmarks. For all microbenchmark measurements, we report the average over $100$ runs.

## Results

### Effect of sampling and randomization parameters

We first measure the effect of randomization parameters on the utility and privacy guarantee of the query results.  In particular, the utility is measured by the query result's accuracy loss _(<a href="https://privapprox.github.io/design/#step-ii-answering-queries-at-clients">Equation 3</a>)_, and privacy is measured by the level of achieved zero-knowledge privacy _(Theorem C.4. in the <a href="https://arxiv.org/abs/1701.05403">technical report</a>)_. For the experiment, we generated $10,000$ original answers randomly, 60% of which are "Yes" answers.

_Table 1_ shows that different settings of the two randomization parameters, $p$ and $q$, do affect the utility and the privacy guarantee of the query results.  The higher $p$ means the higher probability that a client responds with its truthful answer.  As expected, this leads to higher utility (i.e., smaller accuracy loss $\eta$) but weaker privacy guarantee (i.e., higher privacy level $\epsilon$).  In addition, _Table 1_ also shows that the closer we set the probability $q$ to the fraction of truthful "Yes" answers (i.e., $60%$ in this microbenchmark), the higher utility the query result provides. Nevertheless, to meet the utility and privacy requirements in various scenarios, we should carefully choose the appropriate $p$ and $q$.
</div>

<div class="medium-12 medium-pull-12 columns" markdown="1">
|p    |q    | Accuracy loss ($\eta$)| Privacy level ($\epsilon$) |
|----:|----:|------:|------:|
|0.3  |0.3  |0.0278 |1.7047 |
|0.3  |0.6  |0.0262 |1.3862 |
|0.3  |0.9  |0.0268 |1.2527 |
|0.6  |0.3  |0.0141 |2.5649 |
|0.6  |0.6  |0.0128 |2.0476 |
|0.6  |0.9  |0.0136 |1.7917 |
|0.9  |0.3  | 0.1036| 4.1820|
|0.9  |0.6  |0.0079 |3.5263 |
|0.9  |0.9  |0.0102 |3.1570 |
|=====|=====|=======|=======|

***Table 1: Utility and privacy of query results with different randomization parameters $p$ and $q$.***

We also measured the effect of sampling parameter on the accuracy loss. _Figure 1 (a)_ shows that the accuracy loss decreases with the increase in sampling fraction, regardless of the settings of randomization parameters $p$ and $q$.  The benefits reach diminishing returns after  $80%$ sampling fraction.

<div class="medium-12 medium-pull-12 columns" markdown="1">
 <img class="t20" width="100%" src="{{ site.urlimg }}micro-benchmark1.png" alt="micro-benchmarks">
</div>

***Figure 1: (a) Accuracy loss with varying sampling and randomization parameters. (b) Error estimation during the randomized response process and sampling process, combined and individually. (c) Accuracy loss with varying # of clients.***

### Error estimation

To analyze the accuracy loss, we first separately measured the accuracy loss caused by running, _individually_, the sampling  process and the randomized response process. For the comparison, secondly, we also computed the total accuracy loss after running the two processes in succession as in PrivApprox. For the experiment, we set he number of original answers to $10,000$ with $60%$ of which being "Yes" answers. We compute the accuracy loss of the randomized response process separately by setting the sampling parameter to $100%$ ($s = 1$) and the randomized response parameters $p$ and $q$ to $0.3$ and $0.6$, respectively. Meanwhile, we measure the accuracy loss of the sampling process without the randomized response process by setting $p$ to $1$.  

_Figure 1 (b)_ represents that the accuracy loss during the two experiments is statistically independent to each other. In addition, the accuracy loss of the two processes can effectively be added together to calculate the total accuracy loss.


### Effect of the number of clients
We next analyzed how the number of participating clients affects the utility of the results.  For the experiment, we fix the sampling and randomization parameters $s$, $p$ and $q$ to $0.9$, $0.9$ and $0.6$, respectively, and set the fraction of truthful "Yes" answers to $60%$.  

_Figure 1 (c)_ shows that the utility of query results improves with the increase in the number of participating clients, and few clients (e.g., $<100$) may lead to low-utility query results.

### Effect of the fraction of truthful answers
We also measured the utility of both the native and the inverse query results with different fractions of truthful "Yes" answers.  For the experiment, we still keep the sampling and randomization parameters $s$, $p$ and $q$ to $0.9$, $0.9$ and $0.6$, respectively, and set the total number of answers to $10,000$.  

_Figure 2 (a)_ shows that PrivApprox achieves higher utility as the fraction of truthful "Yes" answers gets closer to $60$% (i.e., the $q$ value). In addition, when
the fraction of "Yes" truthful answers $y$ is too small compared to the $q$ value (e.g., $y = 0.1$), the accuracy loss is ($2.54$%). However, by using the query inversion mechanism _(see §3.3.3 in the <a href="https://arxiv.org/abs/1701.05403">technical report</a>)_, we can significantly reduce  the accuracy loss ($0.4$%).

<div class="medium-12 medium-pull-12 columns" markdown="1">
 <img class="t20" width="100%" src="{{ site.urlimg }}micro-benchmark2.png" alt="micro-benchmarks">
</div>

### Effect of answer's bit-vector sizes

We also measured the throughput at proxies with various sizes for the bit-vector of client answers _(<a href="https://privapprox.github.io/design/#submitting-queries">$A[n]$ </a>)_. We conducted this experiment with a $3$-node cluster. _Figure 2 (b)_ shows that the throughput, as expected, is inversely proportional to the answer's bit-vector sizes.

### Effect of stratified sampling

To illustrate the use of stratified sampling, we generated a synthetic data stream with three different stream sources $S_1$, $S_2$, $S_3$. Each stream source is created with an independent Poisson distribution. In addition, the three stream sources have an arrival rate of $3:4:5$ data items per time unit, respectively. The computation window size is fixed to $10,000$ data items.

_Figure 2 (c)_ shows the average number of selected items of each stream source with varying sample fractions using the stratified sampling mechanism.  As expected, the average number of sampled data items from each stream source is proportional to its arrival rate and the sample fractions.


### Computational overhead of crypto operations

We also compared the computational overhead of crypto operations used in PrivApprox and prior systems.  In particular, these crypto operations are XOR in PrivApprox, _<a href="http://dl.acm.org/citation.cfm?id=2382268"> RSA</a>_, _<a href="http://dl.acm.org/citation.cfm?id=2228316">Goldwasser-Micali </a>_, and _<a href="http://dl.acm.org/citation.cfm?id=1807247">Paillier </a>_. For the experiment, we measured the number of crypto operations that can be executed on: _(i)_ Android Galaxy mini III smartphone running Android 4.1.2 with a 1.5 GHz CPU; _(ii)_ MacBook Air laptop with a 2.2 GHz Intel Core i7 CPU running OS X Yosemite 10.10.2; and _(iii)_ Linux server running Linux 3.15.0 equipped with a 2.2 GHz CPU with 32 cores.

_Table 2_ shows that the XOR operation is extremely efficient compared with the other crypto mechanisms. This highlights the importance XOR encryption for our system design.

|            |||            Encryption               |||||||              Decryption              |
|            |     Phone     ||     Laptop     ||    Server     ||     Phone     | |    Laptop     |  |   Server     ||
|------------
|     RSA    | 937 | 16$\times$ | 2,770 | 341$\times$  | 4,909 |  275$\times$  |  126  |  25890$\times$  |  698  |  23666$\times$  |  859  |   26401$\times$  |  
| Goldwasser | 2,106 | 7$\times$ | 17,064 |  55$\times$  | 22,902 |  59$\times$  |  127  |  25686$\times$  |  6,329  |  2610$\times$  |  7,068  |  3209$\times$  |
|  Paillier  | 116  |  129$\times$  |  489  |  1930$\times$  |  579  | 2335$\times$  |  72  |  45308$\times$  |  250  |  66076$\times$  |  309  |  73392$\times$  |
| PRIVAPPROX |   15,026   ||  943,902 ||   1,351,937    ||    3,262,186    ||    16,519,076    ||     22,678,285    ||
|============

***Table 2: Comparison of crypto overheads (# operations/sec). The public-key crypto schemes use a 1024-bit key.***

### Throughput at clients

We also measured throughput at clients. In particular, we measured the number of operations per second that can be executed at clients for the query answering process. For this experiment, we used the same set of devices as in the previous experiment.

_Table 3_ presents the throughput at clients. To further investigate the overheads, we measured the individual throughput of three sub-processes in the query answering process: _(i)_ database read, _(ii)_ randomized response, and _(iii)_ XOR encryption. The result indicates that the performance bottleneck in the answering process is actually the database read operation.

|No. of operations/sec| Phone | Laptop | Server |
|-------------------
|SQLite read| 1,162 | 19,646 | 23,418 |
|Randomized response| 168,938 | 418,668 | 1,809,662|
|XOR encryption| 15,026 | 943,902 | 1,351,937 |
|Total| 1,116 | 17,236 | 22,026|
|===================

***Table 3: Throughput (# operations/sec) at clients.***
