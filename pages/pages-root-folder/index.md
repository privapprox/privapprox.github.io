---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
#layout: page-fullwidth
show_meta: false
header: no
subheadline:
teaser:
permalink: /index.html
homepage: true
---

{% include mathjax_support %}

<div class="row">
<div class="large-6 large-push-3 columns" markdown="0">

    <h1 id="privapprox" style="text-align:center; margin-bottom: 2pt;">PrivApprox</h1>
    <h4 style="text-align:center; color: #333;">Privacy-Preserving Stream Analytics</h4>
<br>

</div>
</div>

<!-- <div style="text-align:center;" class="medium-12 medium-pull-12 columns" markdown="1">
## PrivApprox: Privacy-Preserving Stream Analytics
</div> -->

<!-- ##### [Read more in our tech report -- "Privacy Preserving Stream Analytics: The Marriage of Randomized Response and Approximate Computing" --](https://arxiv.org/abs/1701.05403) <a href="https://arxiv.org/abs/1701.05403v1.pdf"><img class="t0" width="3%" src="/images/report-icon.png" alt=""></a> <a href="https://bitbucket.org/lequocdo/privapprox"><img class="t0" width="3%" src="/images/github-icon.png" alt=""></a> -->

<div class="row">
<div class="large-4 columns" markdown="0" display="inline;">
    <div style="text-align:center;">
        <a href="https://arxiv.org/abs/1701.05403v1.pdf">
            <img class="t0" width="8%" src="/images/report-icon.png" alt="Technical report">
            <div style="text-align:center; margin: 0 0 0 0;">Technical report</div>
        </a>
    </div>    

</div>    

<div class="large-4 columns" markdown="0" display="inline;">
    <div style="text-align:center;">
        <a href="http://dblp.uni-trier.de/rec/bibtex/journals/corr/QuocBBCFS17">
            <img class="t0" width="8%" src="/images/bibtex-icon.png" alt="Bibtex">
            <div style="text-align:center; margin: 0 0 0 0;">BibTex</div>
        </a>
   </div>      
</div>

<div class="large-4 columns" markdown="0" display="inline;">

    <div style="text-align:center;">
        <a href="https://bitbucket.org/lequocdo/privapprox">
            <img class="t0" width="8%" src="/images/github-icon.png" alt="Source code">
            <div style="text-align:center; margin: 0 0 0 0;">Source code</div>
        </a>
    </div>

</div>    
</div>

<!-- <div style="text-align:center;" class="medium-12 medium-pull-12 columns" markdown="1">
<a href="https://arxiv.org/abs/1701.05403v1.pdf"><img class="t0" width="3.6%" src="/images/report-icon.png" alt=""></a> <a href="http://dblp.uni-trier.de/rec/bibtex/journals/corr/QuocBBCFS17"><img class="t0" width="3.6%" src="/images/bibtex-icon.png" alt=""></a> <a href="https://bitbucket.org/lequocdo/privapprox"><img class="t0" width="3.6%" src="/images/github-icon.png" alt=""></a>
</div> -->

----------
<!-- <div class="medium-12 medium-pull-12 columns" markdown="1"> -->
<h2 style="text-align:center; margin-top: 0; margin-bottom: 1em; font-size: 1.2em;"> How to preserve users' <i>privacy</i> while supporting <i>high-utility</i> analytics for <i>low-latency</i> stream processing? </h2>


<div style="text-align:center;" class="medium-12 medium-pull-12 columns" markdown="1">
<img class="t20" width="68%" src="{{ site.urlimg }}motivation.jpg" alt="System overview">
</div>

----------
<h2 style="text-align:center; margin-top: 0; margin-bottom: 1em; font-size: 1.2em;">Looking for more information?</h2>
<!-- <div class="medium-12 medium-pull-12 columns" markdown="1">
#### Looking for more information?
</div> -->

<div class="row">
<div class="large-3 columns" markdown="0">

    <div style="text-align:center;">
        <a href="/design/">
            <img class="t0" width="50%" src="/images/design-icon.png" alt="Design">
            <h4 style="text-align:center; margin: 0 0 0 0;">Design</h4>
        </a>
    </div>

</div>

<div class="large-3 columns" markdown="0">

    <div style="text-align:center;">
        <a href="/benchmarks/">
            <img class="t0" width="50%" src="/images/benchmark-icon.png" alt="Micro-bencharks Evaluation">
            <h4 style="text-align:center; margin: 0 0 0 0;">Micro-benchmarks</h4>
        </a>
    </div>

</div><!-- /.large-4.columns -->
<div class="large-3 columns" markdown="0">

    <div style="text-align:center;">
        <a href="/case-studies/">
            <img class="t0" width="50%" src="/images/casestudy-icon.png" alt="Case-study Evaluation">
            <h4 style="text-align:center; margin: 0 0 0 0;">Case-studies</h4>
        </a>
    </div>

</div>
<div class="large-3 columns" markdown="0">

    <div style="text-align:center;">
        <a href="/proofs/">
            <img class="t0" width="50%" src="/images/proof-icon.png" alt="Proofs">
            <h4 style="text-align:center; margin: 0 0 0 0;">Proofs</h4>
        </a>
    </div>

</div>
</div>
--------





<!-- * <a href="https://privapprox.github.io/design/">Design</a>

* <a href="https://privapprox.github.io/benchmarks/">Micro-bencharks evaluation</a>

* <a href="https://privapprox.github.io/case-studies/">Case-studies evaluation</a>

* <a href="https://arxiv.org/abs/1701.05403">Read more in our tech report</a>

* <a href="https://bitbucket.org/lequocdo/privapprox" class="icon-github">  Source code</a> -->

<!-- To answer this question: we describe the design, implementation and evaluation of PrivApprox, a data analytics system for privacy-preserving stream processing. PrivApprox provides three properties: _(i)_ $$\underline{Privacy}$$: zero-knowledge privacy guarantees for users, a privacy bound tighter than the state-of-the-art differential privacy; _(ii)_ $$\underline{Utility}$$: an interface for data analysts to systematically explore the trade-offs  between the output accuracy (with error-estimation) and query execution budget; _(iii)_ $$\underline{Latency}$$: near real-time stream processing based on a scalable "synchronization-free"  distributed architecture.

<div class="medium-12 medium-pull-12 columns" markdown="1">
<img class="t20" width="100%" src="{{ site.urlimg }}motivation.jpg" alt="System overview">
</div>

The key idea behind our approach is to marry two existing techniques together: namely, _sampling_ (used in the context of approximate computing) and _randomized response_ (used in the context of privacy-preserving analytics). The resulting marriage is complementary---It achieves stronger privacy guarantees and also improved performance, a necessary ingredient for achieving low-latency stream analytics.
</div> -->

<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://www.youtube.com/embed/3b5zCFSmVvU" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>
