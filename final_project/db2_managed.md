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

*Reference these steps [here](https://github.com/incredablechris/marist-mscs621-ciacobellis/blob/master/final_project/Iacobellis_Final_PPT.pdf)*

For #2, I will post the Termainal steps and commands here; for the Power User.


