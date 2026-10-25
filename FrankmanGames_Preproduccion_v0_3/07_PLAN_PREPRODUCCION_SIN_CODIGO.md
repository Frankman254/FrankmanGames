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
