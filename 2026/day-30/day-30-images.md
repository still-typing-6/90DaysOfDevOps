# Task 1:Docker Images
Q1. Pull the nginx, ubuntu, and alpine images from Docker Hub
    Ans. Done
Q2. List all images on your machine — note the sizes
    Ans. Done
Q3. Compare ubuntu vs alpine — why is one much smaller?
    Ans. alpine is much smaller it only takes 13.1MB of disk space where as the ubuntu take the 160MB of disk space.
Q4. Inspect an image — what information can you see?
    Ans. Done
Q5. Remove an image you no longer need
    Ans. Done

# Task 2:Images Layer
Q1. Run docker image history nginx --- what did you see? 
docker image history nginx
    IMAGE          CREATED      CREATED BY                                      SIZE      COMMENT
    1881968aff6f   2 days ago   CMD ["nginx" "-g" "daemon off;"]                0B        buildkit.dockerfile.v0
    <missing>      2 days ago   STOPSIGNAL SIGQUIT                              0B        buildkit.dockerfile.v0
    <missing>      2 days ago   EXPOSE map[80/tcp:{}]                           0B        buildkit.dockerfile.v0
    <missing>      2 days ago   ENTRYPOINT ["/docker-entrypoint.sh"]            0B        buildkit.dockerfile.v0
    <missing>      2 days ago   COPY 30-tune-worker-processes.sh /docker-ent…   16.4kB    buildkit.dockerfile.v0
    <missing>      2 days ago   COPY 20-envsubst-on-templates.sh /docker-ent…   12.3kB    buildkit.dockerfile.v0
    <missing>      2 days ago   COPY 15-local-resolvers.envsh /docker-entryp…   12.3kB    buildkit.dockerfile.v0
    <missing>      2 days ago   COPY 10-listen-on-ipv6-by-default.sh /docker…   12.3kB    buildkit.dockerfile.v0
    <missing>      2 days ago   COPY docker-entrypoint.sh / # buildkit          8.19kB    buildkit.dockerfile.v0
    <missing>      2 days ago   RUN /bin/sh -c set -x     && groupadd --syst…   86.7MB    buildkit.dockerfile.v0
    <missing>      2 days ago   ENV DYNPKG_RELEASE=1~trixie                     0B        buildkit.dockerfile.v0
    <missing>      2 days ago   ENV PKG_RELEASE=1~trixie                        0B        buildkit.dockerfile.v0
    <missing>      2 days ago   ENV ACME_VERSION=0.3.1                          0B        buildkit.dockerfile.v0
    <missing>      2 days ago   ENV NJS_RELEASE=1~trixie                        0B        buildkit.dockerfile.v0
    <missing>      2 days ago   ENV NJS_VERSION=0.9.6                           0B        buildkit.dockerfile.v0
    <missing>      2 days ago   ENV NGINX_VERSION=1.29.8                        0B        buildkit.dockerfile.v0
    <missing>      2 days ago   LABEL maintainer=NGINX Docker Maintainers <d…   0B        buildkit.dockerfile.v0
    <missing>      6 days ago   # debian.sh --arch 'amd64' out/ 'trixie' '@1…   87.4MB    debuerreotype 0.17
Q2. Each line is a layer. Note how some layers show sizes and some show 0B
    Ans. When you create a dockerfile you define the base image and other configration using (FROM, WORKDIR, COPY, RUN, CMD) so whenever there is a instruction it create a new layer.
         Layers show 0B usually from matadata instruction like (CMD, WORKDIR, ENV, LABEL). This instruction does not added a new data so that's why it show 0B.
Q3. Write in your notes: What are layers and why does Docker use them?
    Ans. Docker uses layers for:

        faster image builds through caching
        efficient storage through layer sharing
        faster image downloads
        reusability between images
        easier rollback/versioning
        reduced bandwidth usage    

    Docker layers are immutable read-only filesystem changes created by Dockerfile instructions.
    Each instruction in a Dockerfile usually creates a new layer.

# Task 3: Container lifecycle

Q1. Practice the full lifecycle on one container:

    Create a container (without starting it)
    Start the container
    Pause it and check status
    Unpause it
    Stop it
    Restart it
    Kill it
    Remove it
    Ans. Done

# Task 4: Working with running container

Q1. Run an Nginx container in detached mode
    Ans. docker run -d -p 80:80 nginx
Q2. View its logs
    Ans. docker logs nginx
Q3. View real-time logs (follow mode)
    Ans. docker logs -f nginx 
Q4. Exec into the container and look around the filesystem
    Ans. 06
Q5. Run a single command inside the container without entering it
    Ans. Done
Q6. Inspect the container — find its IP address, port mappings, and mounts
    Ans. Done
