# SXE - Tarea 10 - Odoo + PgAdmin

## Instala Odoo 17 Community con docker-compose.

Los comandos empleados durante esta parte son los siguientes:

```
mkdir SXE_Tarea10
cd SXE_Tarea10
touch README.md
touch docker-compose.yml
```

Desde tu editor de texto favorito abre el archivo **docker-compose.yml** y pega el siguiente código:

```
services:
  web:
    image: odoo:17.0
    depends_on:
      - mydb
    ports:
      - "8069:8069"
    environment:
      HOST: mydb
      USER: odoo
      PASSWORD: myodoo
    volumes:
      - odoo-web-data:/var/lib/odoo

volumes:
  odoo-web-data:
```

**Cierra y guarda el archivo** para luego ejecutar el comando `sudo docker compose up -d`. Este comando levanta los contenedores en segundo plano.

Si lo que vemos es lo siguiente entonces todo ha ido correctamente:

![compose](./images/compose-d.png)

Para confirmarlo definitavemente, si vas a la direccion `http://localhost:8069` debería cargarte la siguiente página:

![odoo](./images/odoo.png)

## Instala PgAdmin y conectala a lo BBDD

En el readme tiene que estar explicado las diferentes partes del docker-composer, así como los comandos para lanzar los contenedores y capturas de pantalla que demuestren la instalación de Odoo, configuración y acceso al mismo así como de PgAdmin. Es necesario incluir una captura DENTRO de Odoo para demostrar que se ha instalado y configurado correctamente y también dentro de PgAdmin (instalad primero odoo y cread una base de datos).

## ¿Que ocurre si en el ordenador local el puerto 5432 está ocupado? ¿Y si lo estuviese el 8069? ¿Como puedes solucionarlo?

