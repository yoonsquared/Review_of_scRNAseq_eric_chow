# Studying RNAseq
## Plate-based SMART-seq
polyA and ployG, 2 PCR handles for cDNA
100~1000s of samples, 1 cell-per-well.
Manual labor

## DropSeq
Microfluidics
Beads -> cell junction -> oil junction : some droplets with oil, oil+bead, oil+bead+cell, oil+bead+2cells.
The beads have oligoDT with all the same barcodes. So we know which cell that came from.
1,000 ~ 10,000 samples in a well.
An academic lab did this.

Cons: 
-	82% empty, 16% single cell, 2% multiplets/doublets (2+ cells or beads)
-	When increasing the cell concentration and beads, 37% empty, 37% single cell, 26% multiplets

## 10x genomimcs
Microfluidics
Chip-based
The droplet-to-bead efficiency brought up to 90%.
Within the droplet, capture + reverse transcription occurs.

After reverse transcription, break the emulsion, amplify in a single tube and then construct library.

Up to [25,000 cells per lane] * There are [8 lanes per chip] = ~[200,000 cells per chip].

## Microwells – parallel sc sequencing without droplets.
SeqWell, Celsee Genesis, Bectron

A well is a few-microns in diameter. 100,000 of wells in a chip.
A bead that is designed to only fit 1-per-well. You coat the wells with the beads first.
Pour cells on top, the cells will settle down on the wells, and lysis + enzymatic reactions + unique barcoding done in the wells.

## Combinatorial indexing (over million cells in a study)
*In situ* reactions: using cells as a compartment.
Not working with an individual cell at any given moment. However, multiple barcoding is done, so that we tag a combination of barcodes per cell (unique) -> resulting a single-cell barcoding.

Fixed cells – reagents can flow in-and-out of the cells
Each well has multiple cells, after reverse transcription, re-distribute in new chip of wells.
96 wells (1st chip) * 96 wells (2nd chip), barcodes in each well.
Illumine barcodes on third steps possible.
3rd and 4th level of barcoding makes millions of cells with unique barcodes.

## Quantifying Proteins – CITEseq
PCR handle + antibody Barcode + polyA tail.
Counting the antibody barcode-based to see how many proteins have bound to that antibody.
Protein abundance + transcription read-out of which genes are on/off in RNA.

## Focusing on Multiplets
Multiplets limit loading concentration.

### Demuxlet – multiplexing by genotype
Even if you have doublets, they are using genotypes of original samples to distinguish transcripts from different samples. Remove those reads from doublet droplet.

Given: when you have doublets, it is likely to get 2 cells in a droplet that are from different samples.

### Non-genetic multiplexing strategies
Using an antibody that binds to certain cells, labeling based on the cells that are pulled with certain antibody and then go through scRNAseq methods.

### Mcginnis et al. UCSF
Barcoding singlets and doublets with just open-chromatin region labeling.

## Conclusions
Many types: RNA, DNA, protein, …
Generates high dimensional data (20k genes) per cells.
-	Reveal biology hidden from lower dimensional techs
Lower throughput and more expensive compared to flow and mass cytometry

Microscopy methods
-	seqFISH, MERFISH, CODX
-	lower throughput but provide spatial info.

