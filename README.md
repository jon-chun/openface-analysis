# OpenFace Analysis Repository
A project under the Study of Adolescent Neural Development

This is the order that you need to run all the files in:
1. OpenFacePrep: This pulls raw Cold Press files straight from OpenFace, removes everyone that needs to be excluded, and smushes them together into a file called "cp_full.csv".
2. OpenFaceFixingCortisol: This pulls the raw cortisol .csv, properly transforms relevant variables, and spits out a corrected file called "cortisol.csv". 
3. OpenFaceEmotion: This takes the "cp_full.csv" file, takes the AU data, and calculates the following emotions: anger, fear, happiness, sadness, and pain (although pain isn't technically an emotion). 
4. OpenFaceProgress: This takes several relevant files (facial data, cortisol, CTQ, demographics, etc.), matches them by id number, and spits out a file called "cp_joined.csv". 
5. OpenFaceReformat: This takes "cp_joined.csv" and turns it from a wide format into a long format. This file should be run directly after OpenFaceProgress and will generate a file called "cp_long.csv". 

After the above files are run, you can run the below files. 

Files that are related to analysis:
- OpenFaceAim1: It conducts analysis relating to Aim1. Will utilize "cp_joined.csv" and "cp_long.csv".
- OpenFaceAim2a: It conducts analysis relating to Aim2a, mostly modelling. Will utilize "cp_long.csv".
- OpenFaceAim2b: It conducts analysis relating to Aim2b. Will utilize "cp_joined.csv" and "cp_long.csv". 

Files that are related to descriptive statistics:
- OpenFaceDeStatCTQ: This runs descriptive statistics on CTQ data. Should be run directly after OpenFaceProgress. Does not change data in any way. 
- OpenFaceDeStatCort: This runs descriptive statistics on the cortisol data. Should be run directly after OpenFaceProgress. Does not change data in any way. 
- OpenFaceDeStatFacial: This runs descriptive statistics on the facial expression data. Should be run directly after OpenFaceProgress. Does not change data in any way. 

Notes to self: 
- There's no age, puberty, or race/ethnicity anywhere at the moment, so you might want to add that in somewhere. You could add it to OpenFaceProgress but then everything after would have to be adjusted a bit. Or you could add it directly in OpenFaceReformat but that might be difficult. 
- You need to adjust the first/last lines of every .rmd file depending on where you're running it from i.e. correct the paths.
- Files that you need to have on hand before beginning: cortisol_original, ctq, gender, and medication. 
