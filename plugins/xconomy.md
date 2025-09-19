# XConomy

XConomy es un plugin para servidores de Minecraft que añade un sistema de economía y dinero virtual para los jugadores, permitiendo crear tiendas, trabajos y otros elementos económicos dentro del juego. Requiere otros plugins como Vault para funcionar y permite a los administradores configurar la moneda, el saldo inicial y los comandos para gestionar la economía del servidor.

https://www.spigotmc.org/resources/xconomy.75669/

# Comandos basicos

La lista de todos los comandos esta en la [pagina](https://www.spigotmc.org/resources/xconomy.75669/).

* **/money :** Muestra el dinero disponible del jugador
* **/xconomy help :** Muestra la ayuda del plugin.
* **/balance :** Hace lo mismo que el comando **/money**.
* **/eco set \[nombre_usuario] \[cantidad_de_dinero] :** Asigna una cantidad de dinero al jugador.
* **/eco take \[nombre_usuario] \[cantidad_de_dinero] :** Quita una cantidad de dinero al jugador.
* **/eco give \[nombre_usuario] \[cantidad_de_dinero] :** Permite dar una cantidad extra de dinero al jugador.
* **/pay \[nombre_usuario] \[cantidad_dinero] :** Permite pagar una cantidad de dinero a un jugador.


# Archivos de configuracion

Se recomienda reiniciar el servidor al hacer cambios en los archivos de configuracion.

## config.yml

* **Settings.initial-bal:** Define el balance inicial con el que un nuevo jugador comienza.
* **Currency.singular-name:** Permite cambiar el nombre que tendra la moneda en singular.
* **Currency.plural-name:** Permite cambiar el nombre que tendra la moneda en plural.
* **Currency.integer-bal:** Si esta en **'false'** la moneda permite decimales, pero si esta en **'true'** la moneda solo permite numeros enteros.
* **Currency.thousands-separator:** Permite definir el caracter para el separador de miles.

## message.yml

* **prefix:** Permite definir el prefijo que aparecera en los mensajes del chat.

# Permisos

El plugin activa por defecto todos los permisos disponibles en la [pagina](https://www.spigotmc.org/resources/xconomy.75669/). Para desactivar los permisos se debe usar Luck Perms.

Por ejemplo, para que los jugadores no puedan ver el dinero que tienen otros jugadores se debe ejecutar el siguiente comando:

* **lp group \[nombre_grupo] permission set xconomy.user.balance.other false**