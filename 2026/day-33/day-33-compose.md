# Task 1: Install and Varify 

1. Check if Docker Compose is available in your machine
    sol. docker compose version 
2. verify the version 
    sol. done

# Task 2: Your first compose file 

1. Create a folder compose-basics
    sol. mkdir compose-basics
2. Write a docker-compose.yml that runs a single Nginx container with port mapping
    sol. touch docker-compose.yml
    services:
      nginx:
        image: nginx:latest
        ports:
          - 80:80
3. Start it with docker compose up
    sol. Done
4. Access it in your browser
    done
5. Stop it with docker compose down
    done

# Task 3: Two-Container Setup


