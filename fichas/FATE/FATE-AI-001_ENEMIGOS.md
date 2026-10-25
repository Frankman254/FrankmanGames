# FATE-AI-001 — Parámetros y roles de enemigos

**Juego / edición / versión:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345  
**Sistema y subtema:** percepción, persecución, combate y roles  
**Agente / fecha:** Codex / 2026-10-25  
**Estado de evidencia:** `OBSERVADO` para datos; `INFERIDO` para estados  
**Confianza:** `MEDIA`; no se ha aislado todavía la máquina de estados del binario.

## Pregunta específica

¿Qué parámetros diferencian el comportamiento de los enemigos y qué roles emergen de sus combinaciones?

## Observaciones verificables

| Observación | Ruta de evidencia | Línea/campo | Estado | Cómo verificar |
|---|---|---|---|---|
| Hay 138 monstruos: 116 `EVIL`, 20 `NEUTRAL` y 2 `GOOD`. | `MONSTERS/monsters.dat` + `fate_inventory.py` | enum raíz `ALIGNMENT` | OBSERVADO | Ejecutar inventario. |
| Todos declaran caminar/correr, giro, vista, movimiento, atención y seguimiento. | `MONSTERS/monsters.dat` | Topaz Gel, líneas 5–50 | OBSERVADO | Leer registro. |
| Death Cap añade `BRAVERY:.5`, radios diferentes y preferencias de equipo. | `MONSTERS/monsters.dat` | líneas 151–216 | OBSERVADO | Leer registro. |
| Imp Shaman tiene `BRAVERY:.25`, cinco hechizos, 2–3 minions, colisión de minions y `TACTICS:MAGE`. | `MONSTERS/monsters.dat` | líneas 1066–1146 | OBSERVADO | Leer registro. |
| Solo cinco registros declaran explícitamente `TACTICS:MAGE`; 207 asignaciones `SPELL` aparecen en el archivo. | mismo archivo + inventario | conteos de tags/enums | OBSERVADO | Repetir conteo. |
| Los ataques desarmados declaran animación, rango, daño y tipo; algunos monstruos tienen varios ataques. | mismo archivo | sección `UNARMED_ATTACK` | OBSERVADO | Contar 229 secciones. |

## Regla inferida / modelo mental

```text
reposo / movimiento local
  -> detectar algo en VIEW o ATTENTION
  -> acercarse usando WALKING/RUNNING y TURN_RATE
  -> mantener o romper persecución según FOLLOW_RADIUS
  -> elegir ataque por rango, arma, hechizos, minions y TACTICS
  -> BRAVERY probablemente influye en huida/agresividad
```

Los nombres de los radios sugieren este flujo, pero sus condiciones exactas aún no están demostradas en código.

## Qué ve y hace el jugador

- Reconoce roles por distancia, velocidad, arma, hechizos y acompañantes.
- Puede provocar persecución, separarse de grupos o priorizar lanzadores.
- Resistencias y tipos de daño obligan a variar herramientas.
- Sonido, animación y partículas comunican alerta, ataque e impacto.

## Incertidumbres

- Semántica exacta de `MOTION_RADIUS`, `ATTENTION_RADIUS` y `BRAVERY`.
- Navegación, evasión de obstáculos y coordinación entre enemigos.
- Prioridad de objetivos, cooldowns y ponderación de hechizos.
- Escalado con dificultad, nivel y profundidad.

## Opciones de inspiración sin aprobación automática

- A: roles definidos enteramente por datos combinables.
- B: árboles de comportamiento por arquetipo con parámetros externos.
- C: pocos estados universales y habilidades que generan variedad emergente.

## Pregunta breve para el autor

¿Te divierte más leer rápidamente roles claros —tanque, perseguidor, mago— o descubrir comportamientos impredecibles durante el combate?
