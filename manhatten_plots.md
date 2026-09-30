---
title:  
layout: page
permalink: /coding_tutorials/manhatten_plots/
nav_exclude: true
---

## Manhatten Plots ##
### Background ###


### Data ###
I will be using data from a recent publication (here). This dataset contains population allele frequency estimates from independent strains of Fruit Flies. We want to ask  
Let's say we have a `data.frame` containing 100 randomly sampled minor allele frequency estimates from across the Fruit Fly genome:

Let's begin by taking a look at our data
```
> head(h_i_results.df)
          site  chrom      pos p.MvI_g100
        <char> <fctr>    <int>      <num>
1: 2L:10000016     2L 10000016 0.19003553
2: 2L:10000033     2L 10000033 0.18094568
3: 2L:10000089     2L 10000089 0.09474531
4: 2L:10000135     2L 10000135 0.05707835
5: 2L:10000234     2L 10000234 0.22296519
6: 2L:10000294     2L 10000294 0.06593546
```
To make a manhatten plot you need three key elements:
- some kind of scaffolding variable, in this case `chrom`
- some kind of positioning variable, in this case `pos`
- a metric you are plotting for each position, in this case a p-value comparing two groups

It is often the case that reference genomes do not automatically contain cumulative positions, that is the `pos` variable does not span chromosomes. Rather each chromosome ranges from position 1 to the length of that chromosome. To plot the positions properly however the plotting tool needs to know how to position the chromosomes themselves and then the positions relative to those chromosomes.

`ggplot2` and **R** order elements lexicographically. To override this we can specify a custom order by coercing the variable to a factor:
```r
h_i_results.df$chrom <- factor(h_i_results.df$chrom, levels = c("2L","2R","3L","3R","X", "4"))
```
We now need to change the chromosome-specific positions to be cumulative and span across all chromosomes
```r
data_cum <- h_i_results.df %>%
  group_by(chrom) %>%
  summarise(max_bp = max(pos)) %>%
  mutate(bp_add = lag(cumsum(max_bp), default = 0)) %>%
  select(chrom, max_bp, bp_add)
```
which gives us:
```
# A tibble: 6 × 3
  chrom   max_bp    bp_add
  <fct>    <int>     <int>
1 2L    23512951         0
2 2R    25283588  23512951
3 3L    28109694  48796539
4 3R    32073153  76906233
5 X     23538616 108979386
6 4      1296295 132518002
```
which we can follow with 
```r
# create bp_cum to results data frame by adding the position to bp_add
h_i_results.df <- h_i_results.df %>%
  inner_join(data_cum, by = "chrom") %>%
  mutate(bp_cum = pos + bp_add)
```
that results in 
```
          site  chrom      pos p.MvI_g100   max_bp bp_add   bp_cum
        <char> <fctr>    <int>      <num>    <int>  <int>    <int>
1: 2L:10000016     2L 10000016 0.19003553 23512951      0 10000016
2: 2L:10000033     2L 10000033 0.18094568 23512951      0 10000033
3: 2L:10000089     2L 10000089 0.09474531 23512951      0 10000089
4: 2L:10000135     2L 10000135 0.05707835 23512951      0 10000135
5: 2L:10000234     2L 10000234 0.22296519 23512951      0 10000234
6: 2L:10000294     2L 10000294 0.06593546 23512951      0 10000294
```
We can then set the chromosome labels to be at the midpoint of each chromosome
```r
axis_set <- data_cum %>%
  mutate(center = bp_add + max_bp/2)
```


![alt text]({{ "/assets/images/manhatten_plot.png" | relative_url }})
``` r

```