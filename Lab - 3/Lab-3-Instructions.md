# Lab 3

We now start with Lab 4. The pre-requisites remain the same as for Lab 1.

This lab will cover instrumenting and observing two applications, one a monolith and next a microservices application. Second section of the lab will cover alerting.

---
### Elastic APM Setup

We will be using the same Elastic Cloud instance provisioned earlier.


1. Login to your Elastic Cloud Instance and navigate to APM
   ![Alt text](../assets/image-24.png) 

2. You will see options to configure your application with Elastic APM. Go to the Java setup to begin with.
   ![Alt text](../assets/image-25.png)
   Download the agent jar as instructed on the page.
   
   You can run the below command on the VM to download the agent too.
   ```bash
      wget https://oss.sonatype.org/service/local/artifact/maven/redirect?r=releases\&g=co.elastic.apm\&a=elastic-apm-agent\&v=LATEST -O elastic-apm-agent.jar
   ```
3. Now login to your Lab VM and clone the spring boot application we intend to instrument.
   
   ```bash
      #Java should already be installed. If not run the following command.
      sudo apt install openjdk-17-jdk -y
   ```
   You can either clone the application from GitHub [Spring Pet Clinic](https://github.com/spring-projects/spring-petclinic) and follow the steps below to build the application. 

   ```bash
      mkdir -p lab4
      cd lab4
      git clone https://github.com/spring-projects/spring-petclinic.git
      cd spring-petclinic
      export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
      ./mvnw package
      java -javaagent:/path/to/elastic-apm-agent.jar \
      -Delastic.apm.service_name=petclinic \
      -Delastic.apm.secret_token=XXXXXXX \
      -Delastic.apm.server_url=XXXXXXX \
      -Delastic.apm.environment=o11y-workshop \
      -jar target/spring-petclinic-3.1.0-SNAPSHOT.jar
   ```   
   __OR ALTERNATIVELY__

   Skip the build part & download the jar from this repository and use it for the lab.
   
   ```bash
      java -javaagent:/path/to/elastic-apm-agent.jar \
      -Delastic.apm.service_name=petclinic \
      -Delastic.apm.secret_token=XXXXXXX \
      -Delastic.apm.server_url=XXXXXXX \
      -Delastic.apm.environment=o11y-workshop \
      -jar target/spring-petclinic-3.1.0-SNAPSHOT.jar
   ```
   
   Once the application starts running, access the URL with the FQDN or IP address of the lab machine at port 8080.

   http://lab-machine-fqdn-or-url:8080/

   Interact with the application. 

4. Navigate to APM screen. Check Inventory, Service Map, Traces etc. 
   What do you see? 



                        End Of Lab 4.


