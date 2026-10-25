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
