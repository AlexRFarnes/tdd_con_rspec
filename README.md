# tdd_con_rspec

## Requisitios
Es necesario tener instalado:
- Docker
- Docker compose

## Clonar repositorio
El proyecto se compone de dos repositorios, el repositorio principal donde tenemos nuestro archivo docker compose y configuramos nuestras variables de ambiernte. El segundo repositorio es el proyecto de rails con nuestro código.

`git clone --recurse-submodules https://github.com/AlexRFarnes/tdd_con_rspec`

## Iniciando el setup
Dentro de la carpeta environments escribir el valor de nuestras credenciales.

Creamos nuestra imagen del proyecto store api
```
  docker-compose build
```
Iniciamos nuestros servicios
```
  docker-compose up -d
```
Entramos al contenedr
```
docker exec -it store_api bash
```
Creamos la base de datos del proyecto
```
  rails db:create
```
Ejecutamos las migraciones del proyecto
```
  rails db:migrate
```
## Services
* Store api
  * Nombre del servicio: store_api
  * Port: 3000
  * Dependencias: db_store
* Postgres
  * Nombre del servicio: db_store 
  * Port: 5432
