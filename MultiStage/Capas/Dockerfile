#Capa 1: la imagen base
FROM ubuntu:latest

#Capa 2:
RUN apt-get update && \
  apt-get install -y curl && \
  rm -rf /var/lib/apt/lists/*

#Capa 4
COPY . /app

#Capa 5
CMD ["echo", "Hello World"]
