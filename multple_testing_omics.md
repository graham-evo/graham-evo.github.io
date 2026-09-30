---
title:  
layout: page
permalink: /coding_tutorials/multiple_testing/
nav_exclude: true
---

## Multiple Testing ##
### Background ###
In the age of *omics scale data, we are often confronted with massive datasets. In the context of association studies someone might be interested in scanning the genome for genes, regions, loci, etc. associated with a trait.

Statistically, we can figure out if a genomic location is associated with a particular trait by conducting a hypothesis test. A hypothesis test gives a probability or **p-value**. p-values are a contentious topic, but definitionally, a p-value is just the probability that our test gives us a false positive - or in other words - the chance of falsely rejecting null hypothesis when it is actually true. Our test says there an effect when there really wasn't one.

Scientists generally accept a threshold of 0.05, or a 5% significance level to say there is an effect, accepting that 5% of the time they might be wrong.

This isn't the case when conducting many hypothesis tests, as in hundreds, to *thousands*, to even *millions* of hypothesis tests in the context of omics data because the probability that you will actually observe a false positive accumulates when more tests are conducted.

| Number of tests | Expected false positives |
| --------------- | ------------------------ |
| 1               | 0.05                     |
| 20              | 1                        |
| 100             | 5                        |
| 10,000          | 500                      |

You can see how this becomes a real issue when the number of tests gets extremely large.

There are a number of ways to deal with this but first let's fit a model and generate some test statistics and p-values.

### Model ###
I will be using data from a recent publication (here). This dataset contains population allele frequency estimates from independent strains of Fruit Flies. We want to ask  
Let's say we have a `data.frame` containing 100 randomly sampled minor allele frequency estimates from across the Fruit Fly genome:
```

```
``` r

```