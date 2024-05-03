# Explanation of Implementation

## Choice of Base Image 

For the backend container , I chose the `node:alpine` base image . Alpine Linux is known for its lightweight nature , which helps keep the Docker image size small . The `node` image provides the necessary environment to run Node.js applications.

For the frontend container, I chose the `nginx:alpine` base image. Alpine Linux is lightweight, and NGINX is widely used as a web server, making it suitable for serving static files efficiently.



## Dockerfile Directives 

### Frontend Container
In the Dockerfile for the frontend container, I used the following directives:
- `FROM nginx:alpine`: Sets the base image to NGINX on Alpine Linux.
- `ENV NODE_OPTIONS=--openssl-legacy-provider`: Sets the environment variable `NODE_OPTIONS` to use the OpenSSL legacy provider.
- `COPY --from=build /app/build /usr/share/nginx/html`: Copies the built frontend files from the build stage into the NGINX HTML directory.
- `EXPOSE 80`: Exposes port 80 to allow external access.
- `CMD ["nginx", "-g", "daemon off;"]`: Specifies the command to start NGINX in the foreground.



### Backend Container
In the Dockerfile for the backend container , I used the following directives :
- `WORKDIR /app` : Sets the working directory inside the container to `/app` .
- `COPY package*.json ./` : Copies the package.json and package-lock.json files into the container .
- `COPY . .`: Copies the rest of the application files into the container.
- `EXPOSE 5001`: Exposes port 5001 to allow external access.
- `CMD ["node", "server.js"]`: Specifies the command to run when the container starts.


## Docker-Compose Networking

The frontend container is exposed on port 80, allowing external access to the NGINX server serving the frontend files. The backend container is exposed on port 5001, enabling communication with the backend Node.js application.


## Git Workflow

I followed a standard Git workflow, including branching, committing changes, and pushing to a remote repository. Pull requests were created and reviewed before merging changes into the main branch.


## Debugging Measures

In case of any issues, I would check the container logs using `docker logs <container_name>` to identify errors. Additionally, I would review the Dockerfile and docker-compose.yml files for any misconfigurations.


## Docker Image Tag Naming Standards

I followed the convention of `<username>/<repository_name>:<version>` for tagging Docker images. For example, `christopherian2004/yolo:v1.0` is an example of a tagged Docker image.


## Screenshot of Deployed Image on DockerHub

!(<Screenshot from 2024-05-03 22-12-20.png>)
