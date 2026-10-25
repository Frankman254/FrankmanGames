# FATE-SAVE-001 — Guardado y persistencia del mundo activo

**Juego / edición / versión:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345  
**Sistema y subtema:** rutas, enumeración y serialización `.FFD`  
**Agente / fecha:** Codex / 2026-10-25  
**Estado de evidencia:** `OBSERVADO` para rutas/contenido; `INFERIDO` para estructura  
**Confianza:** `ALTA` para ubicación y consumidores, `MEDIA` para campos binarios.

## Pregunta específica

¿Qué persiste FATE y cómo separa caché, configuración y partidas?

## Observaciones verificables

| Observación | Ruta de evidencia | Símbolo/offset | Estado | Cómo verificar |
|---|---|---|---|---|
| `CSaveFile::GetRootPath` acepta dos tipos: 0 añade `\\Cache`; 1 añade `\\Persistent`; otros lanzan excepción. | `FATE-DATA-SAVE-XREFS.md` | `FUN_00562a90`, línea 75262 | OBSERVADO | Abrir Ghidra en `0x00562a90`. |
| La cadena `/SAVE/` tiene cuatro consumidores directos. | mismo informe | `FUN_0051a0b0`, `FUN_0051f6a0`, `FUN_00515240`, `FUN_00524440` | OBSERVADO | Xrefs desde `0x0097f42c`. |
| `FUN_0051f6a0` enumera archivos con `FindFirstFileA/FindNextFileA` y comprueba una extensión de tres caracteres. | mismo informe | función en línea 74814 | OBSERVADO | Revisar pseudocódigo. |
| `FUN_0051a0b0` abre archivos y lee campos binarios, doce cadenas con longitud de 16 bits, otros bytes y objetos de tamaño `0x480`. | mismo informe | función en línea 74591 | OBSERVADO; significado INFERIDO | Revisar `_fread` y constructores. |
| Dos rutas de acción construyen un archivo bajo `/SAVE/` y llaman rutinas distintas (`FUN_00514e20`, `FUN_00524020`). | mismo informe | funciones en líneas 75004 y 75134 | OBSERVADO | Seguir llamadas. |
| La partida activa está en `Persistent\\SAVE\\es\\0.FFD`, mide 76,069 bytes y su SHA-256 es `09e40b7f...50332d`. | archivo local inspeccionado | metadata 2026-10-25 | OBSERVADO | `Get-FileHash` sobre la partida original. |
| Sus 746 secuencias ASCII incluyen jugador, mascota, inventario, misión principal, recompensa y múltiples entidades del nivel. | copia leída en modo estático | strings del `.FFD` | OBSERVADO | Ejecutar `summarize_save` sin modificar el archivo. |

## Modelo mental

```text
Special Folder de Windows
  ├─ Cache        -> derivados regenerables (p. ej. DDS)
  └─ Persistent
      ├─ config.dat
      └─ SAVE/<locale>/<slot>.FFD
          -> cabecera/metadata
          -> jugador y mascota
          -> inventarios/objetos
          -> quests y progreso
          -> estado del nivel y entidades activas
```

La segmentación interna exacta del `.FFD` aún no está identificada.

## Qué ve y hace el jugador

- El menú permite guardar/continuar/eliminar partidas.
- Volver a una partida restaura más que la hoja del personaje: también parte del mundo activo.
- El locale aparece como parte de la ruta física del slot.

## Incertidumbres

- Versionado, checksum y compatibilidad entre builds/locales.
- Qué datos se guardan por valor frente a referencias a prototipos.
- Atomicidad, archivo temporal y recuperación ante escritura interrumpida.
- Diferencia exacta entre las dos rutinas que consumen `/SAVE/`.

## Próximo experimento seguro

1. Copiar la partida a un directorio de evidencia.
2. Registrar hash y tamaño.
3. Cambiar una sola variable legítima en juego: oro, posición, un objeto o quest.
4. Guardar en otro slot o copiar inmediatamente el nuevo archivo.
5. Comparar offsets y repetir para confirmar; nunca experimentar sobre la única copia.

## Opciones de inspiración sin aprobación automática

- A: guardar mundo activo completo para continuidad fuerte.
- B: guardar solo estado canónico y regenerar niveles desde semilla.
- C: snapshots rotativos con migraciones de versión y recuperación automática.

## Pregunta breve para el autor

¿Quieres que una partida recuerde exactamente el estado del nivel o que cada regreso regenere parte del mundo para mantener la sorpresa?
