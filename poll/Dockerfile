FROM python:3.8-slim

COPY poll /app

WORKDIR /app
RUN pip3 install  -r requirements.txt

EXPOSE 80

CMD ["flask", "run", "--host=0.0.0.0", "--port=80"]