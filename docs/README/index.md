---
layout: default
title: Read me
nav_order: 2
---
<a target="_blank" href="https://colab.research.google.com/github/luquelab/bioinformatics_mice_microbes/blob/main/notebooks/main_pipeline.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>


Bioinformatics Group Project: Protein Sequence Analysis Pipeline
================================================================

This project performs comprehensive analysis on a set of DNA sequences. It includes sequence property exploration, translation to protein, multiple and pairwise alignments, phylogenetic tree construction, and BLAST functional annotation.

A tutorial can be found [here](https://luquelab.github.io/bioinformatics_mice_microbes/tutorial/).

Project Overview
----------------

This pipeline, written in Python and run via Google Colab, processes input DNA sequences (.fna) to explore their properties and translate them into protein sequences. It then performs various bioinformatics analyses including:

- GC content and sequence length visualization
- Translation to proteins
- Multiple sequence alignment (MSA) using Clustal Omega
- Sequence conservation analysis
- Pairwise similarity and clustering
- Phylogenetic tree generation
- Functional annotation via BLAST

Dependencies
------------

Ensure the following packages are installed:

pip install biopython matplotlib numpy scipy pandas seaborn
apt-get install -y clustalo

Steps in the Pipeline
---------------------

1. Data Preparation

- Input: sequences.fna (FASTA format)
- Parsing: Using Biopython to load sequences
- Verification: Displays sequence ID, length, and snippet

2. Sequence Properties

- GC Content:
  - Calculated per sequence
  - Bar plot (gc_contents.png)
- Sequence Length:
  - Measured in base pairs
  - Bar plot (lengths.png)
- Summary Output:
  - CSV with Sequence ID, GC Content, Length (bp)
  - Combined DataFrame visualizations (distribution_lengths_GC.png)

3. Protein Translation

- Translates nucleotide sequences to protein using Biopython
- Saves results in protein_sequences.fasta and temp_proteins.fasta

4. Sequence Alignment and Conservation

- MSA via Clustal Omega
  - Input: temp_proteins.fasta
  - Output: sequence_alignments_proteins.faa
- Conservation Analysis
  - Calculates position-wise conservation score
  - Visualization: conservation_plot.png
- Pairwise Similarity
  - Matrix heatmap (distance_matrix.png)
  - Hierarchical clustering (hierarchical_clustering.png)

5. Phylogenetic Tree Construction

- Method: UPGMA (Unweighted Pair Group Method with Arithmetic Mean)
- Tool: Biopython Phylo
- Input: MSA from Clustal Omega
- Output Visualization: phylogenetic_tree.png

6. Functional Annotation via BLAST

- Tool: NCBI BLASTP (online query)
- For Each Protein:
  - Identifies top hit, organism, function, E-value, score
- Summary Table: blast_df (pandas DataFrame)
- Visualizations:
  - Top organisms (organism_frequency_distribution.png)
  - Top protein functions (function_distribution.png)

Output Summary
--------------

| Output File                          | Description                           |
|-------------------------------------|---------------------------------------|
| gc_contents.png                     | GC content bar plot                   |
| lengths.png                         | Sequence lengths plot                 |
| properties.csv                      | Sequence ID, GC content, length       |
| distribution_lengths_GC.png         | Combined histogram & boxplot          |
| protein_sequences.fasta             | Translated protein sequences          |
| sequence_alignments_proteins.faa    | MSA results                           |
| conservation_plot.png               | Consensus conservation scores         |
| distance_matrix.png                 | Pairwise distance heatmap             |
| hierarchical_clustering.png         | Sequence clustering dendrogram        |
| phylogenetic_tree.png               | Phylogenetic tree                     |
| organism_frequency_distribution.png | Top organisms from BLAST              |
| function_distribution.png           | Top protein functions from BLAST      |

Notes
-----

- The pipeline is designed to be run in Google Colab.
- BLAST queries are performed online using Biopython's NCBIWWW.qblast(). Internet is required.
- Clustal Omega must be available via command line (clustalo).

Credits
-------

Developed by Of Mice and Microbes.
Part of the Bioinformatics course group project, Spring 2025.


### ---(___C'>   (.o)=   ~
