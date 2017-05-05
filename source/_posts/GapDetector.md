---
title: Gap Detector
date: 2017-05-03 16:23:02
tags:
cover_image: images/gap_detector.jpg
---

I created this program to help one of the people on my team, Heather. She had to manage a lot of data from the CloudSat and Calipso (two satelites that collected data for atmosphere scientists.) CIRA at the time was doing a data inventory, organizing and listing what data they had and didn't have. Heather needed to know which data was missing from her dataset. She asked me to write a program for her. 

My program read the files that she had on her computer, and looked at the timestamps on the data, and if there was any data that had very large gaps, I would create a text file saying which files were missing and when, and when the program finished, I would calcuate how many files were missing based on the size of the gaps, and display the total number of files missing and the number of files missing during each month. That way she could check to see if there were no data files at all (aka the satelite was down) or if somehow the data just did not get sent to her. 

My program could run with commandline arguments or with user interaction in the console. The user would have to give the folder location of the files, the output location of the textfile, the type of file is should be looking for, and how long each orbit of the satelite was supposed to be in seconds.

The source code can be found at https://github.com/pbstrein/CIRA_gap_detector.