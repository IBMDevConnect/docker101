- Create your [Github](https://github.com/) and [DockerHub](https://hub.docker.com/) Accounts

- Login to [Docker Playground](https://labs.play-with-docker.com/) with your docker hub ID

## Assignment 1:

Run the following commands on Docker playground

```
docker container run --name welcome hello-world:latest
docker container ls --all
```

```
docker container run -t -i --privileged --rm ubuntu bash
```

```
uname -a
exit
```

```
docker container rm -f $(docker ps -aq)
```

## Asignment 2:

- Download app.zip from git repo or from [here](http://ip172-18-0-47-c1mgkhpbqvp000aacg80-80.direct.labs.play-with-docker.com/assets/app.zip)
- Drag & drop it on Docker playground terminal
- Execute the following command in sequence

```
unzip app.zip
cd app
ls
```

- Create a file with name “Dockerfile” without extensions and save it as “all files” type
- Add the following contents to Dockerfile

```
FROM node:10-alpine
WORKDIR /app
COPY .  .
RUN yarn install --production
CMD [“node”, “/app/src/index.js”]

```

- Drag and drop Dockerfile into the Play with Docker terminal

```
docker build -t docker-101:1.0 .
docker image ls
```

```
docker run -d -p 5000:3000 docker-101
docker container ls
docker container kill b3c
```

- Go to Docker Hub and log in if you need to.
- Click the Create Repository button.
- For the repo name, use 101-todo-app. Make sure the Visibility is Public.
- Click the Create button!

```
docker login -u YOUR-USER-NAME
docker tag docker-101 YOUR-USER-NAME/101-todo-app
docker push YOUR-USER-NAME/101-todo-app
docker run -dp 3000:3000 YOUR-USER-NAME/101-todo-app
```
