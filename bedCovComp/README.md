# Protocol for running BedCovComp
by Berkley E. Gryder and Shanqing Gu 
December 2021

### (1)	Generate high quality ChIP-seq or CUT&RUN data +/- a treatment condition
    [use on a DATA directory with the DATA/SampleName/SampleName.bam file structure as here https://github.com/CBIIT/ChIP_seq.]
    assumes MACS output present in the SampleName/ directory with this format:
        bed1path=${DATA_HOME}/${sample1}/MACS_${pValue}/${sample1}.clean.bed
### (2)	Configure bedCovComp
    a.  Use codebuilder, go to the “bedCov_Spiked” tab.  
        Gryder Lab location: \\ads.case.edu\rc\SOM_GENE_BEG33\ChIP_seq\hg38\scripts\multisample_analysis\bedCovComp_builder.xlsx
        Github copy: <a href="https://github.com/GryderLab/ChIPseqPipe/blob/master/bedCovComp/bedCovComp_builder.xlsx">  
    b.  Add your sample names, sample file names, MACS p value (ie, p-14)
    c.  Select a bed file to split the data by an overlapping feature (ie, TSS)
    
### (3)	Run on the HPC
    a. log into HPC and navigate to working directory (/mnt/rstor/SOM_GENE_BEG33/ChIP_seq/hg38/projects/ARIA/bedCovComp) 
    b. in the codebuilder, copy line 23 "paste to command line:" and run 

### (4) Example output
    a. The output files are genearted in the project folder (e.g.: "/mnt/rstor/SOM_GENE_BEG33/ChIP_seq/hg38/projects/ARIA/bedCovComp/")
    b. The plot files include deltaboxplot, logCovboxplot, MA, l2fcboxplot, peaksizes, and rankl2FC.
    c. Example plots (peaksize and rankl2FC) are shown below).
<a href="https://github.com/guvp2017/ChIPseqPipe/blob/master/bedCovComp/bedCovCompExample.PNG"> 
<p align="center"> <img width="400" height="800" src="bedCovCompExample.PNG"></p>
