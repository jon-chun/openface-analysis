# OpenFace Analysis Repository
A project under the Study of Adolescent Neural Development


This is the order that you need to run all the files in:
1. OpenFacePrep: This pulls raw Cold Press files straight from OpenFace, removes everyone that needs to be excluded, and smushes them together into a file called "cp_full.csv".
2. OpenFaceFixingCortisol: This pulls the raw cortisol .csv, properly transforms relevant variables, and spits out a corrected file called "cortisol.csv". 
3. OpenFaceEmotion: This takes the "cp_full.csv" file, takes the AU data, and calculates the following emotions: anger, fear, happiness, sadness, and pain (although pain isn't technically an emotion). 
3. OpenFaceProgress: This takes several relevant files (facial data, cortisol, CTQ, demographics, etc.), matches them by id number, and spits out a file called "cp_joined.csv". 
4. OpenFaceReformat: This takes "cp_joined.csv" and turns it from a wide format into a long format. This file should be run directly after OpenFaceProgress and will generate a file called "cp_long.csv". 
5. OpenFaceAnalysis: This is where actually analysis occurs and conducts multilevel growth curve modeling on "cp_long.csv".  

Files that aren't explicitly part of the protocol: 
- OpenFaceDeStatCTQ: This runs descriptive statistics on CTQ data. Should be run directly after OpenFaceProgress. Does not change data in any way. 
- OpenFaceDeStatCort: This runs descriptive statistics on the cortisol data. Should be run directly after OpenFaceProgress. Does not change data in any way. 
- OpenFaceDeStatFacial: This runs descriptive statistics on the facial expression data. Should be run directly after OpenFaceProgress. Does not change data in any way. 


