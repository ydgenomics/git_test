## 1. 我明明传参给了p1，但是还是自动打印生成了Rplots.pdf
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

## 2. 2023年Seurat v4更新到v5，可以使用“矩阵替换”的方法Debug
```R
#convert a v5 assay to a v3/v4 assay
SRR780_object[['RNA']] = as(object = SRR780_object[['RNA']], Class = "Assay") 
# convert a v3/4 assay to a v5 assay
SRR780_object[['RNA']] = as(object = SRR780_object[['RNA']], Class = "Assay5")
```
