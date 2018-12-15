## marist-mscs621-ciacobellis
# Cloud Object Store Configuration

To configure Cloud Object Store (COS), the user will need to log in to the [IBM Cloud Dashboard](https://console.bluemix.net/dashboard/apps) and create an instance of Object Storage.

Like Secure Gateway and DB2Managed, the Object Store configuration steps mainly occur in the IBM Cloud GUI itself. For the easiest instructions, I've provided a link to my [Final Report](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/Iacobellis_Final_PPT.pdf) with the corresponding steps and screen captures.
__________________________________________________________________________________________________________________________

## Create a Bucket

After creating a **Bucket** in the COS Dashboard, you can seamlessly upload and download metadata and files.

Below, we can see each individual bucket created.

![COS Bucket](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/object_store_bucket.png)

__________________________________________________________________________________________________________________________

## View, Upload, and Download Content

Inside each of these buckets, there is content files. These include .docx, .pdf, .txt, etc.

![COS Content](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/object_store_content.png)

__________________________________________________________________________________________________________________________

A user can upload files here, and they can download files from here.

A use case example would include:

1. A developer may include an API to pull an Object Store bucket [with content] for implementation in a Front-End website. Users who access this website can view files they have uploaded, and can download them if they choose.

* This idea is similar to uploading and download files from the Marist iLearn site, although the IBM Cloud COS is a bit more sophisticated.

## Endpoint

For a developer to incorporate the Cloud Object Store into their front-end facing site, they will need to acquire the **Endpoint** of the COS.

Below are examples of Endpoint URLs.

![Endpoint](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/object_store_endpoint.png)

## Congratulations

You have created and configured an IBM Cloud Object Store environment of your own! Please return to the [README](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/README.md) page to continue with configuration of the remainder of the project.
