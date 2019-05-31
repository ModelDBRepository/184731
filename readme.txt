Simulation files and code for "Control of betaAR- and
N-methyl-D-aspartate (NMDA) Receptor-Dependent cAMP Dynamics in
Hippocampal Neurons" by Chay et al. in PLoS Computational Biology

The zip file contains
1. this file
2. A list of Model files, with brief explanation of parameter
combinations, is provided in ChayEtAl2015ModelList.xlsx
3. a tar file with 
	(A) all the xml files needed to simulate the models, 
	(B) The software for running the simulations is neuroRD,
	specifically stochdiff2.1.9.jar (provided).
	(C) python and C programs used for processing the output.
	
This software requires a single Model*.xml file as input.  Within the
Model files, the reactions (Rxn*.xml), morphology (Morph*.xml),
stimulation (Stim*.xml), initial conditions (IC*.xml) and output
molecules (IO*.xml) are specified.
Several files are used to process the output. 

1. NRDpostAB (provided) extracts single molecules into separate files
2. NRDpost.py will automatically create the input commandlines for
NRDpostAB, to extract Epac1 and Epac1cAMP; you'll need to enter by
hand the name of the output file, which should be an abbreviation, as
shown in NRDpostAutoEdited.bat
3. BatchFRET.py will take the output of NRDpostAB, and calculate the
Fret signal, plotted as traces in many of the figures
4. Fret_peaks.py will take the output of BatchFRET.py (i.e., the
fret.txt files) and extract the peak and difference between NMDA after
ISO, and NMDA alone; specific file name pairs must be specified.
These values are used in the bar graphs.
5. An example of how to extract other molecules is provided in
NRDpostMol.bat
6. SumMoleculeForms.py will sum different forms of PKAc, or pPDE4 as
desired (need to edit lines near top of the python program).
NRDpostMol.bat and SumMoleculeForms.py were used to create the figure
panels showing e.g. pPDE4 or PKAc activity.
