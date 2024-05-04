# <code style="color : blue">SNVs/Indels inspection from exome sequencing data</code>  
Federica Isidori (bosco@aosp.bo.it)  
Computational Genomics, IRCCS Azienda Ospedaliero-Universitaria di Bologna  
---
Medical Genomics, Bachelor Degree in Genomics, University of Bologna  
Prof. Tommaso Pippucci  

---

**READ ME FIRST**
-	Actions you need to perform are indicated in bold
-	Questions are designated by “Q” and are marked by the 'important' alert.
-	Screenshots are just examples, your specific output may look slightly different.
-	For this workshop you require:
-	This manual
- Files in following folder: SNVs_exomes
- Software: Integrative Genomics Viewer (IGV), an Internet browser

---
**TABLE OF CONTENTS:**
 - [Introduction](#item-one)
 - [IGV settings and operations](#item-two)
 - [CASE 1](#item-three)

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
Open your browser and go to [IGV web App ](https://igv.org/app/). Right-click on the link to open it in a new window. *(It runs in a web browser and requires no downloads)*

**Settings**
1. **Load Human (GRCh37/hg19) genome assembly  
Click on Genome and from the drop-down menu select Human (GRCh37/hg19).**

2. To upload tracks on IGV, click on “Traks” in the IGV upper bar menu and select “Local file” from the same drop-down menu following the instructions given case by case in this manual.
3. To navigate to specific genomic regions, type the region coordinates (e.g., chr1:100000-200000) or the gene name directly in the search box and then zoom in, zoom out with the `+` `-` bar or by clicking and dragging on the genomic coordinates.

<a id="item-three"></a> 
### CASE1 
**Load aligned sequence data**  
Tracks for this exercise are in the PROBAND1 folder.  
**Select both files: `proband.bam` and `proband.bam.bai`**  

**In text box type the gene name *B4GALNT1***  
IGV will look up the genomic coordinates for the gene (Fig.4) and set the viewing region accordingly.

![Fig.4](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/cc69dbd1-3690-4302-8e6a-3e1a6a6b2b2b)
**Fig.4**

Here is a quick summary of the generic information displayed in IGV:
1. In the navigation box we now find the **genomic coordinates** of the gene.
2. **Chromosome ideogram**. The red bar on the chromosome ideogram indicates the position of the gene along the chromosome.  

![Fig.5](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/7398e5e9-9d6c-467b-b118-735feca6be6d)
**Fig.5**

3. **Coverage track**. The coverage track displays the depth of the reads at each position as a grey bar chart; e.g. if the coverage of a genomic position is 100X , this means the base was sequenced 100 times.
View count details of a position by clicking over the coverage bar. The box that appears provides further information for the position taken in consideration. In the example in Fig.6, there are 302 reads and all nucleotides at this position are “T”.
If a nucleotide differs from the reference sequence in the reads, IGV colors the bar in proportion to the read count of each base (A, C, G, T).

![Fig.6](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/98722810-eb5c-4601-b568-cf32428b45ef)
**Fig.6**

4. This section give an overview of the **alignment track**. The reads are represented by grey bars stacked on top of each other, where they are aligned to the reference genome. The reads are pointed to indicate their orientation (i.e. the forward strand or the reverse strand). 
Reads that are displayed with light grey borders and transparent or in other colors, have bad mapping quality. 
At each base that the read sequence mismatches the reference, IGV uses color markers to highlight potential genetic alterations in reads against a reference sequence. By clicking over a specific grey bar you can obtain additional information about the specific read: the read name, alignment quality, CIGAR and information about its mate read. 

![Fig.7](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/3860b027-d078-4f13-9d80-62c5825f2798)
**Fig.7**

5. **Gene track**. Graphical representation of the gene. Genes are represented as lines and boxes. Lines represent intronic regions, and boxes represent exonic regions. The arrows indicate the direction/strand of transcription for the gene. When an exon box become narrower in height, this indicates a UTR. In this section can be loaded other annotation tracks (e.g. dbSNP database of common polymorphisms or Clinvar database for interpretations of clinical significance of variants)

![Fig.8](https://github.com/easydorica/genomicscourse.github.io/assets/89908049/c1a42ad4-d906-43ad-817a-8adf56bd0502)
**Fig.8**


> [!IMPORTANT]
> **Q1.1**: What are the genomic coordinates for *B4GALNT1* gene?  
> **Q1.2**: On which chromosome arm is the *RASAL1* gene located?  

**Enter the genomic coordinate: chr6:150209805**

> [!IMPORTANT]
> **Q1.3**: Is a variant reported at this position? If so, what type of variant is it (SNV or InDels)?  
> **Q1.4**: If any variant is present, what do you think about it? Can be considered true or not? Why?  

> _**NOTE**_  
> Look at the sequence of the reference genome close to the entered position!! 


**Enter this genomic interval: chr12:40876455-40876798**

> [!IMPORTANT]
> **Q1.5**: There are many variants in this region. What are the allelic fractions of variants inside the region? Are the allelic fractions suggestive of real heterozygous variants?  

Although most of the reads is gray, some are entirely displayed in different colors. You can click on any read to visualize its mapping quality among other features of the read and its mate. 

> [!IMPORTANT]
> **Q1.6**: Do you notice some read with low mapping quality?  
> **Q1.7**: What is the mapping quality of the green coloured read?








