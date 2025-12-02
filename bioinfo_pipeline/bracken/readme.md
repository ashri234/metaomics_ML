**Bracken Tool**

**Overview**

Bracken (Bayesian Reestimation of Abundance with Kraken) is a statistical tool designed to improve species- and genus-level abundance estimates from Kraken2 classification outputs.

Kraken classifies reads using exact k-mer matches, but it often assigns reads to higher taxonomic ranks ( genus or family) if multiple species share similar k-mers. Bracken refines these results by redistributing reads from higher taxonomic levels down to species or genus levels, providing a more accurate abundance estimation.

**Key Features**

- Works on top of Kraken2 outputs.
- Provides more accurate relative abundance of species/genus.
- Uses Bayesian inference to re-estimate abundances.
- Handles cases where reads are ambiguously classified by Kraken.
**Workflow**
1.Input:

Kraken2 classification report (.kreport file).
Bracken database built from the same Kraken database.

2.Processing:

Reads assigned to higher taxonomic ranks are probabilistically redistributed to lower taxonomic ranks using precomputed k-mer distributions.

3.Output:

Abundance estimates of taxa at a user-specified level (species, genus, etc.).
Results in a tab-delimited text file.
**Example Command**
```
bracken -d kraken_database \
        -i kraken2_output/ERR14218891.k2report \
        -o bracken_output/ERR14218891.bracken.out \
        -r 100 -l S -t 10
```
**Breakdown of Options**
Option	Parameter	Description
-d	kraken_database	Path to the Kraken2 database used during classification. Bracken requires the same database.
-i	kraken2_output/ERR14218891.k2report	Input file: Kraken2 report (.kreport) containing taxonomic classification results.
-o	bracken_output/ERR14218891.bracken.out	Output file where Bracken’s re-estimated abundances will be saved.
-r	100	Read length (in base pairs). Needed for Bracken’s statistical model to redistribute reads.
-l	S	Taxonomic level for abundance estimation: S = Species. (Other options: G = Genus, F = Family, etc.).
-t	10	Threshold: Minimum number of reads required to report a taxon. Taxa with fewer reads are excluded.
**Summary**
This Bracken command it to estimate species-level abundances (-l S), assuming 100 bp read length (-r 100). It will only include taxa supported by at least 10 reads

**Command to merge braken output**
```
python ../combine_bracken_outuptu.py --files  *out -o combined_otu_data.tsv
```
