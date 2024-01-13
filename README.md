## Background
This repository provides the notebook and the data for the case study was used in the **Accelerate Biomedical Data Analysis with Generative AI** workshop

## Case study
- Research Article: [Pediatric Brain Cancer (CPTAC/CHOP, Cell 2020)](https://pubmed.ncbi.nlm.nih.gov/33242424/)
- Data Description 
    -  Source: cBioportal
    -  Sample size: 218 
    -  Classes: medulloblastoma, ganglioglioma, low grade glioma, ependymoma, high grade glioma, craniopharyngioma, and atypical teratoid rhabdoid tumor.
    -  Demonstration Purpose: Sample from MBL and GNG classes and only 2000 genes taken.
- Notes:
    -  [Medulloblastoma (MBL)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9911713/), one of the central nervous system (CNS) embryonal tumors arising from the cerebellum, is the most common pediatric malignant brain tumor. MBL comprises 15% of all pediatric CNS tumors.
    -  [Gangliogliomas (GBL) (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4231627/#B6), are benign tumors of CNS, can occur anywhere in CNS  including the cerebrum, cerebellum, thalamus, spinal cord, hypothalamus, lateral ventricle, or brainstem, but are most commonly found in the temporal lobe. 

## Objectives
Identifying genes having the potential to discriminate between MBL and GNG and understanding the network of these genes using PPI (Protein Protein Interaction network).

## Analyses
- Find differentially expressed genes using t-test between the two classes, given the data is normalized 
- Perform PCA with differentially expressed genes
- Perform enrichment analysis to look for the pathways these genes are enriched in.
- Build an ML-based classifier using the set of genes obtained from Differential expression.

## [Simple] Set up instructions to run on Google Colab
- Create a personal Google Drive folder called *workshop*
- Download *Workshop_Data.csv* and *Workshop_codebook_final.ipynb* from this repo and upload to *workshop*  
- Use [Google Colab](https://colab.research.google.com/) to run *Workshop_codebook_final.ipynb*

**Important points to note:**
- The notebook requires OpenAI keys, which can be obtained [here](https://platform.openai.com/api-keys)
- The first line of the notebook needs to be executed to download the correct packages
- Indicate the correct path when loading the dataset: `gene_exp = pd.read_csv('/correct-path-on-google-drive/Workshop_Data.csv',index_col=0)`
- The code outputting does not work properly on Colab. You can try the following magic command `%%ai openai-chat:gpt-3.5-turbo` instead of `%%ai openai-chat:gpt-3.5-turbo --format code`. This will make the output behavior similar to the ChatGPT web application, which returns additional text along with the code
- You can try the following advanced setup if you would like to have a clean coding workflow

## [Advanced] Set up instructions to run on a local machine
The following instructions are meant to be run on a terminal. The instructions have been tested on a Linux machine
- Clone this repository: `git clone git@github.com:Nilzkool/Biomedical_GenAI_Workshop.git`
- Open a terminal from the folder containing the cloned repository.
- Install [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html#)
- Install mamaba using: `conda install mamba -n base -c conda-forge`
- Set up the environment using the provided yml file: `mamba env create -f workshop_environment.yml`
- Activate the environment: `conda activate genai-workshop`
- Run Jupyter lab: `jupyter lab`
- Open the notebook titled Workshop_codebook_final.ipynb and have fun!

**Important point to note**
- The notebook requires OpenAI keys, which can be obtained [here](https://platform.openai.com/api-keys)

