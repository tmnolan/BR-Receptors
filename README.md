This repository contains the code to reproduce the analysis described in Brassinosteroid receptor genes safeguard cell-autonomous brassinosteroid signaling across tissues

## Arabidopsis Root Virtual Expression eXplorer (ARVEX)

Visit [ARVEX](https://shiny.mdc-berlin.de/ARVEX/) to interactively view the data associated with this study. 

## Data

The raw and processed scRNA-seq data are available at the NCBI GEO under accession [GSE212230](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE212230).

## Notebooks 

[BR-Receptor-01-CVP-Ref_Integration_v3_1](https://github.com/tmnolan/BR-Receptors/blob/292139501a476eff986ecc6d97b0ed5b0f6526ae/Notebook/BR-Receptor-01-CVP-Ref_Integration_v3_1.ipynb)

[BR-Receptor-02-CVP-Prep_RDS](https://github.com/tmnolan/BR-Receptors/blob/292139501a476eff986ecc6d97b0ed5b0f6526ae/Notebook/BR-Receptor-02-CVP-Prep_RDS.ipynb)

[BR-Receptor-03-CVP-muscat-DEG](https://github.com/tmnolan/BR-Receptors/blob/292139501a476eff986ecc6d97b0ed5b0f6526ae/Notebook/BR-Receptor-03-CVP-muscat-DEG_all_samples.ipynb)

[BR-Receptor-04-GL2-Ref_integration](https://github.com/tmnolan/BR-Receptors/blob/292139501a476eff986ecc6d97b0ed5b0f6526ae/Notebook/BR-Receptor-04-GL2-Ref_integration-7S_GL2_lines_20240129.ipynb)

[BR-Receptor-05-GL2-GFP-Prep_RDS](https://github.com/tmnolan/BR-Receptors/blob/292139501a476eff986ecc6d97b0ed5b0f6526ae/Notebook/BR-Receptor-05-GL2-GFP-Prep_RDS.ipynb)

[BR-Receptor-06-muscat_DEG_GL2_BRI1-GFP](https://github.com/tmnolan/BR-Receptors/blob/292139501a476eff986ecc6d97b0ed5b0f6526ae/Notebook/BR-Receptor-06-muscat_DEG_GL2_BRI1-GFP_cell_type_only.ipynb)

COPILOT filtering, label transfer, and integration are further described in [https://github.com/tmnolan/Brassinosteroid-gene-regulatory-networks-at-cellular-resolution/tree/main](https://github.com/tmnolan/Brassinosteroid-gene-regulatory-networks-at-cellular-resolution/tree/main) 

## Create custom genome for alignment

> library(BSgenome)

> forgeBSgenomeDataPkg("path/to/my/seed")

Depending on the size of the genome and your hardware, this can take between 2 minutes and 1 or 2 hours. 
By default forgeBSgenomeDataPkg will create the source tree of the target package in the current directory. 
Once forgeBSgenomeDataPkg is done, ignore the warnings (if any), quit R, and build the source package (tarball) 
with 

> R CMD build <pkgdir> 

where <pkgdir> is the path to the source tree of the package. 
Then check the package with

> R CMD check <tarball> 
 
where <tarball> is the path to the tarball produced by R CMD build.
Finally install the package with 
  
> R CMD INSTALL <tarball>


