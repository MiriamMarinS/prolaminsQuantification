# prolaminsQuantification
Processing of multiple csv output files of the high-reverse phase liquid chromatography software for the quantification of wheat prolamins.

To start the script, first prepare a directory with all the output files of the HPLC software. These will be the input files.

The format of input file must be the same as that of Instrument 1 software , with the following structure:
Retention time (min), area (mAu)

Files must be named as follows:
The name must contain 'GLI' or 'GLU' to detect the type of protein family.

File with the weight of the grains used for extraction is required. This file has to be in the same directory as the other files, in csv format and named as 'peso'. The structure of this file has to be:

Sample name*, weight (mg)

*The sample name muest be the same as the other input files.

The command line for execute the script:

>python prolamins_area_to_excel.py \<options>
  
Options:

>-h | --help <display arguments>

>-m | --microgramo \<units of the output data, 'mg' for micrograme of protein/miligrame of flour, 'grano' for micrograme of protein/grain>

>-d | --directory \<directory path containing csv files>

>-v | --volumen \<volumen of extraction in microliters>

>--debug \<display debug comments, default False>
 
All the options are required, except -h and --debug ones.
 
The output file is a xlsx with the protein content in the selected unit and the average, standard desviation, standar error, ..., for all the samples. The recognition of the files per gluten fractions, family and replicates is done by regular expression methods.

This script was developed in Python 2.7.
