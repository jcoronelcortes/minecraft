# Respaldos y restauracion

Los scripts estan instalados en **'/usr/local/bin/'** y se ejecutan con **sudo**. Los respaldos quedan en **'/home/papermc/backups'**.

Cada respaldo es un solo archivo comprimido con **toda** la carpeta del servidor (mundos, plugins con su configuracion, archivos .yml y server.jar).
El nombre incluye la fecha y la version de Paper, por ejemplo **'minecraft-2026-11-07_084505-paper-26.3-244-35a2d15.tar.zst'**.
Se guardan los **3 mas recientes** y los anteriores se borran solos.

## Hacer un respaldo

* **'sudo mc-backup.sh'**
>Respaldo en caliente: el servidor sigue encendido y los jugadores no se desconectan. Desactiva el guardado automatico, guarda el mundo, comprime y lo vuelve a activar.

* **'sudo mc-backup.sh --stop'**
>Apaga el servidor, respalda y lo vuelve a encender. **Recomendado antes de actualizar.**

* **'sudo mc-backup.sh --stop --no-start'**
>Apaga el servidor y respalda, pero lo deja apagado (para actualizar despues).

* **'sudo mc-backup.sh --list'**
>Muestra los respaldos existentes.

* **'sudo KEEP=5 mc-backup.sh'**
>Cambia cuantos respaldos se conservan (por defecto 3).

## Restaurar un respaldo

* **'sudo mc-restore.sh'**
>Lista los respaldos disponibles.

* **'sudo mc-restore.sh ultimo'**
>Restaura el respaldo mas reciente.

* **'sudo mc-restore.sh \[archivo.tar.zst]'**
>Restaura un respaldo especifico.

La restauracion pide confirmacion, apaga el servidor y **no borra nada**: la instalacion actual se renombra a
**'/home/papermc/minecraft.antes-de-restaurar-\[fecha]'** por si se quiere volver a ella.

## Enviar comandos a la consola

* **'sudo mc-consola.sh "comando 1" "comando 2"'**
>Envia comandos a la consola del servidor (sesion screen **mcjava**) y muestra la respuesta. Ejemplo: **'sudo mc-consola.sh "list" "lp listgroups"'**.

## Respaldo automatico (opcional)

Para hacer un respaldo todos los dias a las 4 de la mañana, agregar con **'sudo crontab -e'**:

```
0 4 * * * /usr/local/bin/mc-backup.sh >> /var/log/mc-backup.log 2>&1
```

>**NOTA:** los respaldos quedan en el mismo disco que el servidor. Conviene copiar uno de vez en cuando a otro disco o a la nube.
