---
layout: post
title: BlocChat
thumbnail-path: "img/blocflix.png"
short-description: BlocChat is a real-time chat application.

---

{:.center}
![]({{ site.baseurl }}/img/blocflix.png)

## Summary

    Communication is one of the most valuable aspects of our society. The ease with which the internet allows us to communicate has been the driving force behind the technological revolution that we've experienced in our lifetimes. When it comes to messaging, simplicity and performance are key and BlocChat aims to provide both of these to the consumer.

## Explanation

    BlocChat is a Single Page Application, developed using an AngularJS framework along with UI bootsrap, and utilizing Firebase as a real-time database. The main purpose of this project was to really gain a better understanding of the AngularJS framework, including mastering the dynamic between controllers and services that make the framework so powerful. This project also served as my first experience using a real-time database such as Firebase, which allowed me to dip my feet into the backend of web development. With these experiences, the hope is that I would be able to independently develop a similar web application using these resources.

## Problems + Solutions

    While this project was meant to put into practice all I've learned about AngularJS, HTML, and CSS, I still ran into a few new obstacles...

    Firebase is a real-time, non-relational database, a new concept for me as I had only previously worked with static, relational databases in previous projects. For functionality purpose, the dynamic aspect of this database is necessary for a chat room application such as BlocChat as it allows the user to add/delete rooms and messages in "real-time". The trickiness in this dynamic is referencing the database in the application in a way that works and is intuitive. An important detail in AngularJS is that all references to the database should be in the services. While you might be able to get away with referencing Firebase in your controller (as I tried to do), Angular's purpose is to isolate these data references in order to make updating the code as easy as possible. Understanding this concept, has been one of my first ventures into thinking about how the application will be managed in the future instead of solely focusing on if the code works when its created. I look forward to focusing on this important concept in the future to ensure the quality perfomance of my applications and differentiate myself from other developers.

    The second obstacle I ran into, using Modals for the user-entry pop up windows, seemed daunting at first having never seen it before. However, after reading more about UI Bootsrap's $uibModal service I was able to wrap my head around its implementation. The $uibModal service is actually rather simple in that it only has one method: $uibModal.open() and several properties in which you can control attributes of the Modal. After implementing this method to get the Modal window open, I was faced with the problem of finding the method to close this window, given that $uibModal only has the open() method. Through research on sites such as StackOverflow, I found the $uibModalInstance service which has a close() method that solved this problem.

    A third problem we had was being able to restrict new messages to only be added to the current chat room. To do this by populating the new message object with a roomId property that matches the roomId of the current chat room. The homeCtrl, which uses the getByRoomId method to compare roomIds, then adds the message to the correct array which is displayed in the chat room.

    To add the final touches to the site I wanted to prevent the message input box and submit button from showing up before a chat room is selected. Even if a user entered a message in this state, it would have a roomId of undefined and never show up on the page. To prevent confusion I used ng-show="home.activeRoom.room" on the div tag containing both elements. This restricts the elements to only showing up when the current chat room is defined. To utilize the empty space we put an ng-hide on the same exact variable with the text "Select a Room to start messaging!".


## Results

    After working through the kinks and learning some new concepts, we were left with a very smooth, functional Single Application View Chat Room site. Through queries linking the site to Firebase and Angular JS's intuitive framework we were able to add messages and create chat rooms in real-time. When the page first opens, the message input does not appear and we can see the prompt asking the user to select a room. Once the chat room is selected, messages added in a chat room are successfully added to the Firebase database and only show up in the current chat room. The time and username that are also also properties of the new message object are correctly displayed next to the message.


## Conclusion

   With the completion of this project, I believe that I made great strides in expanding my knowledge of AngularJS and its unique framework. Creating many of the controllers and services on my own also allowed me to see the interactions between the two more clearly. Firebase worked in unison with the Angular framework and I would definitely use it again in my applications. I look forward to applying what I've learned with this project in the future
