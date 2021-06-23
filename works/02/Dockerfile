# 2.1
# FROM python:3.7-alpine

# RUN apk add --no-cache gcc musl-dev linux-headers


# 2.2
# FROM volving/python:3.7-alpine-gcc

# WORKDIR /code
# COPY requirements.txt requirements.txt
# RUN pip install -r requirements.txt

# 2.3
FROM volving/python:3.7-alpine-gcc-flask-redis

ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
EXPOSE 5000

VOLUME ["/code"]
CMD ["flask", "run"]