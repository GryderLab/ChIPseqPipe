## Pipeline Overview
![Alt text](pipeline_workflow_v0.0.png?raw=true "Title")

## Usage 
```
## select sample to run
read-xls.sh | grep <sample_name> > input.txt
## Run pipeline
run-fastChIP.pl input.txt
```

## Examples Runs
```
## extract sample input
bash read-xlsx.sh | grep 22Rv1_BG15n_AR_073021_CWRU > input.txt
# input.txt: 22Rv1_BG15n_AR_073021_CWRU      073021_CWRU     ecoli   .

## run the pipeline
run-fastchip.sh input.txt

## output structure
HOME=/mnt/rstor/SOM_GENE_BEG33/ChIP_seq/hg38/DATA
$HOME/22Rv1_BG15n_AR_073021_CWRU/
├── Fastqc
│   ├── 22Rv1_BG15n_AR_073021_CWRU_R1_fastqc
│   │   ├── Icons
│   │   └── Images
│   └── 22Rv1_BG15n_AR_073021_CWRU_R2_fastqc
│       ├── Icons
│       └── Images
├── MACS_p-14
│   ├── 22Rv1_BG15n_AR_073021_CWRU_motifs
│   │   ├── homerResults
│   │   └── knownResults
│   └── ROSE
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
└── SpikeIn

```


