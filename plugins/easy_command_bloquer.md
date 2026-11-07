# Easy Command Blocker

Es un plugin o complemento para servidores que permite a los administradores bloquear comandos específicos para los jugadores, e incluso ocultar estos comandos de la lista que aparece al usar la tecla TAB (autocompletado). El propósito es evitar que los usuarios ejecuten comandos no deseados o que no deben tener acceso, lo que ayuda a mantener el control y la seguridad del servidor.

https://www.spigotmc.org/resources/easycommandblocker-spigot-waterfall-velocity-1-8-1-21-8.101752/

>**NOTA:** Este plugin puede usar [Protocol Lib](protocol_lib.md) de forma opcional, pero no lo necesita (funciona sin el desde nov-2026).
>
>En nov-2026 se quitaron **/login**, **/register** y **/changepassword** de las listas de comandos, porque esos comandos eran de nLogin.
>Para recargar este plugin: **/ecb reload**.

Al instalarlo, se recomienda borrar la configuracion por defecto de **'custom_commands_actions''**.


* Configuracion del archivo config.yml

Se debe ejecutar el comando **/lp reloadconfig** para que el servidor tome los cambios

* **blocked_command_default_actions:** permite configurar el texto que se mostrara cuando no tiene permisos para ejecutar un comando.
* **use_commands_as_whitelist:** Si esta en 'true', todos los comandos se bloquearan a excepcion de los comandos definidos en la lista **'commands'**.

** Configuracion de grupos (Luck Perms) en el archivo de configuracion

El archivo de configuracion trae por defecto el grupo **default**, pero se pueden agregar los grupos creados en Luck Perms para asignar el permniso de ejecutar comandos por grupos. Cada vez que se agrega un grupo, se debe ejecutar el siguiente comando para dar el permiso en Luck perms:

* **/lp group \[nombre_grupo] permissions set easycommandblocker.tab.\[nombre_grupo]**