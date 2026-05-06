eseq2 analysis using ovarian cancer cell sample

![R](https://img.shields.io/badge/R-4.5.2-276DC3?style=flat&logo=r)
![DESeq2](https://img.shields.io/badge/DESeq2-Bioconductor-brightgreen)
![clusterProfiler](https://img.shields.io/badge/clusterProfiler-Bioconductor-yellow)
![DAVID](https://img.shields.io/badge/DAVID-NCBI-pink)
![Dataset](https://img.shields.io/badge/EBI-E--MTAB--9479-pink)


A complete Deseq2 analysis, GO enrichment and KEGG pathway analysis using RNA-seq datasets of OC samples were obtained from EBI (https://www.ebi.ac.uk/gxa/experiments/E-MTAB-9479/Experiment%20Design).  

---

## 🧬 Biological Question

> What happens to cell when they are given BMP treatment?

| | |
|---|---|
| **Dataset** | E-MTAB-9479 — Homo sapiens,ovarian cancer cell |
| **Comparison** | BMP treatment vs Control |
| **Key finding** | BMP induction caused upregulated ID family gene, which correlated bHLH inhibition leading to ovarian cancer|
| **Paper** |Fukuda et al., Cell Death Discovery 6, no. 1, 1033–1049, 2020 |

---

## Results

### Volcano Plot
![Volcano Plot](https://github.com/ashar200599/deseq-2-e-mtab-9479-ovarian-cancer/blob/046b763ca59fdd54478d72a1cc9f7e35b0d18dc1/file/plot/volcano_plot.png)

### Heatmap
![Heatmap](https://github.com/ashar200599/deseq-2-e-mtab-9479-ovarian-cancer/blob/046b763ca59fdd54478d72a1cc9f7e35b0d18dc1/file/plot/heatmap_top100.png)

### GO Biological Process (BP)
![GO BP](https://github.com/ashar200599/deseq-2-e-mtab-9479-ovarian-cancer/blob/046b763ca59fdd54478d72a1cc9f7e35b0d18dc1/file/plot/GO%20barplot_BP.png)

### GO Molecular Function (MF)
![GO MF](https://github.com/ashar200599/deseq-2-e-mtab-9479-ovarian-cancer/blob/046b763ca59fdd54478d72a1cc9f7e35b0d18dc1/file/plot/GO%20barplot_MF.png)

### GO Cellular Component (CC)
![GO CC](https://github.com/ashar200599/deseq-2-e-mtab-9479-ovarian-cancer/blob/046b763ca59fdd54478d72a1cc9f7e35b0d18dc1/file/plot/GO%20barplot_CC.png)

### KEGG plot
![KEGG](https://github.com/ashar200599/deseq-2-e-mtab-9479-ovarian-cancer/blob/046b763ca59fdd54478d72a1cc9f7e35b0d18dc1/file/plot/KEGG_barplot.png)



---

## 📁 Repository Structure

```

deseq-2-e-mtab-9479-ovarian-cancer/
│
├── README.md
│
├── files/                                  # Local analysis (run in RStudio)
│   ├── script/
|   |  ├── .RData
|   |  |── .Rhistory
|   |  |── deseq-2-e-mtab-9479-ovarian-cancer.RData
|   |  |── deseq-2-e-mtab-9479-ovarian-cancer.Rmd                  
│   ├── data/
│   │   ├── count_data_clean.csv             # Sample count
│   │   |── metadata_data_clean.csv          # Sample metadata
│   ├── results/
│   │   ├── DESeq2_results_BMP_vs_PBS.csv
│   │   ├── top100_upregulated_gene_result.csv
│   │   |── top100_downregulated_gene_result.csv
│   └── plots/
│       ├── volcano_plot.png
│       ├── heatmap_top100.png
│       ├── GO barplot_BP.png
|       |── GO barplot_MF.png 
|       |── GO barplot_CC.png 
|       |── KEGG_barplot.png
│   

```


---
## Methods
| Step | Tool | Details |
|---|---|---|
|Data Download| Manual | E-MTAB-9479 |
|Data Wrangling |Manual|BMP and PBS - treatment only |
|Differential Expression| DESeq2 | design=~treatment
|Low-count filtering | DESeq2 | ≥10 counts in all samples|
|Significance | Manual |padj < 0.05 AND |log2FoldChange| >= 1
|Gene Annotation | AnnotationDbi and org.Hs.eg.db | keytype = "ENSEMBL", column = "SYMBOL"
|Visualization| EnhancedVolcano, complexHeatmap | Volcano, heatmap
|GO Enrichment and KEGG pathways | clusterProfiler | Biological Process (BP), Molecular Function (MF), Cellular Component (CC)

---


