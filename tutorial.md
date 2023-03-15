Ecoli_genes  <- read.csv("Ecoli_gene_functional_annotations.csv", row.names = 1)
intersect(rownames(Dogma), Ecoli_genes$gene) -> keep


# Exploratory analysis of E coli gene and protein parameters
