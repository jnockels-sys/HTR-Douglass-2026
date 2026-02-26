# HTR-Douglass-2026
This repository includes data from an AHRC-funded International Placement Award, between the University of Edinburgh and Library of Congress. The project focused on making the autobiographical writings of Frederick Douglass (1818 - 1895) more accessible through AI-enabled transcription workflows, as well as contributing to analyses of his work. The mixed-method analysis primairly used Douglass's travel diary as case study data (1886-1894) (https://www.loc.gov/collections/frederick-douglass-papers/?fa=partof:frederick+douglass+papers:+diary,+1886-1894), which forms part of the Frederick Douglass Papers at the Library of Congress.

# Technologies Used

Transkribus for machine-readable text generation (https://www.transkribus.org)

Limited Python and Regular Expressions for data cleaning and structuring.

Gephi for network visualisation (https://gephi.org)

# Prerequisites 

Transkribus free account, register here - https://account.readcoop.eu/, with the trained Douglass model made accessible vai contacting the corresponding author. 

Gephi 10.1 installed locally, see https://gephi.org/desktop/. 

The datasets constructed for this work were conducted on an Apple Mac 1 Silicon set-up, as such code may need converting to different syntax for other environments. The limited Python code used was written within Jupyter Notebooks to prioritise reproducibility through human-language descriptions and comments, however can also be used locally in the command line (https://jupyter.org).

# Workflow 

-- Handwritten Text Recognition

The Douglass transcription was reached through the semi-automatic training of an ATR model in Transkribus by Nockels, while a Kluge Scholar, at the Library of Congress, between April - July 2024. The diary was first captured by the LoC Manuscript Division in 2000, alongside creating an encoded finding aid (https://lccn.loc.gov/item/mss1187900001). Unsuccessful attempts were made in using OCR (ABBYY FineReader) on the diary, with Handwritten Text Recognition through Transkribus being opted for instead (see Nockels et al. 2025).

The model ‘Late Douglass (1886 - 1887)’ was trained on 8,980 words, and achieved an overall character accuracy of 94.28%, with the dataset’s small size allowing for manual data correction. We used the developers’ English language model for handwriting as a base to bolster our training dataset. Late Douglass was then applied across the full text to produce a 12,642-word output and again, due to the size of the dataset, was manually corrected. The resultant data is also made available through Zenodo (10.5281/zenodo.17143899), with our model shareable through Transkribus by contacting the corresponding author.  

As comparison, we also include Helen Pitts's 1886 travel diary, written on the accompanying voyage, through uploading Emerson (2003, 134 - 180) into Transkribus and using a pre-trained base model for print text recognition. This resulted in a character accuracy of 87.94%. As with DD, the manageable size of the dataset enabled manual correction before performing any network analysis. 

-- Network Analysis

To uncover the networked structure of co-occuring terms in both diaries, we used Gephi, due to it requiring limited programming expertise and following established methods for digital archive research with HTR outputs. This involved using Regular Expressions to split and reassemble each diary based on their entry dates, before standardising these dates into the ISO YYYY-MM-DD format. After this, we used spaCy (http://spacy.io), an open-source Python library, to perform Named Entity Recognition (NER) of key persons, events, places and organisations. Fuzzy pattern matching was also used to limit the manual correction of duplicate nodes.

By demonstrating the ability of distant reading approaches, coinciding with traditional scholarship, this project serves as an example of leveraging automation for historical research on text-based library collections.

# Credits 

We would like to emphasise again the foundational digitisation of the LoC Manuscript Division. 

Dr Joe Nockels (corresponding author, j.nockels@sheffield.ac.uk) - Conceptualisation, Methodology, and Lead on Research Paper Writing and Review
Dr Ash Charlton (University of Edinburgh, History, Classics and Archaeology) - Conceptualisation, Methodology, and Research Paper Writing and Review
Prof Melissa Terras (University of Edinburgh, Edinburgh College of Art) - Conceptualisation, Methodology, and Research Paper Writing and Review

R text analysis approaches were also applied to Douglass's unpublished and published autobiographical works, see the aligned repository - https://github.com/jnockelsss/Douglass-Project-LoC-2024 for the datasets used, and the paper: 

Nockels, J., Nguyen, G., Charlton, A., Terras, M. (2025). 'God on the Stage: A Text Analysis of Frederick Douglass's Religiosity (1845 - 1887)', International Journal of Humanities and Arts Computing, 19(2), https://doi.org/10.3366/ijhac.2025.0352
