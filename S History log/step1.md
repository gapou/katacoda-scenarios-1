First, start a new Docker container for a MySQL Server.
`docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=root mysql:latest`{{execute}}

`docker exec -it mysql bash`{{execute}}

`docker exec -it mysql bash`{{execute}}

`mysql -u root -p`{{execute}}

`CREATE USER 'test'@'localhost' IDENTIFIED BY 'pass123546';`{{execute}}
