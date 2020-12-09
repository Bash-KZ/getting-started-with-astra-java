<!--- STARTEXCLUDE --->
# Getting Started with Apache Cassandra™ and Java using DataStax Astra
*50 minutes, Intermediate, [Start Building](https://github.com/DataStax-Examples/getting-started-with-astra-java#prerequisites)*

This provides an example REST backend built in Java using `Spring Boot` for use with the [Getting Started with Astra UI](https://github.com/DataStax-Examples/getting-started-with-astra-ui).
<!--- ENDEXCLUDE --->


![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-sample-app-default.png)


## Objectives
* How to connect to Astra via the Secure Connect Bundle
* How to manage a Cassandra Session within a JAVA web application
  
## How this Works
This is an example of a Spring Boot Microservice for use with the Astra Getting Started UI which is found [here](https://github.com/DataStax-Examples/getting-started-with-astra-ui).

## Get Started
To build and play with this app, follow the build instructions that are located here: [https://github.com/DataStax-Examples/getting-started-with-astra-java](https://github.com/DataStax-Examples/getting-started-with-astra-java#prerequisites)

<!--- STARTEXCLUDE --->
## Prerequisites
Let's do some initial setup.

### DataStax Astra
1. Create a [DataStax Astra account](https://astra.datastax.com/register?utm_source=github&utm_medium=referral&utm_campaign=UTM_CODE) if you don't 
already have one:
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-register-basic-auth.png)

2. On the home page. Locate the button **`Add Database`**
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-dashboard.png)

3. Pick **free plan** and a **region** close to you, click configure.
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-create-db-1-top.png)
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-create-db-1-bottom.png)

4. Define a **database name**, **keyspace name** and **credentials** (Take note of the DB Password)
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-create-db-2.png)

5. Your Astra DB will be ready when the status will change from *`Pending`* to **`Active`** 💥💥💥 
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-active.png)

6. Locate the combo `Organization: <Your email>` on the top navigation. In the drop down menu, click your current organization.
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-org-menu-open.png)

7. Scroll down to the bottom of the page and locate `Service Account` in `Security Settings` and select `Copy Credentials` as shown below.
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-org-copy-credentials.png)

### Github
1. Click `Use this template` at the top of the [GitHub Repository](https://github.com/DataStax-Examples/getting-started-with-astra-java):
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-use-template.png)

2. Enter a repository name and click 'Create repository from template':
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-create-repository.png)

3. Clone the repository:
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-clone.png)

## 🚀 Getting Started Paths:
*Make sure you've completed the [prerequisites](#prerequisites) before starting this step*
  - [Running on your local machine](#running-on-your-local-machine)

### Running on your local machine
Make sure that you have:
* Java 11+
* An Astra compatible Java driver, instructions may be found [here](https://docs.datastax.com/en/astra/aws/doc/dscloud/astra/dscloudConnectJavaDriver.html) to install this locally.
* An Astra database with the CQL schema located in [schema.cql](src/main/resources/schema.cql) already added.
* The username, password, keyspace name, and secure connect bundle downloaded from your Astra Database.  For information on how to obtain these credentials please read the documentation found [here](https://docs.datastax.com/en/astra/aws/doc/dscloud/astra/dscloudObtainingCredentials.html).

This application is a Spring Boot web application. This sample can be run from the root directory using:
```sh
cd getting-started-with-astra-java

mvn spring-boot:run
```

This will startup the application running on `http://localhost:8080`

You will know that you are up and working when you get the following in your terminal window:
```sh
16:23:01.569 INFO  com.datastax.astra.GettingStartedWithAstra  : Started GettingStartedWithAstra in 1.851 seconds (JVM running for 2.39)
```

#### Access the API documentation from a browser

[http://localhost:8080](http://localhost:8080)

*Note: If you want to change the listening port of the application, locate the file `src/main/resources/application.yml` and change key `server.port`*

#### Setup the user interface to use this backend
To setup the UI to connect to Java backend define a `.env` file in the `getting-started-with-astra-ui` project main directory. Inside the file it should have one entry pointing to this project's API endpoint:
```sh
BASE_ADDRESS=http://localhost:8080/api
```
Once you start that project with a `npm run build` it will point the UI to the backend API which will then be using Astra as a database. When you first connect to the UI, a dialog box will open asking for Astra connection information. 
<!--- ENDEXCLUDE --->
