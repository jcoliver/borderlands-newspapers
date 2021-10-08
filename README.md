# Collections as Data

This repository hosts Python code for downloading and assembling scanned OCR 
text from a collection of southwestern U.S. borderlands newspapers. The texts 
were initially downloaded as part of the project _Using Newspapers as Data for 
Collaborative Pedagogy: A Multidisciplinary Interrogation of the Borderlands in 
Undergraduate Classrooms_, funded in part by the Mellon Foundation through the 
[Collections as Data](https://collectionsasdata.github.io/part2whole/) program. 
More information about the project is available found at 
[https://libguides.library.arizona.edu/newspapers-as-data](https://libguides.library.arizona.edu/newspapers-as-data).

If you would like to try out text mining the corpus, another repository 
[https://github.com/jcoliver/dig-coll-borderlands](https://github.com/jcoliver/dig-coll-borderlands) 
hosts Jupyter Notebooks introducing text data mining with Python.

## The work focuses on the following titles:
+ _Arizona Post_, a Tucson newspaper by and for the Jewish community
+ _Arizona Sun_, an African American newspaper published in Phoenix
+ _Apache Sentinel_, published by African American soldiers stationed at Fort 
Huachuca
+ _Bisbee Daily Review_, a newspaper published in Bisbee, a mining town at that 
time
+ _Border Vidette_, a newspaper published in Nogales, Arizona, on the border 
with Nogales, Mexico
+ _Phoenix Tribune_, the first African American newspaper published in Arizona
+ _El Sol_, a Spanish-language, Mexican American newspaper published in Phoenix
+ _El Tucsonense_, a Spanish-language, Mexican American newspaper published in 
Tucson

The text for these newspapers is available at 
[Chronicling America](https://chroniclingamerica.loc.gov/newspapers/). 
Downloads of the texts used the API, documented at 
[https://chroniclingamerica.loc.gov/about/api/](https://chroniclingamerica.loc.gov/about/api/).

## Data preparation scripts
1. download-pages.py: Download files via the Chronicling America API. Pages are 
in the "pages" folder within an individual title's folder. For example, pages 
for _El Tucsonense_ are downloaded to 'el-tucsonense/pages'. File names reflect 
the date, in YYYYMMDD, and the page number; e.g. page 2 of _El Tucsonense_'s 
paper from January 3, 1925 is stored as 19250103-2.txt.
2. assemble-volumes.py: Assemble text file for a single day's newspaper by 
concatenating all individual pages for a particular day/title combination. The 
text for each day's paper is stored in the 'volumes' folder for each title. For 
example, the text for the January 3, 1925 issue of _El Tucsonense_ is located 
in data/el-tucsonense/volumes/19250103.txt.
3. retrieve-complete.py and retrieve-complete.sh: Python and bash scripts for 
downloading full data set from the 
[University of Arizona Research Data Repository](https://arizona.figshare.com/). 
These scripts download the archive file from the data repository and extract 
the contents to data/complete. Both scripts accomplish the same thing, they 
differ only in language used.
