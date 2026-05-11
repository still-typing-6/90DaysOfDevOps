# Task 1: What is Docker?

Q1. What is the container and why we need them ? 
Ans.Container is a isolated place where our application run it uses shared reseorces form out kernal instead of using hyperviosr or VM to get a dedicated memory and storage so it is very light weight.We need them because if we have multiple micro services like frontend, backend, payment gateway we can make a dedicted container of each one and and connect them with each other, So if we need to update any services later, then we don't have to down the hole application we just down that dedicated container  

Q2. Container Vs VM what is the real difference ?
Ans. Container share resorces from host kernal and is very lightweight where as teh VM need dedicated memory and storage which is heavy.

Q3. What is docker Architecture ? (Client, Daemon, Image, Container, registry)
Ans. Docker uses a Client-Server architecture.The Docker talk to the Docker Daemon which build, run, and manages containers. They communicate why REST API via UNIX sockets.
     The core model.
     Docker Client: It is the Primary interface for the user. When you execute any command such as docker run, docker build the client translate them into REST API request and sends them into docker deamon.

     Docker Host: It run the docker daemon and provide the environment to execute and run the container.

     Docker Repository: This is the remote repository to store and distribute your images.

# Task 2: Install Docker 

Q1. Install docker on your machine.
Ans. Docker install using sudo

Q2. Varification of installation.
Ans. docker --version 

Q3. Run the hello-world container.
Ans. OUTPUT: Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

# Task 3: Run real world container 

Q1. Run a Nginx container and access it in your browser 
Ans. DONE
Q2. Run a ununtu cantainer and run it in interactive mode
Ans. DONE
Q3. List all running containers
Ans. DONE 
Q4. List all containers (including stopped ones)
Ans. DONE 
Q5. Stop and remove a container
Ans. DONE
 




