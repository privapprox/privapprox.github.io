---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header: no
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
#callforaction:
#  url: https://tinyletter.com/feeling-responsive
#  text: Inform me about new updates and features ›
#  style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---

{% include mathjax_support %}

<div class="medium-12 medium-pull-12 columns" markdown="1">
## How to preserve users' _privacy_ while supporting _high-utility_ analytics for _low-latency_ stream processing?

$$\\\\$$

To answer this question: we describe the design, implementation and evaluation of PrivApprox, a data analytics system for privacy-preserving stream processing. PrivApprox provides three properties: _(i)_ $$\underline{Privacy}$$: zero-knowledge privacy guarantees for users, a privacy bound tighter than the state-of-the-art differential privacy; _(ii)_ $$\underline{Utility}$$: an interface for data analysts to systematically explore the trade-offs  between the output accuracy (with error-estimation) and query execution budget; _(iii)_ $$\underline{Latency}$$: near real-time stream processing based on a scalable "synchronization-free"  distributed architecture.

<div class="medium-12 medium-pull-12 columns" markdown="1">
<img class="t20" width="100%" src="{{ site.urlimg }}motivation.jpg" alt="System overview">
</div>

The key idea behind our approach is to marry two existing techniques together: namely, _sampling} (used in the context of approximate computing) and _randomized response_ (used in the context of privacy-preserving analytics). The resulting marriage is complementary---It achieves stronger privacy guarantees and also improved performance, a necessary ingredient for achieving low-latency stream analytics.
</div>

<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://www.youtube.com/embed/3b5zCFSmVvU" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>
