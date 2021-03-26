# SIMPLE 2.0

### Instalacion para Azure:

1) Crear un Azure Container Registry (Basic instance) en su cuenta de Azure (6 dolares al mes)

2) Crear un Azure Database for Mysql en Azure. Luego de crearlo, dirijase al recurso y vaya a Settings y pinche en connection security. Debe habilitar el accesso a los recursos de Azure, añadir las ips de las maquinas que se conectaran a Azure (puede habilitar todas las ips añadiendo 0.0.0.0 a 255.255.255.255) y deshabilitar las conexiones SSL (Luego puede habilitarla siguiendo estos pasos https://docs.microsoft.com/en-us/azure/app-service/tutorial-php-mysql-app?pivots=platform-linux#configure-tlsssl-certificate)

3) Conectarse via mysql -u username@mysqlinstance" -h mysqlinstance.mysql.database.azure.com -P 3306 -p 

EJ:  mysql -u sag@simplecontainer -h simplecontainer.mysql.database.azure.com -P 3306 -p

4) Corra el comando CREATE DATABASE simple; y cierre la conexion a la base de datos.

5) Debe descargar este repositorio a su maquina local.

6) Dentro de .env, debe agregar sus credenciales en MYSQL como indica el archivo.

7) Debe instalar el Azure CLI (https://aka.ms/installazurecliwindows) en su maquina local.

8) Dentro de la carpeta de este repositorio, debe correr az acr build -t simple:1.0.0 -r " Your Azure Container Registry Instance" -f Dockerfile .

EJ: az acr build -t simple:1.0.0 -r simplebasic -f Dockerfile .

9) Luego de este comando (10 min aprox), proceda a crear un app service con 


Container image creation for Simple:

#local

docker build -t simple:1.0.0 -f Dockerfile .

#Azure

az acr build -t simple:1.0.0 -r " Your Azure Container Registry Instance" -f Dockerfile . 
