# Task 1: The Problem

   1. Run a Postgres or MySQL container
      Done
   2. Create some data inside it (a table, a few rows — anything)
      Done
   4. Stop and remove the container
      Done
   5. Run a new one — is your data still there?
      No. data is not there beause when we delete the container the data is automatically deteled by it and not store any wehre localy.

# Task 2: Named Volume

    Create a named volume

    Run the same database container, but this time attach the volume to it
    Add some data, stop and remove the container
    Run a brand new container with the same volume
    Is the data still there?
    Verify: docker volume ls, docker volume inspect
    Sol. DONE

# Task 3: Bind Mounts

    Create a folder on your host machine with an index.html file
    Run an Nginx container and bind mount your folder to the Nginx web directory
    Access the page in your browser
    Edit the index.html on your host — refresh the browser
    Write in your notes: What is the difference between a named volume and a bind mount?

Ans. name volume cannot be access or edited by the host but the bind mount can be access and edited by inside and outside the volume.

# Task 4: Docker Networking Basics

   1. List all Docker networks on your machine
      docker network ls
   2. Inspect the default bridge network
      docker network inspect 59
   3. Run two containers on the default bridge — can they ping each other by name?
      NO
   4. Run two containers on the default bridge — can they ping each other by IP?
      Yes

# Task 5: Custom Network 

   1. Create a custom bridge network called my-app-net
      docker network create name
   2. Run two containers on my-app-net
      --network network-name
   3. Can they ping each other by name now?
      Done 
   4. Write in your notes: Why does custom networking allow name-based communication but the default bridge doesn't?
      Custom networking provide auto DNS(Domain Name Services) that help containers on the same networke to communicate with each other.
      whereas the Container on default network does not have this service so they can communicate with each other through IP address. 

# Task 6: Put It Together 

   1. Create a custom network
     `docker network create twotier` 
   2. Run a database container (MySQL/Postgres) on that network with a volume for data
     `docker run -d -v mysql-data:/var/lib/mysql --network=twotier --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=admin -e MYSQL_DATABASE=mysqldb mysql:latest `
   3. Run an app container (use any image) on the same network
     `docker run -d --network=twotier -p 5000:5000 -e MYSQL_HOST=mysql -e MYSQL_USER=root -e MYSQL_PASSWORD=admin -e MYSQL_DB=mysqldb flaskapp:latest`
   3. Verify the app container can reach the database by container name
      DONE
