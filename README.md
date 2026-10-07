# Viral Meningitis Genome Classification

## Project Purpose
The primary objective of this project is to classify primary viral meningitis pathogens based on their genomic sequences using machine learning and Convolutional Neural Networks (CNN)[cite: 1]. The study aims to build a highly accurate classification model by processing and analyzing high-quality, complete genome sequences isolated specifically from *Homo sapiens*, sourced from the NCBI database[cite: 1].

The target viral pathogens strictly focus on primary meningitis agents, including[cite: 1]:
* Cytomegalovirus (CMV)[cite: 1]
* Herpes simplex virus 1 (HSV-1)[cite: 1]
* Herpes simplex virus 2 (HSV-2)[cite: 1]
* Varicella zoster virus (VZV)[cite: 1]
* Human parechovirus (HPeV)[cite: 1]
* Human herpesvirus 6 (HHV-6A and HHV-6B)[cite: 1]
* Enterovirus (Targeting specific meningitis variants: Coxsackievirus B group, Echoviruses, and Enterovirus A71)[cite: 1]

## Data Preprocessing Pipeline (Completed Stages)
To ensure data integrity and prevent any loss of the original genomic data, the project is structured upon a strict non-destructive data pipeline[cite: 1]. The data processing stages completed so far are organized into the following distinct directories:

* **`raw_data`**: Contains the original FASTA files downloaded from NCBI[cite: 1]. These files consist of complete genomes filtered by human host and minimum sequence lengths[cite: 1].
* **`cleaned_data`**: In this formatting stage, all FASTA metadata and identification headers (e.g., `>NC_...`) were completely stripped from the files[cite: 1]. The sequences were converted into plain text documents containing only pure genetic codes (A, T, C, G), with each viral sequence separated by a single blank line (double newline) to prepare them for algorithmic feature extraction[cite: 1].
* **`filtered_data`**: This directory contains the premium dataset consisting of sequences that successfully passed a strict **1% 'N' (Unknown Nucleotide) tolerance filter**[cite: 1]. Any viral sequence containing more than 1% unread/unknown nucleotides was eliminated to maintain the gold standard of the dataset[cite: 1].
* **`tested`**: A secondary experimental dataset created with a more flexible **5% 'N' tolerance filter**[cite: 1, 2]. This specific dataset was constructed to conduct comparative performance analyses using CNN models, evaluating the trade-off between strict data quality (1%) and a larger data volume (5%) without artificially manipulating or imputing the original 'N' values in the sequences[cite: 1, 2].
