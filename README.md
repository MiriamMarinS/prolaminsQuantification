# prolaminsQuantification
Processing multiple csv output files from high-reverse phase liquid chromatography software for quantification of wheat prolamins.

For initiate the script first prepare a directory with all the output files of the HPLC software in it.

The format of input file has to be the same that the output of the software Instrument 1, with the follow structure:
Retention time (min), area (mAu)

The files have to be named as follow:
The name has to contain 'GLI' or 'GLU' for detecting type of protein family.

It is required file with the weight of the grain used for extraction. This file has to be in the same directory that the other files, in csv format and named with the word 'peso' in it name. The structure of this file has to be:

Sample name*, weight (mg)

*The sample name has to be equal that ones in the other input files.

The command line for execute the script:

>python prolamins_area_to_excel.py \<options>
  
Options:

>-h | --help <display arguments>

>-m | --microgramo \<units of the output data, 'mg' for micrograme of protein/miligrame of flour, 'grano' for micrograme of protein/grain>

>-d | --directory \<path of the directory that contains csv files>

>-v | --volumen \<volumen of extraction in microliters>

>--debug \<display debug comments, default False>
 
All the options are required, except for -h and --debug ones.
 
The output file is a xlsx with the protein content in the unit selected and the average, standard desviation, standar error, ..., for all the samples. The recognition of the gluten fractions, family and replicates is done by regular expression methods.

This script was developed in Python 2.7.
