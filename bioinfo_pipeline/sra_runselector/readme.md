📥 **SRA RunSelector – NCBI Data Retrieval Tool**

🔎**What is SRA RunSelector?**

**SRA RunSelector**is a powerful web-based tool provided by the NCBI Sequence Read Archive (SRA) that allows researchers to search, filter, and download metadata and sequencing run information from publicly available studies.

It serves as the first step in any bioinformatics pipeline when working with NCBI-hosted next-generation sequencing (NGS) datasets.

⚙️ **Key Features**

Search by SRA Project Accession (SRP), BioProject (PRJNA), or Experiment
Input the study accession ID to retrieve all sequencing runs associated with it.

**Filter Samples by Metadata**

- Organism
- Library type (RNA-seq, WGS, Metagenome, etc.)
- Sequencing platform (Illumina, PacBio, Oxford Nanopore)
- Layout (Single-end / Paired-end)
- Study condition (disease/control, tissue type, etc.)
- **Download Metadata Tables**
- Export a customized CSV/TSV file containing all relevant run information (SRR IDs, experiment type, sequencing length, etc.).

**Batch Data Access**
Prepare a list of SRA Run IDs (SRR) for bulk download using prefetch, fasterq-dump, or other SRA Toolkit commands.
```
Use **fastq-dump** only if you have very limited storage or a small dataset.

Use **fasterq-dump** for speed and efficiency, especially in metagenomics or cancer genomics projects where datasets are huge.
```

The SRA RunSelector is the gateway to efficiently query, filter, and retrieve sequencing datasets from NCBI’s SRA, making it an essential tool for metagenomics, transcriptomics, and cancer genomics research.

📚 Reference
🔗 - [SRA RunSelector ](https://www.ncbi.nlm.nih.gov/Traces/study/)
📖 - [NCBI SRA Documentation](https://www.ncbi.nlm.nih.gov/sra)
