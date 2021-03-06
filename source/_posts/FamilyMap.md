---
title: Family Map
date: 2017-05-04 12:37:59
tags:
cover_image: images/family_map_client.jpg
thumbnailImage: family_map_client.jpg
autoThumbnailImage: yes
coverImage: family_map_client.jpg
thumbnailImagePosition: right
coverSize: partial
coverCaption: I'm a caption
coverMeta: out
---

Family Map was a project for my CS240 class at BYU. That class had only major projects - the family map server and the family map client, and they were related to each other.

## Family Map Client
I created an Android App (a preview seen in the picture above) that would display the family relationships of a user. The information was generated by the Family Map server. I created an app that would be able to respond to user interaction, used asycrous tasks to communicate with the server, and that followed a MVC (model-view-controller) pattern. I learned about a lot of Android terms and coding practices, including - views, fragments, textviews, recyclerviews, Google Map Fragments, and more.

## Family Map Server
I created a server in Java that would communicate to the Family Map Client. It used a SQLite database, and followed good software principles.
1. Single Responsibility Rule - we had to divide our code into multiple classes that did one thing. Ihad a ServerProxy class that would act as the Client and make calls to the server by taking arguments, making them into JSON, and creating an HTTP connection to our server with the JSON. I also created HttpHandlers, which would parse the JSON, turn it into Java models, and give those models to the server's services. There were services for each of my API calls which would do all the algorithmic work that was needed for the API. And finally I created DAOs (Data Access Objects) whose primary job was to communicate to the SQLite database. 
2. Unit testing - for my DAO objects and my Server Proxy, I created unit tests that made sure that each class and its public methods worked as it should. These unit tests then could be used for regression testing, to make sure that the project didn't break along the way.
3. Reduced code duplication - I reduced code duplication by making sure that repeated work was put into functions, and if needed, I used inheritance and polymorphism to reduce more code duplication. The inheritance was primariliy used for catching and handling any and all errors that would occur while the server was being run.