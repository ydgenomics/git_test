1. 我明明传参给了p1，但是还是自动打印生成了Rplots.pdf
```R
> p1 <- pheatmap(t(expr), scale="column",angle_col=90, cluster_rows = F,cluster_cols = T,show_colnames=T) # nolint
> dev.off()
null device 
          1
```
解决方案，设置`silent = TRUE`
```R
p1 <- pheatmap(t(expr), scale = "column", angle_col = 90, cluster_rows = FALSE, cluster_cols = TRUE, show_colnames = TRUE, silent = TRUE)`
```
