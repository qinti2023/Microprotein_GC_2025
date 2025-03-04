# The Genetic Code's Inherent Bias Shapes the Folding and Stability Landscapes of Microprotein
This repository contains Python code and shell script to reproduce the results presented in the manuscript “**The Genetic Code's Inherent Bias Shapes the Folding and Stability Landscapes of Microprotein**” 
## Long-Range Interactions Calculation
### Layout
`long_interactions/pdb_to_cm.py : ` Simple Python script for computing protein contact maps from PDB files as described in Godzik and Skolnick, (1994). An edge is added between all non-adjacent pairs of amino acids where the euclidean distance between their alpha carbons are less then some threshold. <br>
`long_interactions/batch_calculate_cm.sh : ` This shell script automates batch processing of PDB files, executing `pdb_to_cm.py` to calculate the proportion of residues with long-range interactions in each protein structure.
### Usage
Compute the contact map for 1BPI with a threshold of 7.5 ångström.
```
python pdb_to_cm.py 1bpi.pdb 1bpi.cm -t 7.5
```
The batch calculation can be executed by modifying the protein structure folder path in batch_calculate.sh, followed by running the script.
```
sh batch_calculate_cm.sh
```
### Reference
> Godzik A, Skolnick J. Flexible algorithm for direct multiple alignment of protein structures and sequences. Computer applications in the biosciences: CABIOS. 1994 Dec 1;10(6):587-96
