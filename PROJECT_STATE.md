# PROJECT_STATE
Fase activa: 2-5 (versión "solo servidor", compatible con clientes vanilla).

| Componente | Estado |
|---|---|
| rpgcore (XpCurve, PlayerProgress, Stamina) | Compilado y probado (autocomprobaciones en tools/SelfCheck.java) |
| Todo el código de com.saorpg (Fabric) | Escrito, SIN compilar, SIN probar en juego |
| Nivel/XP, persistencia v2 (migra v1), niveles y escalado de mobs (jefes sin escalar), XP anti-farmeo | Escrito |
| Maestrías (10 ramas), bonus/penalización por atributos, XP por kill | Escrito |
| Energía (sprint, regeneración, agotamiento), 4 habilidades (Shift + clic derecho) | Escrito |
| HUD en action bar (apagado/compacto/completo) + info del enemigo apuntado | Escrito |
| Menú interactivo con botones clicables (/rpg), comandos admin, config/saorpg.json | Escrito |
| Pantalla de bienvenida dinámica (título + panel; distinta la 1ª vez y al volver), `/rpg intro`, nombre configurable | Escrito |
| Rarezas, mazmorras, misiones, Paper, resource pack | No implementado |

## Limitaciones de diseño (por ser solo servidor)
- No se pueden ocultar los corazones vanilla ni dibujar barras estilo anime: eso exige mod de cliente (HudElementRegistry). Pendiente.
- Sin teclas propias: habilidades con Shift + clic derecho.
- Arcos/ballestas/tridente ganan maestría pero el bonus de daño por atributo no afecta flechas.
- Solo mobs `Enemy` ganan nivel; antiabuso básico (x0,25 XP a mobs 10+ niveles inferiores). Sin detección de granjas.

## Riesgos de compilación (APIs 1.21.11 no verificadas)
Commands.hasPermission(LEVEL_GAMEMASTERS), paquetes ClientboundSetTitle*/SetSubtitle*/SetTitlesAnimation, ServerPlayer.connection/playNotifySound, ClickEvent.RunCommand, Identifier.fromNamespaceAndPath,
hurtServer, addOrUpdateTransientModifier, ProjectileUtil.getEntityHitResult, UseItemCallback (retorno InteractionResult),
loom plugin id. Protocolo: pegar el primer error de Actions y corregir solo ese símbolo.
