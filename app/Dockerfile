FROM python:3.11-alpine

ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0

WORKDIR /code

RUN apk add --no-cache gcc musl-dev linux-headers

COPY requirements.txt ./

RUN pip install -r requirements.txt

EXPOSE 5000

RUN adduser -D -g '' flaskuser
USER flaskuser

COPY --chown=flaskuser:flaskuser . .

CMD ["flask", "run", "--debug"]