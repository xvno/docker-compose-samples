# Docker compose sample app

## Refs

- https://docs.docker.com/compose/gettingstarted/#step-1-setup
- https://docs.docker.com/samples/wordpress/
- https://docs.docker.com/samples/django/


## works

1. make a simple Flask-redis app running in container;
2. optimize the docker iamges and rebuild the app;
3. try other commands

### 1. Flask-redis

#### 1.1 create `requirements.txt` and `app.py` (the flask app)

#### 1.2 install `docker` & `docker-compose`

#### 1.3 create a new `Dockerfile`

#### 1.4 create `docker-compose.yml` file

#### 1.5 build and run
```sh
docker-compose up
# to stop
docker-compose stop # or
docker-compose down # delete
```

### 2. Optimize docker image, spec for python:3.7-alpine -> volving/python:3.7-alpine-gcc -> volving/python:3.7-alpine-gcc-flask-redis

#### 2.1 make `volving/python:3.7-alpine-gcc`


```sh
docker build -t python:3.7-alpine-gcc .
```

> rename this image and push to my dockerhub repo

```sh
docker login
docker tag python:3.7-alpine-gcc volving/python:3.7-alpine-gcc
docker push
```

#### 2.2 make `volving/python:3.7-alpine-gcc-flask-redis`

```sh
docker build -t python:3.7-alpine-gcc-flask-redis .
docker tag python:3.7-alpine-gcc-flask-redis volving/python:3.7-alpine-gcc-flask-redis
docker push
```


#### 2.3 use `volving/python:3.7-alpine-gcc-flask-redis` in `docker-compose.yml`

```sh
docker-compose up
```

### 3. try other commands