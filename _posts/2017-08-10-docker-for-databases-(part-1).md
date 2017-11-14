---
layout: post
title: "Docker for Databases (Part 1)"
date: 2017-08-10 05:35:32
initpath: 'assets/img/Post_Images/2017-08-10-docker-for-databases-\(part-1\)/docker_database.jpg'
image: '../assets/img/Post_Images/2017-08-10-docker-for-databases-(part-1)/docker_database.jpg'
description: A brief introduction to working with the Databases and Volumes in Docker.
category: 'devops'
tags:
- Docker
- Database
- Containers
twitter_text:
introduction:
---

Docker containers were created with dynamic data in mind. This meant that, out of the box, Docker containers did not know how to deal with persistent data such as large databases.


**Two workarounds** were initially used to make Docker containers work with databases. The Docker volume API was later introduced to deal with persistent data natively.

<br>


`Part 1` of this blog post will contain a brief introduction to working with the Databases and Volumes in Docker.


<br>


In `Part 2`, we will see a tutorial/case study of using **MySQL** in Docker.


### History of Workarounds


1. The first workaround to the Docker/database problem is to store the database itself elsewhere on an online platform such as the cloud or on a virtual machine. This is essentially a service via a port for legacy applications.


2. Another workaround for dealing with persistent data is to store it on, say, Amazon S3 and retrieve it if the container goes bust. This means the data present within the container is also backed up on the cloud so that it can be retrieved should the container go belly up. Given that databases are typically large files, this can be a very cumbersome process.


### Databases in Containers

<p align="justify">
<img align="right" width="300" height="320" src="../assets/img/Post_Images/2017-08-10-docker-for-databases-(part-1)/docker1.png">   

In the case of a database server, retaining your data can be critical. The default storage for containers themselves is not persistent but can be with a little planning.

<br> <br>

Note in the figure, how the container host, like the traditional Linux deployment, has enterprise storage associated with it. Through the use of docker volumes, we can assign storage to containers and those volumes will persist regardless of the state of the container.

</p>

`There can be 2 approaches of running databases in a containerized environment.`

#### 1. Single Node Database with Database and Client in separate containers on the same node.

![placeholder](<../assets/img/Post_Images/2017-08-10-docker-for-databases-(part-1)/docker2.png> "Docker with Databases")



In this setup, there are actually two clients. One is containerized and the other is executing from the container host directly. The database is also containerized but isolated by namespacing as well.

The database client executing on the host can still communicate with the containerized database server via TCP/IP because Docker has an internal network for containers to communication with each other and the host. Once an interconnection mechanism has been established a container developer must ensure that service containers are properly configured to allow access to these connections.


Some container coordination frameworks, such as Kubernetes, attempt to simplify this use case for containers co-located on a single node by sharing the network port space between node-local containers.


####  2. Multiple Node Deployment where Database and Client are separated:

![placeholder](<../assets/img/Post_Images/2017-08-10-docker-for-databases-(part-1)/docker3.png> "Jenkins Git")

In this scenario, the database server and clients are on different nodes and require network access to communicate. In this case, you must ensure that Docker not only exposes a port for the database container but that a port is also exposed to the network so other clients can communicate with it.

Notice how in this scenario, the database server is still containerized but the client resides on a different node. For network connections, Docker provides a simple directive in the Dockerfile to expose a port from the running container. For example, to create a Postgres DB server container that listens on the default Postgres port, you would add the following line: EXPOSE 8080

You then also need to ensure that you perform the port mapping when the container runs using either the -P or -p flags.


### Things to Consider

<p align="justify">

- Ensure that your container environment has enough CPU and memory resources. If your container environment does not have enough resources, databases will suffer.

</p>
<br>
<p align="justify">

* Keep container as secure as possible. With Docker, it’s simple to set up an isolated network that only the containers for a given application can access. The database can be completely isolated from the external network this way.

</p>
<br>
<p align="justify">

* Don’t try to recreate your database infrastructure using containers as a replacement for virtual machines or physical machines. This is especially true for applications whose SLA is not mission critical.

</p>
<br>
<p align="justify">

* Rather, try to keep single databases to a DBMS for smaller applications. Treat databases more like an application component rather than as a separate environment that hosts a database. This scenario works well too for open source databases given there are no restrictions on how many instances one can spin up.

</p>

### Conclusion

<p align="justify">
For containers and databases, the bottom line is to be cautious when considering containers for databases. This is one of those areas where containers are probably not the best choice in many cases, however, sometimes the container benefits outweigh the costs of using containers for smaller/moderate applications.

</p>


**`Check out Part 2 of this post to see a tutorial/case study of using MySQL in Docker.`**