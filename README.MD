# using Docker Containers
## Create/run React Vite
```bash
npm create vite@latest react-app -- --template react
cd react-app
npm install
npm run dev -- --host 0.0.0.0 --port 7775
```
Open:
```bash
http://localhost:7775
```
## Create Dockerfile

In the project root, create a file named Dockerfile:
```bash
FROM node:22-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 7775

CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0", "--port", "7775"]
```

## Create .dockerignore
```bash
node_modules
dist
.git
```
## Build Docker image
```bash
docker build -t react-app .
```
## Run Docker container on port 7775
````bash
docker run --name lastName_firstName_coding_assignment11 -p 7775:7775 react-app
```

