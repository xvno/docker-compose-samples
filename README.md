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

#### Frequently Used Commands

- `up`: `docker-compose up` build and run a project, use `--build` to rebuild
- `stop`: `docker-compose stop` runs in the directory with `docker-compose.yml`
- `start`: `docker-compose start` to start the stopped project
- `down`: stop and remove containers, add `--volumes` if volumes are to removed: `docker-compose down --volumes`
- `-d`: to run in detached mode: `docker-compose up -d`
- `-f`: to specify a compose file, can use multiple times.
- `-p`: specify a certain name for the project
- `run`: `docker-compose run <service name> <command name>` to run one-off commands for the service: `docker-compose run web env` # to run env in newly started web container
#### others
use `docker-compose --help` to see the **man**
