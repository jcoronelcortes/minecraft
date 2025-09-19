# Economy Shop GUI

Es un plugin para servidores de Minecraft que permite crear y gestionar una tienda con una interfaz gráfica de usuario (GUI) para que los jugadores compren y vendan objetos usando moneda virtual. Es un sistema de tiendas altamente configurable, donde los administradores pueden crear categorías, definir precios de compra y venta, añadir o eliminar ítems personalizados, y hasta modificar el inventario o características de los objetos directamente desde el juego, todo ello sin necesidad de reiniciar el servidor.

https://www.spigotmc.org/resources/economyshopgui.69927/

Toda la informacion y documentacion del plugin esta en la Wiki:

* https://wiki.gpplugins.com/economyshopgui


# Comandos

* **/shop :** Abre una ventana con el inventario para comprar y vender.


# Archivos de configuracion

Cada vez que se modifica un archivo de configuracion se debe ejecutar el comando **/sreload**.

## config.yml

* **language-file :** Permite definir el idioma de los mensajes. Para dejarlo en español se debe usar **lang-es.yml**.
* **local :** Permite definir el formato de las monedas. Para dejarlo en español, se debe usar **es-ES*.
* **disabled-wolrds-per-command :** Permite desactivar comandos por mundo. Se puede borrar todo y dejarla vacia si no se quiere bloquear comandos por mundo.
* **main-menu.fill-items.enable :** Permite activar (**true**) o desactivar (**false**) que los casilleros vacios se rellenen con bloques trasparentes.
* **main-menu-nav-bar :** Permite configurar la barra inferior de navegacion.
* **shop-commands :** Listado de comandos que el jugador puede ejecutar para abrir la tienda.
* **enable-spawnerbreak :** Se recomienda dejarlo en **'false'**.
* **enable-spawnerplace :** Se recomienda dejarlo en **'false'**.