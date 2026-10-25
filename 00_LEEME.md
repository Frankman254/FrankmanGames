# RPG propio — Paquete de contexto para investigación y diseño
**Versión:** 0.1 · **Fecha:** 2026-10-25 · **Estado:** investigación, sin decisiones arquitectónicas cerradas.

> Principio rector: **investigar no es adoptar; proponer no es decidir**. La visión creativa pertenece al creador del proyecto. Ningún agente puede aprobar mecánicas, reglas, arquitectura o motor en su nombre.

## Propósito
Alinear los trabajos de investigación sobre **FATE: Undiscovered Realms**, **DOFUS Retro** y **DOFUS 3** para extraer conocimiento útil sobre sistemas de juego y construir eventualmente un RPG **original**, no una reproducción de los binarios, activos, personajes, mundo, protocolo de producción o marcas de los referentes.

## Qué hay en este paquete
- `01_EVIDENCIA_Y_LAGUNAS.md` — estado de los análisis compartidos, con separación de evidencias y pendientes.
- `02_MATRIZ_COMPARATIVA.md` — matriz para registrar mecánicas sin suponer cómo se combinarán.
- `03_PROMPTS_DE_AGENTES.md` — instrucciones listas para proporcionar al coordinador y a los agentes de cada referente.
- `04_VISION_Y_DECISIONES.md` — orientación provisional, preguntas creativas y registro de decisiones solo aprobadas por el autor.
- `05_PLANTILLA_FICHA_MECANICA.md` — ficha estándar de investigación de cada sistema.
- `06_INDICE_FATE.md` — corte auditado de FATE, índice de fichas y próximos experimentos.
- `fichas/FATE/` — seis fichas con evidencia de carga de datos, combate, objetos, IA, mazmorras y persistencia.

## Alcance y límites de los insumos
El corte original del paquete se elaboró a partir de resúmenes. Desde el 2026-10-25, la sección FATE sí fue contrastada directamente con la instalación, sus `.dat`, la tabla de recursos de idioma, la partida local y los informes del proyecto persistente de Ghidra. Las salidas Cpp2IL y FFDec de DOFUS todavía deben auditarse localmente antes de promover sus afirmaciones de `REPORTADO` a `OBSERVADO`.

No convertir un número de scripts, firmas, enums o prefijos de red en una afirmación de que ya se conoce la regla del combate, la progresión u otra mecánica.

## Fuente de verdad / flujo
1. **Fuente del juego / evidencia**: archivo, script, pseudocódigo, dato, prueba reproducible o captura de comportamiento.
2. **Ficha de investigación**: describe lo observado y sus incertidumbres.
3. **Comparación entre referentes**: coincide, difiere, depende de otras mecánicas.
4. **Propuesta de diseño**: un agente plantea opciones, separadas de los hechos.
5. **Decisión creativa**: únicamente el autor decide y registra su aprobación.
6. **Prototipo original**: se desarrolla solo después de definir una hipótesis acotada y criterios de validación.

## Ubicaciones reportadas por el usuario (rutas, no acceso verificado)
- Herramientas compartidas: `C:\Users\frank\Desktop\2026\REA-Toolchain`
- Investigación de FATE: `C:\Users\frank\Desktop\2026\FATE-ReverseEngineering`
- Instalación de DOFUS 3: `C:\Users\frank\AppData\Local\Ankama\Dofus-dofus3`
- Instalación de Retro: `C:\Users\frank\AppData\Local\Ankama\Retro`

Los nombres exactos de carpetas de resultados DOFUS (`out/dofus3`, `out/retro`) están reportados, pero su raíz absoluta debe confirmarse localmente.

## Lo siguiente, por orden
1. Recopilar `README.md`, `REPORT.md` y los índices existentes de **cada** investigación (no hace falta compartir los binarios).
2. Pedir a los tres agentes 3–5 fichas de mecánica prioritarias, con referencias verificables y sin implementación todavía.
3. Revisar las fichas en conjunto, detectar contradicciones y preparar opciones explícitas para que el autor las evalúe.
4. Identificar un prototipo vertical mínimo *después* de que el autor determine qué experiencia desea.

## Reglas de cooperación
- Los análisis de juegos de terceros permanecen separados de la implementación del juego original.
- No importar código, modelos, texturas, música, interfaces o nomenclatura propietaria al repositorio del nuevo RPG.
- No usar hallazgos de autenticación, tokens o mensajería para acceder a servicios reales.
- No cambiar los juegos instalados ni alterar partidas de referencia en las tareas de investigación sin una solicitud específica del usuario.
- Toda afirmación técnica debe conservar su procedencia; «no sabemos» es un resultado válido.
