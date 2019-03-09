# OpenFace Analysis Repository
**A project under the Study of Adolescent Neural Development**

## Instructions

Before running anything, make sure you put these files somewhere so they can be called upon: cortisol_original.csv, ctq.csv, gender.csv, medication.csv, and threatdep.csv. Now run the files in this order:

1. OpenFacePrep: This pulls raw Cold Press files straight from OpenFace, removes everyone that needs to be excluded, and smushes them together into two files called "cp_full.csv" and "cp_master.csv". 
2. OpenFaceCortisol: This pulls the raw cortisol data (cortisol_original.csv), properly transforms relevant variables, and spits out a corrected file called "cortisol.csv". 
3. OpenFaceEmotion: This takes the "cp_full.csv" and "cp_master.csv" files, takes the AU data, and calculates anger, fear, happiness, sadness, and pain.
4. OpenFaceProgress: This takes several relevant files (facial data, cortisol, CTQ, demographics, etc.), matches them by id number, and spits out a file called "cp_joined.csv". After you run this file, you can run any of the files in the destat folder, as they solely run descriptive statistics. These "DeStat" files do not change the data in any way. 
5. OpenFaceReformat: This takes "cp_joined.csv" and turns it from a wide format into a long format. This file should be run directly after OpenFaceProgress and will generate a file called "cp_long.csv".
6. OpenFaceAnalysis: This actually starts meaningful analysis in the form of mixed models. Utilizes the nlme() and lme4() packages. Currently a work-in-progress.
7. OpenFaceExplanation: Located in the other folder. Explain my choices and experiments with models with random intercepts/slopes, different packages, and optimization. 

## Notes to self
- Need to add more demographic variables to OpenFaceProgress and OpenFaceReformat
