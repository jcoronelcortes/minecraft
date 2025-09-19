# Mini MOTD

MiniMOTD es un plugin para servidores de Minecraft (tanto para Paper como para Fabric) que permite personalizar de forma atractiva el "Message of the Day" (MOTD), que es el texto y el icono que se muestran en la lista de servidores del juego. Este plugin se destaca por su soporte para colores RGB y degradados mediante el formato MiniMessage, además de ofrecer otras funcionalidades como la aleatorización de iconos y la personalización del número de jugadores.

https://www.spigotmc.org/resources/minimotd-server-list-motd-plugin-with-rgb-gradients.81254/

## Archivos de configuracion

Cada vez que se realiza un cambio en los archivos de configuracion, se debe ejecutar el siguiente comando para actualizar los cambios en el servidor:

* **/minimotd reload**

### main.conf

* **icon-enabled:** Debe tener el valor **false** si queremos que utilice el icono del servidor o **true** si queremos usar los iconos configurados en este plugin.
* **max-players-enabled:** Debe tener el valor **false** si queremos que muestre el número real de jugadores conectados o **true** si queremos usar el numero falso definido en la variable **max-players**.
* **motds:** Permite definir el icono y los textos que aparaceran en la lista de servidores. Se puede configurar mas de una opcion. **IMPORTANTE:** El formato de los texto es en MiniMessage, para lo cual se puede usar el MiniMessage Viewer (https://webui.advntr.dev). tambien se pueden agregar simbolos unicode al texto (https://www.fileformat.info/info/unicode/category/So/index.htm).