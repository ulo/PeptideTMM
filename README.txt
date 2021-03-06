### Welcome to PeptideEclipse
PeptideEclipse allows you to map your proteomics peptide identifications to transmembrane regions as annotated in UniProt, 
and thus showing which peptides were completely or partially hidden within the lipid bilayer.

Homepage: http://ulo.github.io/PeptideEclipse/

### Input
First, download the corresponding UniProt Knowledgebase packages from their FTP server:

ftp://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/taxonomic_divisions/

Note: you do not have to unzip the files!

Then just provide the ProteinProphet output, either the complete `prot.xml` file or a filtered and exported `prot.xls` file.

### Command
To run PeptideEclipse type the following into your command line:
```
java -jar PeptideEclipse.jar -in inFile -up uniprot1.dat.gz [uniprot2.dat.gz ...] > outFile
```
* inFile: a ProteinProphet file (e.g: interact.prot.xml | interact.prot.xls)
* outFile: target file (e.g: interact.prot.tmAnalysis.tsv)

### Output
For a `prot.xml` file input, PeptideEclipse will generate a tab-separated file (open using Excel) with the following columns:
```
group_number	protein-group number
group_probability	protein-group probability
protein_name	name of first protein
protein_peptides	number of peptides
protein_pct_spectrum_ids	percent of total spectral counts
protein_percent_coverage	percent of protein sequence coverage
peptide_sequence	stripped peptide sequence
peptide_sequence_modified	modified peptide sequence
peptide_charge	peptide charge state
peptide_nsp_adjusted_probability	peptide probability
peptide_n_enzymatic_termini	number of proteolytic termini
peptide_calc_neutral_pep_mass	neutral theoretical peptide mass
proteinID	matching UniProt ID
protein_transmemRegions	UniProt transmembrane domain count
protein_AA	length of protein
protein_AA_covered	length of protein covered by peptides
protein_AA_transmem	length of protein's TM region(s)
protein_AA_transmem_covered	length of protein's TM region(s) covered by peptides
peptide_AA	length of peptide
peptide_AA_transmem	length of peptide's TM region(s)
```
For a `prot.xls` file input, PeptideEclipse will create a copy of the input file with the following columns appended:
```
peptide_AA	length of peptide
peptide_AA_transmem	length of peptide's TM region(s)
proteinID	matching UniProt ID
protein_transmemRegions	UniProt transmembrane domain count
protein_AA	length of protein
protein_AA_covered	length of protein covered by peptides
protein_AA_transmem	length of protein's TM region(s)
protein_AA_transmem_covered	length of protein's TM region(s) covered by peptides
```

### Dependencies
All dependencies are packed within the `PeptideEclipse.jar` file. No external dependencies are needed!
Internally, PeptideEclipse depends on two libraries:
* Apache Commons CLI: http://commons.apache.org/proper/commons-cli/
* Google Guava: http://code.google.com/p/guava-libraries/

### Credits
PeptideEclipse was developed by Ulrich Omasits, and was published as part of a proteomics study.
Please cite [Waas et al. Anal Chem. 2014 Feb 4;86(3):1551-9](http://www.ncbi.nlm.nih.gov/pubmed/24392666).

### License
PeptideEclipse is licensed under a Creative Commons Attribution 3.0 Unported License.
