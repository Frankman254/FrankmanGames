# Estado de los tres análisis — evidencia frente a interpretación
**Corte:** 2026-10-25. La palabra «reportado» significa que el dato aparece en los mensajes del agente. La evidencia de FATE ya fue auditada localmente; las salidas DOFUS siguen pendientes de auditoría en este paquete.

## FATE: Undiscovered Realms
**Auditado directamente en la instalación y salidas FATE:**
- 7,094 archivos, ~315 MB.
- Ejecutable principal analizado: `Fate-WT.exe`; PE x86 de 32 bits, versión `1.0.0.345`.
- Gráficos Direct3D 8; audio FMOD 3.74; vídeo AVI/Video for Windows.
- Datos editables `.dat`: 717 objetos, 138 monstruos, 53 hechizos, nueve plantillas de generación procedural (cuentas dependientes de la copia inspeccionada).
- Formatos identificados: `.MDL`, `.SMA`, `.SMS`, `.AMS`, `.SCN`, `.COL`.
- Guardados `.FFD` aparentemente contienen gran parte del estado activo (personaje, mascota, inventario, misión, monstruos, cofres, botín y entidades).
- Ghidra: base persistente guardada; el análisis inicial REA registró 2,060 cadenas y 96,270 procedimientos locales/externos. Este número no equivale a funciones de jugabilidad distintas y validadas.
- El barrido focalizado terminó y quedó en `FATE-ReverseEngineering/evidence/ghidra/FATE-DATA-SAVE-XREFS.md`.
- `FUN_00457aa0` referencia y construye los cargadores de misiones, plantillas, monstruos, objetos y hechizos; el pseudocódigo y sus offsets fueron auditados.
- `FUN_00562a90` separa `Cache` de `Persistent`; cuatro funciones consumen `/SAVE/` y una de ellas enumera slots con APIs Win32.
- Se mantienen seis fichas de mecánica y una ficha arquitectónica en `fichas/FATE/`; cada una separa hechos, inferencias e incógnitas.
- Se recuperó el circuito ejecutable de combate: `FUN_005480b0` valida/ejecuta y `FUN_00546e60` resuelve impacto, crítico, daño, mitigación, bloqueo y aplicación.
- La tirada de fallo usa la razón `defensa/(defensa+ataque)` limitada a 5–95%; crítico y bloqueo usan curvas saturantes con techo 50%.
- El crítico duplica el daño base; el bloqueo pone a cero el daño mitigado antes de aplicarlo a vida.

**Pendientes más relevantes para el diseño:**
1. Tipado final de offsets, separación de armadura/resistencias y velocidad/hit frames; el circuito, orden y curvas principales de impacto/daño/crítico/bloqueo ya están documentados.
2. Máquina de estados y navegación de enemigos; los parámetros de percepción, persecución, valentía, roles y hechizos ya están documentados.
3. Generador topológico y uso real de `DUNGEONSEED`; el contrato de nueve plantillas ya está documentado.
4. Selección de loot, afijos y fórmula de compra/venta; el esquema de 717 objetos y 1,327 efectos ya está documentado.
5. Mapa binario del `.FFD` mediante guardados diferenciales; las rutas, consumidores y contenido general ya están documentados.
6. Observación reproducible del jugador para contrastar tiempos, feedback, dificultad y casos límite.

**Ejemplo aportado por el usuario, NO verificado por el dump:** modificaba el precio de venta de un pergamino en un archivo de datos para obtener grandes cantidades de oro. Es una pista útil sobre diseño data-driven y economía offline, no una especificación ni una mecánica aprobada para el juego nuevo.

## DOFUS Retro
**Reportado por el agente DOFUS:**
- FFDec produjo una exportación inicial de 778 scripts de `loader.swf` y 2,578 de `core.swf` (no es obligatorio que estas cifras y el siguiente recuento representen el mismo conjunto).
- Exportación posterior desofuscada: 4,629 scripts en `out/retro/loader_deobf/` según el resumen.
- Tabla `dispatch_table.md` de **311 prefijos** de mensajes entrantes; generador `retro_dispatch_table.py`.
- Se identificaron clases nominales/familias de mensajes como Chat, Party, Guild, Items; las asociaciones con algunos nombres de clases permanecen **hipótesis**, señaladas con `?` en el README según el agente.
- El proceso Java falló varias veces bajo carga y terminó cuando se limitó a dos núcleos (~11 min 45 s). Esto **no prueba** una causa específica de inestabilidad del equipo.

**Pendientes más relevantes para el diseño:**
1. Separar handlers de red de reglas efectivas de interfaz, combate, estadísticas y progresión.
2. Identificar en scripts concretos turnos, acciones, movimientos, estados, buffs, efectos y restricciones visibles.
3. Registrar interacciones entre clases, hechizos, equipamiento y decisiones tácticas sin deducirlas solo de nombres de paquetes.
4. Acompañar análisis estático con observaciones reproducibles de juego legítimo.

## DOFUS 3
**Reportado por el agente DOFUS:**
- Cpp2IL obtuvo 26,917 archivos C# que representan firmas/estructura de código, no necesariamente cuerpos de métodos de alto nivel completos.
- Reconstrucción reportada de 2,212 mensajes y 551 enums en `connection.proto` y `game.proto`, mediante `d3_rebuild_proto.py`.
- Existe ofuscación de nombres; se reportaron campos/tipos reconstruidos, pero la exactitud debe verificarse contra muestras.
- Se describieron envelopes Request/Response/Event y mensajes `google.protobuf.Any`; esto es arquitectura de mensajería **no diseño de juego por sí solo**.
- Se mencionan login/token, heartbeat y LZ4: **fuera del alcance creativo prioritario**, y no se deben usar para interactuar con servicios remotos.

**Pendientes más relevantes para el diseño:**
1. Determinar qué lógica vive en el cliente frente al servidor antes de atribuir comportamiento a los binarios locales.
2. Relacionar pantallas, flujo de usuario, restricciones de combate y representación de habilidades con observaciones de juego.
3. Documentar mejoras o diferencias respecto a Retro **solo cuando haya evidencia de ambas versiones**.
4. Declarar como «no determinado» todo lo que no pueda establecerse sin lógica del servidor.

## Calidad de las afirmaciones
Clasificar cada afirmación en:
- `OBSERVADO`: dato directamente extraído del archivo/traza/captura citada.
- `REPRODUCIDO`: verificado mediante prueba repetible, con versión y procedimiento.
- `REPORTADO`: mensaje de agente que falta auditar.
- `INFERIDO`: interpretación razonada, marcada como tal.
- `DESCONOCIDO`: no hay base suficiente.

Estas categorías **no** expresan qué quiere implementar el autor.

## Control mínimo de evidencias
Para cada sistema registrar: juego/versión, rutas relativas, hash (si existe), símbolo o método, fragmento o intervalo, observación en gameplay, fuente, incertidumbre, fecha y agente responsable.
