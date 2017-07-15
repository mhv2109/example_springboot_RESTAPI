# example springboot RESTAPI
A very simple example project using Spring Boot to build a rest API. The example project is intended to showcase how you can build an application based upon the spring boot framework in combination with Maven. The example code is based upon the example from Spring which can be found at https://spring.io/guides/gs/rest-service/ 

##### step 1 - getting the code
Getting the code on your machine can be done using the git command as shown in the example below. this will ensure you will get the source code including the pom.xml file which is needed by Maven to build the code into a package
```shell
git clone https://github.com/louwersj/example_springboot_RESTAPI
```

##### step 2 - compile and package the code
As soon as you have retrieved the code you will have to compile and package your code. The result of this will be a jar file which you can use to run the example project. Using maven you can package the appication with the command shown below:
```shell
mvn clean package
```
