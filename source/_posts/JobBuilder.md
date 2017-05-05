---
title: Job Builder
date: 2017-05-03 16:22:38
tags:
cover_image: images/data_conversion.jpg
---

This program was part of a bigger picture at CIRA. CIRA has the CloudSat, is a satelite collecting data and sending it down every 90 minutes to CIRA. CIRA takes that original data and converts it into many other data types. JobBuilder is the pretty much the queue-maker for that data conversion. It creates "jobs" based on the data file given, and a configuration job, and it creates a job to be sent to the queue to be converted by a different program. The program had to query a MySQL database, find the datafiles it needed, and if the files existed, it would create a job with the specifications so that the converter could get the right files and convert them to the file needed.

CIRA had this program already in PHP, but they wanted to have a program with similar functionality in Python, so I created a script, following what they did, making minor changes for the change in the language.

You can find the source code for this at https://github.com/pbstrein/CIRA_jobbuilder