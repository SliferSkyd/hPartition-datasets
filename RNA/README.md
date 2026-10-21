# RNA benchmark datasets

Datasets assembled to benchmark hPartition on RNA data, in response to a reviewer request.
`PROVENANCE.md` records, for each dataset, what comes from the source publication and what was
built here. Read it before reusing anything.

## Layout

```
alignments/
  pf/         the four multi-locus datasets benchmarked by Lanfear et al. (2012):
              barkbeetles and saxifragales from the alignment set distributed with
              PartitionFinder, hummingbirds and midges from TreeBASE (M3354, M5116)
  mito/       33-taxon grasshopper mitogenome, 37 loci (Leavitt et al. 2013 accessions)
source/       original NEXUS files for the PartitionFinder datasets, as deposited
scripts/      dataset preparation; scripts/pipeline/ holds the benchmark runner
results/      result tables and figures
```

These five alignments are the ones benchmarked in the paper (its Table 9):
`alignments/pf/{barkbeetles,midges,hummingbirds,saxifragales}.phy` and
`alignments/mito/mito.phy`.

Each alignment directory holds `<name>.fasta` and `<name>.phy` (identical content), plus
`<name>.genes.nex` where the source defines charsets and `<name>.names.tsv` mapping the short
IDs back to the original taxon labels.

## Notes

- MAFFT intermediates (`*.mafft.fasta`) and IQ-TREE run artefacts are not included; they are
  regenerable from the scripts.
