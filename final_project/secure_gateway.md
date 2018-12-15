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


## Docker Commands

The Secure Gateway offers 3 methodologies for creating a connection through your Terminal Shell. These include:

1. IBM Installer
2. Docker
3. IBM DataPower

