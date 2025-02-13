---
layout: page
title: Indexing for Near-Sorted Data
description: An Indexing Framework to harness data sortedness
img: assets/img/read-write-tradeoff.jpg
importance: 1
category: work
---

Indexing in data systems can be perceived as the process of adding structure to the incoming, otherwise unsorted data. If the data ingestion order matches the indexed attribute order, the indexing effort is redundant and can be avoided altogether. We identify <i><b>sortedness</b></i> as a resource that can accelerate index ingestion, and propose a new sortedness-aware paradigm, <b>SWARE</b>, that pays less indexing cost for near-sorted data. This framework can be applied to any tree-based index!

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/read-write-tradeoff.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/w-opt-tree.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
State-of-the-art indexing and data organization techniques pay a higher
write cost in order to store data as sorted (or, in general, more organized) and offer efficient reads. Since the goal of indexing is to store the data as sorted, we ideally expect that ingesting near-sorted data would be more efficient, which is not the case. The SWARE meta-design offers better performance as data exhibit higher degree of sortedness.
</div>

We apply SWARE to two state-of-the-art search trees: <b>B<sup>+</sup>-tree</b> and <b>B<sup>&epsilon;</sup>-tree</b> to create their sortedness-aware counterparts, i.e., <b><i>SA</i>-B<sup>+</sup>-tree</b> and <b><i>SA</i>-B<sup>&epsilon;</sup>-tree</b> that offer between 1.3&times; - 5&times; benefit for mixed read/write workloads with near-sorted data.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/mixed.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
     <b><i>SA</i>-B<sup>+</sup>-tree</b> is efficient with reasonable data
sortedness for any read-write ratio.
</div>
