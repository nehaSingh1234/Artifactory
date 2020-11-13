# Artifactory
Download the jar files.

You can execute this jar file directly for running the application or use below steps for running on docker.
Steps to run jar on docker container-

Make sure docker is installed
Open a terminal or command prompt
Go to assignment folder /Assigment>
Run below command-
$docker build -t assignment .

You should see output like below:

Sending build context to Docker daemon 16.79MB Step 1/4 : FROM openjdk:8-jdk-alpine ---> a3562aa0b991 Step 2/4 : ARG JAR_FILE=target/*.jar ---> Using cache ---> 4ef945b4787c Step 3/4 : COPY ${JAR_FILE} Assignment-0.0.1-SNAPSHOT.jar ---> ce16839ed6df Removing intermediate container 515d5942cc2d Step 4/4 : ENTRYPOINT java -jar /Assignment-0.0.1-SNAPSHOT.jar ---> Running in b28bdcfdc8a2 ---> 18a65c736bd7 Removing intermediate container b28bdcfdc8a2 Successfully built 18a65c736bd7 Successfully tagged assignment:latest

Once docker image is built, check the image with command- $ docker images
REPOSITORY TAG IMAGE ID CREATED SIZE assignment latest 18a65c736bd7 2 minutes ago 121MB

Now execute below commands for running the image.
$ docker run -p 80:8080 assignment --name runningversion

You should receive output like below- . ____ _ __ _ _ /\ / ' __ _ () __ __ _ \ \ \
( ( )__ | '_ | '| | ' / ` | \ \ \
\/ )| |)| | | | | || (| | ) ) ) ) ' || .__|| ||| |_, | / / / / =========||==============|/=//// :: Spring Boot :: (v2.3.5.RELEASE)

2020-11-12 23:00:56.277 INFO 1 --- [ main] A.Assignment.AssignmentApplication : Starting AssignmentApplication v0.0.1-SNAPSHOT on d6ad53d8f203 with PID 1 (/Assignment-0.0.1-SNAPSHOT.jar started by root in /) 2020-11-12 23:00:56.301 INFO 1 --- [ main] A.Assignment.AssignmentApplication : No active profile set, falling back to default profiles: default 2020-11-12 23:00:59.949 INFO 1 --- [ main] o.s.b.w.embedded.tomcat.TomcatWebServer : Tomcat initialized with port(s): 8080 (http) 2020-11-12 23:00:59.998 INFO 1 --- [ main] o.apache.catalina.core.StandardService : Starting service [Tomcat] 2020-11-12 23:01:00.000 INFO 1 --- [ main] org.apache.catalina.core.StandardEngine : Starting Servlet engine: [Apache Tomcat/9.0.39] 2020-11-12 23:01:00.256 INFO 1 --- [ main] o.a.c.c.C.[Tomcat].[localhost].[/] : Initializing Spring embedded WebApplicationContext 2020-11-12 23:01:00.257 INFO 1 --- [ main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 3622 ms 2020-11-12 23:01:00.935 INFO 1 --- [ main] o.s.s.concurrent.ThreadPoolTaskExecutor : Initializing ExecutorService 'applicationTaskExecutor' 2020-11-12 23:01:01.459 INFO 1 --- [ main] o.s.b.w.embedded.tomcat.TomcatWebServer : Tomcat started on port(s): 8080 (http) with context path '' 2020-11-12 23:01:01.527 INFO 1 --- [ main] A.Assignment.AssignmentApplication : Started AssignmentApplication in 6.611 seconds (JVM running for 7.988)

Now access the URL "http://localhost/units/si?units=degree/minute"
