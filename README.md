# SAO RPG (Fabric 1.21.11) — v0.1.0

Solo servidor: funciona con clientes vanilla. Interacción: comando `/rpg` (menú clicable), HUD en action bar, habilidades con Shift + clic derecho con el arma.

## Cómo obtener el JAR sin pagar nada
1. Crea un repositorio en GitHub y sube esta carpeta (en la web: "Add file > Upload files").
2. Pestaña **Actions** > workflow **build** (arranca solo al subir) > al terminar, descarga el artifact **saorpg-jar**.
3. Si el build falla, copia el primer error y pégamelo en el chat: lo corrijo.
4. Instalar: Minecraft 1.21.11 + Fabric Loader >= 0.18.1 + Fabric API, y el JAR en `mods/`.

## Qué hace hoy
- Bienvenida al entrar: título en pantalla y panel que explica el mundo (completo la primera vez, resumen personalizado después). `/rpg intro` la repite; `worldName` y `welcomeEnabled` en la config.
- Nivel/XP persistentes; mobs hostiles con nivel (escalan vida/daño, jefes no); XP por kill.
- Maestrías por arma y armadura (espada, hacha, lanza, arco, ballesta, tridente, maza, armadura ligera/media/pesada) con penalización suave al inicio.
- Energía: correr consume, se regenera; agota habilidades.
- Habilidades (Shift + clic derecho): Corte veloz (espada), Estocada (lanza, m.5), Golpe demoledor (hacha, m.10), Impacto sísmico (maza, m.15).
- Pantalla en action bar + nombre/nivel/vida del enemigo al que apuntas.
- `/rpg` menú con botones clicables; `/rpg hud off|compact|full`; `/rpg mastery`; `/rpg skills`.
- Admin: `/rpg admin addxp|setlevel|setmastery|reload`. Config en `config/saorpg.json`.

## Estado real
Ver PROJECT_STATE.md.
