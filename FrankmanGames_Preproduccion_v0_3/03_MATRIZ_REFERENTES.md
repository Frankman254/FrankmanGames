# FrankmanGames — Matriz de experiencias y mecánicas de los referentes

**Leyenda:** E = expresado por el autor; R = reportado por un agente; X = fuente histórica externa; ? = falta verificar; — = no asignado. Ninguna celda aprueba una regla del juego nuevo.

## A. Mapa de experiencias prioritarias

| Tema | FATE | DOFUS Retro / DOFUS 3 | Temporis IV | Qué queremos comprender del futuro juego | Estado |
|---|---|---|---|---|---|
| Misterio | Descenso incierto, monstruos intimidantes (E) | Exploración, mundo y narrativa por investigar (?) | Misterio en obtención de hechizos (X) | Cómo provocar curiosidad sin ocultar injustamente datos esenciales | ESTUDIAR |
| Música | Recuerdo emocional central, incluso pescando (E) | Arte y música admirados (E) | ¿Qué aporta su presentación? (?) | Ritmo ambiental y función de la música | ESTUDIAR |
| Botín raro | En combate y pesca (E) | Economía/equipamiento muy valorados (E) | Hechizos y equipamiento obtenibles (X) | Recompensas que cambien decisiones | ESTUDIAR |
| Hechizos | Diversos, no necesariamente ligados a una clase (E) | Profundidad y variedad (E) | Selección de 10 entre muchos de diversas clases (E/X) | Libertad combinatoria con identidad propia | ALTA PRIORIDAD |
| Ataques con arma | Repetitivos según el autor (E) | Consumen PA y tiempo de turno (E) | Igual problema por turnos (?) | Qué función cumplen en acción | ALTA PRIORIDAD |
| Turnos y movimiento | Tiempo real (E) | Turnos, PA/PM y posicionamiento (E) | Variación de barajas dentro de turnos (X) | Táctica sin rejilla/turno | ALTA PRIORIDAD |
| Encuentro aislado | FATE tradicionalmente offline; validar versión (?) | El autor destaca peleas que no interrumpen a otros jugadores (E) | Hereda contexto por turnos (?) | Instancia en tiempo real con cooperación | ALTA PRIORIDAD |
| Bestiario | Enemigos grandes y temor a no poder vencerlos (E) | Amplia identidad visual (E) | Hechizos ligados a drops específicos (X) | Atributos de enemigos que se recuerden | ESTUDIAR |
| Pesca / pausa | Muy memorable al bajar pisos (E) | Oficios/sistemas por investigar (?) | Oficio especial de hechizos (X) | Alternar tensión y tranquilidad sin perder propósito | ESTUDIAR |
| Progresión | Progresar a pisos profundos se volvió repetitivo (E) | Equipables/profundidad (E) | Builds adaptadas a hechizos obtenidos (X) | Progreso tangible hacia historia final | ESTUDIAR |
| Mundo / historia | El autor quiere evitar infinito sin final (E) | Mundo y estética encantan (E) | Temporada temporal; no modelo narrativo impuesto | Historia con final y potencial social | ALTA PRIORIDAD |
| Animación / arte | Movimientos robotizados; quiere pulirlos (E) | Arte gusta en ambas eras (E) | No referido | Lenguaje visual propio y movimiento expresivo | ALTA PRIORIDAD |
| Mercado/economía | Precio editable del pergamino (E, anécdota) | Mercado/comercio por estudiar (?) | Intercambio de hechizos (X) | Economía equilibrada con servidor si es compartida | ABIERTO |
| Persistencia | Guardados `.FFD` reportados (R) | Cliente-servidor reportado (R) | Servidor temporal (X) | Qué persiste para historia/coop/MMO | ABIERTO |

## B. Sistemas técnicos ya descubiertos (NO equivalen a mecánicas comprendidas)

**FATE** (reportado): `Fate-WT.exe` PE x86; Direct3D 8; FMOD; archivos `.dat` de monstruos, objetos y hechizos; datos de nueve plantillas; guardados `.FFD`; Ghidra persistente y ancla `FUN_00457aa0` relacionada con cargadores. Reproducir referencias concretas desde el README y evidencia local antes de afirmar detalles funcionales.

**DOFUS Retro** (reportado): scripts SWF exportados/desofuscados, ~311 prefijos de despachador, grupos de mensajes; desconocido qué lógica efectiva de combate persiste en cliente o servidor. Leer los handlers necesarios y correlacionarlos con la interfaz y partida, no asumir equivalencias con FATE.

**DOFUS 3** (reportado): firma/estructura C# extraída por Cpp2IL, mensajes protobuf reconstruidos; nombres ofuscados y la lógica del servidor no está necesariamente disponible. No llevar trabajo al login o protocolos oficiales: no aporta a la decisión de videojuego original.

## C. Investigación prioritaria por juego

### FATE: cuatro fichas para las sensaciones
1. `FATE-ATM-01`: eventos de amenaza, tamaño, audio y señales de monstruos excepcionales. Evidencia de juego más datos (no limitarse a motor).
2. `FATE-LOOT-01`: circuito entre botín de monstruos/pesca, rareza y progreso; fuentes de premio y momentos sorpresivos.
3. `FATE-CMB-01`: tipos de hechizo, tiempos, efectos, alcance, dependencia de clase y uso de ataques básicos.
4. `FATE-WLD-01`: cuándo y cómo se hace repetitiva la mazmorra, cuánto cambia por planta, qué es historia y qué es generación.

### DOFUS Retro: cuatro fichas
1. `RETRO-CMB-01`: secuencia de turno, gestión PA/PM, acciones, ataques con arma, área/alcance y estados; distinguir cliente/servidor.
2. `RETRO-SPL-01`: categorías de hechizos, control del terreno, posicionamiento, equipo e interacción de efectos; datos verificables.
3. `RETRO-INS-01`: entrada y salida de combates desde un mapa con más jugadores; participantes, espectadores y persistencia.
4. `RETRO-ART-01`: función de audio, UI, arte legible, anticipación de habilidades y personalidad de mundo.

### DOFUS 3: cuatro fichas
1. `D3-CMB-01`: comparativa de presentación del combate y telegráficos con Retro, no solo efectos visuales.
2. `D3-SPL-01`: taxonomía y representación de hechizos; separaciones entre definición, ejecución y feedback.
3. `D3-INS-01`: flujo visual de instancias y encuentros; qué puede inferirse sin servidor.
4. `D3-ART-01`: mejoras de animación y presentación que cambian legibilidad; observación de juego legítimo.

### Temporis IV: revisión documental especial
1. `TEMP4-DECK-01`: obtención, límite, selección, modificación entre combates y sinergias; referencias contemporáneas.
2. `TEMP4-PROG-01`: cómo el hallazgo de habilidades convirtió exploración/loot en personalización; evitar asumir que su equilibrio era adecuado para un RPG permanente.
3. `TEMP4-SOC-01`: comercio/intercambio de hechizos: beneficios y problemas que podrían surgir en un mundo persistente.

**Aviso importante:** Temporis IV es un modo histórico de DOFUS, no un cuarto código de cliente decompilado. Su investigación debe ser documental y de experiencia de juego; los binarios Retro y Dofus 3 no demuestran automáticamente sus reglas de 2020.

## D. Esquema para actualizar celdas

Cada afirmación nueva debe incluir: `ID mecánica | referente/versión | estado de evidencia | localizador verificable | qué hace el jugador | mecánica observada | qué sensación produce | límite de confianza | pregunta al autor`. Conservar desacuerdos o diferencias entre versiones.

## E. Fuentes históricas complementarias

- Temporis IV: https://dofus.jeuxonline.info/actualite/57690/temporis-saison-iv-resume-informations-avant-ouverture-serveurs
- Temporis IV (detalles de hechizos): https://dofus.jeuxonline.info/article/14890/temporis-iv-liste-sorts-obtention
- Temporis IV (clases activas/pasivas): https://dofus.jeuxonline.info/article/14891/temporis-iv-effets-passifs-actifs-classes

Citar fechas y versión del referente al utilizar estos recursos. No presentar referencias comunitarias como código fuente primario.
