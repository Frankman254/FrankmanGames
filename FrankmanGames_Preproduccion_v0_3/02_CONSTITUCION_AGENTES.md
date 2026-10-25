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
