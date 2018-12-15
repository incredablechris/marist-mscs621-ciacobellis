## marist-mscs621-ciacobellis
# Secure Gateway

For this project, we will use a IBM Cloud Secure Gateway Service for data migration.

## Overview

Briefly, the Secure Gateway will allow a user to establish a bridge and|or connection between two different networks. In our case, the Gateway will create a connection between a legacy internal IBM server and the new IBM Cloud infrastructure.

The reason a Secure Gateway is needed is due to the specific zone configuration of each type of network. The legacy database server may be located in the "BlueZone" [as IBM 'coins' it], whereas the IBM Cloud server is configured differently. Therefore, in order to transfer data between the two 'zones,' a Secure Gateway needs to be established.

## Review Final Report

The [Final Report](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/Iacobellis_Final_PPT.pdf) illustrates in detail the step-by-step process for:

1. Creating an Instance of an IBM Secure Gateway.
2. Configuring Source and Target Destinations.
3. Initiating the gateway through a Terminal Shell with Docker.

*To install Docker on your local machine [ if you are using macOS ], please visit [Docker](https://docs.docker.com/docker-for-mac/install/) here.

## Requirements

The main requirement you will need to correctly configure a Secure Gateway is the **hostname** and **port** of the Source Database server and the **hostname** and **port** of the Destination Database server.

With these, you will need a **username** and **password** for each respective database.

Along with these, you will need **Docker** installed on your local machine. Let's begin with Docker.

## Docker

The Secure Gateway offers 3 methodologies for creating a connection through your Terminal Shell. These include:

1. IBM Installer
2. Docker
3. IBM DataPower

![Docker Secure Gateway](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/Docker%20Options.png)

Since we have used Docker all throughout the semester, I thought it would be best to use for this project as well.

### Commands

After Docker is installed on your local machine, you will need to paste the Docker Command into your Terminal Shell, to initiate the Secure Gateway. 

For my example, I am using the native Terminal Application for macOS. You may use any Terminal Shell application. I also recommend checking out [iTerm2](https://www.iterm2.com/) for macOS.

```
docker run -it ibmcom/secure-gateway-client 5Ph4rPiqyxw_prod_ng -t eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJjb25maWd1cmF0aW9uX2lkIjoiNVBoNHJQaXF5eHdfcHJvZF9uZyIsInJlZ2lvbiI6InVzLXNvdXRoIiwiaWF0IjoxNTQwMjIxNzI5LCJleHAiOjE1NDc5OTc3Mjl9.XbJ8H49wFLDCS1Wko9_uTsJO40gqtQ_29USl5JF8rJs
```

Once activated, your local machine becomes the bridge between the two networks.

#### Congradulations

You have successfully created and connected a Secure Gateway between two networks.

Please return to the [README.md](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/README.md) page to continue with the tutorial. Also, please reference the [Final Report PDF](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/Iacobellis_Final_PPT.pdf).
