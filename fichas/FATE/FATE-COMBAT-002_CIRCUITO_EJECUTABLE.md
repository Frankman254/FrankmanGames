# FATE-COMBAT-002 — Circuito ejecutable de impacto y daño

**Juego / edición / versión:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345  
**SHA-256:** `d59a1540038c9ef31c695e202ab42fb54051f30cc414c23aacbeafbd16a6de5d`  
**Sistema y subtema:** ataque físico, impacto/esquiva, crítico, mitigación y bloqueo  
**Agente / fecha:** Codex / 2026-10-25  
**Estado de evidencia:** `OBSERVADO` para flujo, constantes y operaciones; `INFERIDO` para nombres de algunos campos sin símbolos  
**Confianza:** `ALTA` para el orden del circuito y las curvas; `MEDIA` para el nombre semántico de varios offsets.

## Resultado principal

La ejecución del ataque converge en `FUN_005480b0`, que valida objetivo/colisión y llama a `FUN_00546e60`. Esta última concentra la resolución del golpe. El orden recuperado es:

```text
objetivo válido + definición de ataque
  -> tirada de crítico
  -> tirada de impacto frente a defensa/esquiva
  -> daño base y bonos
  -> crítico duplica el daño base
  -> mitigación por porcentaje/tipo, con mínimo previo de 1
  -> bloqueo puede anular todo el daño ya mitigado
  -> limitar al valor de vida restante
  -> aplicar multiplicadores porcentuales y delta de vida/stamina
  -> procs, estados, partículas, sonido y feedback
```

## Puntos de anclaje

| Papel recuperado | Función | Evidencia |
|---|---|---|
| Ejecución del ataque y selección/colisión del objetivo | `FUN_005480b0 @ 005480b0` | Llama a `FUN_00546e60` después de validar objetivo y geometría. |
| Resolución del golpe | `FUN_00546e60 @ 00546e60` | Contiene tiradas, daño, crítico, mitigación, bloqueo, aplicación y efectos. |
| Ataque total candidato | `FUN_00530600 @ 00530600` + `FUN_0052e9f0 @ 0052e9f0` | Base/bonos y contribución de un atributo dividida entre 5. |
| Defensa/esquiva candidata | `FUN_005312a0 @ 005312a0` | Incluye base 50, nivel, mitad del mismo atributo y bonos de equipo/acción. |
| Daño de arma/ataque | `FUN_0053b990 @ 0053b990` + `FUN_00530690 @ 00530690` | Rango aleatorio, atributo/porcentajes, categoría de arma y bono de nivel de mascota. |
| Mitigación | `FUN_0052eaa0 @ 0052eaa0` | Escala, fuerza mínimo 1, limita porcentaje a `[-100,100]` y nunca devuelve menos de 0. |
| Bloqueo | `FUN_005300f0 @ 005300f0` | Exige el objeto/slot correspondiente, usa curva saturante y pone el daño en 0. |
| Aplicación de vida | `FUN_00540f40 @ 00540f40` | Suma el delta al campo de vida, limita por máximo y no permite bajar de 0. |
| Aleatorio flotante | `FUN_004a0a00 @ 004a0a00` | Uniforme entre dos límites mediante `_rand()`. |
| Aleatorio entero | `FUN_004a0a40 @ 004a0a40` | Uniforme inclusivo `[mínimo,máximo]`. |

Evidencia completa: `FATE-ReverseEngineering/evidence/ghidra/FATE-COMBAT-RESOLUTION.md` y `FATE-COMBAT-FORMULA.md`.

## Fórmulas recuperadas

### Impacto frente a esquiva

La forma algebraica observada en `FUN_00546e60` es:

```text
ataque  = ataque_base_y_bonos + aporte_atributo/5
defensa = 50 + nivel + aporte_atributo/2 + bonos_de_equipo/acción
fallo%  = clamp(100 * defensa / (defensa + ataque), 5, 95)
impacta = tirada_uniforme_0_100 >= fallo%
```

La asociación del atributo con Destreza es `INFERIDA` por la coincidencia entre estas funciones y el texto de UI que dice que Destreza aumenta acertar y esquivar. Los límites `5` y `95` y la forma de la razón son `OBSERVADOS`.

### Crítico

La curva observada es:

```text
crit% = min(50, 50 - 50 / (1 + 0.03 * puntuación_crítica))
si crítico: daño_base *= 2
```

La función también trata una tirada límite de 100 como crítica. El campo de puntuación incluye el offset de actor `+0x888` y un término entero auxiliar; la procedencia semántica exacta de ese término sigue abierta. El sonido de crítico está cargado como `SOUNDS\BATTLE\critical.wav`.

### Bloqueo

`FUN_005300f0` exige que exista el objeto asociado al slot consultado y calcula:

```text
bloqueo% = min(50,
               50 - 50 / (1 + 0.03 * puntuación_bloqueo)
               + bonus_porcentual_de_bloqueo)
bloquea = tirada_entera_0_100 no extrema y tirada < bloqueo%
```

Cuando bloquea, `FUN_00546e60` asigna `0` al daño mitigado antes de aplicar vida. El sonido está cargado como `SOUNDS\BATTLE\block.wav`.

### Daño y mitigación

La secuencia verificable es:

```text
daño_base = daño_arma_y_bonos + bono_adicional_de_actor
si crítico: daño_base *= 2

daño_escalado = max(1, redondear(daño_base * multiplicador%))
mitigación% = clamp(valor_seleccionado_por_tipo, -100, 100)
daño_mitigado = max(0,
                     daño_escalado
                     - redondear(mitigación% * daño_escalado / 100))

si bloqueo: daño_mitigado = 0
daño_aplicable = min(daño_mitigado, vida_actual_objetivo)
```

Después se multiplica `daño_aplicable` por campos porcentuales del atacante (limitados a `[-100,100]`) para producir deltas de vida y otro recurso. Los signos y nombres finales de esos dos campos requieren tipado adicional; la llamada a `FUN_00540f40` confirma cuál termina en vida.

## Constantes confirmadas

| Dirección | Valor | Uso observado |
|---|---:|---|
| `00976d44` | `50.0` | techo y numerador de curvas de crítico/bloqueo |
| `0097ac8c` | `0.03` | pendiente de las curvas saturantes |
| `00978d64` | `5.0` | mínimo de probabilidad de fallo |
| `0097d3c8` | `95.0` | máximo de probabilidad de fallo |
| `00975050` | `100.0` | conversión a porcentaje |
| `0097be3c` | `-100.0` | límite inferior de multiplicador |
| `00975000` | `0.01` | porcentaje a factor |
| `00974ff8` | `0.5` | factor usado en varias ramas |

## Qué queda abierto

- Nombrar con seguridad cada offset de actor usado como puntuación, porcentaje o resistencia.
- Separar armadura física de resistencias elementales en el selector de tipo de `FUN_0052eaa0`.
- Determinar el redondeo exacto en cada frontera; Ghidra muestra auxiliares x87 y duplica algunas conversiones.
- Mapear los eventos de animación `HIT` al instante exacto en que entra `FUN_005480b0`.
- Medir en juego los casos límite de 5/95%, crítico al 50% y bloqueo al 50%.

## Límite de uso

Este documento describe comportamiento observado para estudio y comparación. No convierte automáticamente estas fórmulas en decisiones de FrankmanGames.
