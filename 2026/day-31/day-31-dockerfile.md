# Task 1: Your First Dockerfile

1. Create a folder called my-first-image
   mkdir my-first-image 
2. Inside it create a docker file that (i) Uses ubuntu as a base image (ii) Install curl (iii) set a default command to print "Hellow from my custom image!" 
Sol.FROM ubuntu:latest

    WORKDIR /app

    RUN apt update
    RUN apt install curl -y 

    CMD ["echo","Hello from my custom image!"]
3. Build the image and tag it my-ubuntu:v1
Sol. docker build -t my-ubuntu:v1
4. Run a container from your image
Sol. docker run -d my-ubuntu:v1    

# Task 2: Dockerfile Instruction

1.  Create a new Dockerfile that uses all of these instructions:

    FROM — base image
    RUN — execute commands during build
    COPY — copy files from host to image
    WORKDIR — set working directory
    EXPOSE — document the port
    CMD — default command
    Build and run it. Understand what each line does.

Sol.FROM ubuntu:latest

    WORKDIR /app

    RUN apt update
    RUN apt install curl -y 

    CMD ["echo","Hello from my custom image!"]

# Task 3: CMD vs ENTRYPOINT

Sol. Image with CMD
    
    FROM alpine 

    CMD ["echo", "hello"]

    CMD vs ENTRYPOINT

    Use CMD when:

    You want to provide a default command
    Users should be able to easily override it
    The container behaves like a normal executable environment

    Use ENTRYPOINT when:

    The container should always run a specific executable
    You want the image to behave like a dedicated command/tool
    Extra arguments should be appended automatically

# Task 4: Build a simple web app image 

    Create a small static HTML file (index.html) with any content
    
   1.  Write a Dockerfile that:
   2. Uses nginx:alpine as base
   3.  Copies your index.html to the Nginx web directory
   4.  Build and tag it my-website:v1
   5.  Run it with port mapping and access it in your browser

Sol DONE

# Task 5: .dockerignore

Create a .dockerignore file in one of your project folders
Add entries for: node_modules, .git, *.md, .env
Build the image — verify that ignored files are not included

