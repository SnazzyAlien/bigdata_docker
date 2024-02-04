# BIG DATA ECOSYSTEM WITH DOCKER

Environment for studying the main big data frameworks in Docker.
<br> This setup will create dockers with the HDFS, HBase, Hive, Presto, Spark, Jupyter, Hue, Mongodb, Metabase, Nifi, Kafka, Mysql and Zookeeper frameworks with the following architecture:
<br>

![Ecosystem](ecosystem.jpeg)

## REQUIRED SOFTWARE
#### To create and use the environment, we will use git and Docker
    * Installation of Docker Desktop on Windows [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows) or docker on [Linux](https://docs.docker. com/install/linux/docker-ce/ubuntu/)
    * [Git installation](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git)
   
## SETUP
*NOTE: This step must only be performed once. After the environment is created, use docker-compose to start the containers as shown in the topic STARTING THE ENVIRONMENT*

#### Creation of the docker directory:
*NOTE: Create a directory called docker*

    * Suggestion on Windows:
       * Create the docker directory at the root of your drive
          ex: C:\docker
          
    * Suggestion on Linux:
       * Create the directory in the user's home
         ex: /home/user/docker

#### In a terminal/DOS, inside the docker directory, clone the project to github
           git clone https://github.com/fabiogjardim/bigdata_docker.git

#### In the bigdata_docker directory there will be the following objects
![ls](ls.JPG)

   
## STARTING THE ENVIRONMENT
   
   *On Windows open PowerShell, on Linux a terminal*

### In the terminal, in the bigdata_docker directory, run docker-compose
           docker-compose up -d

### Check images and containers
 
          docker image ls

![docker image ls](docker_image_ls.JPG)

          docker container ls

![docker container](docker_container_ls.JPG)

## SOLVING PROBLEMS
   
   *On Windows open the Docker Quickstart Terminal*

### Stop a container
          docker stop [container name]

### Stop all containers
          docker stop $(docker ps -a -q)
  
### Remove a container
          docker rm [container name]

### Remove all containers
          docker rm $(docker ps -a -q)

### Container data
          docker container inspect [container name]

### Start a container
          docker-compose up -d [container name]

### Start all containers
          docker-compose up -d

### Access container log
          docker container logs [container name]

## Frameworks WebUI Access
 
* HDFS *http://localhost:50070*
* Presto *http://localhost:8080*
* Hbase *http://localhost:16010/master-status*
* Mongo Express *http://localhost:8081*
* Kafka Manager *http://localhost:9000*
* Metabase *http://localhost:3000*
* Nifi *http://localhost:9090*
* Jupyter Spark *http://localhost:8889*
* Hue *http://localhost:8888*
* Spark *http://localhost:4040*

## Shell access

    #####HDFS

           docker exec -it datanode bash

    ##### HBase

           docker exec -it hbase-master bash

    ##### Sqoop

           docker exec -it datanode bash
        
    ##### Kafka

           docker exec -it kafka bash

## JDBC Access

    ##### MySQL
           jdbc:mysql://database/employees

    #####Hive

           jdbc:hive2://hive-server:10000/default

    ##### Presto

           jdbc:presto://presto:8080/hive/default

## Users and passwords

    ##### Hue
     User: admin
     Password: admin

    ##### Metabase
     User: bigdata@class.com
     Password: bigdata123

    ##### MySQL
     User: root
     Password: secret
   
    ##### MongoDB
     User: root
     Password: root
     Authentication Database: admin

## Images

[Docker Hub](https://hub.docker.com/u/fjardim)

## Official Documentation

* https://zookeeper.apache.org/
* https://kafka.apache.org/
* https://nifi.apache.org/
* https://prestodb.io/
* https://spark.apache.org/
* https://www.mongodb.com/
* https://www.metabase.com/
* https://jupyter.org/
* https://hbase.apache.org/
* https://sqoop.apache.org/
* https://hadoop.apache.org/
* https://hive.apache.org/
* https://gethue.com/
* https://github.com/yahoo/CMAK
* https://www.docker.com/
