## Dockerfile

```js
// Base Image
FROM node:20-alpine

// Where app data stored
WORKDIR /app

// first (.) means copy all data in WORKDIR
//  second (.) means where to copy

COPY . .

// RUN command execute while building the Docker Image
RUN npm install

EXPOSE 3000

// Execute when container start
CMD ["node", "dist/index.js"]
```

---

## Step 1: Clone the Repo

## Step 2: Create Docker Image

```bash
docker build -t <image-name> <path>
```

## Step 3: Run Docker Image

```bash
docker run -d -p 3000:3000 DATABASE_URL="postgresql://postgres:password@localhost:5432/db_name" <image_name>
```

---

## SSH into docker container

```bash
docker ps
docker exec -it <containerId> /bin/bash
or
docker exec -it <containerId> /bin/sh

```

---

## Volumes

- Volumes helps to persist data even after container terminated 
- Access this create new container and attach volume to that

```bash
docker volume create <volume-name>

docker run -v <volume-name>:/data/db/ -d -p 27017:27017 mongo

```
