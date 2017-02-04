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


<div class="medium-12 medium-pull-12 columns" markdown="1">
## How to preserve users' _privacy_ while supporting _high-utility_ analytics for _low-latency_ stream processing?
</div>

<!-- ##### [Read more in our tech report -- "Privacy Preserving Stream Analytics: The Marriage of Randomized Response and Approximate Computing" --](https://arxiv.org/abs/1701.05403) <a href="https://arxiv.org/abs/1701.05403v1.pdf"><img class="t0" width="3%" src="/images/report-icon.png" alt=""></a> <a href="https://bitbucket.org/lequocdo/privapprox"><img class="t0" width="3%" src="/images/github-icon.png" alt=""></a> -->

<div class="medium-12 medium-pull-12 columns" markdown="1">
##### Read more in our technical report -- "Privacy Preserving Stream Analytics: The Marriage of Randomized Response and Approximate Computing" -- <a href="https://arxiv.org/abs/1701.05403v1.pdf"><img class="t0" width="2.5%" src="/images/report-icon.png" alt=""></a> <a href="http://dblp.uni-trier.de/rec/bibtex/journals/corr/QuocBBCFS17"><img class="t0" width="2.5%" src="/images/bibtex-icon.png" alt=""></a> <a href="https://bitbucket.org/lequocdo/privapprox"><img class="t0" width="2.5%" src="/images/github-icon.png" alt=""></a>
</div>

----------

<div style="text-align:center;" class="medium-12 medium-pull-12 columns" markdown="1">
<img class="t20" width="68%" src="{{ site.urlimg }}motivation.jpg" alt="System overview">
</div>

----------  

<div class="row">
<div class="large-4 columns" markdown="0">

    <div style="text-align:center;">
        <a href="/design/">
            <img class="t0" width="50%" src="/images/design-icon.png" alt="Design">
            <h4 style="text-align:center; margin: 0 0 0 0;">Design</h4>
        </a>
    </div>

</div>

<div class="large-4 columns" markdown="0">

    <div style="text-align:center;">
        <a href="/benchmarks/">
            <img class="t0" width="50%" src="/images/benchmark-icon.png" alt="Micro-bencharks Evaluation">
            <h4 style="text-align:center; margin: 0 0 0 0;">Micro-benchmarks</h4>
        </a>
    </div>

</div><!-- /.large-4.columns -->
<div class="large-4 columns" markdown="0">

    <div style="text-align:center;">
        <a href="/case-studies/">
            <img class="t0" width="50%" src="/images/casestudy-icon.png" alt="Case-study Evaluation">
            <h4 style="text-align:center; margin: 0 0 0 0;">Case-studies</h4>
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
