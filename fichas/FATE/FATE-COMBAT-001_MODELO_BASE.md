# FATE-COMBAT-001 — Interacción y modelo base de combate

**Juego / edición / versión:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345  
**Sistema y subtema:** control, ataque, atributos y efectos  
**Agente / fecha:** Codex / 2026-10-25  
**Estado de evidencia:** `OBSERVADO` para entradas, campos y circuito ejecutable; `INFERIDO` para el nombre de offsets sin símbolos  
**Confianza:** `ALTA` para el orden y las curvas; `MEDIA` para el tipado semántico de algunos campos.

## Pregunta específica

¿Qué decisiones y variables forman un ataque en tiempo real y qué parte de la fórmula puede afirmarse desde la copia inspeccionada?

## Observaciones verificables

| Observación | Ruta de evidencia | Símbolo/línea/offset | Estado | Cómo verificar |
|---|---|---|---|---|
| Clic izquierdo mueve, ataca e interactúa; clic derecho lanza hechizos; `Shift` permite atacar sin moverse. | `LANG/en-US.dll` | recurso `RT_STRING` ID 890 | OBSERVADO | Extraer tabla con `fate_inventory.py::summarize_string_table`. |
| Fuerza afecta daño; Destreza afecta acertar y esquivar; Vitalidad determina vida y stamina; Magia determina maná y aumenta daño de hechizos. | `LANG/en-US.dll` | IDs 926–929 | OBSERVADO | Misma extracción. |
| La UI separa rango de daño, attack rating y defense/dodge. | `LANG/en-US.dll` | IDs 919–935 | OBSERVADO | Misma extracción. |
| La mejora de habilidad de arma añade 1 a daño y 1 a ataque; hay progresión de crítico, bloqueo, velocidad de lanzamiento y daño de ambas manos. | `LANG/en-US.dll` | IDs 977–981 | OBSERVADO | Misma extracción. |
| Un arma declara daño, radios de ataque/impacto y categoría de velocidad. | `ITEMS/items.dat` | Light Handaxe, líneas 5161–5183; daño `3:6`, radios `5/7`, `Fast` | OBSERVADO | Leer el registro. |
| Un monstruo declara `TOHIT`, armadura, daño, tipo de daño y resistencias. | `MONSTERS/monsters.dat` | Topaz Gel, líneas 5–50 | OBSERVADO | Leer el registro. |
| Los hechizos declaran objetivo, tiempo de lanzamiento, maná, rangos, bonus por habilidad, tipo elemental y efectos temporales. | `SPELLS/spells.dat` | Slow, líneas 7–49; Fireball, 51–83; Frost, 85–137 | OBSERVADO | Leer los registros. |
| La ejecución del ataque converge en una rutina que resuelve impacto, crítico, daño, mitigación, bloqueo y aplicación a vida. | `FATE-COMBAT-RESOLUTION.md` | `FUN_005480b0` → `FUN_00546e60` | OBSERVADO | Revisar ambas decompilaciones. |
| La probabilidad de fallo usa `defensa/(defensa+ataque)` y queda limitada a 5–95%. | `FATE-COMBAT-FORMULA.md` | `FUN_00530600`, `FUN_0052e9f0`, `FUN_005312a0`; constantes 5/95/100 | OBSERVADO | Reconstruir la expresión en `FUN_00546e60`. |
| Crítico y bloqueo usan curvas saturantes con techo 50%; el crítico duplica daño y el bloqueo lo pone en cero. | `FATE-COMBAT-FORMULA.md` | `FUN_00546e60`, `FUN_005300f0`; constantes 50 y 0.03 | OBSERVADO | Revisar ramas y constantes globales. |

## Regla inferida / modelo mental

```text
entrada del jugador
  -> mover hacia el objetivo o mantener posición con Shift
  -> comprobar alcance y tiempo/velocidad de ataque
  -> resolver impacto con fallo = clamp(100*defensa/(defensa+ataque), 5, 95)
  -> si impacta, obtener rango de daño
  -> sumar atributo/habilidad; crítico duplica el daño base
  -> aplicar porcentaje/tipo de mitigación y mínimo previo de 1
  -> permitir que bloqueo anule el daño mitigado
  -> limitar a la vida restante y aplicar el delta
  -> disparar efectos, sonido, partículas y feedback de UI
```

El orden y las curvas proceden del pseudocódigo recuperado. La traducción de ciertos offsets a nombres de diseño sigue siendo inferida. Véase `FATE-COMBAT-002_CIRCUITO_EJECUTABLE.md`.

## Qué ve y hace el jugador

- Decide entre reposicionarse automáticamente o atacar quieto con `Shift`.
- Escoge arma/hechizo por alcance, velocidad, coste, tipo de daño y efectos.
- Recibe feedback de impacto, fallo, crítico, bloqueo, daño y estados.
- Los atributos conectan progreso del personaje con precisión, supervivencia y potencia.

## Incertidumbres

- Nombre y tipo originales de varios offsets de puntuación/porcentaje.
- Separación exacta entre armadura física y resistencias elementales dentro del selector por tipo.
- Cómo se traducen `Fast/NORMAL/...` a tiempo en segundos.
- Redondeo x87 exacto en todas las fronteras de bonus planos y porcentuales.
- Cooldown real, cancelación, hit frames y relación con eventos de animación.

## Opciones de inspiración sin aprobación automática

- A: combate de clic con persecución automática y modificador para mantener posición.
- B: control directo con habilidades que conservan el mismo modelo de atributos.
- C: acción legible con pocas estadísticas visibles y fórmulas publicadas al jugador.

## Pregunta breve para el autor

¿Qué te gusta más del combate de FATE: la inmediatez del clic, perseguir automáticamente, el loot que cambia números o combinar hechizos y estados?
