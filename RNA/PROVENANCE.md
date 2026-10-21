# Provenance of the multi-locus RNA-benchmark datasets

Three tiers, by how much of the dataset comes from the source publication.

## Tier 1 — published and deposited; used as the authors released it

### barkbeetles — 44 taxa x 1,897 sites, 7 charsets
- **Study:** Cognato AI, Vogler AP (2001). *Exploring data interaction and nucleotide alignment in a
  multiple gene analysis of* Ips *(Coleoptera: Scolytinae).* Systematic Biology 50(6):758-780.
- **Deposit:** the alignment set distributed with PartitionFinder,
  `roblanf/BenchmarkAlignments/datasets/Cognato_2001/alignment.nex`; local copy in
  `source/Cognato_2001.alignment.nex`.
- **Blocks:** ef1a 1-649, COI 650-1415, 16S 1416-1897, with codon-position charsets for the two
  coding genes.
- **Note on the site count:** the distributed file has NCHAR=1897, while Table 1 of Lanfear et al.
  (2012) reports 1,896 for this dataset. The discrepancy is in their materials; we use the file as
  distributed.
- **Not used:** the authors' own Dryad deposit `doi:10.5061/dryad.678`
  (`Ips.poy.g2.nexus`, NCHAR=2083, blocks 16s 1-525 / EF1a 526-1314 / COI 1315-2083) is a different
  alignment of the same study. A local copy is in `hPartition/doi_10_5061_dryad_678__v20090630/`.

### saxifragales - 40 taxa x 9,005 sites, 5 charsets
- **Study:** Fishbein M et al. (2001). Systematic Biology 50:817-847.
- **Deposit:** the alignment set distributed with PartitionFinder,
  `roblanf/BenchmarkAlignments/datasets/Fishbein_2001/alignment.nex`; local copy in
  `source/Fishbein_2001.alignment.nex`, NCHAR=9237.
- **Genes:** atpB, 18S, rbcL, matK, 26S. Their five CHARSETs span 9,005 of the 9,237 columns, which
  is the figure Table 1 of Lanfear et al. (2012) reports; only those columns are kept.
- NEXUS uses `GAP=':'`, `MISSING='N'`.

### hummingbirds — 164 taxa × 3,821 sites, 11 charsets
- **Study:** McGuire et al. (2007).
- **Deposit:** TreeBASE matrix **M3354**, downloaded as `.nexorg` (the original submitted NEXUS, which
  retains the SETS block).
- NCHAR=4122; the author's EXSET removes 301 sites, giving the 3,821 columns PartitionFinder Table 1
  reports.
- **Genes:** ND2 and ND4 with codon positions, AK1, bfib, tRNA.

### midges — 74 taxa × 2,701 sites, **charsets not recovered**
- **Study:** Ekrem, Willassen & Stur (2010).
- **Deposit:** TreeBASE study **10378**, matrix 5116; original file name `Micropsectra_molecular.nex`.
- **Genes:** COI, COII, CAD, 16S *according to the publication* — we could not verify this against the
  file, because the TreeBASE **per-matrix** download strips the SETS block. The copy we hold contains
  only TAXA and CHARACTERS blocks: no CHARSET, no gene names.
- **To fix:** download the `.nexorg` for study 10378 and run `scripts/prep_nexorg.py`, as was done for
  hummingbirds. TreeBASE is unreachable from this cluster.

## Tier 2 — published taxon set and canonical gene set; alignment reconstructed by us

### mito — 33 taxa × 15,490 sites, 37 loci
- **Study:** Leavitt JR et al. (2013). Molecular Phylogenetics and Evolution 67:494–508, who analysed
  34 grasshopper mitogenomes.
- **What is theirs:** the GenBank accessions listed in their Table 1, and the per-gene alignment protocol.
- **What is ours:** the alignment itself. Their alignment was never deposited, so this is a
  reconstruction, not their file. The 37-gene metazoan mitochondrial set is fixed by biology, so the
  gene content is not a choice we made; the alignment procedure is.

