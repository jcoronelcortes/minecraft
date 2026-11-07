# BlueMap

Dibuja el mundo en 3D y lo muestra en una pagina web, con las construcciones y donde esta cada jugador.

https://modrinth.com/plugin/bluemap

* **Version instalada:** 5.29 (07-nov-2026).
* **Pagina:** **http://192.168.4.145:8100** (solo dentro de la casa; el puerto 8100 no esta abierto en el router).
* **Mapas:** world (principal), creativo y ooo (Tierra de Ooo). Los demas estan desactivados (archivos **'.conf.desactivado'** en **'plugins/BlueMap/maps'**).

## Configuracion (plugins/BlueMap/core.conf)

* **accept-download: true:** BlueMap descarga las texturas del juego desde Mojang (acepta la EULA de Minecraft). Sin esto no dibuja nada.
* **render-thread-count: 4:** usa 4 de los 16 nucleos para dibujar, para no afectar el juego.
* **metrics: false:** no envia estadisticas de uso.

Para activar otro mundo: quitar **'.desactivado'** al archivo del mapa y ejecutar **'bluemap reload'**.

## Comandos (desde la consola)

* **'bluemap':** estado y avance del dibujo.
* **'bluemap reload':** recarga la configuracion.
* **'bluemap freeze \[mapa]'** / **'bluemap unfreeze \[mapa]'**: pausa o sigue el dibujo de un mapa.

>**NOTA:** Los mapas dibujados (**'plugins/BlueMap/web/maps'**) no se guardan en los respaldos, porque ocupan mucho y BlueMap los vuelve a dibujar solo.
