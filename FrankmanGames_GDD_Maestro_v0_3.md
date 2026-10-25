# FrankmanGames — Expediente maestro de preproducción v0.3

**Fecha:** 2026-10-25 · **Naturaleza:** investigación y visión, NO especificación jugable aprobada.

**Lectura prioritaria de la actualización:** capítulo 11 y registro 08.

---

<!-- Archivo: 00_INICIO_Y_MAPA.md -->

# FrankmanGames — Inicio y mapa del expediente de preproducción

**Versión:** 0.3 · **Fecha:** 25 de octubre de 2026 · **Estado:** BORRADOR DE TRABAJO, NO GDD APROBADO  
**Proyecto:** RPG original en investigación, nombre comercial por definir. *FrankmanGames* designa el espacio de trabajo, no necesariamente el título del videojuego.

## Propósito

Registrar fielmente la visión expresada por su creador, investigar mecánicas y experiencias de FATE: Undiscovered Realms, DOFUS Retro, DOFUS 3 y Temporis IV, y tomar decisiones **sin adelantarse a programar**. Ningún análisis ni recomendación de IA equivale a una decisión de diseño del autor.

> **Principio principal:** «Investigar no es adoptar. Proponer no es aprobar. Un documento de ingeniería inversa no es una especificación de nuestro juego».

## Orden de lectura para humanos y agentes

1. `01_BIBLIA_MAESTRA_VISION.md`: experiencia buscada, hechos confirmados, tensiones de diseño, mapa integral de sistemas y objetivos del juego.
2. `02_CONSTITUCION_AGENTES.md`: reglas del proceso y de manejo de evidencias. Son reglas de investigación, **no reglas jugables**.
3. `03_MATRIZ_REFERENTES.md`: tabla de investigación comparativa por mecánica y fuente; conserva huecos.
4. `04_COMBATE_Y_HECHIZOS.md`: preguntas y opciones para convertir un RPG táctico por turnos en acción, **sin escoger una solución aún**.
5. `05_MUNDO_HISTORIA_Y_MULTIJUGADOR.md`: experiencia de exploración, historia finita, instancias, cooperativo y MMO.
6. `06_PRODUCCION_ARTE_AUDIO.md`: cómo producir escenarios, personajes, objetos, animaciones, sonido y música de manera realista.
7. `07_PLAN_PREPRODUCCION_SIN_CODIGO.md`: fases, entregables, puertas de aprobación y lista de investigaciones priorizadas.
8. `08_REGISTRO_DECISIONES.md`: fuente de verdad de aprobaciones y preguntas pendientes.
9. `09_PROMPT_COORDINADOR.md`: orden de trabajo lista para entregar a los agentes en la carpeta FrankmanGames.
10. `10_PLANTILLAS_FICHAS.md`: modelos de registro para fichas de mecánicas, experiencia y evidencias.
11. `11_FILOSOFIA_COMBATE_PREPARACION_Y_EJECUCION.md`: **actualización prioritaria** de visión sobre combate, sin mecánicas aprobadas.
12. `12_PROMPT_ALINEACION_AGENTES_COMBATE.md`: actualización puntual para orientar los agentes con la visión nueva.

## Qué cambió en v0.3

El creador respondió que busca **profundidad de builds/hechizos combinada con habilidad manual y ejecución**. Añadimos V-018 y V-019 al registro, y un capítulo nuevo de filosofía del combate. Esto NO fija recursos, 10 ranuras, clases, habilidades defensivas, balances ni motor. Es la dirección que deben usar los agentes al investigar.

## Antecedentes desde v0.1

La conversación del autor aportó una visión mucho más precisa: misterio, música, miedo al enemigo desconocido y botín de FATE; expresión de hechizos y combinaciones de DOFUS/Temporis IV; combate sin turnos; encuentros separados del resto del mundo; historia con final; deseo de cooperación o MMO. También dejó explícito que **todavía no existe una especificación de juego aprobada**, y que no quiere quemar las propuestas de los agentes como reglas.

Este paquete complementa los cinco documentos de `RPG_Contexto_Agentes_v0_1` que ya están en FrankmanGames. No presupone que sus investigaciones locales hayan sido auditadas; los resultados técnicos compartidos siguen como REPORTADOS hasta consultar los archivos originales.

## Directorios del usuario, referenciales — no auditados desde aquí

- `C:\Users\frank\Desktop\2026\FrankmanGames` — espacio de trabajo.
- `C:\Users\frank\Desktop\2026\FATE-ReverseEngineering` — investigación FATE.
- `C:\Users\frank\Desktop\2026\REA-Toolchain` — herramientas de análisis.
- Rutas DOFUS Retro / DOFUS 3 y sus resultados: verificar desde los README locales de sus agentes.

## Lo que NO se autoriza con estos documentos

- Programar el RPG, seleccionar definitivamente motor o crear un repositorio de implementación.
- Declarar aprobados «10 hechizos», maná, enfriamientos, dash, clases, mapas, lore o servidor MMO.
- Copiar código, modelos, música, textos, interfaces, nombres propios o archivos de los juegos investigados al proyecto original.
- Conectarse a servidores de juegos externos mediante protocolos reconstruidos o manipular autenticación.
- Modificar instalaciones, partidas o datos originales sin consentimiento concreto.

## Entrega esperada de la siguiente ronda

Un dossier comparativo con **hechos comprobados, sensaciones de juego, opciones con trade-offs y preguntas decisivas**. No un árbol de código ni una arquitectura congelada.


---

<!-- Archivo: 01_BIBLIA_MAESTRA_VISION.md -->

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


---

<!-- Archivo: 02_CONSTITUCION_AGENTES.md -->

# FrankmanGames — Constitución de trabajo para agentes

**Tipo:** normas del **proceso** de investigación, diseño y documentación. **No son las reglas del videojuego.**  
**Vigencia:** propuesta para que el autor la adopte o modifique.

## A. Autoridad y cambios

1. **El creador es el director de diseño.** Los agentes no pueden convertir opiniones, benchmarks o tradiciones de género en requisitos definitivos.
2. Todo archivo que describa una mecánica empieza como `BORRADOR`. El único estado jugable definitivo es `APROBADO_POR_AUTOR`, con una referencia a su decisión explícita.
3. La IA puede proponer; debe señalar `PROPUESTA_DEL_AGENTE`. Si sintetiza la intención del creador, señalar `SÍNTESIS_POR_VALIDAR`.
4. Si documentos anteriores contradicen una preferencia reciente, elevar el conflicto: no borrar silenciosamente el documento viejo ni adjudicarse autoridad.
5. No modificar un archivo considerado aprobado sin una entrada en el historial de cambios y aprobación del autor.
6. Los documentos `RPG_Contexto_Agentes_v0_1` son antecedentes de investigación, no especificaciones vinculantes de FrankmanGames.

## B. Separación y calidad de fuentes

Definir dos campos **independientes** para cada enunciado:

- `ESTADO_EVIDENCIA`: `OBSERVADO / REPRODUCIDO / REPORTADO / INFERIDO / NO_VERIFICADO / FUENTE_EXTERNA`.
- `ESTADO_DISENO`: `NO_PLANTEADO / PROPUESTA / SÍNTESIS_POR_VALIDAR / APROBADO_POR_AUTOR / RECHAZADO_POR_AUTOR / POSTERGADO`.

Ejemplo válido: «Temporis IV usó diez hechizos equipados» = `FUENTE_EXTERNA`, y «Nuestro juego tendrá diez hechizos» = `NO_PLANTEADO`. No transferir automáticamente el 10.

Toda evidencia técnica concreta debe conservar: referente, edición/versión, tipo de artefacto, ruta relativa, archivo, símbolo/clase/función cuando aplique, identificador/hash o fecha, método de verificación, duda pendiente y responsable.

## C. Ingeniería inversa acotada a aprendizaje

- Leer y analizar artefactos locales de una copia legítima, **sin entrar a infraestructura oficial** con protocolos reconstruidos, tokens u otros medios.
- No importar directamente recursos, modelos, música, texto protegido, marcas, mapas o código de FATE/DOFUS a FrankmanGames.
- Los ejemplos técnicos en las fichas son descripciones y pseudocódigo originales, no material decompilado trasladado como implementación.
- Distinguir sistemas del cliente, reglas inferidas del servidor y lo observado por el jugador; si un cliente de DOFUS solo dibuja efectos, no adjudicarle fórmulas del servidor.
- No iniciar nuevas tareas pesadas sobre el equipo del autor ni alterar overclock, BIOS, seguridad o archivos de instalación de terceros sin una instrucción específica.
- No dar por probado que limitar FFDec a dos núcleos identificó la causa de fallos previos de JVM; queda como correlación observada.

## D. Investigación orientada a experiencia

Cada investigación debe contestar **dos cosas distintas**:

1. **Cómo funciona:** datos, secuencia, restricciones, operaciones, interfaz, impactos, evidencia.
2. **Por qué vale la pena estudiar:** qué siente/hace/decide el jugador, qué evita repetición y qué coste trae adaptarlo al juego nuevo.

Distinguir `MECÁNICA` (acción/regla), `SISTEMA` (conjunto), `EXPERIENCIA` (efecto que siente la persona) y `IMPLEMENTACIÓN` (código/herramienta). Un análisis de red no demuestra jugabilidad; un objeto `.dat` no demuestra cómo juega el usuario.

## E. Reuniones de agentes y formatos

Antes de un informe, revisar los documentos nuevos y el expediente v0.1. No repetir el análisis entero si ya existe salida reutilizable. Trabajar en `docs/research` y `docs/design-proposals` separados de `reverse-engineering` y de un futuro código propio.

Entregas mínimas:
- Fichas de investigación por experiencia o mecánica, con evidencia verificable.
- Matriz comparativa actualizada con `DESCONOCIDO` cuando corresponda.
- Mapa de dependencias (qué afecta combate, arte, economía, red, historia).
- Un máximo de cinco decisiones pendientes para el autor por entrega; ordenadas por impacto.
- Tres alternativas cuando haya tensión real, con consecuencias y riesgos. No forzar tres por cortesía si solo existen una o dos.
- Resumen ejecutivo de una página para el creador, antes del detalle exhaustivo.

## F. Antídotos contra el «teatro de progreso»

NO aceptar como conclusión:
- «Hay 26,917 archivos C#, por tanto reconstruimos el juego completo».
- «Hay 311 prefijos, por tanto conocemos las reglas del combate».
- «FATE tiene nueve plantillas, por tanto ya sabemos generar sus mazmorras».
- «Podemos usar IA, por tanto modelar 500 personajes es trivial».
- «El renderizado usa GPU, por tanto no habrá problemas de rendimiento».
- «Cooperativo y MMO son la misma arquitectura a diferente escala».
- «El agente recomienda X, por tanto X ya es una ley del diseño».

Reemplazar esas frases por afirmaciones trazables, incertidumbre explícita y próximos pasos verificables.

## G. Gobierno del contexto para IA

Usar tres niveles de contexto:
- **Nivel 0, siempre:** `00_INICIO_Y_MAPA.md`, este documento, `08_REGISTRO_DECISIONES.md`, resumen de la tarea.
- **Nivel 1, por trabajo:** capítulos de visión y ficha/matriz del sistema solicitado, no toda la colección de análisis.
- **Nivel 2, bajo demanda:** Ghidra/pseudocódigo/JSON/AS/C# concretos enlazados desde una ficha.

Un agente no debe ingerir miles de archivos descompilados al comenzar. Usar índices, búsquedas, evidencias y fragmentos enfocados para mantener el costo de contexto controlado.

## H. Aprobación de trabajos futuros

**Etapa actual:** PREPRODUCCIÓN DOCUMENTAL. Está permitido investigar, leer documentos, comparar, redactar propuestas y preparar preguntas. No está permitido iniciar código del nuevo RPG en nombre del creador. Un eventual experimento técnico, juego prototipo o prueba de rendimiento requerirá una aprobación separada con alcance definido. El laboratorio JS anterior es un experimento independiente, no el repositorio oficial del RPG.


---

<!-- Archivo: 03_MATRIZ_REFERENTES.md -->

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


---

<!-- Archivo: 04_COMBATE_Y_HECHIZOS.md -->

# FrankmanGames — Cuaderno de diseño: combate de acción y libertad de hechizos

**Estado:** ALTERNATIVAS NO APROBADAS. Objetivo: convertir los recuerdos y restricciones del autor en preguntas examinables, no escoger reglas por él.


> **Actualización v0.3 (2026-10-25):** el creador expresó que quiere combinar **profundidad de builds y hechizos** con **habilidad manual y ejecución**. Esto **no aprueba** ninguna mecánica concreta ni un reparto numérico fijo. Para la formulación vigente, leer `11_FILOSOFIA_COMBATE_PREPARACION_Y_EJECUCION.md`. Las tres hipótesis del apartado 4 son alternativas para investigar, no opciones entre las que deba elegir ya.

## 1. Problema de diseño central

DOFUS permite planificar bajo un presupuesto discreto de PA/PM, turnos, casillas y alcance. En tiempo real, la persona puede moverse y atacar continuamente. Sustituir `1 PA = X maná` no conserva automáticamente decisiones, contra-juego, duración ni roles. Se requiere conservar **la riqueza de elecciones**, no la sintaxis de recursos.

La preferencia por Temporis IV tiene dos componentes diferenciables:
- **Coleccionar/descubrir habilidades:** recompensa de la exploración y de la actividad social.
- **Construir repertorios combinables:** elegir herramientas para un estilo propio, incluso cruzando identidades tradicionales de clase.

El número diez es un precedente histórico, no nuestra limitación aprobada.

## 2. Traducción conceptual: PA/PM frente a acción

| Función táctica en juego por turnos | Equivalente posible en tiempo real | Riesgos a investigar | Aprobación |
|---|---|---|---|
| Limitar acciones por turno (PA) | Maná, cargas, enfriamientos, recuperación, fatiga, tiempos de lanzamiento o combinaciones | Spam, espera pasiva, combos dominantes | PENDIENTE |
| Limitar movimiento por turno (PM) | Velocidad, sprint, stamina, inercia, esquiva, dash o restricciones por hechizo | Movilidad excesiva inutiliza posicionamiento | PENDIENTE |
| Alcance por casillas | Distancia física, puntería, trayectoria, línea de visión, área, proyectiles | Dificultad de lectura de hitboxes | PENDIENTE |
| Control de mapa por zonas | Suelo persistente, barreras, trampas, líneas de tiro, desplazamiento forzado | Caos visual, dificultad en multijugador | PENDIENTE |
| Efectos por turnos | Duración en segundos, impactos, eventos, acumulaciones o hit counts | Escalas temporales difíciles de equilibrar | PENDIENTE |
| Invocaciones | IA de aliado, órdenes directas o comportamiento programado | Complejidad y coste de simulación | PENDIENTE |
| Coste de arma en PA | Ventana de ataque, combo, coste de recurso, recuperación, vulnerabilidad | Repetición de básicos o armas irrelevantes | PENDIENTE |
| Fin de turno | Ventanas de vulnerabilidad, ritmo de encuentro, pausas tácticas, cambio de fase | Fatiga si no hay espacios de decisión | PENDIENTE |

No determinar reglas de física o tiempos numéricos hasta que el creador ratifique la sensación buscada y el trabajo de investigación aporte ejemplos.

## 3. Diseño de hechizos: taxonomía a investigar

**Posibles familias de función, no lista aprobada:** daño directo, daño periódico, sanación, escudo, movilidad, control del adversario, control del terreno, invocación, soporte al grupo, transformación, defensa reactiva, utilidad ambiental, obtención de recursos. Pedir a los agentes ejemplos concretos de cada referente y qué decisiones generan. **No trasladar nombres ni efectos propietarios al juego propio.**

Para cada hechizo hipotético, investigar:
- **Intención:** ¿qué problema resuelve y qué fantasía cumple?
- **Adquisición:** ¿cómo se obtiene o desbloquea? ¿es significativo encontrarlo?
- **Activación:** coste, condición, tiempo, posición, línea de visión, objetivos.
- **Efecto:** tipos de resultado y duración, contramedidas.
- **Feedback:** audio, silueta, anticipación, impacto, recuperación.
- **Sinergia:** qué habilita con otras habilidades y qué contradicciones crea.
- **Juego en equipo:** coordinación, roles espontáneos, superposición de efectos.
- **Lectura:** cómo entiende la amenaza un enemigo o compañero humano.
- **Balance y explotación:** ventanas de invulnerabilidad, cadenas infinitas, abuso de control.

## 4. Tres hipótesis de ritmo — exclusivamente experimentales

**A. Acción ágil:** mayor énfasis en esquivar, timing, reposicionamiento y lanzamientos frecuentes. Riesgo: saturación visual y alejamiento del lado táctico.

**B. Acción táctica deliberada:** hechizos con compromisos de animación, anticipación, alcance y recursos. Riesgo: sentirse lento o como un turno encubierto.

**C. Ritmo híbrido:** movimiento constante con algunas habilidades de alta decisión, recursos y recuperación. Riesgo: equilibrio difícil; puede terminar con lo peor de ambos.

**No recomendar una variante como final sin entender si el autor prefiere intensidad, control y planeación o un balance.**

## 5. El problema del ataque básico

El autor criticó el combate de FATE como «pegar y pegar»; no quiere un juego de botones básicos repetitivos. De aquí NO se desprende eliminar ataques normales. Opciones para evaluación:
- Ataque básico como herramienta mínima de recuperación de recursos.
- Arma como un conjunto pequeño de movimientos situacionales.
- Ataque normal como generador de oportunidades para hechizos.
- Arma con un coste/compromiso real comparable a un hechizo.
- Ausencia de ataque básico universal y dependencia de habilidades equipadas.

Cada opción afecta tutorial, animaciones, balance, equipamento y combate cooperativo. El agente debe estimar ese impacto.

## 6. Monstruos enormes y miedo justo

El recuerdo central de FATE no es solo «enemigo grande», sino **no saber si puedo con él**. Candidatos de investigación: descubrimiento por sonido/sombra, comportamiento que evidencia inteligencia, ataques legibles y severos, posibilidad real de retirada, encuentro no obligatorio, mejoras de música y luz, botín/recompensa con significado. No asignar daño, tamaño ni «jefes cada N pisos» sin decisión.

**Objetivo de experiencia a validar:** tensión sin frustración injusta; sorpresa sin telegráficos invisibles.

## 7. Sistemas de combate y red

Un combate instanciado en tiempo real introduce cuestiones que no existían de igual forma en DOFUS por turnos:
- ¿Se sincroniza cada posición, habilidad y estado? ¿Qué predice el cliente?
- ¿Qué valida la autoridad del servidor (en particular si existe economía compartida)?
- ¿Cómo se unen aliados y quién controla el inicio?
- ¿Qué sucede con compañeros desconectados o muertos?
- ¿Qué ve el resto del mundo durante la pelea?
- ¿Qué pasa con criaturas de mapa cuando comienza la instancia?

No diseñar mensajes específicos ni reutilizar el protocolo de DOFUS. Estas son restricciones conceptuales para discutir con el autor.

## 8. Qué pedir exactamente a los agentes

- Una ficha de `PA/PM → intención táctica` por referente.
- Un catálogo de **funciones jugables de hechizo**, no un inventario de nombres.
- Un análisis del papel de armas versus magia en ambos sistemas.
- Un estudio de entrada/salida y visibilidad de combates DOFUS.
- Un mapa de «posibles decisiones del jugador por segundo/minuto», separado de fórmulas.
- Cuando se propongan cambios, mostrar ventajas, efectos secundarios y qué se perdería de cada referente.

## 9. Decisiones explícitamente abiertas

¿Clases o no? ¿Habilidades universales o parcialmente restringidas? ¿Límite de equipadas? ¿Maná? ¿Enfriamientos? ¿Stamina? ¿Ataques básicos? ¿Dash? ¿Puntería? ¿Hitboxes? ¿PVP? ¿Cambio de baraja fuera de combate? ¿Hechizos como loot? ¿Controles de teclado/ratón/gamepad? ¿Cámara? ¿Duración ideal de pelea? ¿Dificultad? Ninguna resuelta.

## 10. Pregunta fuerte para el creador (no necesaria para seguir investigando)

**Respondida en dirección general:** quiere combinar profundidad estratégica de builds/hechizos con habilidad manual y ejecución. **Pendiente:** cómo deberían convivir para distintos tipos de jugadores y encuentros, sin presuponer porcentajes ni reglas.

No convertir la respuesta en reglas de forma automática; usarla para ordenar investigaciones y prototipos futuros.


---

<!-- Archivo: 05_MUNDO_HISTORIA_Y_MULTIJUGADOR.md -->

# FrankmanGames — Mundo, misterio, historia finita y multijugador

**Estado:** marco de preguntas, restricciones expresadas y alternativas sin aprobar. No existe aún lore oficial.

## 1. Contrato emocional de la exploración

Según el creador, FATE producía misterio con audio, peligro y botín imprevisible. El ejemplo de pescar en un piso profundo ilumina un contraste interesante: poder relajarse en un sitio hostil, aunque al avanzar vuelva la incertidumbre.

**Expresado:** misterio, música, miedo ante monstruos enormes, exploración de profundidad, objetos raros en combate y pesca. **Síntesis por validar:** alternar momentos de tensión, curiosidad, refugio y sorpresa. **No aprobado:** pesca obligatoria, biomas, niveles, número de pisos, pesca cooperativa, mapas generados por semilla.

Preguntas:
- ¿Qué descubre el jugador: historia, geografía, criaturas, hechizos, objetos, secretos del mundo?
- ¿Cómo evitamos una exposición constante de enemigos que acabe anulando el misterio?
- ¿Cómo diferenciar amenazas desconocidas de simples enemigos demasiado fuertes?
- ¿Cuándo se experimenta calma y qué actividad hace memorable ese momento?
- ¿Qué distingue un gran hallazgo de una recompensa estadística genérica?

## 2. Estructura finita: historia con final ≠ mundo sin rejugabilidad

El creador rechaza el descenso infinito repetitivo de FATE y quiere una historia y un final. Esto **no define aún** estructura de campañas, eventos, mazmorras, exploración libre ni endgame.

Modelos para investigación (OPCIONES, no decisiones):
- **Campaña de regiones conectadas:** historia con capítulos y accesos que se transforman.
- **Núcleo social + expediciones:** salir de una ciudad/refugio hacia historias acotadas.
- **Mundo compartido por zonas + escenas privadas:** zonas públicas y contenidos narrativos instanciados.
- **Mundo semipersistente con misiones de grupo:** progresión individual con episodios comunes.

Para cada modelo evaluar: cómo progresas, cómo se reencuentran amistades con distinto avance, qué pasa después del final, cuántos escenarios únicos demanda y cómo se evita repetir mapas sin significado.

## 3. Historia: plantilla de intención narrativa, no trama inventada

No existe antagonista, protagonista, bioma, mapa ni sinopsis aprobados. Los agentes NO deben inventar y fijar automáticamente una «gran profecía», «reino de...» o «dioses del universo».

### Premisas de historia a definir con el creador

- **Pregunta dramática:** ¿qué misterio impulsa el viaje?
- **Promesa inicial:** ¿por qué el jugador comienza a explorar?
- **Revelaciones:** ¿cómo evoluciona la comprensión del mundo?
- **Tensión principal:** ¿qué se pone en riesgo?
- **Motivo para mejorar:** ¿progreso instrumental o también moral/narrativo?
- **Convergencia:** ¿qué decisiones deben poder compartir jugadores con progresos distintos?
- **Conclusión:** ¿qué significa realmente terminar la campaña?
- **Vida posterior:** ¿qué puede continuar tras créditos sin invalidar el final?

**Prueba de coherencia:** un jugador solitario y un grupo deben entender la historia central; la repetición social no debe convertir en absurdo un desenlace ya alcanzado.

## 4. Monstruos, ambientación y diseño de encuentros

Crear un repertorio de amenazas con propósitos emocionales distintos: desconocimiento, peligro evidente, sorpresa, curiosidad, desafío de equipo, rareza, recompensa y recuperación. No fijar cantidad de especies; la cantidad de **comportamientos diferentes** puede importar más que el total.

Plantilla de encuentro a estudiar:
- Qué percibe el jugador ANTES de ver al enemigo.
- Qué decisión toma al reconocer la amenaza.
- Qué cambia al entrar en combate.
- Cómo se comunica riesgo, posibilidad de escapar y recompensa.
- Qué importancia tiene el sonido/música en lugar del texto/UI.
- Cómo se adapta a varios jugadores sin destruir la legibilidad.

No hacer «enemigo enorme = jefe con millones de HP» por defecto.

## 5. Tres interpretaciones distintas del mundo social

| Variante abierta | Experiencia | Complejidad sustancial | Dudas principales |
|---|---|---|---|
| RPG solo con cooperativo por sesión | Grupo pequeño comparte aventura y combate | Sincronización, partidas, conectividad, host/servidor, progreso de grupo | Quién guarda progreso y cómo se unen |
| Mundo social por regiones y encuentros instanciados | Ves a otros afuera; peleas privadas de tu grupo | Servidores persistentes, instancia, identidad, progresión, seguridad y operaciones | Qué comparte el mundo y qué queda privado |
| MMO persistente de gran escala | Comunidades y economía de largo plazo | Escalado, persistencia, seguridad, moderación, soporte en vivo, herramientas y costes recurrentes | Cuál es el umbral mínimo de jugadores para cumplir la fantasía |

**Expresado por el creador:** le interesa MMO o al menos cooperativo. **No existe decisión de adoptar una de las filas.** No imponer hoja de ruta «co-op y después MMO» sin consulta.

## 6. Instancias de combate sin turnos

**Preferencia expresada:** si un monstruo te agrede, la pelea no debería molestar a los demás jugadores. Una interpretación posible en acción: jugador/grupo entra a una instancia localmente separada mientras el mundo público sigue activo, pero quedan muchas preguntas:

- ¿La instancia es una copia del lugar exacto o una arena propia?
- ¿Los amigos entran automáticamente, por invitación o por proximidad?
- ¿Puede entrar alguien después de iniciado el combate?
- ¿Se pueden observar o ayudar sin entrar?
- ¿Los enemigos regresan al mapa o desaparecen mientras dura el encuentro?
- ¿Qué pasa si otra persona pisa la misma criatura o si dos grupos reclaman el encuentro?
- ¿Se preservan objetos y progresión en combate individual?
- ¿Cómo evitar la desconexión/lag como fuente de pérdida injusta?

**Cuidado especial:** FATE offline, DOFUS por turnos y un RPG cooperativo de acción tienen costes y reglas de instanciación distintos; hay que diseñar nuevas soluciones originales.

## 7. Consecuencias cruzadas que deben figurar en cada propuesta

| Decisión potencial | Impacto en diseño | Impacto en producción |
|---|---|---|
| Combates instanciados | Ritmo distinto entre explorar y luchar; accesibilidad en grupo | Gestión de mapas, sincronización y estados |
| Historia con final | Capítulos, revelaciones, recontextualizar enemigos | Escritura, cinemáticas/escenas, pruebas de progresión |
| Exploración repetible | Rejugar sin aburrimiento, secretos dinámicos | Variedad de espacios, enemigos, audio, combinaciones |
| Eventos sociales | Encuentros espontáneos y cooperación | Servidores, moderación, UI social, operaciones |
| Hechizos compartibles/comerciables | Progreso, economía y descubrimiento | Verificación de propiedad en servidor y antifraude |
| Pausas atmosféricas | Identidad emocional y contraste con acción | Música, ambientales, animaciones, actividades opcionales |

## 8. Entregables para agentes

1. Mapa de experiencia del jugador desde ciudad/exploración hasta encuentro/retorno en FATE y DOFUS, con evidencia.
2. Diagrama de transición a pelea DOFUS Retro/3 (qué es cliente y qué servidor cuando sea identificable); no copiar protocolo.
3. Mapa de posibilidades narrativas sin crear lore definitivo, incluida la definición de «final del juego» en cooperativo.
4. Rúbrica para comparar sistemas multijugador según visión, coste, arte y soporte.
5. Estudios de referencia de la música, la exploración y el temor, con alternativas de **expresión original**.


---

<!-- Archivo: 06_PRODUCCION_ARTE_AUDIO.md -->

# FrankmanGames — Plan de investigación para producir arte, modelos, animaciones y audio

**Estado:** rutas de producción posibles, NO selección de estilo, proveedor, técnica o motor.

## 1. El problema que planteó el creador

«¿Cómo vamos a modelar personajes, casas, cuevas, montañas, equipables y todo el resto solos?» No se resuelve afirmando que una IA produce miles de modelos. Hay que construir un **pipeline repetible y coherente**, con coste conocido de cada activo, aunque aún no tengamos un artista de tiempo completo.

La diferencia decisiva no es solo obtener un modelo bonito: es tenerlo optimizado para un juego, con escala, colisiones, UV, materiales, rig (si corresponde), animaciones, LOD, pivotes, variantes, exportación limpia y permiso legal de uso.

## 2. Estrategias para evaluar

| Método | Qué aporta | Limitación | Recomendación metodológica |
|---|---|---|---|
| Modelado original en Blender | Control de identidad, topología y animación | Horas de aprendizaje/producción | Probar con un personaje y un entorno pequeño |
| Kits modulares propios | Casas, cuevas, ruinas y arquitectura componibles | Repetición si la identidad modular no varía | Definir lenguaje modular y piezas maestras |
| Activos CC0/licenciados | Arrancar prototipos y estudiar escenas | Estilos mezclados, licencia por activo | Mantener registro de procedencia y uso permitido |
| Generación asistida por IA (conceptos) | Iterar siluetas, paletas, criaturas, biomas | No entrega necesariamente recursos 3D válidos | Tratar conceptos como referencia artística, no asset final |
| Modelos 3D generados por IA | Acelerar formas preliminares | Topología, materiales, rig, retopología y licencias | Someter a mismo control de calidad que cualquier modelo |
| Encargos externos puntuales | Resolver un personaje base, rig, música o animación clave | Coste monetario y dependencia | Valorar uso focalizado en piezas que definan identidad |

**Fuentes verificadas** para evaluar licencias iniciales: Blender permite uso comercial de obras creadas con él: https://www.blender.org/support/faq/ . Kenney declara CC0 para sus paquetes de assets: https://kenney.nl/support . Poly Haven declara CC0 en sus modelos/texturas/HDRI: https://polyhaven.com/license . El agente debe comprobar la licencia **de cada recurso concreto**, no asumir que todas las plataformas/marketplaces son CC0.

## 3. Pipeline conceptual de un personaje 3D

`Brief de personaje -> silueta y referencias originales -> arte conceptual aprobado -> blockout 3D -> escultura/modelado -> retopología/UV -> materiales/texturas -> rig -> animación -> exportación -> importación -> pruebas de cámara y combate -> correcciones -> versión optimizada`.

**Puertas de calidad** que deberían estudiarse:
- Silueta reconocible incluso sin textura y en la cámara realmente elegida.
- Volúmenes y proporciones coherentes; no deformaciones en articulaciones.
- Pivotes, escala, esqueleto y nombres consistentes.
- Animaciones de locomoción, hechizo, impacto, caída y transición consistentes.
- Compatibilidad de materiales/formatos con tecnologías candidatas.
- Licencia o autoría registrada y posibilidad de distribución comercial.
- Presupuesto de rendimiento medible una vez exista prototipo autorizado.

No fijar ahora triángulos, número de huesos, tamaño de texturas o formatos exclusivos: dependen de plataforma, cámara, estilo y benchmark.

## 4. Equipamiento y visualización del personaje

Preguntas:
- ¿Las armas aparecen realmente en el cuerpo? ¿Y las armaduras o accesorios?
- ¿Un ítem cambia el modelo, textura, partículas o solo estadísticas?
- ¿Los personajes comparten un esqueleto o familias de rigs?
- ¿Una habilidad necesita animación única por arma o puede reutilizarse?
- ¿Cómo afectan tamaños corporales y especies al número de animaciones?
- ¿Cómo se comunica la rareza sin saturar el arte?

Una armadura que cambia visualmente puede multiplicar el coste en modelado, clipping, rigs, QA y sincronización en red. **El creador debe elegir cuánto importa esta personalización visual.**

## 5. Movimiento y «no se vea robótico»

El creador exige una mejora percibida en expresividad respecto a FATE. Investigar opciones:
- Transiciones suaves entre reposo, desplazamiento y combate.
- Aceleración/desaceleración coherente con fantasía del personaje.
- Animaciones direccionales y mezcla de locomoción.
- Anticipación y recuperación de ataques; reacciones al impacto.
- Alineación de pies y cuerpo con superficies; cuidado con deslizamiento de pies.
- Respuesta del objeto/arma al contacto (audio, hit-stop moderado, efectos).
- Reacción convincente de criaturas enormes al entorno y al daño.

No confundir física realista con animación satisfactoria: un RPG estilizado puede usar animaciones expresivas y físicas selectivas.

## 6. Pipeline de escenarios

**Opciones para estudiar, sin seleccionar:** mundo construido a mano, kit modular, terreno procedural acotado, combinación de sectores con piezas reutilizables. Para cada opción describir identidad visual, repetición, coste de creación, streaming, colisiones, navegación IA, variación climática, iluminación y producción de secretos.

El problema no es solo «hacer montañas»: hay que hacer montañas **navegables, legibles, con rendimiento, interesantemente explorables y coherentes con la historia**.

## 7. Audio y música como pilares jugables

El testimonio de FATE da relevancia excepcional a música y ambientalización. No relegar audio al final del desarrollo. Investigar:

- Mapa emocional de escenas: ciudad/refugio, exploración, tensión, enemigo intimidante, combate, descubrimiento, fracaso, calma, recompensa.
- Capas musicales variables según estado sin cambios bruscos molestos.
- Sonidos que revelan criaturas o lugares antes de que se vean.
- Silencios y momentos de reposo que hacen significativa la música posterior.
- Audio de feedback de hechizos distinguible para multijugador.
- Espacialización y mezcla que no tape sonidos críticos.
- Identidad musical propia con compositor, sonidos originales o licencias adecuadas.

**No utilizar pistas de FATE/DOFUS dentro del producto** sin licencias expresas. Las referencias musicales sirven para describir atmósferas, no para copiarlas.

## 8. Prueba de viabilidad artística (solo planificación por ahora)

Antes de producir un catálogo enorme, pedir al equipo de arte/IA una hoja de costes hipotéticos y un «paquete representativo» para aprobación futura:
- Un personaje con dos conjuntos de movimientos.
- Una criatura pequeña y una enorme.
- Una arma y un equipable con diferencia visual.
- Un módulo de cueva, una construcción y una pieza natural.
- Tres estados de audio: exploración, amenaza y calma.

**Aún no producir estos recursos.** Primero acordar estilo, cámara, nivel de detalle, herramientas y restricciones legales con el autor. El paquete solo sirve para estimar y probar un pipeline cuando se autorice.

## 9. Registro de licencias de assets, obligatorio cuando se usen

`asset_id | título | autor | origen/URL | licencia y versión | fecha de descarga | ámbito de uso | modificaciones | créditos necesarios | formato | responsable | aprobado para distribuir`.

Esto aplica también a música, voces, efectos, recursos adquiridos y salidas de IA sujetas a términos de plataforma. Separar material de investigación de recursos finales del juego.


---

<!-- Archivo: 07_PLAN_PREPRODUCCION_SIN_CODIGO.md -->

# FrankmanGames — Fases de preproducción sin escribir código de juego

**Objetivo:** alinear visión, investigación, decisiones y viabilidad antes de desarrollar el RPG. Las etapas son puertas de conocimiento, **no fechas ni sprints obligatorios**.

## Fase A. Recuperar y auditar contexto

Entradas: carpeta `FrankmanGames`, paquete v0.1, este paquete v0.2 y los README/REPORT generados por los agentes.

1. Inventariar documentos y ubicaciones reales; distinguir originales, copias, datos de juego y notas.
2. Revisar contradicciones o trabajos incompletos de los agentes anteriores.
3. Crear un índice de evidencia y vincular cada afirmación de la matriz con una fuente.
4. Comparar fecha/versión de cliente o juego para evitar mezclar Dofus Retro, DOFUS 3 y Temporis IV.
5. Conservar `DESCONOCIDO` donde no haya pruebas.

**Salida exigida:** inventario comprobado, mapa de referencias y lista corta de dudas de mayor impacto. **Criterio:** ningún hecho técnico clave queda sin su marca de fuente y confianza.

## Fase B. Convertir ingeniería inversa en fichas útiles

Dividir por experiencia, no por extensión de decompilación:

- FATE: misterio/amenaza, hechizos y daño, loot, pesca/recompensas, generación y repetición.
- Retro: PA/PM, tácticas de hechizos, armas, efecto de terreno, instancias, mundo y legibilidad.
- DOFUS 3: presentación y lectura de hechizos/combate, animación, UI, flujo instancias y comparación con Retro.
- Temporis IV: obtención de hechizos, combinación libre, limitación de equipados, comercio de hechizos y sinergias.

**Salida exigida:** fichas con evidencia, efecto en el jugador, incertidumbres, diferencias y posibles líneas de inspiración sin copiarlas.

## Fase C. Alinear visión con el creador

Mostrar primero una síntesis de máximo dos páginas: qué busca emocionalmente, qué le frustraba, qué no sabemos y qué decisiones alteran más el diseño. Plantear **una o dos preguntas potentes por conversación**, no formularios de 50 campos.

Los agentes pueden aportar alternativas y dibujos conceptuales/documentos cuando el autor los solicite, pero el creador decide. Actualizar `08_REGISTRO_DECISIONES.md`; cualquier aprobación debe tener una cita o referencia al mensaje de aprobación.

**Salida exigida:** pilares validados, antipilares corregidos, rumbo del combate y prioridades explícitas. No necesita resolver todos los atributos numéricos.

## Fase D. Diseño de sistemas originales

Proponer **documentos de diseño de alto nivel** para: combate/hechizos, enemigo/IA, loot, progresión, instancia, cooperación, exploración, historia/estructura, economía y dirección audiovisual.

Cada sistema requiere: propósito, reglas propuestas, estados y casos límite, dependencias con otros sistemas, ventajas/desventajas, riesgos, costes, pruebas y **aprobación diferenciada** (visión, mecánica e implementación).

**Salida exigida:** GDD ya con capítulos seleccionados por el creador. Los capítulos pendientes no se rellenan por invención.

## Fase E. Evaluación de viabilidad y alcance

Sin iniciar implementación todavía: comparar nivel esperado de arte, cantidad de contenido, técnica de multijugador, operaciones, tiempo de creación de activos, escalas de presupuesto, herramientas y posibles MVP. Cualquier presupuesto estimado debe declarar hipótesis.

**Salida exigida:** documento de alcance elegido (vertical slice futuro), riesgos y decisiones diferidas; lista de recursos con licencias verificadas y pipeline artístico candidato.

## Fase F. Autorización para experimentar

Solo después de autorización del creador, definir experimentos pequeños y reversibles para la primera mecánica. Ejemplo de *hipótesis*, no instrucción: comprobar qué sensación de acción produce una combinación limitada de habilidades bajo dos modelos de coste. Cada experimento tendrá un objetivo, una duración acotada, una medición y un criterio de descartar/seguir.

**Salida exigida:** orden de trabajo aprobada para crear un prototipo original. Hasta esa autorización, **NO PROGRAMAR EL JUEGO**.

## Priorización sin estimaciones falsas

| Investigación | Valor para visión | Riesgo de incertidumbre | Equipo sugerido |
|---|---|---|---|
| Libertad de hechizos/Temporis IV | Muy alto | Medio | Retro + Temporis + diseñador |
| Conversión PA/PM a acción | Muy alto | Muy alto | Dofus + FATE + revisor |
| Combates instanciados en tiempo real | Muy alto | Alto | Experiencia DOFUS + diseño de sistemas |
| Misterio, audio y peligro | Muy alto | Alto | FATE + arte/audio |
| Historia y estructura de final | Muy alto | Alto | Diseñador narrativo + creador |
| Pipeline 3D y animación | Alto | Alto | Arte/animación |
| Alcance MMO/co-op | Muy alto | Muy alto | Diseño de red + creador |
| Motor/JS/C#/GPU | Importante, pero subordinado a requisitos | Alto | Evaluador tecnológico futuro |
| Fórmulas exactas propietarias del cliente | Variable | Alto costo de análisis | Solo si responden pregunta creativa concreta |

## Criterio de calidad antes del primer código

- [ ] El creador corrigió/aprobó los objetivos emocionales centrales.
- [ ] Hay al menos una descripción concreta de «cómo se sentiría un encuentro».
- [ ] Está claro qué rasgo de Temporis IV se valora y qué no se asume automáticamente.
- [ ] Se puede explicar por qué existen instancias sin turnos y qué ocurre al entrar/salir.
- [ ] La definición de historia con conclusión es compatible con la modalidad multijugador elegida.
- [ ] Los riesgos de producción de assets tienen plan de evaluación, no suposiciones.
- [ ] Existe un alcance propuesto para el primer prototipo y está expresamente autorizado.
- [ ] El motor, las licencias, la seguridad de red y la distribución no se han decidido por familiaridad o inercia.

**La meta no es agotar toda duda, sino evitar que las decisiones de mayor coste se tomen accidentalmente.**


---

<!-- Archivo: 08_REGISTRO_DECISIONES.md -->

# FrankmanGames — Registro de visión, decisiones y preguntas

**Versión:** 0.3 · **Estado:** compilación de declaraciones del creador; pendiente de revisión conjunta.  
**Principio:** una intención expresada NO es una regla implementable completa. Solo el autor convierte una propuesta en decisión de diseño. No se exige volver a preguntar lo que ya dejó claro.

## A. Orientaciones expresadas por el creador

| ID | Enunciado fiel a lo dicho | Clasificación | Aspecto aún indeterminado |
|---|---|---|---|
| V-001 | Queremos hacer un videojuego ORIGINAL que estudie FATE, DOFUS Retro y DOFUS 3 | EXPRESADO | Nombre/ambientación/género fino |
| V-002 | Del FATE le atraen misterio, música, monstruos enormes e incertidumbre de vencerlos | EXPRESADO | Sistemas que provocan esa emoción |
| V-003 | Botín raro de enemigos y pesca dejó recuerdos fuertes | EXPRESADO | ¿Pesca necesaria o evocación del tipo de sorpresa? |
| V-004 | Recuerdo de pescar en piso 30 y la música, esperando la picada | EXPRESADO | Cómo recrear el contraste de calma/riesgo sin copiar |
| V-005 | Quiere acción sin turnos en lugar de reproducir combates de DOFUS | EXPRESADO | Controles, velocidad, dificultad, física |
| V-006 | El combate básico de FATE era tosco/repetitivo y los hechizos eran atractivos | EXPRESADO | Función de armas, básicos y spells |
| V-007 | Le encanta experimentar con repertorio de hechizos de distintas clases como en Temporis IV | EXPRESADO | Número de hechizos, obtención, clases, desbloqueo |
| V-008 | PA/PM y coste de arma requieren reinterpretación para el tiempo real | EXPRESADO | Maná, stamina, cooldown, tiempos, cargas |
| V-009 | Le gustan las peleas instanciadas que no molestan al resto del mundo | EXPRESADO | Flujo, acceso de aliados, topología red |
| V-010 | Quiere arte/música atractivos y animaciones menos robóticas | EXPRESADO | Estética, cámara, dirección musical, producción |
| V-011 | No quiere mazmorras interminables, repetitivas y sin propósito | EXPRESADO | Rejugabilidad, contenido opcional, procedural |
| V-012 | Quiere historia y final del juego | EXPRESADO | Trama, longitud, estructura, progresión y final compartido |
| V-013 | El destino es MMO o, como mínimo, RPG cooperativo | EXPRESADO | Modelo de lanzamiento, escala y costes |
| V-014 | Necesita un plan creíble para modelado de personajes, edificios, cuevas, montañas y equipables | EXPRESADO | Herramientas, estilo, licencia, presupuesto |
| V-015 | Quiere alinear tres investigaciones mediante documentación extensa ANTES de programar el RPG | EXPRESADO | Momento de autorizar primer experimento oficial |
| V-016 | Las propuestas de asistentes/agentes no se convierten en «leyes» sin su visión y aprobación | EXPRESADO | Flujo concreto de ratificación |
| V-017 | Interesa evaluar si se podría usar JS/TS y un motor propio sin escoger motor prematuramente | EXPRESADO ANTERIORMENTE | Plataforma, benchmarks, engine |
| V-018 | Quiere combinar profundidad de builds y hechizos con habilidad manual y ejecución en el combate | EXPRESADO (2026-10-25) | Relación entre estrategia, ejecución, accesibilidad y progreso |
| V-019 | Quiere desarrollar esa filosofía SIN aprobar mecánicas concretas todavía | EXPRESADO (2026-10-25) | Investigar y comparar antes de definir sistemas |

*V-005 junto con V-007 indica dirección creativa, no asigna toda la mecánica de combate. V-013 tampoco decide un MMO de producción.*

## B. Síntesis del asistente que el autor puede corregir

| ID | Interpretación | Estado |
|---|---|---|
| S-001 | El misterio requiere que no todo sea predecible, pero que el peligro sea legible | SÍNTESIS_POR_VALIDAR |
| S-002 | Los hechizos deben crear diversidad de decisiones, no solo variedad visual | SÍNTESIS_POR_VALIDAR |
| S-003 | Actividades tranquilas como la pesca pueden dar significado a la exploración peligrosa | SÍNTESIS_POR_VALIDAR |
| S-004 | El final narrativo y la rejugabilidad no son necesariamente excluyentes | SÍNTESIS_POR_VALIDAR |
| S-005 | La presentación audiovisual merece atención desde la preproducción | SÍNTESIS_POR_VALIDAR |
| S-006 | Combates instanciados en tiempo real pueden resolver interferencias del mundo compartido si se diseñan bien | SÍNTESIS_POR_VALIDAR |

## C. Propuestas que expresamente NO están aprobadas

| ID | Propuesta histórica o reciente | Estado | Nota |
|---|---|---|---|
| P-001 | Exactamente 10 hechizos activos | NO DECIDIDO | Ejemplo de Temporis IV, no mandato |
| P-002 | Maná como sustituto de PA | NO DECIDIDO | Solo una opción |
| P-003 | Enfriamientos en lugar de recursos | NO DECIDIDO | No confirmado |
| P-004 | Dash / esquiva | NO DECIDIDO | Mencionado como posibilidades por el autor |
| P-005 | Sistemas de clases o ausencia de clases | NO DECIDIDO | Temporis IV no obliga ninguno |
| P-006 | Motor JS propio/Babylon.js/PlayCanvas/Unity/Godot | NO DECIDIDO | Evaluación técnica futura |
| P-007 | MMO en primera versión | NO DECIDIDO | Se requiere estimar coste de servicio |
| P-008 | Cooperativo como primera versión | NO DECIDIDO | Variante posible, no promesa |
| P-009 | Pesca como sistema obligatorio | NO DECIDIDO | Recuerdo positivo no mandato |
| P-010 | Cuevas/dungeons con partes procedurales | NO DECIDIDO | Investigar la repetición en FATE |
| P-011 | Perspectiva isométrica 3D | NO DECIDIDO | Cámara y presentación abiertas |
| P-012 | Uso de kitbash, modelos CC0, IA 3D o Blender para los assets finales | NO DECIDIDO | Opciones de producción |
| P-013 | PVP, casas, oficios, monturas, guilds | NO DECIDIDO | No presuponer por tradición DOFUS |

## D. Decisiones aprobadas formalmente sobre mecánicas concretas

| ID | Mecánica | Decisión y fecha | Prueba de aprobación | Estado |
|---|---|---|---|---|
| — | — | Ninguna regla numérica/arquitectónica ha sido aprobada todavía | — | SIN DECISIONES REGISTRADAS |

**La dirección V-018 NO aprueba mecánica concreta, ni una contribución numérica 50/50.**

**No interpretar esta tabla vacía como ausencia de visión:** el autor sí ha expresado con claridad direcciones y preferencias. El vacío corresponde a especificaciones jugables detalladas.

## E. Preguntas de gran impacto, para sesiones futuras, no formulario obligatorio

1. **Combate [DIRECCIÓN YA RESPONDIDA]:** combinar la profundidad de builds/hechizos con habilidad manual y ejecución. Pendiente: describir sus interacciones y el espacio para diferentes perfiles de jugadores sin fijar fórmulas.
2. **Mundo compartido:** ¿Qué experiencia exacta quieres con otros jugadores fuera del combate: verlos, comerciar, formar grupos, encontrarlos aleatoriamente, compartir historia, todo lo anterior? (Ayuda a discriminar MMO de cooperativo).
3. **Progreso narrativo:** ¿Qué imaginas cuando dices «terminar el juego» en una aventura que podría seguir online?
4. **Construcción de personaje:** ¿Las clases deben tener identidad/ventajas propias aunque puedas equipar hechizos transversales, o tu personaje debería ser libre de clase?
5. **Sensación de combate instanciado:** ¿Te imaginas que una amenaza te arrastre a un encuentro privado en el mismo paisaje o prefieres combatir en el mundo abierto con aislamiento de interacción?
6. **Dirección artística:** ¿Deseas estilización tipo DOFUS, reinterpretación 3D tipo FATE o una estética completamente nueva? (No fijar estilo por ejemplo de referencia).
7. **Producción:** ¿Qué te gustaría crear tú artesanalmente y en qué querrías ayuda de herramientas, colaboradores o IA?

**Prioridad sugerida:** continuar con preguntas cualitativas del capítulo 11 y mantener la pregunta 2 de mundo compartido como próxima gran decisión, sin imponer un orden. Seguir investigando el resto en paralelo sin bloquearlo por respuestas ausentes.

## F. Entrada estándar de decisión

```markdown
### DEC-AAAA-NNN — Título
- Fecha:
- Dominio: combate / mundo / historia / arte / red / tecnología / negocio
- Decisión textual del creador:
- Qué quedó incluido:
- Qué quedó expresamente fuera:
- Fuente de aprobación (mensaje/transcripción/enlace):
- Consecuencias sobre otros sistemas:
- Riesgos/experimentos asociados:
- Estado: APROBADO_POR_AUTOR | REVOCADO_POR_AUTOR
- Versión de documentos impactados:
```

Solo una autorización explícita puede crear entrada `APROBADO_POR_AUTOR`. Las decisiones antiguas podrán revocarse; el cambio se documenta sin reescribir la historia.


---

<!-- Archivo: 09_PROMPT_COORDINADOR.md -->

# FrankmanGames — Prompt operativo para agente coordinador y subagentes

**Uso:** copiar la sección «PROMPT LISTO» en el agente que tenga acceso local a `FrankmanGames`. **Objetivo inmediato:** investigación y documentación, NO código del RPG.

> **Actualización v0.3:** leer también `11_FILOSOFIA_COMBATE_PREPARACION_Y_EJECUCION.md` y aplicar `12_PROMPT_ALINEACION_AGENTES_COMBATE.md` en esta ronda. La pregunta general estrategia vs ejecución ya fue respondida: el creador quiere combinar ambas. Ninguna mecánica concreta ha sido aprobada.

## PROMPT LISTO

> Actúa como **coordinador de investigación y preproducción** del videojuego original de **FrankmanGames**. No eres el director creativo; las decisiones pertenecen al creador. Tu tarea es alinear el material de FATE: Undiscovered Realms, DOFUS Retro y DOFUS 3, complementando una investigación documental de Temporis IV, para producir un expediente de experiencia y diseño, **antes de iniciar cualquier código del videojuego**.
>
> **CARPETA RAÍZ REPORTADA:** `C:\Users\frank\Desktop\2026\FrankmanGames`. Confirma su existencia en el entorno actual. No asumas que puedes leer directorios ajenos a los conectados. Primero lee `00_INICIO_Y_MAPA.md`, `01_BIBLIA_MAESTRA_VISION.md`, `02_CONSTITUCION_AGENTES.md`, `08_REGISTRO_DECISIONES.md` de `FrankmanGames_Preproduccion_v0_3` y el paquete anterior `RPG_Contexto_Agentes_v0_1` que ya está en la carpeta. Consulta los demás capítulos solo cuando sean relevantes a tu tarea.
>
> **RESPETA LA VISIÓN EXPRESADA:** FATE aporta misterio, música, monstruos enormes cuya fuerza se desconoce, emoción al encontrar botín raro incluso pescando y el recuerdo de pescar en una mazmorra profunda; se quiere superar combate repetitivo y animaciones rígidas, y evitar mazmorras infinitas sin final. DOFUS aporta profundidad de hechizos, combinaciones (Temporis IV), arte, música y peleas separadas del mundo; la dirección es combatir en TIEMPO REAL y reinterpretar PA/PM, coste de armas y movimiento, sin asumir equivalencias. El creador quiere HISTORIA CON FINAL y MMO o, como mínimo, RPG COOPERATIVO. No están definidos motor, clases, límite de habilidades, recursos, jugabilidad concreta de dash, lore, cámara ni modelo de servidor.
>
> **NO PROGRAMAR:** no crear código del nuevo juego, no iniciar prototipos, no fijar motores, cifras de balance, biomas o personajes. Las propuestas de IA no son leyes. Si encuentras un antiguo MD que las presente como decisiones, marca contradicción en vez de obedecerlo como especificación aprobada.
>
> **REVISAR PRIMERO EL TRABAJO EXISTENTE:** FATE cuenta con directorio reportado `C:\Users\frank\Desktop\2026\FATE-ReverseEngineering`, resultados REA/Ghidra y `.dat`; DOFUS Retro reportó SWF exportados/desofuscados y una tabla de 311 prefijos; DOFUS 3 reportó firmas C# de Cpp2IL y protobuf. Comprobar cada archivo realmente existente. Si un directorio es desconocido, localizarlo por README y rutas documentadas antes de concluir que falta. No repetir descompilaciones costosas si ya hay resultados legibles. No sobrecargar deliberadamente CPU/GPU ni cambiar configuraciones del PC.
>
> **SEPARAR EVIDENCIA / EXPERIENCIA / PROPUESTA:** cada hecho lleva referente+versión+archivo/captura/ruta+procedimiento+certeza. Ningún número de scripts o mensajes equivale a haber entendido el combate. Retro y DOFUS 3 requieren distinguir interfaz de reglas de servidor. Temporis IV requiere fuentes históricas de 2020 y no debe atribuirse automáticamente a clientes modernos. Documenta cómo se siente y qué decide el jugador, no solo símbolos técnicos.
>
> **PRIORIZA ESTOS TEMAS:** (1) descubrimiento y combinación de hechizos y rol de Temporis IV; (2) transición de PA/PM/armas/turnos a combate de acción; (3) encuentro instanciado sin interferencia a otros jugadores; (4) misterio, audio, enemigos intimidantes y contrastes tranquilos en exploración; (5) botín y equipamiento interesante; (6) estructura de historia con fin y exploración no repetitiva; (7) producción de modelos, animaciones, escenarios y música de forma sostenible; (8) diferencias de alcance entre cooperativo y MMO.
>
> **ROL DE SUBAGENTES, SI DISPONIBLES:** agente FATE (atmósfera, IA, loot, hechizos, dungeons); agente DOFUS Retro (combate táctico, instancias, progresión); agente DOFUS 3 (presentación/UI/animación/comparativa); documentalista Temporis IV (hechizos/deck/obtención/fuentes); especialista de producción audiovisual (pipeline/animación/licencias/coste); revisor independiente (evidencias, contradicciones y riesgo de clon). Si no existen subagentes, realizar en ese orden sin inventar salidas.
>
> **SALIDAS ESPERADAS:** (a) índice de todas las evidencias realmente comprobadas; (b) entre 3 y 5 fichas relevantes por referente; (c) matriz de coincidencias/diferencias/cosas desconocidas; (d) mapa de sistemas y dependencias; (e) documento de opciones y tensiones con pros, contras, riesgos de producción; (f) listado priorizado de como máximo 5 preguntas que SOLO el creador puede decidir; (g) resumen de una página en español comprensible para el autor.
>
> **DIRECTORIOS DE SALIDA SUGERIDOS:** `FrankmanGames/docs/research/` para evidencia y fichas, `FrankmanGames/docs/proposals/` para alternativas no aprobadas, `FrankmanGames/docs/reviews/` para la revisión cruzada, `FrankmanGames/docs/decisions/` para propuestas de decisión y, solo después de la aprobación, decisiones formales. No renombres ni borres los resultados de ingeniería inversa actuales; crea un índice por referencia.
>
> **ENTREGA INTERMEDIA:** señala qué áreas se pueden resolver ya con los datos existentes, cuáles requieren observación del gameplay y cuáles dependen de reglas del servidor que no tenemos. Es aceptable registrar `DESCONOCIDO` y detener análisis invasivos de poco valor.
>
> **LÍMITES:** no conectarse a infraestructura de Ankama con protocolo reconstruido; no extraer credenciales ni manipular autenticación; no copiar código, assets, música, diálogos, iconos o marcas de terceros al repositorio de FrankmanGames. Las investigaciones se hacen con fines de estudio y documentación. Si una extracción entra en conflicto con los términos o derechos de terceros, escalar la duda y optar por observar comportamientos de juego sin replicar implementación protegida.
>
> **CRITERIO DE FINALIZACIÓN:** que el creador pueda leer los informes y decidir qué experiencias busca, con una imagen clara de costes y consecuencias. No equivaler «terminado» con cantidad de archivos creados. Ante decisiones aún no aprobadas, preguntar de forma concreta al creador, sin autoasignar diseño.

## Evaluación de calidad del coordinador

- [ ] Resume la visión del creador de manera fiel, con citas a sus expresiones.
- [ ] Marca cada conclusión técnica como verificada/reportada/inferida/desconocida.
- [ ] Mantiene separados los tres referentes y Temporis IV como caso histórico.
- [ ] No inicia desarrollo del nuevo juego ni cambios de tecnología.
- [ ] Entrega opciones de combate/repertorio/instancias en vez de fórmulas arbitrarias.
- [ ] Trata historia con final, audio y pipeline artístico como parte central, no extras.
- [ ] Plantea pocas preguntas de gran impacto, no listas enormes sin prioridad.


---

<!-- Archivo: 10_PLANTILLAS_FICHAS.md -->

# FrankmanGames — Plantillas uniformes de evidencia y propuesta

## Plantilla A: ficha de experiencia o mecánica por referente

```markdown
# [ID] — [Sistema / experiencia]

- Referente y versión exacta:
- Investigador/fecha:
- Pregunta de investigación:
- Estado de evidencia: OBSERVADO | REPRODUCIDO | REPORTADO | INFERIDO | DESCONOCIDO
- Confianza y motivo:

## Qué experimenta el jugador
- Contexto en el mundo:
- Qué ve, oye o siente (sin atribuir emociones universalmente):
- Opciones disponibles:
- Limitaciones, coste y consecuencias:
- Recompensa / sorpresa / frustración:
- Cómo cambia con un compañero o grupo:

## Funcionamiento verificable
- Descripción funcional:
- Datos/configuración:
- Lógica del cliente:
- Reglas que parecen depender del servidor:
- Ejemplos observados:
- Límites/casos extremos:

## Evidencia
| Hecho concreto | Versión | Ruta/captura | Función/línea/offset | Método | Confianza |
|---|---|---|---|---|---|
| | | | | | |

## Comparativa (sin decidir implementación)
- Relación con otros referentes:
- Qué sería interesante investigar para FrankmanGames:
- Qué problemas no queremos reproducir:
- Opciones de inspiración (NO APROBADAS):

## Pregunta al creador
- Una pregunta cuyo resultado afecte decisiones reales:

## Pendientes
- Experimento observacional o documental siguiente:
- Información que no se puede deducir de esta evidencia:
```

## Plantilla B: comparación transversal

```markdown
# COMPARATIVA — [experiencia de juego]
- Necesidad manifestada por el creador:
- Fuente de la preferencia:

| Aspecto | FATE | DOFUS Retro | DOFUS 3 | Temporis IV |
|---|---|---|---|---|
| Qué hace el jugador | | | | |
| Qué decisiones toma | | | | |
| Cuál es el coste/restricción | | | | |
| Qué siente / qué sorprende | | | | |
| Qué está comprobado | | | | |
| Qué queda desconocido | | | | |

- Convergencias de diseño:
- Contradicciones de diseño:
- Opciones para un diseño ORIGINAL (todas pendientes de aprobación):
- Impactos en red, arte, animación, balance, historia:
- Pregunta decisiva:
```

## Plantilla C: propuesta del agente (NO es una decisión)

```markdown
# PROPUESTA P-XXX — [nombre]
- Estado: PROPUESTA_NO_APROBADA
- Experiencia que intenta provocar:
- Declaración del creador que la motivó:
- Evidencias y referencias comparadas:
- Opción A:
- Opción B:
- Opción C (si existe):
- Qué se gana y qué se pierde en cada opción:
- Dependencias con otros sistemas:
- Riesgos de arte, programación, multijugador y mantenimiento:
- Experimento mínimo FUTURO (requiere aprobación antes de ejecutarse):
- Pregunta al creador:
```

## Plantilla D: revisión legal/recursos

```markdown
# ASSET-XXX — [nombre]
- Uso propuesto:
- Fuente/autor/URL:
- Licencia exacta / fecha de consulta:
- Permitido modificar, distribuir, usar comercialmente:
- Obligaciones de atribución:
- Riesgo de parecido con tercero:
- Estado: PROTOTIPO | FINAL_PENDIENTE | FINAL_APROBADO | NO_USAR
- Verificado por:
```

## Plantilla E: resumen para el creador (máximo una página)

```markdown
# Resumen de investigación [área]
**Lo que ya sabemos:** [hasta 5 ideas con evidencia]
**Lo que NO sabemos:** [hasta 3 lagunas que sí afectan decisiones]
**Qué nos enseña de FATE/DOFUS:** [experiencia jugable, sin copiar]
**Alternativas:** [2–3 opciones con pros/contras]
**Costo/riesgo mayor:** [uno o dos]
**Pregunta de alto impacto para ti:** [una]
**¿Podemos seguir investigando sin tu respuesta?:** sí/no, con motivo
```

## Plantilla F: bitácora de cambios de documentos

```markdown
- Fecha:
- Archivo / versión anterior:
- Cambio:
- Motivo y evidencia:
- ¿Era una corrección factual o una nueva propuesta?:
- ¿Requiere aprobación creativa?:
- Aprobación disponible (si aplica):
- Autor del cambio:
```


---

<!-- Archivo: 11_FILOSOFIA_COMBATE_PREPARACION_Y_EJECUCION.md -->

# FrankmanGames — Filosofía del combate: preparación + ejecución

**Versión:** v0.3 | **Fecha:** 2026-10-25 | **Etapa:** preproducción conceptual, sin código.
**Estado de este documento:** dirección expresada + síntesis por validar. **NO contiene mecánicas implementables aprobadas.**

## 0. Declaración del creador — fuente de verdad

> «Quiero que el combate combine la profundidad de builds y hechizos con habilidad manual y ejecución. Desarrollemos esta visión para FrankmanGames sin aprobar todavía mecánicas concretas.»

**ESTADO:** `EXPRESADO_POR_AUTOR` para la dirección creativa general. La preferencia por un equilibrio no establece ponderación numérica 50/50, sistema de puntos, controles, recurso ni duración de combates.

**Formulación conceptual de trabajo [SÍNTESIS_POR_VALIDAR]:** «La preparación abre posibilidades. La ejecución convierte esas posibilidades en decisiones acertadas frente a una amenaza cambiante». No es un eslogan comercial aprobado, sino una brújula de investigación.

## 1. Qué significa la combinación, sin convertirla en un sistema

Llamamos **profundidad de construcción** a la cantidad y calidad de decisiones relevantes que el jugador realiza *antes* de combatir o entre encuentros: descubrir capacidades, entender sus interacciones, seleccionar herramientas y adaptarse a lo que espera encontrar. No equivale a coleccionar una cifra máxima de estadísticas ni necesariamente a disponer de clases.

Llamamos **dominio de ejecución** a la capacidad de convertir esas opciones en acciones oportunas *durante* el encuentro: percibir pistas, posicionarse, elegir, coordinarse, controlar la presión y responder a imprevistos. No equivale solamente a pulsar botones rápido o tener reflejos sobrehumanos.

**La profundidad surge de la interacción de ambas.** Una build no debería reducir toda pelea a una victoria automática (hipótesis de diseño); la buena ejecución tampoco tendría que hacer irrelevante cada decisión de preparación (hipótesis de diseño). Hasta probarlo, evitar afirmar que siempre deben contribuir por igual.

| Eje de experiencia | Señal de que funciona | Señal de alerta | Estado |
|---|---|---|---|
| Descubrimiento | Obtener/entender una capacidad revela una nueva manera de afrontar una amenaza | Solo aumenta el daño sin modificar decisiones | Criterio de estudio, no regla |
| Elección | Hay motivos razonables para variar repertorios según preferencias o circunstancias | Una build obligatoria domina todo | Criterio de estudio |
| Dominio de ejecución | Aprender el patrón de una amenaza cambia el resultado sin cambiar equipo | Todo depende de estadísticas o de pulsar más rápido | Criterio de estudio |
| Información | Puedo interpretar qué ocurrió y qué podría mejorar | Recibo daño inevitable o no comprendo la pelea | Criterio de estudio |
| Adaptación | La situación obliga a priorizar y reaccionar | Siempre repito la misma rotación | Criterio de estudio |
| Cooperación | Aliados pueden coordinar decisiones y acciones significativas | Solo se multiplica la vida de los enemigos | Criterio de estudio |
| Identidad | El combate conserva misterio y tensión sin volverse arbitrario | La respuesta óptima se memoriza para todo encuentro | Criterio de estudio |

## 2. Tres momentos del combate

### Antes: planificar sin convertirlo en trabajo administrativo

Experiencia deseada para examinar: la emoción de descubrir nuevas posibilidades y pensar «¿y si combino esto con aquello?». La preparación debería poder expresarse en decisiones comprensibles con consecuencias apreciables. **No deducir** cantidad de ranuras, restricciones de cambio, clases, progresión, UI, rarezas ni métodos de adquisición.

### Durante: actuar, leer y decidir

Experiencia deseada para examinar: tener libertad de movimiento y sentir que las respuestas propias importan. Que existan oportunidades de elegir *qué* hacer, *cuándo* hacerlo y *dónde* situarse, sin reproducir los turnos de DOFUS ni limitar la actividad a ataques básicos repetidos de FATE. **No deducir** dash, stamina, maná, bloqueo, parry, retícula, objetivo fijado, combo, cancelación de animaciones o velocidad concreta.

### Después: entender, aprender y sentir recompensa

Experiencia deseada para examinar: el jugador puede explicar por qué ganó o perdió, identificar una opción de su configuración que le ayudó, reconocer una habilidad que ejecutó bien y anticipar algo que quiere probar. Conectar esa evolución con misterio, exploración, botín y la identidad audiovisual. **No deducir** ranking, sistema de puntuación ni penalización de muerte.

## 3. La tensión correcta NO es “build vs reflejos” como competencia

Preguntas de diseño aún abiertas:

1. ¿Qué tipos de situaciones recompensan principalmente preparación, principalmente ejecución y ambas? ¿Debe variar por enemigo o modo de juego?
2. ¿Puede un jugador metódico con reflejos promedio mejorar y disfrutar? ¿Puede uno con ejecución sobresaliente progresar sin estudiar cientos de sinergias? ¿Qué límites razonables habría?
3. ¿Cómo evitar la rotación dominante o la repetición de ataques básicos sin imponer artificialmente largos tiempos de inactividad?
4. ¿Cómo generar tensión cuando el jugador descubre un monstruo enorme sin recurrir a daño injusto o enemigos imposibles de leer?
5. ¿Qué papel tiene el equipo: expandir estilos y decisiones, otorgar poder estadístico, o una combinación? Todavía no decidido.
6. ¿En cooperación, cómo podrían complementarse estilos sin obligar a clases preasignadas? Todavía no decidido.

No resolver estas preguntas con fórmulas inventadas. Traer referencias, ejemplos observables y pruebas conceptuales.

## 4. Escenas de evaluación (NO son promesas de contenido)

**Escena A — Descubrimiento del monstruo.** El personaje entra a una zona desconocida. Algo en el entorno y en la música anticipa una amenaza difícil. El jugador no sabe si está preparado. El desafío de diseño es distinguir incertidumbre emocionante de castigo inevitable. ¿La selección previa de herramientas cambia las decisiones disponibles? ¿Se puede aprender algo durante el encuentro?

**Escena B — Estrategia inteligente, ejecución imperfecta.** Alguien descubre una combinación ingeniosa, pero comete errores de posición y tiempo. Pregunta: ¿la preparación todavía le aporta ventajas significativas? ¿Los errores siguen teniendo consecuencias visibles?

**Escena C — Gran ejecución, configuración corriente.** Otra persona lee las señales del enemigo con enorme precisión, pero carece de ciertas interacciones entre habilidades. Pregunta: ¿hay margen para la habilidad personal sin que vuelva inútil la preparación?

**Escena D — Dos aliados, repertorios diferentes.** En una pelea separada del mundo compartido, dos jugadores actúan juntos. Pregunta: ¿su coordinación crea posibilidades que no surgen de sumar daño, sin imponerles roles cerrados? La infraestructura de instancia aún no se diseña.

**Escena E — Descubrimiento y pausa.** Una aventura profunda combina tensión, exploración y una actividad tranquila que sorprende con una recompensa memorable (referencia emocional: la pesca en FATE). Pregunta: ¿cómo se relaciona la motivación por descubrir habilidades/objetos con el combate sin hacer que toda actividad sea solo aumentar daño?

Cada escena sirve para una entrevista al creador o un guion de test; no autoriza desarrollar personajes, enemigos, habilidades, UI, biomas, pesca ni sistemas de red.

## 5. Criterios de prueba de una propuesta futura

Antes de sugerir una mecánica concreta, el agente debe responder:

- ¿Qué experiencia explícita del creador intenta servir?
- ¿Qué decisión nueva agrega antes, durante o después de un combate?
- ¿Qué perderíamos respecto a FATE, DOFUS Retro, DOFUS 3 o Temporis IV?
- ¿Qué jugador podría quedar excluido por exigencia cognitiva o de reflejos?
- ¿Cómo se podría reconocer que la solución produjo el efecto deseado?
- ¿Qué efectos tendría sobre enemigos, arte, animaciones, UI, botín, progresión, red y cooperación?
- ¿Qué evidencia la respalda y qué parte es hipótesis?

**Antiobjetivos a vigilar [PROPUESTAS_POR_VALIDAR]:** una sola build universal, decisiones automatizadas por equipo, spam permanente sin elecciones, telegráficos ilegibles, excesiva sobrecarga visual, tiempos muertos que simulen turnos sin propósito, dificultad basada exclusivamente en inflar estadísticas.

## 6. Investigación por referente (no copiar implementación)

| Referente | Pregunta prioritaria | Evidencia requerida | Lo que NO se debe afirmar sin prueba |
|---|---|---|---|
| FATE: Undiscovered Realms | ¿Cómo crean sus datos y enemigos la tensión, progresión y diferencia entre ataques y hechizos? | Datos locales + observación directa + hallazgos dirigidos de Ghidra cuando haga falta | Que ya conocemos sus fórmulas internas por tener `.dat` o referencias al cargador |
| DOFUS Retro | ¿Qué decisiones crean PA/PM, alcance, posición, selección de hechizos y acciones de arma? | Comportamiento observable, código cliente, separar reglas del servidor | Que las fórmulas de servidor estén en el SWF |
| DOFUS 3 | ¿Qué presenta la interfaz para hacer legible complejidad, oportunidades, restricciones y combate en grupo? | Observación del juego, metadatos y métodos identificables; límites explícitos | Que firmas de Cpp2IL equivalgan a implementar reglas de combate |
| Temporis IV | ¿Qué hacía estimulante obtener y combinar hechizos ajenos a una sola clase? | Material histórico con edición/fecha + relatos de experiencia | Que nuestro juego necesite exactamente 10 ranuras, mismos hechizos o mismo sistema |

**Salidas solicitadas:** por cada referente, una ficha sobre *decisiones previas*, otra de *decisiones durante la pelea* y otra de *recompensa/aprendizaje*, con evidencia y grado de confianza. Se pueden consolidar fichas si el material existente ya las cubre.

## 7. Preguntas cuya respuesta pertenece al creador, NO al agente

1. Ante una victoria emocionante, ¿qué te gustaría contarle a un amigo: «inventé esta combinación», «esquivé aquello por muy poco», o «mi combinación me permitió lograr esa maniobra»? Puede haber varias respuestas según el encuentro.
2. ¿Quieres que un jugador menos hábil manualmente, pero muy creativo con builds, pueda completar la aventura principal? No hablamos todavía de números ni modos de dificultad.
3. ¿Qué diferencia percibida quieres entre combatir en solitario y combatir acompañado? No hablamos todavía de tamaño de grupo.

**No bloquear la investigación por estas preguntas:** generar material comparativo y elevar preguntas solo cuando tengan consecuencias de diseño realmente distintas.

## 8. Estado de gobernanza al cerrar v0.3

- `V-018 [EXPRESADO]`: combinar profundidad de builds/hechizos con habilidad manual y ejecución.
- `V-019 [EXPRESADO]`: desarrollar la visión sin aprobar mecánicas concretas.
- **No hay nueva decisión mecánica** sobre recursos, habilidades, animación, cámara, clases, armas, habilidades defensivas, IA, red o tecnología.
- El siguiente paso autorizado es **investigación y discusión documentadas**, no programación del RPG.


---

<!-- Archivo: 12_PROMPT_ALINEACION_AGENTES_COMBATE.md -->

# FrankmanGames — Instrucción de alineación sobre filosofía del combate v0.3

**Objetivo:** alinear los análisis de FATE, DOFUS Retro, DOFUS 3 y Temporis IV con el deseo expreso del creador: **profundidad de builds y hechizos + habilidad manual y ejecución**, SIN APROBAR mecánicas concretas y SIN PROGRAMAR.

## Texto para copiar al agente coordinador

> Lee primero `00_INICIO_Y_MAPA.md`, `08_REGISTRO_DECISIONES.md`, `11_FILOSOFIA_COMBATE_PREPARACION_Y_EJECUCION.md`, luego `01_BIBLIA_MAESTRA_VISION.md`, `02_CONSTITUCION_AGENTES.md` y `04_COMBATE_Y_HECHIZOS.md`. Trata `11` como la actualización conceptual más reciente; trata cualquier elección concreta previa como propuesta, no como regla.
>
> **Dirección expresada por el creador:** el combate debe combinar profundidad estratégica de repertorio y builds con habilidad de ejecución activa. NO implica balance cuantitativo 50/50 ni valida 10 hechizos, clases libres, maná, cooldowns, dash, parry, stamina, cámara, tiempo de combate, PvP o arquitectura. No iniciar código del videojuego.
>
> Asigna investigación sin repetir decompilaciones costosas: agente FATE analiza diferencia entre ataques/hechizos, progresión y encuentros; agente Retro identifica decisiones tácticas del presupuesto PA/PM, armas, distancia y posición; agente DOFUS 3 observa presentación, legibilidad y grupos, distinguiendo cliente/servidor; agente Temporis IV describe libertad de repertorios, obtención y experimentación con fuentes históricas. Revisor independiente comprueba que la salida no convierta inspiración en copia ni propuesta en mandato.
>
> Crea una **MATRIZ DE DECISIONES** con columnas: `referente`, `preparación`, `ejecución`, `interacción de ambas`, `sensación del jugador`, `fuente y método`, `grado de certeza`, `oportunidad para FrankmanGames`, `riesgo`, `estado NO APROBADO`. Compara funciones jugables, no nombres de hechizos/código propietario.
>
> Analiza tres perfiles hipotéticos: (A) buena preparación + ejecución imperfecta; (B) gran ejecución + preparación corriente; (C) buena preparación + gran ejecución. Describe qué preguntas de diseño surgen, **sin decidir resultados obligatorios**.
>
> Produce: (1) un resumen ejecutivo de una página, (2) matriz sustentada, (3) de tres a cinco hipótesis con pros/contras y criterios observables, (4) dependencias con arte, animación, accesibilidad, IA, botín y cooperación, (5) máximo tres preguntas realmente decisivas para el autor. Escribe `DESCONOCIDO` cuando no haya evidencia.
>
> Conserva las fuentes originales y los hashes cuando existan; no redistribuyas ejecutables, recursos ni código descompilado. No uses protocolos reconstruidos para conectar a servidores de terceros. No descargues ni ejecutes herramientas adicionales ni hagas operaciones intensivas sin una autorización específica.
>
> Actualiza documentación de investigación/propuestas, no `APROBADO_POR_AUTOR`. Al finalizar, entrega un resumen de diferencias y señala qué conclusiones anteriores fueron corregidas por la nueva visión.

## Criterio de aceptación de la entrega

- La dirección creativa del usuario aparece citada literalmente.
- Cada referente se analiza en preparación, ejecución y su interacción.
- La evidencia de observación se separa de inferencias de cliente y servidor.
- Hay opciones abiertas, consecuencias y lagunas, no una hoja de ruta tecnológica dictada por los agentes.
- No se presentó ninguna mecánica como aprobada ni se creó código nuevo del juego.
