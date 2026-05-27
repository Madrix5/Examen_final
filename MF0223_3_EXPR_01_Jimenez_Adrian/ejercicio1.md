
# Errores encontrados en docker compose

Tenemos el siguiente código de docker-compose:

```yaml
version: '3.8'

services:
  srv_dev_XX:
    image: ubuntu:22
    container: srv_dev_XX
    volumes:
      - datos_devXX:/var/empresa
    networks:
      - net_devXX
    ports:
      - "8090:3000"

  volumes: 
    datos_devXX:
  networks:
    net_dev_XX: # Debe coincidir con el nombre de arriba, aqui se añade un guión bajo.
```

ERRORES:

* Línea 1: no hace falta poner la versión, al ejecutar salta un warning diciendo que es obsoleto.
* Línea 5: faltaría añadir la versión exacta para ser más especificos, por ejemplo 22.04.
* Línea 6: el nombre correcto es container_name, no container.
* Línea 11-12: si no instalamos nada, no es necesario abrir y ocupar un puerto que no va a mostrar nada.
* Línea 14-17: tiene una mala indentación, debes indicarle que esas variable están en la raíz.
* Extra: falta añadir 'tty: true' para que el contenedor no se apague y se mantenga en bucle infinito esperando instrucciones.

Una vez corregidos estos errores ejecutamos el siguiente comando:

```bash
docker compose up -d
```

```bash
docker compose run -it ubuntu:22.04 bash
```

Si queremos apagar el contenedor ejecutariamos:

```bash
docker compose down
```
