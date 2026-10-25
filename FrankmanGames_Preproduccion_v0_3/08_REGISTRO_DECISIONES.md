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
