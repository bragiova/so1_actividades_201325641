# Gestión de Usuarios
### Creación de usuarios:
```sudo useradd usuario1```  
```sudo useradd usuario1```  
```sudo useradd usuario1```

![img00](./img/img_user1.png)

### Asignación de Contraseñas
```sudo passwd usuario1```  
```sudo passwd usuario1```  
```sudo passwd usuario1```

![img01](./img/img_user2.png)

### Información de Usuarios
```id usuario1``` 

![img02](./img/img_user3.png)

### Eliminación de Usuarios
```sudo userdel usuario3``` 

# Gestión de Grupos
### Creación de Grupos
```sudo groupadd grupo1```   
```sudo groupadd grupo2```   

![img03](./img/img_user4.png)

### Agregar Usuarios a Grupos
```sudo gpasswd -a usuario1 grupo1```   
```sudo gpasswd -a usuario2 grupo2```  

![img04](./img/img_user5.png)

### Verificar Membresía
```groups usuario1```   
```groups usuario1``` 

![img05](./img/img_user6.png)

### Eliminar grupo
```sudo groupdel grupo2```  

# Gestión de Permisos
### Creación de Archivos y Directorios
```
su - usuario1
cat > archivo.txt
mkdir directorio1
cd directorio1
cat > archivo2.txt
```   

![img06](./img/img_user7.png)

### Verificar Permisos
![img07](./img/img_user8.png)

### Modificar Permisos usando chmod con Modo Numérico
```chmod 540 archivo1.txt```

![img08](./img/img_user9.png)

### Modificar Permisos usando chmod con Modo Simbólico
```chmod u+x archivo2.txt```   

![img09](./img/img_user10.png)

### Cambiar el Grupo Propietario
```chgrp grupo1 archivo2.txt```

### Cambiar el Grupo Propietario
```chmod 740 directorio1```

![img10](./img/img_user11.png)

### Comprobación de Acceso
![img11](./img/img_user12.png)

### Verificación Final
![img12](./img/img_user13.png)