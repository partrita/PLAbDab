# About this fork

This GitHub repository contains the full sequence information of antibodies registered in the original PLAbDab database, included as a CSV file. While the original database only included sequences for VH and VL, I was interested in sequences related to the Fc or hinge regions and ultimately obtained them through web scraping. However, a few entries could not be found and were left blank. I hope this will be useful to others with similar interests.

---

<div align="center">    
 
# The Patent and Literature Antibody Database (PLAbDab): an evolving reference set of functionally diverse, literature-annotated antibody sequences and structures

---
    
by 
Brennan Abanades $^{1,\dagger}$, Tobias H. Olsen $^{1,\dagger}$, Matthew I. J. Raybould $^{1}$ Broncio Aguilar-Sanjuan $^{1}$, Wing Ki Wong $^{2}$, Guy Georges $^{2}$, Alexander Bujotzek $^{2}$, and Charlotte M. Deane $^{1,*}$

$^{1}$ Oxford Protein Informatics Group, Department of Statistics, University of Oxford, Oxford, United Kingdom  
$^{2}$ Large Molecule Research, Roche Pharma Research and Early Development, Roche Innovation Center Munich, Penzberg, Germany  
$^{\dagger}$ These authors contributed equally to this work and share first authorship  
$^{*}$ To whom correspondence should be addressed  
</div>



## Abstract
Antibodies are key proteins of the adaptive immune system, and there exists a large body of academic literature and patents dedicated to their study and concomitant conversion into therapeutics, diagnostics, or reagents. These documents often contain extensive functional characterisations of the sets of antibodies the describe. However, leveraging these heterogeneous reports, for example to offer insights into the properties of query antibodies of interest, is currently challenging as there is no central repository through which this wide corpus can be mined by sequence or structure.

Here, we present PLAbDab (the Patent and Literature Antibody Database), a self-updating repository containing over 150,000 paired antibody sequences  and 3D structural models, of which over 65,000 are unique. Each entry in the database also contains the title and authors of its literature source. Here we describe the methods used to extract, filter, pair, and model the antibodies in PLAbDab, and showcase how PLAbDab can be searched by sequence, structure, or keyword.

PLAbDab uses include annotating query antibodies with potential antigen information from similar entries, analysing structural models of existing antibodies to identify modifications that could improve their properties, and compiling bespoke datasets of antibody sequences/structures known to bind to a specific antigen. PLAbDab is freely available via Github (https://github.com/brennanaba/PLAbDab) and as a searchable webserver (https://opig.stats.ox.ac.uk/webapps/plabdab/).

## Usage

To use the PLAbDab python package you must first download a copy of the database. This can be obtained from  <a href="https://opig.stats.ox.ac.uk/webapps/plabdab/static/downloads/plabdab_data.tar.gz">here.</a> The file will come in a compressed format. Once extraxcted, you can point your version of PLAbDab to it as follows:

```python
from PLAbDab import PLAbDab

plabdab = PLAbDab(data_directory, n_jobs = 10)
```

This ''plabdab'' object can then be used to perform searches. PLAbDab will output a pandas dataframe for each search. For more info on how to use the API, please check the notebooks. 

## Install

PLAbDab requires <a href="https://github.com/brennanaba/ImmuneBuilder">ImmuneBuilder</a> to do the structure search. To install it please follow the instructions on the <a href="https://github.com/brennanaba/ImmuneBuilder">ImmuneBuilder repo.</a>

Once ImmuneBuilder and all its dependencies are installed, PLAbDab can be installed by running the following command in the PLAbDab directory:

```bash
$ pip install .
```

## Citing this work

The code and data in this package is based on the <a href="https://www.biorxiv.org/content/10.1101/2023.07.15.549143v1">following paper.</a> If you use it, please cite:

```tex
@article{abanades2023patent,
  title={The Patent and Literature Antibody Database (PLAbDab): an evolving reference set of functionally diverse, literature-annotated antibody sequences and structures},
  author={Abanades, Brennan and Olsen, Tobias Hegelund and Raybould, Matthew IJ and Aguilar-Sanjuan, Broncio and Wong, Wing Ki and Georges, Guy and Bujotzek, Alexander and Deane, Charlotte M},
  journal={bioRxiv},
  pages={2023--07},
  year={2023},
  publisher={Cold Spring Harbor Laboratory}
}
```

