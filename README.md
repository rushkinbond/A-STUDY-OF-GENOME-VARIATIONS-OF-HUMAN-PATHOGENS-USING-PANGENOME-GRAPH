# A-STUDY-OF-GENOME-VARIATIONS-OF-HUMAN-PATHOGENS-USING-PANGENOME-GRAPH
## Introduction to the project
Our project aims to focus on exploring the pangenome concept, moving away from the reliance on a single reference genome to delve deeper into genetic variations. It involves the creation of pangenome graphs for specific COVID-19 variants (Alpha, Beta, Delta, and Omicron) observed across multiple countries. Additionally, our project aims to construct a pangenome graph for a single country that includes the Alpha, Beta, and Omicron variants. The project also intends to identify and analyze structural changes between two GFA (Graphical Fragment Assembly) files.

#### Pangenome Concept Exploration:

Emphasis on the concept of pangenomes over the use of a single reference genome.
Highlighting the significance of pangenome graphs in capturing genetic variations among different variants of the COVID-19 virus.

#### Pangenome Graph Generation:

Creation of pangenome graphs for distinct COVID-19 variants (Alpha, Beta, Delta, and Omicron) observed across various countries.
Development of a specific pangenome graph for a single country that encompasses the Alpha, Beta, and Omicron variants.

#### Analysis of Genetic Variations:

Examination of the structural changes between two GFA files to identify variations in the genetic composition of the different variants.
Identification and characterization of unique genetic features or alterations specific to each variant or country-specific pangenomes.

#### Methodology:

Detailing the methodologies used to construct pangenome graphs, analyze GFA files, and detect structural changes.
Description of the computational tools, algorithms, or bioinformatics techniques utilized for data processing, graph generation, and comparison.

#### Data Representation and Visualization:

Visualization of pangenome graphs using suitable software or tools to represent the genetic relationships and variations between different variants and countries.
Presentation of comparative analyses through visual aids, charts, or diagrams to illustrate the differences in genetic structures.

## Install all the necessary tools requried for this project
1) minigraph - This tool is used to generate a pangenome graph with help of a reference genome.
   download the tool from https://github.com/rushkinbond/minigraph
2) vg tool - this tool is used to identify structural changes in vg format. 
   download the tool from https://github.com/rushkinbond/vg
3) seqwish and wfmash - These tools are used to convert fasta files to gfa files.
   download the tools from https://github.com/rushkinbond/seqwish and https://github.com/rushkinbond/wfmash
4) bandage - This tool is used to visualize the pangenome graph
   download the tool from https://github.com/rushkinbond/Bandage
5) Mumer3 - This tool is used to find structura variation in fasta files.
   download the package from https://github.com/rushkinbond/MUMmer3
6) gfatools - This tool is used to convert gfa to fasta 
   download the package from https://github.com/rushkinbond/gfatools
   
## Commands to Construct a pangenome with help of reference genome by minigraph
   ./minigraph -cxggs -l10k referencefile.gfa file1.fa file2.fa > output.gfa

## Commands to Construct a pangenome when we have fasta files

### when we have single fasta file 
   wfmash file1.fa file1.fa -X > file1.paf
   seqwish -s file1.fa -p file1.paf -g file1.gfa
   
### when we have multiple fasta files and we want to get one gfa file from it 
   wfmash c.fa a.fa > a.paf
   wfmash c.fa b.fa > b.paf
   cat a.fa b.fa c.fa > abc.fa
   seqwish -s abc.fa -p a.paf,b.paf -g abc.gfa

### finding variation graph with help of vg tool the commands are
   vg view -AJ file1.gfa > file1.vg
   vg view -AJ file2.gfa > file2.vg
   vg combine file1.vg file2.vg > file.vg
   vg view file.vg > file.gfa

   #### or 
   cat file1.gfa file2.gfa > merged_modified.gfa
   vg view -AJ merged_modified.gfa > merged_modified.vg
   vg view merged_modified.vg > final_file.gfa

### 

