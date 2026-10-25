# FATE-DUNGEON-001 — Plantillas de generación procedural

**Juego / edición / versión:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345  
**Sistema y subtema:** topología, biomas y colocación ambiental  
**Agente / fecha:** Codex / 2026-10-25  
**Estado de evidencia:** `OBSERVADO` para parámetros; `INFERIDO` para el algoritmo  
**Confianza:** `ALTA` para el contrato de datos, `MEDIA` para su ejecución.

## Pregunta específica

¿Cómo separa FATE la forma de una mazmorra de su apariencia y sus objetos ambientales?

## Observaciones verificables

| Observación | Ruta de evidencia | Línea/campo | Estado | Cómo verificar |
|---|---|---|---|---|
| El manifest habilita nueve plantillas: cellar, sewers, mines, caves, seacellar, mines2, volcano, wood y ruins. | `TEMPLATES/manifest.dat` | líneas 4–12 | OBSERVADO | Leer archivo. |
| `FUN_00457aa0` entrega el manifest al constructor `FUN_00497120`. | `FATE-DATA-SAVE-XREFS.md` | función en línea 73744; xref `0x457edf` | OBSERVADO | Abrir Ghidra en `0x00457aa0`. |
| Cada plantilla controla ancho/alto, tamaño y número de habitaciones, pits, twistiness, connectedness y sparseness. | `TEMPLATES/*.dat` | encabezados de cada archivo | OBSERVADO | Comparar las nueve plantillas. |
| Todas usan mapas de 24–48 por 24–48; cambian habitaciones, pits y forma. | mismos archivos | parámetros numéricos | OBSERVADO | Ejecutar matriz de extracción. |
| Wood fija 0 pits y connectedness 1000; Ruins permite 7–14 habitaciones y twistiness 10–300; Sewers permite 4–12 pits. | `wood.dat`, `ruins.dat`, `sewers.dat` | encabezados | OBSERVADO | Leer archivos. |
| Las secciones `GROUND`, `WALL` y `PROP` conectan topología con texturas, modelos, colisión, luces, sonidos y reglas de ubicación. | `TEMPLATES/cellar.dat` | líneas 52 en adelante | OBSERVADO | Revisar secciones. |
| La cadena `DUNGEONSEED` existe en `0x00974de4`, pero el barrido produjo muchas referencias y aún no aisló la lectura canónica. | `FATE-DATA-SAVE-XREFS.md` | sección inicial | OBSERVADO + pendiente | Filtrar referencias de código reales y seguir llamadas. |

## Matriz resumida

| Plantilla | Habitaciones | Pits | Twistiness | Connectedness | Sparseness | Oscuridad |
|---|---:|---:|---:|---:|---:|---:|
| cellar | 4–12 | 0–6 | 500–800 | 900–1000 | 5–40 | — |
| sewers | 6–12 | 4–12 | 400–700 | 500–1000 | 1–10 | 5–15 |
| mines | 6–12 | 0–6 | 300–600 | 900–1000 | 5–40 | — |
| caves | 6–12 | 2–8 | 500–1000 | 700–1000 | 1–40 | 5–11 |
| seacellar | 4–12 | 2–7 | 600–900 | 600–1000 | 7–50 | — |
| mines2 | 6–12 | 0–5 | 200–500 | 900–1000 | 4–40 | 7–11 |
| volcano | 6–12 | 3–10 | 500–1000 | 700–1000 | 1–40 | 5–11 |
| wood | 6–12 | 0 | 200–300 | 1000 | 2–20 | — |
| ruins | 7–14 | 0–6 | 10–300 | 900–1000 | 6–30 | — |

## Regla inferida / modelo mental

```text
semilla + plantilla
  -> escoger dimensiones y parámetros topológicos dentro de rangos
  -> construir habitaciones/corredores/pits y conexiones
  -> asignar capas de suelo y piezas de pared compatibles
  -> colocar escaleras, puertas y props según LOCATION/buffers/rareza
  -> añadir colisión, luces, agua y audio ambiental
  -> poblar con monstruos, contenedores, quests y loot por profundidad
```

La última etapa de población todavía no está conectada en el call graph.

## Qué ve y hace el jugador

- Explora diseños variables con identidad visual y acústica por bioma.
- Lee riesgos por pits, oscuridad, agua, obstáculos y densidad.
- Encuentra rutas y props condicionados por habitaciones, pasillos, paredes y escaleras.

## Incertidumbres

- Algoritmo exacto de conectividad y significado de las escalas 0–1000.
- Uso y persistencia de la semilla.
- Reglas para poblar enemigos, cofres, quest targets y escaleras.
- Cómo se evita una planta imposible o inaccesible.

## Opciones de inspiración sin aprobación automática

- A: topología procedural y arte modular como FATE.
- B: macroestructura diseñada a mano con salas procedurales.
- C: semillas compartibles y modificadores visibles al jugador.

## Pregunta breve para el autor

¿Te interesa más la sensación de descenso infinito y sorpresa o prefieres niveles con momentos diseñados y variación controlada?
