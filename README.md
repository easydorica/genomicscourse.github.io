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
Exome sequencing is a method that enables the selective sequencing of the exonic regions of a genome - that is the transcribed parts of the genome present in mature mRNA, including protein-coding sequences, but also untranslated regions (UTRs).
Thus, the exome represents only 1% of the human genome, but has been estimated to harbor up to 85% of all disease-causing variants.

Exome sequencing, thus, offers an affordable alternative to whole-genome sequencing in the diagnosis of genetic disease, while still covering far more potential disease-causing variant sites than genotyping arrays. This is of special relevance in the case of rare genetic diseases, for which the causative variants may occur at too low a frequency in the human population to be included on genotyping arrays.

Variant calling is a complex process that involves numerous steps, which can be grouped into three main stages:
- Mapping reads against the reference genome
- Performing variant calling/genotype assignment
- Annotating variants and performing downstream analyses

Any pipeline you use, you are going to have a large collection of variants, thus, identify variants of high quality and between them the variant that could be the cause of a genetic disease 



Finally, manual review of aligned reads is often performed to reduce the risk of false positives and incorrect results 
