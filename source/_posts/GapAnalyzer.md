---
title: Gap Analyzer
date: 2017-05-03 16:23:18
tags:
cover_image: images/cloudsat_gapdetector.jpeg
---

I created this program for CIRA to help detect gaps in the data for the CloudSat satelite in the database located in Fort Collins, CO. The database included the original files from the satelite, and many conversions of that original data into different data formats used by different atmospheric scientists. To convert from one data type to another, certain kinds of files were needed. For example, to create data type GEO, you need just the original data. But to create another data, for example, THERMAL, you need both the original data file and the GEO file. If one of those was missing, you could not create THERMAL. This created a tree like structure, where the children were formed from the parents, and 

As CIRA was doing a data inventory, the scientists needed to know which data was missing from the database and why. My program queried the database, and gathered the information it needed from the database. Then it analyzed all the data it gathered. If there was a file that was missing, the program would recursively search for its parent files. From the recursion search, the program would determine why the file was missing - whether it was an algorithm error (aka, the original data from the satelite existed, but somewhere a conversion didn't happen, causing this file to not be made) or whether this file was missing because the original satelite data was missing. The program would search based on a tree structure file given to it.

As the program ran, it would print out all the files missing, all of its parent files missing, and determine which file was the root cause of the problem, to help the scientists know which data they needed to get and how they could get it.

This program also ran in under a minute, the majority of the time being spent on querying the database for the data, which it then put into a set so that no more queries to the database were needed.

You can find the sourcecode at https://github.com/pbstrein/CIRA_gap_analyzer