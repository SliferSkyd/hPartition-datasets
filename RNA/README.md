# RNA benchmark datasets

Datasets assembled to benchmark hPartition on RNA data, in response to a reviewer request.
`PROVENANCE.md` records, for each dataset, what comes from the source publication and what was
built here. Read it before reusing anything.

## Layout

```
alignments/
  virus/      23 whole-genome RNA virus alignments (measles, mumps, rabies, dengue-1,
              Zika, rubella, HCV-1b, HIV-1b) at 20-35, 50 and 100 taxa
  flu/        17 influenza HA segment alignments
  covid/      SARS-CoV-2 subsets (20-500 taxa)
  ebov/       Ebola subsets and the full 1,610-taxon set
  pf/         the four PartitionFinder benchmark datasets (hummingbirds, midges,
              saxifragales, barkbeetles), with the authors' charsets
  mito/       33-taxon grasshopper mitogenome, 37 loci (Leavitt et al. 2013 accessions)
  beetle/     52-taxon beetle mitogenome, 37 loci (Timmermans et al. 2016 accessions)
  plastome/   33-taxon chloroplast genome, 110 loci, 84,209 sites
source/       original NEXUS files for the PartitionFinder datasets, as deposited
scripts/      dataset preparation; scripts/pipeline/ holds the benchmark runner
results/      result tables and figures
```

Each alignment directory holds `<name>.fasta` and `<name>.phy` (identical content), plus
`<name>.genes.nex` where the source defines charsets and `<name>.names.tsv` mapping the short
IDs back to the original taxon labels.

## Notes

- MAFFT intermediates (`*.mafft.fasta`) and IQ-TREE run artefacts are not included; they are
  regenerable from the scripts.
- `alignments/covid/` excludes the full 3,685-taxon alignment (107 MB, over GitHub's file limit).
- `beetle/beetle.masked.tsv` lists five gene copies masked because they translate with internal
  stop codons; the unmasked alignment is not included.
