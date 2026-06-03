# Inflammatory spondyloarthropathies
Scripts and pipelines to analyze DEGs in inflammatory spondyloarthropathies.

# Beyond the Shared Inflammatory Axis: Differentiating Molecular Signatures in Psoriatic Arthritis and Ankylosing Spondylitis through Integrated Omics

This repository contains the source code, scripts, and analytical pipelines used to perform an integrative transcriptomic and systems biology analysis to differentiate the molecular mechanisms underlying **Ankylosing Spondylitis (AS)** and **Psoriatic Arthritis (PsA)**.

## 📄 Citation & Publications

If you use this code, the data pipelines, or findings in your research, please cite our work:

* **Preprint:** Gonçalves, L. C., Rodrigues-Neto, J. F., Gupta, S., de Souza, G. A., & Lima, J. P. M. S. (2026). Beyond the Shared Inflammatory Axis: Differentiating Molecular Signatures in Psoriatic Arthritis and Ankylosing Spondylitis through Integrated Omics. *bioRxiv*. [doi:10.1101/your-preprint-doi-here](https://doi.org/your-preprint-doi-here)
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


🚀 Getting Started & Requirements
The pipelines in this repository were developed using the R statistical computing environment.

Prerequisites
To replicate the analyses, make sure you have R (v4.0 or higher) installed along with the following mandatory packages:

R
# CRAN Packages
install.packages(c("tidyverse", "BiocManager", "ggplots", "igraph", "visNetwork", "pheatmap"))

# Bioconductor Packages
BiocManager::install(c("DESeq2", "clusterProfiler", "org.Hs.eg.db", "AnnotationDbi"))
Running the Analysis
Clone this repository to your local cluster or machine:

Bash
git clone [https://github.com/evomol-lab/spondyloarthropathies.git](https://github.com/evomol-lab/spondyloarthropathies.git)
cd spondyloarthropathies
Execute the script workflows sequentially inside your R console or RStudio environment to reproduce the statistical outputs and network configurations.

🤝 Institutional Support
This work was conducted at the Evolutionary Molecular Biology Laboratory (EvoMol-Lab) with computational infrastructure and technical support provided by:

BioME (Bioinformatics Multidisciplinary Environment) - IMD/UFRN

NPAD (High-Performance Computing Center) - UFRN

💰 Funding
This study was financed in part by the Coordenação de Aperfeiçoamento de Pessoal de Nível Superior - Brasil (CAPES) - Finance Code 001.

📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
