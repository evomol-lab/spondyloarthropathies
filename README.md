# Inflammatory spondyloarthropathies
Scripts and pipelines to analyze DEGs in inflammatory spondyloarthropathies.

# MASTER'S DEGREE
# Common pathways and molecular signatures in ankylosing spondylitis and psoriatic arthritis: a systems biology perspective.
## Abstract
<div align="justify">
Spondyloarthropathies (SpA) comprise a heterogeneous group of chronic, autoimmune,
inflammatory rheumatic diseases with genetic predisposition and possible environmental and
psychological triggers. This study focuses on two main forms of SpA: ankylosing spondylitis
(AS) and psoriatic arthritis (PsA), which share clinical and immunopathological
manifestations and therapeutic strategies, but also have specific molecular characteristics.
Therefore, one main objective was to investigate the dysregulation of molecular pathways
and differential gene expression patterns in patients with AS and PsA in order to identify
genetic signatures, potential biomarkers, and biological processes that are common and
distinct between the two diseases. Based on text mining and functional enrichment screening,
3,660 genes associated with the pathologies were identified, of which 433 were common
between AS and PsA, representing a common core of biological relevance for SpA.
RNA-Seq data from the Gene Expression Omnibus (GEO) repository were used to perform
differential expression analyses, predict protein-protein interactions (PPI networks), and
reconstruct regulatory networks between transcription factors (TFs) and their target genes.
Data integration allowed the identification of central hubs (PPARG, FOS, STAT1, and
STAT3) and master regulators that have been little explored in the literature (FOXF2, MZF1,
and MAX::MYC), suggesting their role in disease pathogenesis. Common pathways were
identified, such as IL-17 and TNF, already well described in the literature, in addition to lipid
metabolism, recently highlighted in studies as a shared axis between the two diseases. These
results reinforce previous findings and broaden the understanding of spondyloarthropathies,
contributing to the identification of biomarkers and the development of more precise and
personalized therapeutic strategies.
</div>

## Introduction
Psoriatic arthritis (PsA) and ankylosing spondylitis (AS) are chronic inflammatory autoimmune diseases classified as seronegative spondyloarthropathies (SpA) due to the absence of rheumatoid factor. They share clinical, genetic, and immunological manifestations, but maintain specific characteristics. Both cause persistent inflammation, joint pain, stiffness, and can lead to significant structural damage, compromising functionality and quality of life. Therefore, early identification and appropriate treatment are essential.

Spondyloarthropathies, which include six diseases, predominantly affect the axial skeleton (spine and sacroiliac joints). Their common characteristics include association with the HLA-B27 genetic marker, the presence of enthesitis (inflammation at the insertions of tendons and ligaments), and extra-articular manifestations. Therapeutic management is multifaceted, starting with nonsteroidal anti-inflammatory drugs (NSAIDs) and progressing to disease-modifying antirheumatic drugs (DMARDs), immunosuppressants, and immunobiological therapies, in addition to physical therapy. This study selects APs and EA for their clinical relevance and interest in elucidating their distinct and shared molecular mechanisms to identify new therapeutic targets.

A Artrite Psoriásica (APs) é uma condição imunomediada frequentemente associada à psoríase cutânea. Caracteriza-se por inflamação sinovial e entesítica, podendo afetar articulações periféricas (muitas vezes de forma assimétrica) e o esqueleto axial. A patogênese envolve predisposição genética (alelos como HLA-B27 e HLA-C*06:02), desregulação imunológica (vias TNF-α, IL-17, IL-23) e gatilhos ambientais (infecções, traumas). Manifestações clínicas são heterogêneas, incluindo dactilite (inflamação difusa dos dedos), lesões ungueais (onicólise, pitting) e comorbidades como síndrome metabólica e uveíte. O diagnóstico utiliza os critérios CASPAR. O tratamento evoluiu significativamente, incluindo DMARDs convencionais (ex: metotrexato) e terapias biológicas avançadas (inibidores de TNF-α, anti-IL-17, anti-IL-23) e inibidores de JAK.

Ankylosing spondylitis (AS) primarily affects the spine and sacroiliac joints, resulting in chronic inflammatory low back pain (which worsens with rest and improves with activity) and stiffness, with a risk of progression to spinal fusion (ankylosis). The disease has a strong genetic association with HLA-B27 (present in 90-95% of patients). The pathogenesis is also mediated by cytokines such as TNF-α, IL-17, and IL-23. Extra-articular manifestations are common, notably anterior uveitis (up to 40% of cases), inflammatory bowel disease, and osteoporosis. The diagnosis combines clinical findings (inflammatory pain) and imaging findings (sacroiliitis on X-ray or early MRI) and inflammatory markers (CRP, ESR), although these are nonspecific.

The differentiation between PsA and AS is crucial. Both share the IL-23/IL-17 pathway and respond to NSAIDs, anti-TNF, and anti-IL-17. However, PsA has more frequent asymmetric peripheral involvement, dactylitis is common, and it responds well to conventional DMARDs and anti-IL-23 therapy. EA is predominantly axial, has a much stronger association with HLA-B27 (whose misfolding is a specific molecular mechanism), and its axial symptoms respond poorly to conventional DMARDs and do not respond adequately to IL-23 inhibition.

## Methodology
This study used a comparative genomic analysis methodology to investigate psoriatic arthritis (PsA) and ankylosing spondylitis (AS). The analytical workflow, illustrated in Figure 1, was designed to identify biomarkers and decipher common and distinct molecular mechanisms between the two diseases.

The first step consisted of systematic text mining. A bibliographic search was performed in the PubMed database, restricted to articles published between 2014 and 2024, which resulted in the selection of 150 relevant studies on PsA and AS. The genes mentioned in these articles were cataloged. This initial list was then refined and expanded using the Enrichr-KG platform and disease association libraries (such as DisGeNET, GeDiPNet_2023, and Disease Perturbations from GEO). This process, focused on positively and negatively regulated genes, ensured the selection of a robust and biologically relevant set of 433 genes shared between the two pathologies, even before the expression data analysis.

Next, transcriptomic data (RNA-Seq) were selected from public repositories (NCBI BioProject/GEO). Four datasets (GSE186063, GSE117769, GSE205748, GSE221786) were chosen based on criteria of clinical relevance, adequate sample size, and quality. These datasets included skin samples (lesional and non-lesional) and peripheral blood samples (PBMCs) from patients with APs, EA, and healthy controls. Notably, GSE221786 involved in vitro stimulation of PBMCs with CytoStim to activate the IL-17 pathway.

All computational analyses were performed in the R environment (v. 4.4.1). Raw RNA-Seq count matrices obtained from GEO were processed, normalized, and analyzed using packages such as GEOquery, DESeq2, and edgeR. The identification of differentially expressed genes (DEGs) was performed by applying strict statistical thresholds (adjusted p-value < 0.05 and Log2FoldChange > 1 or < -1).

With the list of DEGs, functional enrichment analyses were conducted to identify altered biological pathways and molecular processes, using the Gene Ontology (GO) and KEGG databases, through packages such as clusterProfiler, topGO, and pathview.

Subsequently, protein-protein interaction (PPI) networks were constructed using the DEGs and the STRING database, filtering for interactions with a moderate confidence score (threshold = 400). The topology of these networks was analyzed with visNetwork to identify “hub genes” — highly connected and functionally important nodes. The identification of hubs was based on centrality metrics, such as connectivity degree (number of interactions) and intermediation centrality (role of “bridge” in the network).

At the same time, a Gene Regulatory Network (GRN) was constructed to infer the control relationships between Transcription Factors (TFs) and their target genes, using databases such as TRRUST, ENCODE, and JASPAR2020. From the GRN, Master Regulators (MRs) were identified, defined as TFs whose regulatory activity impacts a significant number of DEGs (more than 5), suggesting a central role in coordinating the transcriptional response of the disease.

Finally, the results obtained for APs and EA (DEG profiles, enriched pathways, hub genes, and MRs) were integrated and compared. The objective of this comparative analysis was to highlight the common molecular mechanisms and distinctive characteristics of each disease, using visualization tools such as ggplot2 and visNetwork.
