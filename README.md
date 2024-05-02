# Exome data analysis: variants inspection
### How to discriminate true variants from exome sequencing results

### Overview

In this section we will be looking at how IGV can be used for visualizing
mutations in sequence data. Here we consider the scenario in which genome
sequencing has been performed on a DNA sample, sequence reads have been
aligned to the reference genome and a variant caller such as GATK HaplotypeCaller
or MuTect2 has been run.

We will inspect some regions of the genome where there are possible variants
in a breast cancer cell line to determine whether these are real events or
artifacts. These will include single nucleotide variants (SNVs), small insertions
and deletions (indels) and larger structural rearrangements.
