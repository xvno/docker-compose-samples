# 2.1
# FROM python:3.7-alpine

# RUN apk add --no-cache gcc musl-dev linux-headers


# 2.2
FROM volving/python:3.7-alpine-gcc

WORKDIR /code
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt