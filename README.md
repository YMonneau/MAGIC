# MAGIC
MAGIC methyl assignment and dataset

!!!!!!!!! Needs Anaconda python2.7 installed: https://www.anaconda.com/download/ !!!!!!!!

_________________________________________________________________________________________

############## STEP 1:
Put all files in the same directory and open the terminal

Input files:
- 2D peak list
- 3D peak list
- PDB file
- sequence of the construct
- parameter file (start.txt)
- Magic_4.0.py

IMPORTANT TIPS: Make sure all files are well formatted according to the exmaple files

############## STEP 2:
type the following command:

>python generate.py [2D peak list file name] 
                    [construct sequence file name, fasta format]
                    [labeling, e.g. AILMTV]
                    [starting sequence number, e.g. 48]
                    [CCH short mixing time peak list] - optional
                   
e.g. python generate.py hmqc.list seq.fasta AILMV 48

issued files:
- Formated 2D peak list (e.g. new_hmqc.list)
- Formated methyl list (e.g. seq.auto)

############## STEP 3:

Edit the issued 2D peak list according to known geminal methyl pairs and methyl types.
Fill the parameter file up (file pathways, labeling and setting parameters)

STANDARD SETTING (see start.txt):
##ppm tolerance (13C,13C,1H):
0.1 0.1 0.01
##score threshold factor:
1
##Distance threshold:
7 10
##Score tolerance for one-by-one step (off or on):
off

############## STEP 4:

type the following command to run automatic assignment:

>python Magic_4.0 start.txt

############## Output files:

The generated folder contains three different folder:

- input folder for your record
- output folder, continuously edited, containing the current assigned 2D and 3D peaklist 
      along with the mapping file to visualize onto the pdb structure the quality 
      of the running assignment
- run folder, which contains all intermediate files used by the software

_________________________________________________________________________________________

############## TRIALS:

Put the magic_4.0.py in one of the demo directories (either Abl or MBPs).
run with the command:

>python Magic_4.0 start.txt

Abl_RD demo directory contains the M mode the MG mode and the G mode start scripts.
M=methyl type specified
MG=methyl & geminal LV specified
G=geminal LV specified

############## IMPORTANT TIPS:
