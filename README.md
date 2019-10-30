# getting-started-with-apollo-java

```
    _____                .__  .__          
   /  _  \ ______   ____ |  | |  |   ____  
  /  /_\  \\____ \ /  _ \|  | |  |  /  _ \ 
 /    |    \  |_> >  <_> )  |_|  |_(  <_> )
 \____|__  /   __/ \____/|____/____/\____/ 
         \/|__|                            
 
 Getting Started with Apollo

```

# I - Installation Guide


#### a) Clone this repo

```
git clone https://github.com/DataStax-Examples/getting-started-with-apollo-java.git
```

#### b) compile and start the backend *(java11+ required)*

```
cd getting-started-with-apollo-java

mvn spring-boot:run
```

#### c) Access the API documentation from a browser

[http://localhost:8080](http://localhost:8080)

*Note: If you want to change the listening port of the application, locate the file `src/main/resources/application.yml` and change key `server.port`*

#### d) Setup UI to use this backend

To setup the UI to connect to Java backend define the `.env` file in the following way:

```
BASE_ADDRESS=http://localhost:8080/api
```


# II - Building the docker image

First, you need to build the project and specially the `jar` deliverable with the following:
```
mvn clean install
```

Then build the images using the following command in same folder as `pom.xml` file:
```
mvn dockerfile:build 
```

To run the project in docker and expose correct port use the following:
```
docker run clunven/getting-started-with-apollo-java:latest -p 8080:8080
```