# Luck Perms

LuckPerms es un plugin para servidores de Minecraft que permite a los administradores gestionar y asignar permisos a jugadores y grupos de manera eficiente, controlando qué comandos y funciones pueden usar. Es rápido, escalable y ofrece flexibilidad a través de comandos dentro del juego, archivos de configuración o un editor web interactivo.

https://www.spigotmc.org/resources/luckperms.28140/

Todos los usuarios comienza con un grupo inicial por defecto que se llama **default**.

## Variables (Placehorlders)

Todas las variables disponibles de Luck Perms estan publicas en el siguiente link:

https://luckperms.net/wiki/Placeholders

## Informacion del usuario

Para obtener información del usuario en Luck Perms, se debe ejecutar el comando:

* **'/lp user \[nombre_usuario] info'**

## Informacion del grupo

Para obtener información del grupo en Luck Perms, se debe ejecutar el comando:

* **'/lp group \[nombre_grupo] info'**

## Creacion de Rangos

Para crear un rango se debe ejecutar el siguiente comando:

* **'/lp creategroup \[nombre_grupo]'**

## Asignar un grupo a un usuario

Para asginar un usuario a un grupo se debe ejecutar el comando:

* **'/lp user \[nombre_usuario] parent set \[nombre_grupo]'**

## Jerarquia de grupos

Se puede hacer una jerarquia de grupos, haciendo que un grupo herede de otro. Esto permite que los grupos hereden los permisos de sus grupos padres, evitando duplicar permisos en los grupos. Para hacer esta jerarquia se debe ejecutar el comando:

* **'/lp group \[nombre_grupo_hijo] parent set \[nombre_grupo_padre]'**

## Asignacion de permisos

Se puede asiganar permisos por grupo, pero si queremos asiganr todos los permisos a un grupo, se le debe asignar el permiso **'*'**. Esto se realiza con el comando:

* **'/lp group \[nombre_grupo_asignar_permiso] permission set \*'**

## Asignacion de un prefijo al grupo

Se pueden asignar un prefijo al grupo para luego usarlo como variable en el Tab, ScoreBar o chat por ejemplo. Para asiganr un prefijo se debe ejecutar el siguiente comando:

* **/lp group \[nombre_grupo] meta setprefix "\[prefijo]"**
>**NOTA:** El prefijo debe estar entre comillas dobles ("). tambien se pueden asginar colores hexadecial al prefijo usando [esta herramienta](https://www.birdflop.com/resources/rgb/).

## Editor web

Para crear y configurar lso grupos se puede usar el editor web. Para ingresar al editor web se debe seguir los siguientes pasos:

* Ejecutar el comando **/lp editor**.
* Hacer click en el link que aparece en la consola.
* Copiar el comando que aparace en la venta web y ejecutarlo en la consola.

### Seccion de grupos

En la seccion de grupos se puede crear o configurar los grupos. Un punto importante que se debe confirmar es que **todos los grupos tengan la misma prioridad**. Esto se debe corregir, en caso de que algun grupo tenga una prioridad diferente.

Una vez realizado los cambios se debe hacer click en el boton **Apply**, para que los cambios se reflejen inmediatamente en la configuracion del servidor.

### config.yml

