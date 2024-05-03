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
 - [First Item](#item-two)
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







