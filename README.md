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

Notes to self: 
- There's no age, puberty, or race/ethnicity anywhere at the moment, so you might want to add that in somewhere. You could add it to OpenFaceProgress but then everything after would have to be adjusted a bit. Or you could add it directly in OpenFaceReformat but that might be difficult. 
- Pretty much every time you load in a .csv file, you have to df$X <- NULL and I don't know why Excel keeps doing this!!!
- You need to adjust the first/last lines of every .rmd file depending on where you're running it from i.e. correct the paths.
- Landmark registration of the cortisol values needs to be stuck somewhere, probably in OpenFaceFixingCortisol. 
- As of 12/14/2018, OpenFaceEmotion just has placeholder emotion values so DON'T forget to properly adjust those once you finish your lit review.
-You should add the "Responder" variable in OpenFaceReformat, probably
