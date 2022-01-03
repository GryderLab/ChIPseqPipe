## Pipeline Overview
![Alt text](pipeline_workflow_v0.0.png?raw=true "Title")

## Usage 
```
## select sample to run
read-xls.sh | grep <sample_name> > input.txt
## Run pipeline
run-fastChIP.pl input.txt
```

## Output Examples
```
22Rv1_BG15n_AR_073021_CWRU/
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


