# A simple MERN stack application 
![mern-stack-3928260886](https://github.com/user-attachments/assets/6758075d-a66a-4380-96c7-c682a80faac4)
![mern-stack-b9q1kbudz0-3925239303](https://github.com/user-attachments/assets/c50b4bf3-5d32-4549-83e2-cd9d791debd7)

### Create a network for the docker containers

`docker network create demo`


### Build the client 

```sh
cd mern/frontend
docker build -t mern-frontend .
```

### Run the client

`docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend`

### Verify the client is running

Open your browser and type `http://localhost:5173`

### Run the mongodb container

`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

### Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```

### Run the server

`docker run --name=backend --network=demo -d -p 5050:5050 mern-backend`

## Using Docker Compose

`docker compose up -d`

