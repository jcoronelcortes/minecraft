# Hora de Aventuras en el servidor (07-nov-2026)

## Mascotas
En el juego: abrir el menú de mascotas (`/mascotas`) → **Apariencia** → botón **Hora de Aventuras** (cabeza de BMO).
Hay 10 personajes: Finn, Jake, BMO, Marceline, Dulce Princesa, Fionna, Cake, Rey Helado, Princesa Grumosa y Princesa Flama.
Al hacer clic, la mascota toma la apariencia de ese personaje.

- Menú: `plugins/PetBlocks/gui/petblocks_skins_ooo_menu.yml`; botón agregado al final de `petblocks_skins_menu.yml`.
- Permiso: `petblocks.gui.petblocks_skins_ooo_menu` en el grupo vip+ (constructor lo hereda).
- Texturas: base de datos de cabezas de CraftMC; los IDs de textura están en `texturas.json`.
- Si se cambia el menú: `sudo mc-consola.sh "petblocksgui reload"`.
  `petblocks reload` falla al recargar los menús por un error interno de PetBlocks.

## Skins (ser Finn, Jake, etc.)
Cualquier jugador puede usar:
- `/skins`: menú con skins sugeridas.
- `/skin set <nombre de jugador>`: copia la skin de una cuenta.
- `/skin url <enlace a una imagen .png>`: usa una skin descargada de una página de skins.
- `/skin clear`: vuelve a la skin propia.

Hay que esperar 30 segundos entre cambios.

## Objetos temáticos
Con los jugadores **conectados**:
```bash
sudo bash ~/Escritorio/projecto-minecraft/hora-de-aventuras/dar-objetos-ooo.sh
```
Sin argumentos, entrega los objetos a nachitoultra y churros5235. También se puede indicar otro jugador.

Objetos que entrega:
- Espada de Finn
- Gorro de Finn
- Hacha-Bajo de Marceline
- Corona del Rey Helado
- Cabeza de BMO
- Peluche de Jake

Las armas y armaduras son irrompibles. Las cabezas se pueden poner como decoración.

Los niños también pueden crear sus propios objetos con ItemEdit, sosteniendo un objeto en la mano:
- `/ie rename &6Espada de Finn`: cambia el nombre.
- `/ie lore add &bEs hora de aventuras!`: agrega una línea de descripción.
