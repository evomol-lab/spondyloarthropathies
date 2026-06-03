# Inflammatory spondyloarthropathies
Scripts and pipelines to analyze DEGs in inflammatory spondyloarthropathies.

# Beyond the Shared Inflammatory Axis: Differentiating Molecular Signatures in Psoriatic Arthritis and Ankylosing Spondylitis through Integrated Omics

This repository contains the source code, scripts, and analytical pipelines used to perform an integrative transcriptomic and systems biology analysis to differentiate the molecular mechanisms underlying **Ankylosing Spondylitis (AS)** and **Psoriatic Arthritis (PsA)**.

## 📄 Citation & Publications

If you use this code, the data pipelines, or findings in your research, please cite our work:

* **Preprint:** Gonçalves, L. C., Rodrigues-Neto, J. F., Gupta, S., de Souza, G. A., & Lima, J. P. M. S. (2026). Beyond the Shared Inflammatory Axis: Differentiating Molecular Signatures in Psoriatic Arthritis and Ankylosing Spondylitis through Integrated Omics. *bioRxiv*. (https://www.biorxiv.org/content/10.1101/2025.08.20.671331v1)
* **Peer-Reviewed Article:** Gonçalves, L. C., Rodrigues-Neto, J. F., Gupta, S., de Souza, G. A., & Lima, J. P. M. S. (2026). Beyond the Shared Inflammatory Axis: Differentiating Molecular Signatures in Psoriatic Arthritis and Ankylosing Spondylitis through Integrated Omics. ***Genes & Diseases*** (In Press).

---

## 🔬 Project Overview

Spondyloarthropathies (SpA), such as AS and PsA, present significant clinical and immunological overlaps, frequently confounding precise molecular differentiation. This study leverages a multi-dataset, integrated transcriptomic approach combined with scientific text mining, network biology, and transcription factor regulon modeling to uncover specific hub genes and distinct regulatory circuits unique to each pathology.

### Key Workflows Implemented:
1.  **Data Retrieval & Curation:** Integration of public RNA-Seq datasets from NCBI Gene Expression Omnibus (GEO): `GSE186063`, `GSE117769`, `GSE205748`, and `GSE221786`.
2.  **Scientific Text Mining & Biological Filtering:** Curation of a refined list of 433 candidate disease-associated genes.
3.  **Differential Gene Expression Analysis (DEG):** Benchmarking transcriptome profiles across patient cohorts.
4.  **Protein-Protein Interaction (PPI) Networks:** Reconstruction of topological functional modules and identification of regulatory hub proteins.
5.  **Transcription Factor (TF) Regulon Modeling:** System-level evaluation of master regulators driving distinct transcriptional signatures.

---

## 🛠️ Repository Structure

```text
├── data/                  # Metadata and curated gene lists (e.g., the 433-gene core list)
├── scripts/               # R scripts organized by analytical steps
│   ├── 01_deg_analysis.R   # Differential expression analysis pipelines
│   ├── 02_enrichment.R     # Functional enrichment analysis (GO and KEGG)
│   └── 03_ppi_network.R   # Network construction and topological analysis
├── plots/                 # Output figures (Heatmaps, Network Diagrams, Volcano plots)
└── README.md              # Project documentation
```

## 🚀 Getting Started & Requirements

The pipelines in this repository were developed using the R statistical computing environment.

## Prerequisites

To replicate the analyses, make sure you have R (v4.0 or higher) installed along with the following mandatory packages:

R
```
# CRAN Packages
install.packages(c("tidyverse", "BiocManager", "ggplots", "igraph", "visNetwork", "pheatmap"))

# Bioconductor Packages
BiocManager::install(c("DESeq2", "GEOquery", "clusterProfiler", "org.Hs.eg.db", "AnnotationDbi"))
```

Execute the script workflows sequentially inside your R console or RStudio environment to reproduce the statistical outputs and network configurations.

## 🤝 Institutional Support

This work was conducted at the Evolutionary Molecular Biology Laboratory (EvoMol-Lab) with computational infrastructure and technical support provided by:

BioME (Bioinformatics Multidisciplinary Environment) - IMD/UFRN

NPAD (High-Performance Computing Center) - UFRN

## 💰 Funding

This study was financed in part by the Coordenação de Aperfeiçoamento de Pessoal de Nível Superior - Brasil (CAPES) - Finance Code 001.

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📚 References

- Almende, et al. (2024). visNetwork: Network Visualization using 'vis.js' Library. R package version 2.1.3.
- Carlson, M. (2024). org.Hs.eg.db: Genome wide annotation for Human. R package version 3.19.0.
- Carlson, M. (2024). TxDb.Hsapiens.UCSC.hg38.knownGene: Annotation package for TxDb object(s). R package version 3.20.0.
- Davis, S., & Meltzer, P. S. (2007). GEOquery: a bridge between the Gene Expression Omnibus (GEO) and BioConductor. Bioinformatics, 23(14), 1846-1847.
- Deng, J., Leijten, E., Nordkamp, M. O., Zheng, G., et al. (2022). Multi-omics integration reveals a core network involved in host defence and hyperkeratinization in psoriasis. Clinical and Translational Medicine, 12(12), e976. https://doi.org/10.1002/ctm2.976.
- Gene Ontology Consortium. (2021). The Gene Ontology resource: enriching a GO for gene product annotation. Nucleic Acids Research, 49(D1), D325-D334.
- Johnsson, H., Cole, J., Siebert, S., McInnes, I. B., et al. (2023). Cutaneous lesions in psoriatic arthritis are enriched in chemokine transcriptomic pathways. Arthritis Research & Therapy, 25(1), 73. https://doi.org/10.1186/s13075-023-03086-z.
- Johnsson, H., Cole, J., McInnes, I. B., Graham, G., et al. (2024). Differences in transcriptional changes in psoriasis and psoriatic arthritis skin with immunoglobulin gene enrichment in psoriatic arthritis. Rheumatology (Oxford), 63(1), 218–225. https://doi.org/10.1093/rheumatology/kead226.
- Kanehisa, M., Furumichi, M., & Tanabe, M. (2023). KEGG: Kyoto Encyclopedia of Genes and Genomes. Nucleic Acids Research, 51(D1), D587-D594.
- KEGG. (2024). Kyoto Encyclopedia of Genes and Genomes.
- Lawrence, M., et al. (2013). GenomicRanges: an R package for manipulating genomic intervals, features and alignments. Bioinformatics, 29(15), 1845-1846.
- Lee, C., Chan, E. R., Schueller, D., Breitman, M., Haghiac, M., & Magrey, M. (2023). RNA-Seq of PBMCs from patients with axial spondyloarthritis and healthy controls treated with IL-17 (GSE221786).
- Lou, S., & Brouwer, K. L. (2013). pathview: an R/Bioconductor package for pathway based data integration and visualization. Bioinformatics, 29(1), 181-182.
- Love, M. I., Huber, W., & Anders, S. (2014). Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2. Genome Biology, 15(12), 550.
- Gene Expression Omnibus, NCBI. https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE221786.
- Pedersen, T. L. (2022). ggraph: An Implementation of Grammar of Graphics for Graphs and Networks. R package version 2.1.0.
- Robinson, M. D., McCarthy, D. J., & Smyth, G. K. (2010). edgeR: a Bioconductor package for differential expression analysis of digital gene expression data. Bioinformatics, 26(1), 139-140.
- Szklarczyk, D., et al. (2021). The STRING database in 2021: genome-wide protein–protein interaction networks and functional enrichment analyses. Nucleic Acids Research, 49(D1), D789-D796.
- Tenenbaum, D. (2024). KEGGREST: Client-side REST access to KEGG. R package version 1.44.0.
- Wickham, H. (2016). ggplot2: Elegant Graphics for Data Analysis. Springer-Verlag New York.
- Wickham, H., et al. (2023). dplyr: A Grammar of Data Manipulation. R package version 1.1.4.
- Xu, H., et al. (2021). Osteopontin in autoimmune diseases. International Journal of Molecular Sciences, 22(19), 10567.
- Yu, G., Wang, L. G., Han, Y., & He, Q. Y. (2012). clusterProfiler: an R package for comparing biological themes among gene clusters. OMICS: A Journal of Integrative Biology, 16(5), 284-287.
- Zhang, L., & Li, Z. (2019). RNA-Seq of peripheral blood mononuclear cells from psoriatic arthritis patients and healthy controls (GSE117769). Gene Expression Omnibus. https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE117769.
  

