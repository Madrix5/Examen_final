# Ejercicio 2

## Creamos toda la estructura de directorios

```bash
mkdir frontend backend frontend/src  frontend/public frontend/src/components frontend/src/pages frontend/src/styles backend/app backend/config backend/tests database database/migrations docs scripts
```

## Instalamos nano

```bash
sudo apt update
sudo apt install nano
```

## Editamos los archivos con nano

```bash
nano (ruta del archivo)
```

Para guardar un archivo en nano pulsamos ^O y a continuación enter.
Para salir del editor pulsamos ^X.

## Listamos los archivos

Yo he instalado tree para tener una visión más clara, pero podríamos ejecutar ```bash ls -lRa``` que es totalmente nativo.

Con tree quedaría:

```bash
tree -a
```

Para mostrar el contenido de frontend/src/ tendríamos:

```bash
tree -a frontend/src
```

## Creamos una carpeta backup

```bash
mkdir backup
```

## Copiamos el frontend dentro de backup

```bash
cp -r frontend backup/frontend
```

Hacemos lo mismo con server.js y lo renombramos a server_backup.js

```bash
cp backend/app/server.js backup/server_backup.js
```

## Reorganizamos el proyecto

Movemos main.css a frontend/public

```bash
mv frontend/src/styles/main.css frontend/public
```

Renombramos App.js a app.js

```bash
mv frontend/src/App.js frontend/src/app.js
```

Movemos config.json a backend/app

```bash
mv backend/config/config.json backend/app
```

## Permisos y seguridad

* deploy.sh ejecutable solo para el propietario.
* server.js lectura/escritura propietario, lectura solo el grupo.
* README.md solo lectura para todos.

```bash
chmod 700 scripts/deploy.sh 
```

```bash
chmod 640 backend/app/server.js
```

```bash
chmod 444 README.md
```

## Simulación de error y recuperación

Eliminamos frontend/src/components

```bash
rm -rf 
```

La recuperamos del backup

```bash
cp -r backup/frontend/src/components frontend/src/components
```

## Limpieza y verificación final

Eliminamos la carpeta temp/ (como no la hemos creado no existe en este preciso instante del espacio tiempo):

```bash
rm -rf temp
```

Eliminamos server_backup.js:

```bash
rm backup/server_backup.js
```

Mostramos la estructura actual:

```bash
tree -a
```

Mostramos la ruta actual:

```bash
pwd
```

Mostramos el historial de comandos:

```bash
history
```
