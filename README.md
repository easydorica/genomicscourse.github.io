# $${\color{blue}SNVs/Indels \space inspection \space from \space exome \space sequencing \space data }$$
Federica Isidori (bosco@aosp.bo.it)  
Computational Genomics, IRCCS Azienda Ospedaliero-Universitaria di Bologna

---

**READ ME FIRST**
-	Actions you need to perform are indicated in bold
-	Questions are designated by “Q” and are in italics.
-	Screenshots are just examples, your specific output may look slightly different.
-	For this workshop you require:
-	This manual
- Files in following folder: SNVs_exomes
- Software: Integrative Genomics Viewer (IGV), an Internet browser

---
**TABLE OF CONTENTS:**
 - [Introduction](#item-one)
 - [IGV settings and operations](#item-two)
 - [Second Item](#item-three)

<a id="item-one"></a> 
### Introduction  
Exome sequencing is a method that enables the selective sequencing of the exonic regions of a genome - that is the transcribed parts of the genome present in mature mRNA, including protein-coding sequences.
Thus, the exome represents only 1% of the human genome, but has been estimated to harbor up to 85% of all disease-causing variants.

Exome sequencing, thus, offers an affordable alternative to whole-genome sequencing in the diagnosis of genetic disease, while still covering far more potential disease-causing variant sites than genotyping arrays. This is of special relevance in the case of rare genetic diseases, for which the causative variants may occur at too low a frequency in the human population to be included on genotyping arrays.

Variant calling is a complex process that involves numerous steps, which can be grouped into three main stages:
- Mapping reads against the reference genome
- Performing variants calling/genotype assignment
- Annotating variants and performing downstream analyses

Any pipeline you use, you will end up with a large collection of variants. To identify variants of high quality, and between them the variant that could be the cause of a genetic disease, we have to apply some quality filters. 
Manual review of aligned reads for confirmation and interpretation of variant calls is an important step in many variant calling pipelines for next-generation sequencing (NGS) data. 

In this workshop we will use the Integrative Genome Viewer (IGV) to visualize variants in exome sequence data and discriminate between true and false calls. 

The following figures depict several frequently occurring artifacts that can be identified by manual review: low-quality base calls (Fig. 1), strand bias artifacts (Fig. 2), erroneous alignments in low-complexity regions (Fig. 3).

![Fig.1](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/5554b1e9-4a56-4dbb-a64e-94ded357f87a)

**Fig.1**: Low quality base-calls. Most reads supporting the variant have low base quality indicated by lightly shaded non-reference bases.

![Fig.2](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/a4858d34-1d97-456b-9d74-d7cb371a0bba)

**Fig.2**: Strand bias artefacts. Variant-supporting reads are on the reverse strand (blue), whereas reference-supporting reads are equally represented on both strands.  

![Fig.3](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/8ad79f7c-e562-417a-b06a-0db41232d625)

**Fig.3**: Erroneous alignments in low-complexity regions (repeated regions in reference genome "TTTTT.."). In this case, reads erroneously showing a single-base deletion (horizontal black line) at a T-homopolymer are enriched in the proband. Some reads supporting insertions (purple bar) are also seen.

<a id="item-two"></a> 
### IGV settings and operations

This manual refers to the local installation of IGV version 2.13.3. You may have a different version, with no or only slightly different features that should not affect the content of this workshop. If, for any reason, it is problematic to run IGV locally, you can open your browser and go to: https://igv.org/app/. 
Here are some instructions on the basic use of IGV (list numbers point to Figure 2, Figure 3, Figure 4).

Settings
1. Load Human (GRCh38/hg38) genome assembly
Note: IGV loads Human (GRCh37/hg19) by default, but we need a more recent version of the human genome (GRCh38/hg38). If the drop-down menu displays only GRCh37/hg19, select “More…” and look for Human GRCh38/hg38 in the opening window.
2. Click on “View” in the IGV upper menu bar and select “Preferences”, then “Alignments” in the opening window. Among the many options displayed, set “Visibility range threshold (kb)” to 5000 and select “Show soft-clipped bases”.

