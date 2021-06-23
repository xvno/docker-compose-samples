FROM python:3.7-alpine

RUN apk add --no-cache gcc musl-dev linux-headers

WORKDIR /code
COPY . .
RUN pip install -r requirements.txt

ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
EXPOSE 5000

CMD ["flask", "run"]