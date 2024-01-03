# Style guide for Computational Ecology Lab Publications.
- Written by Robbie Diaz (Fraser Lab at UCSF) - last updated 01/05/23 (procrastinating thesis writing)
- Adapted by Miguel Lurgi (for the Computational Ecology Lab at Swansea) 03/01/2024

# Style Guide: Publications
## All sections
  - Indent with two spaces
  - Use double quotes for all string entries

# Title
- Only bold the first word and proper nouns
- Do not include a period at the end of the article title

# Authors
- Bold lab member names using the following format: **Last FM**
- Use one pair of double asterisks when multiple Fraser lab members appear sequentially: **Young ID, Diaz RE, Liu LL**
- Use &#42; to add an asterisk denoting co-first/corresponding author. Otherwise, bolding of names using **Surname FM** will break.
- Do not include a period at the end of the author list

# Images and PDFs
- All images and PDFs should be named using the following convention: "FirstAuthorSurname_YYYY"
- Leave PMID and PMCID blank until an ID is assigned.
- Remove any sections that are not relevant to your publication (PDB, data, Zenodo, Github repo, etc).

# Additional Links

# Example below
---
title: "Title of article"
authors: "**Surname FM**, Surname FM, **Lurgi M**"
journal: #"Journal Name" #Leave blank until accepted at journal
pub_date: #"YYYY-MM-DD" #Change from Biorxiv submission date to date accepted at journal
image: "/static/img/pub/YYYY_SurnameFirstAuthor.png" Minimum dimensions TBD
pmid: #"########"
pmcid: #"PMC#######"
biorxiv_version: "YYYY.MM.DD.######v1"
pdf: #Paste link to pdf here
pdbs:
  - #"PDB_ID" #PDB IDs must be in all caps
paired_maps_and_models:
  - pdb: #"PDB_ID" #PDB IDs must be in all caps
    emdb: #"#####"
paired_maps_and_models_and_data:
  - pdb: #"PDB_ID" #PDB IDs must be in all caps
    emdb: #"#####"
    empiar: #"#####"
data:
  - #"10.11577/1602169" #'doi:' prefix will be added automatically
zenodo:
  - code: #"3555658"
    description: #"qPTxM code at time of journal submission"
github:
  - url: #"computational-ecology-lab/code_repository_for_this_paper"
    description: #"qPTxM v3.0"
links:
  - name: "Dynamic of Complex Living Systems Lab @ CASUS, Germany"
    url: "https://www.casus.science/team-members/ricardo-martinez-garcia/"
  - name: "Theoretical and Experimental Ecology Station @ CNRS, France"
    url: "https://sete-moulis-cnrs.fr/en/"
  - name: "Centre for Marine Science and Innovation @ UNSW, Australia"
    url: "https://www.unsw.edu.au/research/cmsi"
---
