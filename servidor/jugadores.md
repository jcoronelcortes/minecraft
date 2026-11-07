# Jugadores: quien puede entrar y como agregar nuevos

## Como esta configurado (nov-2026)

* **Modo online** (**online-mode=true**): solo entran cuentas oficiales de Minecraft Java (Microsoft). Nadie puede entrar con el nombre de otro.
* **Lista blanca activada** (**white-list=true** y **enforce-whitelist=true**): solo entran los jugadores de la lista. Cualquier otro es rechazado al conectarse.
* **Nadie es OP.** La administracion se hace desde la consola del servidor con **'sudo mc-consola.sh "comando"'** (ver [Respaldos](respaldos.md)).

| Jugador | Quien es | Grupo de LuckPerms |
|---|---|---|
| nachitoultra | hijo | constructor |
| churros5235 | hijo | constructor |
| Vicp360 | | default |

## Grupos

* **default:** lo basico para cualquier jugador: warps, spawn, dinero, tienda, mascotas y proteger su terreno con GriefPrevention.
* **constructor** (para los hijos): todo lo de default, vip y vip+, mas casas, teletransporte entre amigos e ItemEdit (ver [Luck Perms](../plugins/luck_perms.md)).
  No incluye comandos de administracion que puedan borrar cosas (**/stop**, **/kill**, WorldEdit, borrar mundos, etc.).

## Pasos para agregar un jugador nuevo de forma segura

1. **Conocer a la persona.** Agregar solo a amigos que los niños conocen en persona, y conversarlo con sus padres.
2. **Pedir el nombre exacto de su cuenta de Minecraft Java.** Tiene que ser una cuenta oficial (comprada). Las mayusculas y minusculas importan.
3. **Comprobar que la cuenta existe** abriendo en el navegador:
   **https://api.mojang.com/users/profiles/minecraft/\[nombre]**
   Si aparece un **"id"**, la cuenta existe. Si no aparece nada, el nombre esta mal escrito o la cuenta no es oficial.
4. **Agregarlo a la lista blanca** desde la consola:
   * **'sudo mc-consola.sh "whitelist add \[nombre]"'**
5. **Confirmar que quedo en la lista:**
   * **'sudo mc-consola.sh "whitelist list"'**
6. **(Opcional) Darle un grupo.** Por defecto queda en **default**, que alcanza para jugar y proteger su terreno. Para darle mas permisos:
   * **'sudo mc-consola.sh "lp user \[nombre] parent set \[grupo]"'** (por ejemplo **vip**).
   * Conviene que **constructor** quede solo para los hijos.
7. **(Opcional) Darle bloques de terreno extra** (GriefPrevention), para que proteja lo que construya:
   * **'sudo mc-consola.sh "adjustbonusclaimblocks \[nombre] 10000"'**
8. **Pasarle la direccion del servidor solo a esa persona.** No publicarla en internet ni en grupos grandes.
9. Cuando entre por primera vez, **revisar que haya entrado bien**:
   * **'grep "UUID of player \[nombre]" /home/papermc/minecraft/logs/latest.log'**

## Quitar a un jugador

* **'sudo mc-consola.sh "whitelist remove \[nombre]" "kick \[nombre]"'**
>Lo saca de la lista blanca y lo desconecta si esta jugando. Sus construcciones y terrenos quedan en el servidor.

* **'sudo mc-consola.sh "ban \[nombre]"'**
>Prohibe la entrada aunque vuelva a estar en la lista blanca. Para quitar la prohibicion: **"pardon \[nombre]"**.

>**NOTA:** si un nombre de la lista blanca tiene un ID viejo (por ejemplo, de cuando el servidor estaba en modo offline),
>**"whitelist remove"** puede responder *"Player is not whitelisted"*. En ese caso hay que quitarlo a mano de
>**/home/papermc/minecraft/whitelist.json** (con el servidor encendido) y ejecutar **"whitelist reload"**.

>**NOTA:** los comandos **"whitelist on"** y **"whitelist off"** reescriben **server.properties** con los valores que el servidor tiene en memoria.
>Si se cambia **enforce-whitelist** a mano, hay que reiniciar el servidor para que lo lea, y conviene revisar el archivo despues de usar esos comandos.

## Por que asi

* El servidor esta conectado a internet y recibe conexiones de bots que buscan servidores de Minecraft. La lista blanca los rechaza a todos.
* Con la lista blanca y el modo online, solo entran las cuentas que agregues, y nadie puede hacerse pasar por otro jugador.
* Nadie es OP, para que ningun comando borre cosas por accidente. Si algo se rompe igual, se puede volver a un respaldo ([Respaldos](respaldos.md)).
