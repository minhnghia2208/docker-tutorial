# Summary:
This small project is for practicing deploying application using Docker

Follwing: udemy.com/course/docker-kubernetes-the-practical-guide course, chapter 5

# Directory:
./backend: ExpressJS

    - Contains backend JavaScript code

./frontend: ReactJS

    - Contains frontend JavaScript code

## How to deploy application:

1. Front-end:
```console
docker build -t node_frontend:latest ./frontend
```
```console
docker run -it --rm -p 3000:3000 --name node_frontend_chap_5 -v "$(pwd)/frontend:/app" -v /app/node_modules node_frontend
```
2. MongoDB: 
```console
docker run --name mongodb_chap_5 -v mongo_chap_5:/data/db -d --rm -e --network chapter_5 mongo
```
3. Back-end:
```console
docker build -t node_backend:latest ./backend
```
```console
 docker run --name node_backend_chap_5 -v backend_chap_5:/app/logs -v "$(pwd)/backend:/app" -v /app/node_modules --network chapter_5 --rm -d --env-file ./backend/.env -p 80:80 node_backend:latest
```