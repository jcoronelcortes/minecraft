# TAB

Es un complemento para servidores que permite personalizar la lista de jugadores que se ve al presionar la tecla TAB, junto con otras características como la información de la vida debajo del nombre del jugador y la creación de un marcador o scoreboard. Este plugin ofrece una configuración detallada para mostrar rangos, estadísticas, animaciones y otra información útil, mejorando la experiencia tanto para el administrador del servidor como para los jugadores.

https://www.spigotmc.org/resources/tab-1-5-1-21-8.57806/

# Archivos de configuracion

## config.yml

Cada vez que se modifica el archivo de configuracion se debe ejecutar el comando **/tab reload**.

* **scoreboard.scoreboards:** Lista de marcadores (scoreboards). Se muestra el primero cuya **display-condition** se cumpla.
  * **scoreboard_bienvenida:** Se muestra en el mundo **world** (**display-condition: '%world%=world'**). Da la bienvenida al servidor de Compadres e indica usar **/warps** para viajar a los mundos. Reemplazo en nov-2026 al marcador de "Registro/Logeo" de nLogin.
  * **scoreboard:** Marcador principal para el resto de los mundos: rango (**%luckperms_prefix%**), dinero (**%vault_eco_balance_formatted%**), kills, muertes, tiempo de juego y jugadores en linea.
* **title:** Titulo del marcador. Usa la animacion **%animation:compadres%** (definida en **animations.yml**).
* **lines:** Lineas del marcador. Se pueden usar colores hexadecimales (**#8addff**) y codigos **&**.