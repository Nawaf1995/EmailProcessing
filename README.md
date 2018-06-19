***Email Processing***
# Abstract:
Every one has an email account full of emails that be read or manage. We receive hundreds of emails daily and some of these emails are garbag or ads. Therefore, we want an application that is able to read all emails and manage them based on what we need from the email. So, the idea of this applcaition is to read all emails from the inbox and manange them. At the end, we will have only the emails that we want, on the other words plain text email that is readable by human and all other ads will not be read by the application.

## What is the system about?
Since we are dealing with big data, this project will make our life easy while reading emails from our inbox. Imagine that a person receives a hundred emails a day. Of course, he cannot read them all in one day. So, this system will read all the important emails for that person and then it will give the person what is the email about. Using data mining approaches the system will be able to do this boring work. Therefore, this system will only do three things:

- First read all emails from the Gmail inbox
- Second filter these emails by remove the ads and emails that contain link to website
- Thrid process the emails and then display the output
## The Algorithm?
![alt text](https://imgur.com/89H7Mzg.jpg)

## More explaination: 

Step 1: the user must specifiy his email and password address via the graphical interface in order for the application to read his email inbox. The email and password that is used in gmail account.

Step 2: After reading all emails inside the inbox, the system will check if the emails that read are plain text. Means, the emails should not be a multi-part emails like html pages, photos, or links to any advertising website. Then, if emails are text the system will start doing the processing. Otherwise, the system will perform filtering to the emails that are not text to remove them from the list of emails that are already read to end up with only text emails. 

Step 3: Now the system is doing processing to the emails that found as text, but the question is how the processing is done or what are criterion that the system will follow to do the processing? 
the answer is: for now the system will do the processing for the meeting emails. For example, a department in a comapny want to sit a meeting, one person will send an email to the employees who will attend the meeting. Here our task comes, the system will read that email and is going to extract the meeting's information from it. It will extract who sent the email, the subject of the meeting, date, time, and venue. So these are the information that will be getten from the email. 

Step 4: Now our system is having the information, but this is not enough we need to store the data somewhere. For the ethical purpose the system will store the infromation in browser session. By doing that only the user can see his information no body else. 

Step 5: Finally, the system will display the result in web view to allow the user to see the information of the email.


## The purpose of this application?
My purpose of this application is we as users of emails do not have to time to read all emails that we receive daily. Some of the emails are garbag or advertising that we never need to read them in our work time. So, with this kind of system we will be able to have a summery of our importatnt emails without wasting time to read all the inbox.

## Requirement To start:
You can use any back end programming language, I used java spring as a back end and Angular as front end.

For the Backend (serer side):

- [Java spring using Eclipse IDE](https://spring.io/).
- [Redis for storing the data in the session](https://redis.io/download).
- [XAMPP as a server to run the application](https://www.apachefriends.org/download.html).
- [Javamail API to access gmail account](https://github.com/javaee/javamail/releases).

For the Frontend (client side):
- [Angular 4](https://angular.io/)

## The backend:
- **DataMiningApplication.java** the server code runs from this file.
- **AccessingGmail.java** this file contains code that can access the Gmail inbox and read the emails. Then these emails will be filtered to be passed to the next stage. Note: filtering in this stage is only separating the emails that contains plain/text from emails that have advertising content.
- **RedisConfig.java** this the configuration of the redis. Redis is database that is stored in the user browser. Means, every user has different data based on his emails.
- **RequestFilter.java** this file for communicating with the front end which is Angular.
- **GmailController.java** this is the most important file in the project. The controller is the one who takes the request and forward it to the appropriate service to response back to the request.
- Then we have the models user model and Mailmodel. In spring MVC we need to have a model which contains the attribute of the model and constructor.
- **EmailExtraction.java** this whill do the processing after recevicing the data from the the AccessingGmail to start extracting the email

## The Fontend:
For the front end we will use Angular as front end. This new version of Angular it is using MVC approach like Spring. So, we will do the same here as we did in the back end. For the front end will have the following:
- Models: **Emails.TS and users.TS** (**TS means type script**)
- Controller: we only have one controller here **access.Service.TS** which will all the methods that will communicate with the back end.
- views: which is the html pages in the components folder

## To run the project:
To the run the project you should run the front end and the back end separately.
- First: run the back end from Eclipse IDE on port 8080 before doing this, two things must be done
        - Start the server in my case I am using XAMPP
        - start the redis server
- After running the server and the redis, then launch the program fro Eclipse IDE
- Second: run the front end by going to the front end folder and open the command line, then type **ng serve**
- Finally, after running both client and server go to your favorite browser and type in the URL: **localhost:4200** 
## License:
This is a free project you have the right to use where ever you want.
