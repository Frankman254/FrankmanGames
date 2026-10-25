# FATE-ARCH-001 — Orquestación de datos de juego

**Juego / edición / versión:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345  
**Sistema y subtema:** arranque de contenido / cargadores de prototipos  
**Agente / fecha:** Codex / 2026-10-25  
**Estado de evidencia:** `OBSERVADO`  
**Confianza:** `ALTA`; una misma función contiene las rutas y llamadas de construcción.

## Pregunta específica

¿Cómo organiza FATE la carga inicial de contenido editable y qué subsistemas nacen de cada archivo?

## Observaciones verificables

| Observación | Ruta de evidencia | Símbolo/línea/offset | Estado | Cómo verificar |
|---|---|---|---|---|
| Una sola función referencia las cinco bases principales. | `FATE-ReverseEngineering/evidence/ghidra/FATE-DATA-SAVE-XREFS.md` | `FUN_00457aa0` en línea 73744; xrefs `0x457dc6`, `0x457edf`, `0x45803d`, `0x458265`, `0x458481` | OBSERVADO | Abrir el proyecto Ghidra y navegar a `0x00457aa0`. |
| Misiones se construyen desde `QUESTS\\quests.dat`. | mismo informe | llamada a `FUN_004872e0`; resultado almacenado en el objeto coordinador a `+0x64c` | OBSERVADO | Revisar pseudocódigo de `FUN_00457aa0`. |
| Plantillas se construyen desde `TEMPLATES\\manifest.dat`. | mismo informe | llamada a `FUN_00497120`; almacenamiento a `+0x648` | OBSERVADO | Igual. |
| Monstruos se construyen desde `MONSTERS\\monsters.dat`. | mismo informe | llamada a `FUN_005567d0`; almacenamiento a `+0x650` | OBSERVADO | Igual. |
| Objetos se construyen desde `ITEMS\\items.dat`. | mismo informe | llamada a `FUN_004bdca0`; almacenamiento a `+0x654` | OBSERVADO | Igual. |
| Hechizos se construyen desde `SPELLS\\spells.dat`. | mismo informe | llamada a `FUN_004c3140`; almacenamiento a `+0x658` | OBSERVADO | Igual. |
| Partículas y brillos se cargan antes que los prototipos jugables. | mismo informe | `PARTICLES\\particles.dat` → `FUN_0042fda0`; `PARTICLES\\glows.dat` → `FUN_00433280` | OBSERVADO | Igual. |

## Modelo mental

```text
FUN_00457aa0 (orquestador)
├─ partículas y glows
├─ nombres
├─ misiones
├─ manifest de plantillas
├─ monstruos ── depende de partículas
├─ objetos
└─ hechizos ─── depende de partículas y otros gestores
```

La interpretación más sólida es que el ejecutable construye gestores de prototipos y conserva sus punteros en un objeto coordinador. No se conoce todavía el nombre original de esa clase.

## Qué ve y hace el jugador

- Los registros externos determinan nombres, estadísticas, recursos, efectos y disponibilidad por profundidad.
- Cambiar un prototipo puede alterar muchas instancias creadas después, pero no se ha probado qué ocurre con instancias ya serializadas en un `.FFD`.
- La localización mantiene copias de varias bases; debe verificarse qué archivo prevalece para el idioma activo.

## Incertidumbres

- Orden exacto de overrides entre base y locale.
- Validación de errores, duplicados y campos desconocidos.
- Si todas las instancias conservan vínculo al prototipo o copian sus valores al crearse.

## Opciones de inspiración sin aprobación automática

- A: datos externos editables en desarrollo y producción.
- B: datos declarativos validados por esquema y compilados al empaquetar.
- C: núcleo estable con paquetes de contenido/mods versionados.

## Pregunta breve para el autor

¿Te atrae de FATE poder modificar el contenido directamente, o prefieres que el juego propio ofrezca herramientas visuales con validación?
