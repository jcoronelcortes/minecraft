# Multiverse Inventories

Complemento de Multiverse-Core que permite que grupos de mundos tengan inventarios separados (items, vida, experiencia, cama, etc.). Se usa para que lo que se gana en el mapa de Hora de Aventuras no se mezcle con la supervivencia.

https://modrinth.com/plugin/multiverse-inventories

**Version instalada:** 5.3.6

## Grupos actuales

* **default:** world, world_nether, world_the_end, compadres, compadres_nether, compadres_end, CropCircle, LuckySkyWars, naciones, ParkourHelix y creativo.
* **ooo:** ooo, ooo_nether y ooo_the_end.

## Comandos

* **/mvinv info \[grupo]:** muestra los mundos y lo que comparte el grupo.
* **/mvinv create-group \[grupo]:** crea un grupo.
* **/mvinv add-worlds \[grupo] \[mundo1,mundo2]:** agrega mundos al grupo.
* **/mvinv add-shares \[grupo] all:** el grupo comparte todo (incluida la cama, **bed_spawn**).
* **/mvinv check-group-conflicts:** revisa que un mundo no este en dos grupos.

>**NOTA:** Cada mundo nuevo se debe agregar a un grupo; si no, tendra un inventario propio.
