# Systemd Unit
## Pasos:
### 1. Creación de Script
Se crea un script que imprime un saludo y la fecha actual.
```
#!/bin/bash
fecha=$(date +"%Y-%m-%d")
while true; do
    echo "Hola, La fecha actual es: $fecha"
    sleep 15  
done
```
### 2. Permisos al script
Para poder ejecutar el script, se debe de otorgar permisos para que sea ejecutable.
```
sudo chmod +x Script.sh
```

### 3. Creación del archivo de unidad de servicio
Se crea el archivo con el nombre `saludo-serv.service` en el directorio `/etc/systemd/system/`. El contenido del servicio es:
```
[Unit]
Description=Saludo Service 

[Service]
ExecStart=/usr/local/bin/Script.sh

[Install]
WantedBy=multi-user.target
```
### 4. Recarga de systemd
Se realiza la recarga de systemd para que se pueda reconocer el servicio creado.
```
sudo systemctl daemo-reload
```
### 5. Ejecución de Servicio
Para ejecutar manualmente el servicio, se realiza con el siguiente comando:
```
sudo systemctl start saludo-serv.service
```
### 6. Verificación de estado del servicio
Se puede verificar el status del servicio con el comando:
```
sudo systemctl status saludo-serv.service
```
### 7. Parar servicio
Si se desea detener el servicio se debe de utilizar el siguiente comando:
```
sudo systemctl stop saludo-serv.service
```