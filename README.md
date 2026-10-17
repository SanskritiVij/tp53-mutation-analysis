# TP53 mutations in breast cancer (TCGA)

An analysis of TP53 mutations and overall survival in the TCGA breast cancer cohort, done in Python.

## Question

Which TP53 mutations are most common in breast cancer, and do patients with a TP53 mutation survive for a shorter time?

## Data

Mutation and clinical files for Breast Invasive Carcinoma (TCGA, PanCancer Atlas) from cBioPortal. After matching the two files, 1,009 patients had both mutation and survival data.

## Methods

- Filtered the mutation file to TP53 and counted mutation types and protein-level changes
- Split patients into TP53-mutant (348) and wild-type (661), leaving out silent mutations
- Plotted Kaplan-Meier survival curves and compared them with a log-rank test

Tools: Python, pandas, matplotlib, lifelines, Google Colab

## Results

- 348 of 1,009 patients (34.5%) carry a TP53 mutation
- Missense mutations are the most common type, 216 of 356 (about 61%)
- The most frequent hotspots are R175H (21 samples), R273H (13) and Y220C (7), all within the DNA-binding domain
- Survival did not differ significantly between mutant and wild-type patients (log-rank p = 0.48, 136 deaths)

![TP53 mutation types](tp53_mutation_types.png)

![Survival by TP53 status](tp53_survival.png)

## Limitations

- The analysis does not adjust for tumor subtype, stage or age, which all affect survival and are linked to TP53 status
- Only 136 patients died, and few were followed past 120 months, so the late part of the curves is noisy

## Files

- `TP53_mutation_analysis.ipynb`: full notebook with code and notes
- `tp53_mutation_types.png`, `tp53_survival.png`: figures
