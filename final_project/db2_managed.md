### marist-mscs621-ciacobellis
### MSCS621 Fall 2018 – Cloud Computing Project

## Db2 Managed Configuration

### Migrating Tables

This is the process for migrating tables from a source (legacy) database to a target (Cloud) database.

This process is an automated procedure that will effectively:

1. DROP all tables
2. CREATE all tables
3. LOAD all table data
4. Add ALTER CONSTRAINTS to all tables
5. Add TRIGGERS, FUNCTIONS, and VIEWS (if applicable)

__________________________________________________________________________________________________________________________

### Migration Method within the Script

#### Create a table in the Target (Cloud) Database

The first step you'll need to perform is to CREATE a TABLE in the Target database that you plan to migrate from your legacy database. You will need to export the CREATE Statement from the Source Database and run that SQL in the Cloud DB -- including Foreign Keys, Constraints, Alters, and Comments.

For this  example: Let's copy the BRAND Table from our (legacy) database to our Cloud Instance.
*The BRAND table is a table used by the Skills Gateway Team to identify the specific BRANDS that belong to a BUSINESS of a client.

1. Export the CREATE TABLE statement from our legacy TADB2 schema.
2. Run this SQL statement in the Cloud and Create the Table.
3. Make sure Foreign Keys, Constraints, Alters, and Comments are included.
4. Complete steps below:

__________________________________________________________________________________________________________________________

There are two methodologies of completing this Migration. 

1. The simpler process focuses on using the GUI in the Db2Managed Bluemix service on the IBM Cloud site.
2. Using a Terminal Shell to Migrate.

For #1, I've laid out the steps in the PowerPoint Presentation, with step-by-step instructions and screen captures. 

*Reference these steps [here](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/Iacobellis_Final_PPT.pdf).*

For #2, I will post the Termainal steps and commands here; for the Power User.

__________________________________________________________________________________________________________________________

## Terminal Shell Migration & Script Examples

This process involves using a terminal shell command line. Begin with opening your terminal shell command line.

* Forewarning, these steps are directed towards a user who may want to learn how to use the Termainal commands to configure a database.

* For a GUI walkthrough of the DB2Managed interface, see the [Final Report](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/Iacobellis_Final_PPT.pdf) steps.

### Create a Service

In the IBM Cloud Dashboard, create a Cloud Foundry Service with the Service Offering of "DB2Managed".
Choose a plan that best suits your desired specifications. The Flex Plan is recommended for scalability.

Once Created, Scale the Instance to your desired specifications. You will need to specify the amount of VPC's [Compute], Memory [RAM], and Total Storage.

An Estimated Charge per month will be calculated.

This process may take a while depending on how many VPC's, RAM, and Storage is allocated. Be patient.

### Credentials
Once the Service is ready, you'll need to create Credentials. In the Service Credentials tab on the left hand pane of the Service, create a New Credential.

Below is an example of a Service Credential. You'll need to specify admin_username, public_ip, port, ssl_port, id, type, admin_password, private_ip, and host_name.

``` 
{
  "admin_username": "root",
  "public_ip": "169.61.12.248",
  "port": 50000,
  "ssl_port": 50001,
  "id": 59263585,
  "type": "MANAGEDDB2",
  "admin_password": "********",
  "private_ip": "10.187.139.179",
  "host_name": "db2hosted-flex-ChristopherIacobellis-13-dal13"
} 
```

### SSH into the Remote Cloud Server

(for this example, we will use our Db2 Cloud Managed test Database)

Type:
```
ssh root@169.61.12.248
```
And enter the password for your root user.


To confirm a successful login, you should see you command line change to
```
[root@db2hosted-flex-ChristopherIacobellis-13-dal13 ~]#
```

### Sudo into the DB2 Instance

You'll now need to change the directory to your Db2 Instance on the Cloud Server.
Type:
```
su - db2inst1
```
The directory is now changed, and you should see this command line:
```
[db2inst1@db2hosted-flex-ChristopherIacobellis-13-dal13 ~]$
```

### Enter into Db2 Command Line

In your Db2 Instance, type:
```
db2
```
This will allow you to enter the Command Line Processor for DB2 Client. You may now enter db2 commands here. You should see
```
db2 =>
```

### Catalog and Create a Node 

You will now need to create a node pointer. To do this, you will need to create an entrie in the node and databse directory.

You will need to type two separate commands:

```
CATALOG TCPIP NODE nodename REMOTE localhost SERVER portnumber
```
For example:
```
CATALOG TCPIP NODE SRCNODE REMOTE gw2dbtst.boulder.ibm.com SERVER 50000
```

```
CATALOG DATABASE SAMPLE AS newnodename AT NODE nodename AUTHENTICATION SERVER
```
For example:
```
CATALOG DATABASE SAMPLE AS SRCDB AT NODE SRCNODE AUTHENTICATION SERVER
```

These commands will have successfully run if you see the following response:
```
DB20
000I  The CATALOG DATABASE command completed successfully.
DB21056W  Directory changes may not be effective until the directory cache is
refreshed.
```

### Connect to your Target Database

You will now need to connect to your db2 Target Database. In our case, we will connect to our new IBM Cloud Db2 Hosted Database.

Following the db2 prompt [ db2> ], type:
```
CONNECT TO databasename
```
For example:
```
CONNECT TO SKILLST
```
*SKILLST is the name of our new IBM Cloud Db2 Managed Database

### Declare & Load Cursors

The final steps in this migration are with the commands DECLARE and LOAD.


#### Declare A Cursor

In the db2 prompt [ db2> ], you will need to DECLARE a CURSOR.

Type:
```
DECLARE cursorname CURSOR DATABASE <databasename> USER <useridforDB> USING <useridpassword> FOR <selectstatement>
```
For example:
```
DECLARE C1 CURSOR DATABASE TACGW USER <useridforDB> USING <useridpassword> FOR SELECT * FROM TADB2.BRAND
```
* This statement declares a cursor for the table BRAND in our legacy database. It is selecting all data from this table.

### Connect to Source DB

Type:
```
CONNECT TO databasename
```

Example:
```
CONNECT TO TACGW
```

* REMINDER
If you are connecting to a Db2 Database from a Remote Connection ( ie, a [Secure Gateway](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/secure_gateway.md) ) you must specify a <user> and <password> for the source Database.
For example:
```
CONNECT TO TACGW USER lsrun USING <password>
```

#### Load the Cursor

Next in the db2 prompt [ db2> ], you will need to LOAD FROM CURSOR.

Type:
```
LOAD FROM <cursorname> OF CURSOR INSERT INTO <schema.tablename> NONRECOVERABLE
```
*This statement loads the cursor you defined in the Declare Statement.

Example:
```
LOAD FROM C1 OF CURSOR INSERT INTO TADB2.BRAND NONRECOVERABLE
```


If this process was successful, you should see output similar to this below:
```
Number of rows read         = 41
Number of rows skipped      = 0
Number of rows loaded       = 41
Number of rows rejected     = 0
Number of rows deleted      = 0
Number of rows committed    = 41
```

Finally, type:
```
TERMINATE
```
to end the process.
__________________________________________________________________________________________________________________________

#### Helpful Commands

```
list node directory
```
This command allows the user to list all node pointers created on the target server.

```
list database directory
```
This command allows the user to list all database pointers created on the target server.


