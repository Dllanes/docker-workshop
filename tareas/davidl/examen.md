# Respuestas Examen 1

## Ejercicio 1
docker run --name mysql_db -e MYSQL_USER=foo -e MYSQL_ROOT_PASSWORD=contraSugurisima -e MYSQL_PASSWORD=bar123 -e MYSQL_DATABASE=baz -d -p 4000:4000 mysql:8

## Ejercicio 2
Para crear la base de datos se utiliza
docker run -d -e MONGO_INITDB_ROOT_USERNAME=DAS -e MONGO_INITDB_ROOT_PASSWORD=extra123 -p 27017:27017 --name m1 mongo

Para el cliente de mongo express se usa el siguiente comando
docker run --name=mexpress -e ME_CONFIG_MONGODB_SERVER=m1  -e ME_CONFIG_BASICAUTH_USERNAME=DAS -e ME_CONFIG_BASICAUTH_PASSWORD=extra123 --link m1:m1 -p 8081:8081 -d mongo-express 

## Ejercicio 3
Para el volumen, usamos el comando 
docker volume create mongo_volume

Ejecutamos este comando para levantar la instancia de mongo
docker run --name mongo -v mongo_volume:/var/lib/mongo_data -p 27017:27017 -d mongo

## Ejercicio 4
Use el archivo Dockerfile que esta en esta carpeta
Para el build "docker build -t dllanes/static_flask ."

y luego para ejecutar el se uso "docker run -d --name flask -p 5000:8000 dllanes/static_flask"
docker build -t flask" 