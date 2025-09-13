# nLogin

nLogin es un plugin de Minecraft para servidores no premium que funciona como un sistema de autenticación de usuarios, permitiéndoles registrarse y acceder a un servidor usando una contraseña. Su propósito es asegurar el servidor al:

* Proteger cuentas de acceso no autorizado.
* Prevenir ataques de bots al controlar el acceso inicial.
* Proporcionar seguridad a los jugadores mediante contraseñas.

https://docs.nickuc.com/

## Configuracion inicial

Al ingresar al servidor por primera vez, aparecera un mensaje que solicitara registrarse. Para hacer esto se debe ejecutar el comando:

* **/register [nombre_usuario] [nueva_password]**

En el caso de ser OP, la pantalla se bloqueara con nuevo menu para seleccionar unas opciones extras. Las opciones a seleccionar son:

* Setup plugin
* Stable channel
* Automatic updates
* Refuse (para no instalar el sistema anti bot)

## Ingreso al servidor

Cada vez que un usuario ingrese al servidor le aparecera un mensaje solicitando que haga login. Para hacer esto debe ejecutar el comando:

* **/login [password]**

## Archivos de configuracion

### config.yml

* **join.remove-join-message:** Establece si se muestra (false) o se elimina (true) el mensaje de que el jugador se ha unido al juego en el chat.

* **advance.client.allowed-commands:** Establece la lista de comandos permitidos antes de autenticarse. Por seguridad la lista se deja vacia ([]) para solamente permitir los comandos **register** y **login**.

* **security.ip-limit.bypass.ips:** Security permite limitar el numero de cuentas que estan registradas a una misma IP. Este parametro permite definir la lista de IPs que ignoran esta limitacion, por lo cual, por seguridad se recomienda que sea una lista vacia ([]).

