# Prism

Prism registra todo lo que pasa en el servidor: quien puso o rompio cada bloque, quien saco o metio cosas en cofres, quien mato animales, etc. Permite **buscar** quien hizo algo y **deshacerlo** (rollback) o **volver a aplicarlo** (restore). Se usa en vez de CoreProtect, que todavia no tiene version publica para Paper 26.3.

https://modrinth.com/plugin/prism

* **Version instalada:** 4.5 (07-nov-2026). Necesita el plugin **NBT-API** (2.16.1).
* **Base de datos:** SQLite en **'plugins/prism/prism.db'**.
* **Limpieza:** todos los dias a medianoche borra los registros con mas de 6 semanas (**purges.command-schedules** en **prism.conf**).
* **Permisos:** solo operador y consola. Los niños no lo pueden usar.

## Comandos (desde la consola con 'sudo mc-consola.sh "..."')

* **'pr l p:nachitoultra'**: todo lo que hizo un jugador.
* **'pr l p:nachitoultra a:item-remove'**: lo que saco de cofres.
* **'pr l a:block-break p:churros5235 since:1d'**: bloques que rompio en el ultimo dia.
* **'pr rb p:\[jugador] since:1h r:20'**: deshace lo que hizo un jugador en la ultima hora, 20 bloques a la redonda.
* **'pr restore ...'**: vuelve a aplicar lo deshecho.

Parametros utiles: **p:** jugador, **a:** accion (block-break, block-place, item-remove, item-insert...), **since:** tiempo (1h, 2d, 1w), **r:** radio, **w:** mundo.

Documentacion: https://docs.prism-mc.org
