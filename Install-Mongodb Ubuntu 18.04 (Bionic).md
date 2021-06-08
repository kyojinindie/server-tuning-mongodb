# Mongo

## Instalación Ubuntu 18.04 (Bionic)

1\.-Importe la clave pública utilizada por el sistema de gestión de paquetes.

```
wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
```

2\.- Crear un archivo de lista para mongodb

```
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
```

3\.- Recargar la base de datos de paquetes local

```
sudo apt-get update
```

4\.- Instalar los paquetes de mongodb

```
sudo apt-get install -y mongodb-org
```

5\.- Start MongoDB

```
sudo systemctl start mongod
```

6\.- Verificar que el servicio inicio

```
sudo systemctl status mongod
```

7\.- Comandos adicionales (stop, restart)

```
sudo systemctl stop mongod
sudo systemctl restart mongod
```

8\.- Uso

```
mongo
```

## **Reinstalar mongodb en caso de fallo**

```
sudo apt purge mongodb-org*
sudo rm -r /var/log/mongodb
sudo rm -r /var/lib/mongodb
wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
sudo apt update
sudo apt-get install -y mongodb-org
```
