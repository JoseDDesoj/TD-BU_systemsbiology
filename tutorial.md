```{r}
Ecoli_genes  <- read.csv("Ecoli_gene_functional_annotations.csv", row.names = 1)
intersect(rownames(Dogma), Ecoli_genes$gene) -> keep

Ecoli_genes <- Ecoli_genes[Ecoli_genes$gene%in%keep,]
Dogma <- Dogma[rownames(Dogma)%in%keep,]

Ecoli_genes <- Ecoli_genes[match(rownames(Dogma), Ecoli_genes$gene),]

par(mar=c(3,20,3,3))
boxplot(log(Dogma$protein.concentration..Pi...1.µm3.)~Ecoli_genes$functional_category_desc,las=2, horizontal=T, ylab="")
abline(v=mean(log(Dogma$protein.concentration..Pi...1.µm3.), na.rm=T), lwd=2, col=2)
```

# Exploratory analysis of E coli gene and protein parameters
