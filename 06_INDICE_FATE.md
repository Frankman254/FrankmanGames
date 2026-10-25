# Índice de investigación FATE

**Corte auditado:** 2026-10-25  
**Edición inspeccionada:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345, x86  
**SHA-256 del ejecutable:** `d59a1540038c9ef31c695e202ab42fb54051f30cc414c23aacbeafbd16a6de5d`

Este índice convierte el inventario técnico de FATE en fichas de mecánicas comparables. No decide qué se implementará en FrankmanGames y no contiene código extraído para reutilizar.

## Fichas disponibles

| ID | Tema | Estado principal | Confianza | Resultado útil |
|---|---|---|---|---|
| `FATE-ARCH-001` | Carga de bases de datos | OBSERVADO | ALTA | Un único orquestador crea los cargadores de partículas, misiones, plantillas, monstruos, objetos y hechizos. |
| `FATE-COMBAT-001` | Interacción y modelo base de combate | OBSERVADO + INFERIDO | ALTA/MEDIA | Controles, estadísticas, parámetros y circuito ejecutable ya están conectados. |
| `FATE-COMBAT-002` | Circuito ejecutable de impacto y daño | OBSERVADO + INFERIDO | ALTA para orden/curvas; MEDIA para offsets | Se recuperaron ejecutor, resolución, límites 5/95%, curvas de crítico/bloqueo, mitigación y aplicación a vida. |
| `FATE-ITEMS-001` | Objetos, loot y economía | OBSERVADO | ALTA para el esquema; BAJA para precios finales | El objeto combina profundidad, rareza, valor, requisitos, efectos, sockets y disponibilidad de mercader. |
| `FATE-AI-001` | Parámetros de enemigos | OBSERVADO + INFERIDO | MEDIA | Los monstruos declaran percepción, persecución, valentía, ataques, hechizos, minions y una táctica opcional. |
| `FATE-DUNGEON-001` | Generación procedural | OBSERVADO + INFERIDO | ALTA para datos; MEDIA para algoritmo | Nueve biomas parametrizan topología, geometría, ambientación y colocación de props. |
| `FATE-SAVE-001` | Guardado y persistencia | OBSERVADO + INFERIDO | ALTA para rutas; MEDIA para serialización | Se verificaron raíz Cache/Persistent, cuatro consumidores de `/SAVE/` y contenido de mundo activo en `.FFD`. |

Las fichas están en `fichas/FATE/`.

## Evidencia primaria

- Instalación de referencia: `C:\Program Files (x86)\WildGames\FATE`
- Investigación separada: `C:\Users\frank\Desktop\2026\FATE-ReverseEngineering`
- Proyecto persistente: `FATE-ReverseEngineering\ghidra-project\FATE.gpr`
- Xrefs de datos y guardado: `FATE-ReverseEngineering\evidence\ghidra\FATE-DATA-SAVE-XREFS.md`
- Xrefs de subsistemas: `FATE-ReverseEngineering\evidence\ghidra\FATE-SUBSYSTEM-XREFS.md`
- Estructura/vtable de actor: `FATE-ReverseEngineering\evidence\ghidra\FATE-COMBAT-STRUCTURE.md` y `FATE-COMBAT-VTABLE.md`
- Núcleo y resolución de combate: `FATE-ReverseEngineering\evidence\ghidra\FATE-COMBAT-CORE.md` y `FATE-COMBAT-RESOLUTION.md`
- Constantes y auxiliares de fórmula: `FATE-ReverseEngineering\evidence\ghidra\FATE-COMBAT-FORMULA.md`
- Línea base REA: `FATE-ReverseEngineering\REA-BASELINE.md`
- Inventario reproducible: `FATE-ReverseEngineering\tools\fate_inventory.py`

## Hallazgos que ya cambiaron de REPORTADO a OBSERVADO

- `FUN_00457aa0` referencia directamente `quests.dat`, `TEMPLATES\manifest.dat`, `monsters.dat`, `items.dat` y `spells.dat`.
- `FUN_00562a90` selecciona `\Cache` para tipo 0 y `\Persistent` para tipo 1.
- Las funciones `FUN_0051a0b0`, `FUN_0051f6a0`, `FUN_00515240` y `FUN_00524440` construyen rutas bajo `/SAVE/`.
- La base de datos contiene 717 objetos, 138 monstruos y 53 hechizos.
- El archivo de guardado inspeccionado contiene estado del jugador, mascota, inventario, misión y entidades del nivel activo.
- `FUN_005480b0` conduce a `FUN_00546e60`, la ruta que ordena impacto, crítico, daño, mitigación, bloqueo y aplicación de vida.
- El fallo se limita a 5–95%; crítico y bloqueo usan curvas saturantes con techo 50%. El crítico duplica daño y el bloqueo lo anula.

## Orden recomendado de investigación, no de implementación

1. Cerrar el tipado de offsets del circuito de combate y separar armadura física de resistencias elementales; el orden y las curvas principales ya están recuperados.
2. Seguir desde los cargadores concretos de objetos hasta selección de loot, afijos y precio final.
3. Recuperar la máquina de estados/navegación de enemigos a partir del despachador `FUN_0053c260` y sus overrides.
4. Aislar el generador topológico detrás del cargador de plantillas y validar el efecto de una semilla mediante observación controlada.
5. Hacer guardados diferenciales sobre copias: una sola variable cambiada por muestra.
6. Registrar observación de juego legítima para conectar datos internos con lo que ve y decide el jugador.

## Límites

- Una etiqueta de datos demuestra que el motor acepta un parámetro; no demuestra por sí sola su fórmula.
- El pseudocódigo de Ghidra no recupera nombres ni tipos originales y puede contener artefactos.
- No se han aprobado mecánicas, motor, arquitectura ni fórmulas para el RPG propio.
