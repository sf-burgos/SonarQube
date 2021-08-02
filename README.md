# SonarQube

## Conectarse por ssh a una maquina virtual

1. Entrar a una pagina de power shell

> ssh -i C:\Users\Brayan\Desktop\SonarQube\AzureKeys.pem azureuser@52.156.156.25

## Instalacion de paquetes JAVA DEVELOPMENT KIT

> sudo apt update

Revisar que no exita una version de Java

> java -version

Instalar java

> sudo apt install default-jre

instalar compilador de java

> sudo apt install default-jdk

Para verificar la instalacion usar 

> java -version

> javac -version

## Instalacion de POSTGRESQL y configuración

instalación en Ubuntu

> sudo apt install postgresql postgresql-contrib

consulta de instalación de POSTGRESQL

> sudo -u postgres psql -c "SELECT version();"

activar sql como servicio

> sudo systemctl enable postgresql.service

iniciar sql como servicio

> sudo systemctl start postgresql.service

configurar postgres: cambiar contraseña por buenas practicas

> sudo passwd postgres

Cambiar de usuario que se crea al instalar

> su - postgres

Crear usuario en POSTGRESQL

> createuser sonar

Ir al shell de postgresql:

> psql

cambiar la contraseña del usuario 'sonar' ya creado:

> ALTER USER sonar WITH ENCRYPTED PASSWORD 'burgos1437';

Crear una base de datos para SONARQ y que el dueño sea 'sonar'

> CREATE DATABASE sonarQDataBase OWNER sonar;

Todos los privilegios para 'sonar' 

> GRANT ALL PRIVILEGES ON DATABASE sonarQDataBase to sonar;

Salir del SHELL de postgresql

> \q

Salir del modo privilegiado.

> exit

Reiniciar el servicio de postgres

> sudo systemctl restart postgresql

Verificar el estado del servicio 

> sudo systemctl status postgresql

## Instalacion de SONARQ

crear una carpeta temporal 

> sudo mkdir /sonarQ

entrar a la carpeta creada

> cd /sonarQ/

instalar sonarQube

> sudo curl -O https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-8.9.1.44547.zip

instalar zip en la maquina virtual

> sudo apt-get install zip

Crear un grupo para sonarQ

> sudo groupadd sonar
            