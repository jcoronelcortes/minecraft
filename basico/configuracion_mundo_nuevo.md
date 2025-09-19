# Pasos para instalar y configurar un mundo nuevo

* Dejar la carpeta del nuevo mundo en la carpeta principal del servidor.
* Importar el mundo en Multiverse ejecutando **mv import \[nombre_mundo]**
* Fijar el spawn del mundo ejecutando **mv setspawn** y **setwroldspawn**
* Editar el archivo de configuracion de mundos en Multiverse (**worlds.yml**)
* - pvp: 'false'
* - allowWeather: 'false'
* - difficulty: peaceful
* - hunger: 'false'
* Ejecutar **mv reload**
* Crear el warp inicial ejecutando **setwarp \[nombre_warp]**
* Editar el archivo zMenu (**inventories/warps.yml**) para agregar el warp creado.
* Una vez editado el archivo, se debe ejecutar **zmenu reload**