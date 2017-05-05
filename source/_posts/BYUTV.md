---
title: BYUTV3
date: 2017-05-04 11:50:17
tags:
cover_image: images/byutv_logo.jfif
---


byutv.org is the digital media platform that BYU Broadcasting uses to distribute all their digitally available content. 

BYUTV2 was version 2 of the website, and BYUTV3 is the version 3 of the website. BYUTV3 was meant to be newer, responsive, mobile friendly, and more capable of new customer demands. It focused on having lists to display the content. 

<div class="col-12 mb-4">
    <p class="portfolio-content-center"> BYUTV2 </p>
    <img class="img-fluid post-img" src="/images/tv2_screenshot.jpg">
</div>
<div class="col-12 mb-4">
    <p class="portfolio-content-center"> BYUTV3 </p>
    <img class="img-fluid post-img" src="/images/tv3_screenshot.jpg">
</div>

I came as a developer for the platform of the BYUTV3 website. I developed with tools such as Git, Jira, BitBucket, SourceTree, Visual Studio, and ElasticSearch. I developed using C#, using Cassandra as the database to store all the data. 

As part of the platform group, all of our work was to help our UI group and Content Management Group (CMS) get all the data they needed to create a responsive and dynamic website. 

My work included:
1. Developing and maintaining over 200 APIs. 
    1. I created APIs to make, get, and delete youtube items from our database. 
    2. I created an API that would save multiple images to our database. We previously had an API that would upload one image, but our CMS wanted to upload multiple images. I coordinated with the CMS team to make sure that our API would read in the right information, and that it would give a correct error message if something went wrong. Due to the nature of the API, if an error occured while uploading an image, the API would continue to upload the other images, while noting that an error occured. At the end of uploading all the images, a new error would be given to the CMS telling them which images had errors. 
2. Using multithreading and asyncounsly programming to optimize the GetListItems API call, reducing it from a 16 second call to a 0.5 second call. In our catalog, we had over 7000 episodes, and we would need to convert them to different models based on the needs of our client. When the list we wanted to get had 15 or fewer items, it was relatively quick. However, if the list had hundreds of items, it took a long time to do it sycronusly. I updated code so that it could read a Cassandra Database asycrously and convert the data from one model type to another asycrounsly, dramatically reducing the call time of the API.