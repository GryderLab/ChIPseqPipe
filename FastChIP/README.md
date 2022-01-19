## Pipeline Overview
![Alt text](pipeline_workflow_v0.0.png?raw=true "Title")
https://docs.google.com/presentation/d/1adXiUHnZrGXjRVzkhA5Axf-_3vq68lwuD4sARz4DEjI/edit#slide=id.p

![Alt text](example_rose.png?raw=true "Title")

### Procedures
- bwa alignment of hg38 and spike-ins if any (mm10, ecoli)
- chipseq-spikein.sh : make a spike-in summary and tdf files 
  - SpikeIn/spike_map_summary
  - *.SPK.tdf (spike-in normalized)
- peak finding:
  - MAC_p-[4/5/7/14] results
    - ROSE results per MAC result

## Usage 
```
## select sample to run
read-xls.sh | grep <sample_name> > input.txt
## Run pipeline
bash ../scripts/run-fastchip.sh input.txt

```

## Examples Runs
```
## extract sample input
bash read-xlsx.sh | grep 22Rv1_BG15n_AR_073021_CWRU > input.txt
# input.txt: 22Rv1_BG15n_AR_073021_CWRU      073021_CWRU     ecoli   .

## run the pipeline
bash ../scripts/run-fastchip.sh input.txt

## output structure
HOME=/mnt/rstor/SOM_GENE_BEG33/ChIP_seq/hg38/DATA
$HOME/22Rv1_BG15n_AR_073021_CWRU/
|22Rv1_BG15n_AR_073021_CWRU.bam
|22Rv1_BG15n_AR_073021_CWRU.bam.bai
|22Rv1_BG15n_AR_073021_CWRU_eco.bam
|22Rv1_BG15n_AR_073021_CWRU_eco.bam.bai
|22Rv1_BG15n_AR_073021_CWRU_eco.flagstat.txt
|22Rv1_BG15n_AR_073021_CWRU.flagstat.txt
├── Fastqc
│   ├── 22Rv1_BG15n_AR_073021_CWRU_R1_fastqc
│   │   ├── Icons
│   │   └── Images
│   └── 22Rv1_BG15n_AR_073021_CWRU_R2_fastqc
│       ├── Icons
│       └── Images
├── MACS_p-14
        22Rv1_BG15n_AR_073021_CWRU.clean.bed
        22Rv1_BG15n_AR_073021_CWRU.nobl.bed
        22Rv1_BG15n_AR_073021_CWRU.p-14.bed
        22Rv1_BG15n_AR_073021_CWRU_p-14.clean.bed
        22Rv1_BG15n_AR_073021_CWRU_peaks.narrowPeak
        22Rv1_BG15n_AR_073021_CWRU_peaks.xls
        22Rv1_BG15n_AR_073021_CWRU_summits.bed
│   ├── 22Rv1_BG15n_AR_073021_CWRU_motifs
│   │   ├── homerResults
│   │   └── knownResults
│   └── ROSE
        22Rv1_BG15n_AR_073021_CWRU_12KB_STITCHED_TSS_DISTAL_ENHANCER_REGION_MAP.txt
        22Rv1_BG15n_AR_073021_CWRU_AllEnhancers.table.txt
        22Rv1_BG15n_AR_073021_CWRU_Enhancers_withSuper.bed
        22Rv1_BG15n_AR_073021_CWRU_Gateway_Enhancers.bed
        22Rv1_BG15n_AR_073021_CWRU_Gateway_SuperEnhancers.bed
        22Rv1_BG15n_AR_073021_CWRU_Plot_points.png
        22Rv1_BG15n_AR_073021_CWRU_SuperEnhancers.table.txt
│       ├── gff
│       └── mappedGFF
├── MACS_p-5
│   ├── 22Rv1_BG15n_AR_073021_CWRU_motifs
│   │   ├── homerResults
│   │   └── knownResults
│   └── ROSE
│       ├── gff
│       └── mappedGFF
├── MACS_p-7
│   ├── 22Rv1_BG15n_AR_073021_CWRU_motifs
│   │   ├── homerResults
│   │   └── knownResults
│   └── ROSE
│       ├── gff
│       └── mappedGFF
└── SpikeIn/spike_map_summary

```


