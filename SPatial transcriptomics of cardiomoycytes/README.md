<<<<<<< HEAD
#                              Spatial transcriptomics of cardiomyocytes
 ### Introduction
Cardiovascular diseases are a major health burden; put it as a leading cause of death and morbidity. To better understand human disease, we should have a clear picture of how normal molecular process work. The functional unit of the heart is cardiomyocyte, which is large, elongated cells measure around 100 um in length and 20-30 um in diameter. For proper heart function, cardiomyocytes need to act as one unit with organized synchronized and timed contraction. Otherwise, this will lead to arrythmia which is a class of common heart disease where this normal pattern is disturbed(Rampazzo et al., 2014). To do so; cardiomyocytes are connected thorough a specialized dynamic structure called intercalated discs which enable rapid transfer of electrolytes between cardiomyocytes. Changes in ICDs composition and mis localization of their proteins have been associated with different cardiac diseases. Classically, it was believed that ICDs are a static structure where their composition is unchanged. However,  studies found that many of proteins of ICDs have short half-lives and need to be synthesized continually(Saffitz et al., 2000). It is energetically and functionally unfavorable for ICDs proteins to move long distance every short period to replenish their pool. In many cell types like neurons, there is local translation of the protein needed at site distal to cell’s nucleus. To achieve this cell; a well-known biological phenomenon called RNA-asymmetry where RNA distribution is not the same within the cells(Martin & Ephrussi, 2009). This means that there is a local pool of RNA within specific regions of cells important for difference of function between cells compartments. This is present in neurons, drosophila; cell migration and xenopaus. 
Much evidence supports the presence of RNA pool specific to ICDs region. 1- The evidence for local translation at intercalated discs(Scarborough et al., 2021). 2- presence of RNA binding proteins at intercalated discs(Chu et al., 2018). 3- Logically; it will be time and energetically unfavorable to replenish ICDs protein pool from distant site of their target region. Based on previous rationale we are hypothesizing that there is an enrichment of specific RNA population at intercalated discs region that’s required for proper ICDs function and targeting these RNAs is mediated by set of RNA binding proteins. The importance of this project will be determining the pathogenesis by which some RNA-binding protein mutation contribute to heart disease and arrythmia related to intercalated discs regulation. It also enable us to understand how these RNA-populations are dysregulated and contributes to heart disease.
The main first question to be first answered is what are the RNA pools and isoforms that are enriched at intercalated discs and what are their RNA-binding proteins.
We found that there are enrichment of some RNA that related to translation and mitochondrial functions among others.
.

## Methods:
1. ##### Intercalated discs isolation: 
 to compare between RNA pool of intercalated discs regions and other regions, we need first to isolate these regions; This will be done using laser capture microdissection at the core facility of university of Iowa, fresh frozen heart tissue are used to make tissue sections on special slides. The tissue is stained by immunohistochemistry for antigen that recognizes intercalated discs. The staining steps contain a buffer that contains 2M NaCl to prevent RNA degradation. Then after identifying the region of interest;, we mark them under microscope and dissect them. This will result in samples that contain ICDs region and control samples that don’t contain ICDs.
2. ##### RNA isolation
 RNA from dissected samples will be isolated using a low input RNA isolation kit as Pico pure toral RNA isolation kit. Isolated RNA will be run on bioanalyzer to measure their integrity and degradation using RIN and DV200 before proceeding to the second steps.
3. ##### cDNA library prepartion and RNA sequenincg
Isolated RNA will be further used for cDNA library preparation using low input Total RNA isolationv3 SMARTer kit by Takara. Then the library will be tested to check if passed the quality test for RNA sequencing. The average length of library was 400 nt. RNA sequenced using Nova-seq SP lane; 100 single read end sequencing at coverage ~ 20 million read.

4. ##### RNA-anlaysis
 RNA data will be mapped to reference transcriptome using HISAT2. Then HTSEQ will be used to quantify the gene expression. Differential gene expression analysis will be used using package DESeq2 and edgeR. After that gene ontology analysis will be done using clusterprofiler package. Data visualization will done using volcano plot.
For my experiment; we have the differential expression of the genes downloaded on excel sheet, which will be my main input for further analysis. 

Load required packages
library(ggplot2)
results['volcano_plot'] = {} 
Loop through signatures 
for label, signature in signatures.items(): 
Run analysis 
results ['volcano_plot'][label] = analyze(signature=signature, tool='volcano_plot', signature_label=label, pvalue_threshold=0.05, logfc_threshold=1.5, plot_type='interactive') 
Display results
 plot(results['volcano_plot'][label])
 
 Figures:
 I will re-produce these figures below; I will also make volacano plot compare the female and male of samples.
 This figure below shows a volcano plot of differential gene expression between control and intercalated discs samples. Red represents upregulated genes in the samples of interest where blue represent downregulated genes. Black means no difference in gene expression. Each dot represents gene with it FDR. 
 ![newplot](https://user-images.githubusercontent.com/125291868/223286827-6e0e70a1-b9f1-4ba5-97f0-bcd66744d89f.png) 
 
 This figure represent gene ontology biological process for upregulated and downregulated genes in intercalated discs regions
 
 ![newplot(1)](https://user-images.githubusercontent.com/125291868/223287376-2c739e31-4efb-40a2-b7ac-acdfa092755b.png)


 




