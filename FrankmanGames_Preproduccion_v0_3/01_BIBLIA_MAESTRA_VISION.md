# FrankmanGames — Biblia maestra de visión y diseño (GDD en descubrimiento)

**Versión:** 0.2 — 2026-10-25  
**Responsable de la visión:** creador del proyecto. **Redacción y estructura:** asistente de IA, para revisión.  
**Estado general:** DOCUMENTO VIVO, NO APROBADO. Ningún detalle propuesto constituye una regla jugable salvo aceptación explícita del autor.

## 0. Cómo interpretar esta biblia

Separar permanentemente:

- `EXPRESADO`: preferencia, objetivo o rechazo manifestado directamente por el creador; no implica que la solución técnica ya esté definida.
- `SÍNTESIS`: interpretación del equipo de investigación, que el autor puede corregir.
- `OPCIÓN`: alternativa de diseño abierta, sin adopción.
- `INVESTIGACIÓN`: algo que debe verificarse con experiencia de juego, datos, documentación o análisis técnico.
- `APROBADO`: diseño elegido expresamente por el autor y registrado en `08_REGISTRO_DECISIONES.md`.
- `DESCARTADO`: diseño rechazado expresamente por el autor.

**No confundir «el autor quiere experimentar con una combinación libre de hechizos» con «el sistema tendrá exactamente diez ranuras»**, ni «quiere MMO o al menos cooperativo» con «MMO aprobado».

## 1. La experiencia: por qué existe el juego

### 1.1. Lo valioso de FATE según el creador [EXPRESADO]

- La atmósfera de misterio y el papel de la música.
- No saber si un monstruo enorme y amenazante puede derrotarte.
- La sorpresa del botín raro obtenido matando monstruos **y pescando**.
- La experiencia memorable de pescar en un piso profundo —el autor recuerda el piso 30—, escuchar la música y esperar la picada.
- La atracción de seguir descendiendo para descubrir qué vendría después.
- El disfrute del repertorio de hechizos, que no se limita necesariamente a una clase.
- La dirección visual antigua le gustaba; desea una realización más pulida y animaciones menos robóticas.
- Lo que NO quiere heredar: combate percibido como «pegar y pegar» y mazmorras indefinidas, repetitivas y sin final narrativo.

**Implicación [SÍNTESIS]:** la emoción principal no es simplemente acumular niveles, sino el contraste entre seguridad e incertidumbre: preparación, riesgo, descubrimiento, pausa atmosférica y recompensa. Pescar es un ejemplo excepcional de cómo una actividad aparentemente secundaria construye memoria emocional. **No confirma que la pesca esté aprobada como mecánica obligatoria.**

### 1.2. Lo valioso de DOFUS según el creador [EXPRESADO]

- Disfruta su mundo, arte, música y amplitud de sistemas.
- Quiere dejar el combate por turnos y examinar cómo conservar la profundidad de los hechizos en tiempo real.
- Quiere conservar la posibilidad de tener un repertorio rico de hechizos y experimentar con sus combinaciones.
- Temporis IV es una referencia central: equipar un conjunto limitado de hechizos obtenidos de diversas clases le resultó especialmente divertido.
- Valora que las peleas ocurran en espacios/instancias separados y no estorben a otros jugadores del mundo.
- Sabe que PA/PM y el coste de usar armas no se trasladan directamente a un combate con movimiento continuo; deben reinterpretarse.
- Le interesan nuevas posibilidades de movimiento, evasión, dash, velocidad y gestión de recursos, pero no ha aprobado una combinación de ellas.

**Información histórica, no mandato de diseño [INVESTIGACIÓN EXTERNA]:** reportes contemporáneos de Temporis IV (2020) describen una baraja de 10 hechizos equipados entre una colección más amplia obtenible mediante botín, logros y fabricación, con aptitudes activas/pasivas de clase. El número de ranuras y la estructura de clases de Temporis IV NO están adoptados en FrankmanGames. Fuentes: https://dofus.jeuxonline.info/actualite/57690/temporis-saison-iv-resume-informations-avant-ouverture-serveurs y https://dofus.jeuxonline.info/actualite/57608/temporis-iv-precise-ankamalive.

### 1.3. Dirección general de la obra [EXPRESADO]

- Se quiere un **juego propio** que extraiga ideas de tres referentes; NO una copia de FATE o DOFUS.
- Se desea una **historia y un final del juego**, en vez de contenido infinito sin resolución.
- El horizonte es **MMO o, como mínimo, RPG cooperativo**. La elección exacta del alcance está pendiente.
- Debe evaluarse cómo producir modelos de personajes, monstruos, casas, cuevas, montañas, equipamiento y demás contenido de forma viable para un equipo muy pequeño con IA.
- Antes de programar una sola línea del videojuego, el autor quiere definir una documentación sustancial y alinear a los agentes de investigación.
- La selección de motor (JS/TS, Babylon.js, Godot, Unity, propio u otro) permanece abierta.

## 2. Declaración de producto tentativa [SÍNTESIS, no lema aprobado]

«Una aventura RPG de acción y fantasía con misterio, exploración significativa, combate basado en habilidades combinables y un mundo con identidad artística y sonora, donde el viaje tiene una historia y una conclusión, y puede disfrutarse con otras personas».

El creador debe corregir tono, género, encuadre y prioridad. **No equivale a una historia, pitch comercial ni promesa técnica.**

## 3. Pilares de experiencia propuestos [SÍNTESIS]

1. **Misterio y asombro:** algo que merece ser descubierto, con información incompleta pero justa.
2. **Construcción libre de personaje:** probar conjuntos de habilidades para encontrar un estilo personal.
3. **Acción con decisiones:** no depender solo de repetir ataque básico; usar posicionamiento, ventanas de oportunidad y elecciones tácticas.
4. **Mundo expresivo:** arte, música, criaturas y actividades que den personalidad a la aventura.
5. **Viaje con propósito y conclusión:** progreso que no se reduce a descender pisos sin fin.
6. **Experiencia compartida sin interferencia:** posibilidad de encuentros aislados del flujo público, respetando un alcance multijugador aún por decidir.

**Todos requieren ratificación o corrección por el autor.**

## 4. Antipilares iniciales [SÍNTESIS de rechazos expresados]

- Rellenar horas con mazmorras ilimitadas y repetitivas por sistema.
- Combate dominado por golpes básicos monótonos.
- Animaciones duras o sin reacción a los impactos, si se pueden mejorar.
- Copiar FATE o DOFUS en nombres, activos, lore, fórmulas y código.
- Escoger un lenguaje o motor antes de saber qué experiencia se está construyendo.
- Inflar el alcance MMO antes de responder cómo jugarían juntos los usuarios y cómo se sostendría la historia.

Estos puntos NO descartan exploración repetible con variedad, ataques básicos situacionales, ni contenidos opcionales de final de juego; solo cuestionan sus versiones poco significativas.

## 5. Bucle de experiencia: investigar antes de escribir una versión oficial

**OBSERVACIÓN [SÍNTESIS]:** el relato de FATE sugiere un ciclo emocional, no una implementación concreta:

1. Curiosidad / señal de algo desconocido.
2. Preparación o elección de equipo/hechizos.
3. Entrada a zona con riesgo.
4. Descubrimiento, encuentro o desvío opcional.
5. Decisión entre seguir explorando, combatir, cooperar, retirarse o detenerse.
6. Hallazgo: botín, nueva información, criatura, historia o recurso.
7. Volver a un lugar relativamente seguro y repensar la próxima aventura.

Esto puede ser evaluado como estructura narrativa **sin convertirlo todavía en un mapa de zonas obligatorio**. Preguntas a resolver: ¿cuánto debe durar una expedición?, ¿cómo se arriesga el botín?, ¿qué sucede si mueres?, ¿qué se conserva entre sesiones?, ¿cómo termina una misión? No inventar números.

## 6. Combate — intención y preguntas irrenunciables

**[EXPRESADO]** Se busca acción en tiempo real, evitando la rigidez de «pegar y pegar» y sin turnos. Importa preservar la riqueza táctica y combinatoria de los hechizos de DOFUS/Temporis IV.

**[NO DECIDIDO]** cámara isométrica o tercera persona; apuntado libre/asistido; cantidad de hechizos equipados; clases o arquetipos; barra de recursos; maná, energía, cargas, enfriamientos, limitación de distancia, coste de arma; dash, bloqueo, parry; combate PVP; reglas de control de masas; precisión del hitbox.

**Preguntas de diseño para estudiar, no contestar automáticamente:**

- ¿Qué hace divertido lanzar un hechizo si ya no existen casillas, PA y turnos?
- ¿Qué decide el jugador cada 2–5 segundos, aparte de «presionar la habilidad disponible»?
- ¿Cómo evitar que una secuencia óptima automática eclipse la creatividad en builds?
- ¿Cómo conservar identidad de hechizos de apoyo, control, posición, invocación y protección, no solo daño directo?
- ¿Qué coste tiene usar armas en un juego donde no se «pasa turno»?
- ¿Cómo se interpreta alcance, visión, área de efecto, línea de visión y distancia sin cuadrícula?
- ¿Cómo se ve una amenaza enorme sin convertirla en una esponja de vida?
- ¿Cómo leer efectos e intenciones del enemigo cuando juegan 2, 3 o más personas?

La tabla de alternativas y su investigación se encuentran en `04_COMBATE_Y_HECHIZOS.md`.

## 7. Exploración, mazmorras y estructura del mundo

**[EXPRESADO]** aventura con misterio y final, no mazmorras infinitas repetitivas. **[NO DECIDIDO]** mundo abierto continuo, regiones conectadas, mapas segmentados, mazmorras prediseñadas, módulos procedurales, expediciones repetibles, asentamientos, historia lineal o ramificada.

Temas a definir sin anticipar soluciones:
- ¿Qué diferencia narrativa y mecánica tiene una cueva frente a otra?
- ¿Cómo se anticipa una criatura especialmente peligrosa (sonido, sombras, huellas, rumores, señales)?
- ¿Cómo se mezclan descanso, pesca/actividades, tensión, descubrimiento y recompensa?
- ¿Qué evita que volver a zonas antiguas sea puro trámite?
- ¿Cómo se narra el final en una experiencia cooperativa o persistente?
- ¿Se pueden compartir historias personales sin duplicar toda la cantidad de arte requerida?

## 8. Botín, equipamiento y progreso

**[EXPRESADO]** botín raro y sorpresas fueron memorables; equipables y hechizos importan muchísimo. **[NO DECIDIDO]** rarezas, afijos, crafting, restricciones de clase, comercio, drop de hechizos, pesca, encantamiento, escalado numérico, temporadas, transfiguración.

Investigar relaciones entre descubrimiento y recompensa. No reducir «loot interesante» a colores o porcentajes. Las fichas deberán explicar qué decisiones producen los objetos y cómo modifican tu estilo de juego; evitar una economía inflacionaria trivial si existe comercio compartido. El antiguo truco del pergamino editado de FATE es una pista de sistemas guiados por datos, **no un exploit a replicar**.

## 9. Mundo compartido, instancia y tipo de juego

**[EXPRESADO]** MMO o al menos cooperativo; combates separados que no estorben a espectadores/jugadores ajenos. **[NO DECIDIDO]** máximo de jugadores por grupo, quién inicia un encuentro, entrada/salida de aliados, persistencia social, chat/comercio, servidor autoritativo, sincronización de zonas, MMO real, soporte offline.

No confundir «encuentro instanciado» con «combate por turnos»: puede existir una arena temporal en tiempo real con mundo exterior separado. Debemos describir el viaje de entrada/salida del encuentro, la coordinación y el coste técnico antes de decidir infraestructura.

## 10. Historia, dirección artística y música

**[EXPRESADO]** historia y conclusión; música y estética constituyen parte esencial del valor emocional del juego; animaciones más fluidas y creíbles.

**[NO DECIDIDO]** universo, personajes, época, biomas, facciones, conflicto central, estilo visual concreto, voces, compositor, sistema musical adaptativo, tecnologías gráficas y herramienta de arte.

**Principio de diseño [SÍNTESIS]:** la música debe tener una función dramática: distinguir tensión, descanso y hallazgo. No colocar música de fondo arbitraria sin articular una intención. Esa función debe comprobarse con un documento de escenas y referencias sonoras originales.

## 11. Alcance y viabilidad de un equipo reducido

Crear un MMO no solo exige una plataforma capaz de mostrar varios jugadores: exige cuentas, persistencia, servidores, instancias, herramientas operativas, actualizaciones, protección frente a trampas, moderación y presupuesto recurrente. Un RPG cooperativo también necesita red, sincronización y diseño de la experiencia compartida; su alcance puede ser significativamente menor. **Aquí no se ha aprobado un plan «co-op primero, MMO después»: es solo una variante que deberá evaluarse.**

No financiar la ilusión de «IA crea todos los assets» sin pruebas de pipeline: el material final requiere consistencia, topología, rigging, retargeting, optimización, licencias, estilo, LOD y revisiones. La IA puede asistir investigación, conceptos, iteración y tareas repetitivas, pero no elimina el trabajo de dirección y control de calidad.

## 12. Preguntas sobre el público y la propuesta de valor

- ¿Para quién sería el juego? ¿Fans de acción RPG, DOFUS, cooperativos de exploración, jugadores casuales o exigentes?
- ¿Qué tensión queremos priorizar: dificultad, misterio, estrategia, descubrimiento o socialización?
- ¿Cuáles serían las primeras 20 minutos ideales?
- ¿Qué nos haría decir «este juego tiene personalidad propia» sin mencionar DOFUS o FATE?
- ¿Qué sería emocionante repetir y qué debería vivirse una sola vez?
- ¿Qué aspectos podrían reducirse sin perder el alma de la experiencia?

## 13. Criterio de aprobación de un sistema

Una sección no se considera definida hasta tener:

1. Problema o emoción que resuelve (formulada por el autor o validada con él).
2. Opciones razonables y comparaciones con evidencias de referentes.
3. Regla jugable propuesta, incluyendo casos límite.
4. Relación con historia, mundo, economía y otros sistemas.
5. Impacto estimado en arte, animación, UI, red y mantenimiento.
6. Evaluación de costes/riesgos y posibles pruebas.
7. **Aprobación expresa del creador registrada en `08_REGISTRO_DECISIONES.md`.**

La aprobación de una mecánica no implica automáticamente aprobar una implementación, motor, biblioteca ni fórmula numérica.

## 14. La primera ronda de decisiones todavía no se decide

Prioridad propuesta para conversar con el creador: (1) sensación del combate de acción; (2) grado de libertad real para mezclar hechizos; (3) cómo comienza/termina una pelea instanciada; (4) estructura de aventura narrativa finita; (5) cooperativo versus MMO como objetivo de lanzamiento. No pedirle al autor 60 parámetros de una vez. Presentar 1–2 preguntas de alto impacto con alternativas ilustrativas y consecuencias.

## 15. Referencias y trazabilidad

- **Fuente principal:** testimonio del creador en la conversación del 25 de octubre de 2026. Este documento lo distingue de conclusiones técnicas de agentes y fuentes públicas.
- **Investigaciones reportadas:** `RPG_Contexto_Agentes_v0_1`, resumen DOFUS en conversación, `Markdown pegado(2).md` del agente FATE. No se inspeccionaron binarios desde este equipo.
- **Temporis IV (historia y hechizos):** https://dofus.jeuxonline.info/actualite/57690/temporis-saison-iv-resume-informations-avant-ouverture-serveurs y https://dofus.jeuxonline.info/actualite/57608/temporis-iv-precise-ankamalive

**Esta versión puede ser corregida, ampliada o contradicha por el autor sin ninguna pérdida de validez de la investigación.**
