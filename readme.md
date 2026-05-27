# Subir examen a github

Primero creamos el repositorio en github.

Vamos a donde vamos a crear el repositorio local, en este caso en MF0223_3_EP_Jimenez_Adrian y ejecutamos los siguientes comandos.

Para crear el repositorio local:

```bash
git init
```

Añadimos los archivos al stack:

```bash
git add .
```

Creamos un commit para tener un backup:

```bash
git commit -m "First commit"
```

Enlazamos el repositorio local con el repositorio remoto de github:

```bash
git remote add origin https://github.com/Madrix5/Examen_final.git
```

Renombramos la rama principal como 'main':

```bash
git branch -M main
```

Subimos los cambios al repositorio remoto:

```bash
git push -u origin master
```
