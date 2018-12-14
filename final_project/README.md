## marist-mscs621-ciacobellis
# MSCS621 Fall 2018 – Cloud Computing Project

developed and documented by Christopher Iacobellis

Marist College, Class of 2018

BS, MS Information Technology

## Fundamental Introduction

The project that I have researched and implemented for this semester relates to Databases, Object Store, and Secure Gateway, all under the IBM Cloud Platform and Service. 

As such, my project for this course will highlight and implement:

1. **Db2Hosted and Db2Managed on Cloud Database**
2. **IBM Cloud Object Store**
3. **Secure Gateway**

__________________________________________________________________________________________________________________________

### What the Application does:

For this project I will be using three separate IBM Cloud services | systems. The overall application ecosystem will:

1. Successfully implement a Db2 Managed Cloud database 
2. Connect this Managed Cloud Database with a Cloud Object Store. The Object Store will hold metadata.
3. Establishe a Secure Gateway link to effectively migrate data from a legacy database server to a Cloud Managed instance.

At a higher level, the appliation environment will have an end-to-end system featuring a database and an object store. A secure gateway will provide a secure connection to bring data into the database, from a legacy environment. The object store will hold metadata, that will be uploaded by the user into a bucket. The bucket and object store itself will be Flex, meaning that it will scale provided the initial storage capacity provided is reached. For this project, we will not exceed this limit by any means.

The database will be a Db2 Managed enviornment, with a GUI for the user to interact with. I will provide steps for the power user, who may want to use a Terminal command line shell to perform database configurations and migration.

The Object Store will upload and download metadata and auxillary files; for example, Word documents, .xls spreadsheets, and PDFs.

The Secure Gateway will be launched from a Terminal shell, and initiated in a dockerized container. The Gateway will be started with Docker, and the IBM Bluemix Dashboard will track progress of data migrated from one database to another (Cloud).

__________________________________________________________________________________________________________________________

## Deploy Application

To deploy the application, we must first configure each of the three components:

1. [Db2 Managed Database]()************************************************************************************
2. [Cloud Object Store]()**************************************************************************************
3. [Secure Gateway]()*****************************************************************************************

__________________________________________________________________________________________________________________________

## Architecture Diagram
 + Architecture diagram (local cloud development, cloud deployment, communication)

***** COPY ARCH DIAGRAM FROM SKILLS GATEWAY ON PPT. EMBED LINK OR PHOTO TO DIAGRAM *******************************

__________________________________________________________________________________________________________________________

## API's
 
For this project, there was no use for an API. This is another field of interest of mine, of which I will be researching after this course and all throughout my time at IBM.
 
__________________________________________________________________________________________________________________________

## GitHub Pages

Please refer to Project Background Description.md for a full background description by following the path below:
      
      marist-mscs621-ciacobellis/Project Background Description.md
      
- or view the page [here]().

__________________________________________________________________________________________________________________________

## URL

Since this application ecosystem will be hosted on the IBM Cloud Bluemix Dashboard, the link is similar to that of which we have used in class this semester. The Dashboard hosts IBM Cloud Foundry Applications and Cloud Foundry Services, which can be interconnected with each other. As such, a user can create a *Db2 Managed Database Cloud Foundry service*, a *Cloud Object Storage service*, and a *Secure Gateway Cloud Foundry service* 

You will find the link below. You may need to create an IBMid if not already done so.

[IBM Cloud Bluemix Dashboard](https://console.bluemix.net/dashboard/apps)

__________________________________________________________________________________________________________________________

## Create a FINAL REPORT
- The final report (ppt) should include the architecture, components, deployment model,
communication, and so on. 

EMBED A PPT HERE!!!***************************************************************************************************
