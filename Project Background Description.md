## marist-mscs621-ciacobellis
# Project Introduction with Background History

Please refer to the README.md [document](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/README.md) for this project after understanding this context.

### Background for this Decision: 

This past June, I had accepted an offer for a Summer Internship at IBM. I was placed on the IBM Learning Skills Gateway Team and for the next three months, I was to learn everything related to IBM Learning.

The IBM Learning Skills Gateway team focuses teaching skills to users around the world. These skills encompass almost anything to leading technology, including (but not limited to) *Analytics*, *Cloud Computing*, *Blockchain*, *Security*, *IT Infrastructure*, and *Watson services.* Users can sign up with IBM to take courses and Learning Journeys offered by IBMers and | or Global Training Providers (GTP's) around the globe. A user simply logs in to the Skills Gateway, and gains access to take  thousands of courses relating to a technological topic of their interest.

#### My Postion on the Skills Gateway Team

As for myself, my primary position on the SG team relates to project management, database migration, and architecture documentation. My goal in the IT industry is to move my career into Project Management in technology. Since I have just begun my journey, I am not yet a project manager. My team lead is the project manager, and he is my mentor in this journey. As such, I have been working more closely with him throughout my time here at IBM. I am learning the aspects of what entails being a successful project manager. One component of this position is being able to successfully gather requirements from a client, and present them to your team for understanding and developement.

*At this time, the Skills Gateway team is transitioning from 



- Check out our front-end [site](https://www-03.ibm.com/services/learning/itesp.wss/zz-en?pageType=page&c=a0011023) to learn more about my team.

- To get a better understanding, think of the IBM Learning Services platform as one related to iLearn at Marist. Marist offers online courses (like this course) to students, hosted on their iLearn platform. Students sign up for a course for either semester, log in to iLearn, and now have access to all content, assignments, quizzes and exams posted by the Instructor.

After those three months, I can truly affirm that I have appreciated my time here at IBM with my team and the company overall. So much so in fact, that at the end of the internship, I was offered a full time position (starting in January). Until then, the internship would be extended. Since I have had such an excellent experience with IBM, I figured I'd focus my Cloud Computing project on technologies that I have used at IBM thus far.

* Of these topics, my favorite Cloud technologies have been **Db2**, **Cloud Object Store**, and **Secure Gateway**.
_________________________________________________________________________________________________________________________

## Definitions

_Db2_: As defined on the IBM Analytics [site](https://www.ibm.com/analytics/us/en/db2/), Db2 "includes products for operational databases, data warehouses, data lakes and fast data." Essentially, Db2 is a relational database that delivers advanced data management and analytics capabilities for a users transactional and warehousing workloads. The database offers features of high performance, insights, data availability, and reliability. 

- For example: For the Learning Skills Gateway (SG) team at IBM, Db2 is our primary database system. It allows the Database Administrator (DBA) to create schemas and tables, which hold data. Data is stored in rows and columns on a Db2 server. There are a few types of Db2 servers (including *Db2 Managed* and *Db2 Hosted*), which we will discuss later in this project. To access this data, typically a user will need access to the database _hostname_, _public IP address_, the _port_, _database type_, a _username_, and a _password_. These are all configured upon initially creating a Db2 

_Cloud Object Store_: IBM Cloud Object Storage is a scalable storage tool that is commonly used for data archiving and backup, web and mobile applications, and analytics. Cloud Object Storage (COS) offers a Flex scalable plan; meaning that the size of storage can increase over time as more objects and data are stored in a single instance (or bucket).

- For example: The SG team uses Object Store to hold course metadata and downloadable content. As time progresses, instructors and students will increase this storage (when uploading new content, creating new courses, etc.). This is why COS Flex is a great option. Storage will expand as needed, only charging for the space utilized. Our Db2 database interfaces with COS, which will be explained later in the project.

_Secure Gateway_: As defined within the IBM Cloud Bluemix Catalog, "the Secure Gateway Service provides a quick, easy, and secure solution for connecting resources in a protected environment to cloud resources." A Secure Gateway is a lightweight client that allows users to establish a secure and persistent connection between their own environment and the Cloud. Once the client is started, applications and resources can safely be connected to one another.

- For example, the SG team uses a Secure Gateway to connect their legacy Db2 database to a Cloud Db2 database for a data migration. Current data hosted on a legacy Db2 server needs to be kept secure. During our migration to the Cloud, the team and I needed to make sure that this data was transferred securely and seamlessly to the IBM Cloud. To launch and start a Secure Gateway, I will use a *Docker* container.  
_________________________________________________________________________________________________________________________

## Return to README

Now that you understand the background of this course project, you may return to the [README](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/README.md) document.
