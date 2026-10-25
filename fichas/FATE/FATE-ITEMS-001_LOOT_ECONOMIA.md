# FATE-ITEMS-001 — Objetos, loot y economía

**Juego / edición / versión:** FATE WildTangent, `Fate-WT.exe` 1.0.0.345  
**Sistema y subtema:** prototipos de objetos, progresión y precio  
**Agente / fecha:** Codex / 2026-10-25  
**Estado de evidencia:** `OBSERVADO`; transformación de precio final `DESCONOCIDO`  
**Confianza:** `ALTA` para el esquema, `BAJA` para compra/venta final.

## Pregunta específica

¿Qué capas convierten un objeto base en una recompensa relevante y cuánto de la economía está expuesto en datos?

## Observaciones verificables

| Observación | Ruta de evidencia | Línea/campo | Estado | Cómo verificar |
|---|---|---|---|---|
| Hay 717 registros `ITEM` y 1,327 efectos anidados. | `ITEMS/items.dat` + `fate_inventory.py` | conteo reproducible | OBSERVADO | Ejecutar el inventario. |
| Los tipos más numerosos incluyen 81 comidas de mascota, 68 gemas, 62 cascos, 47 pergaminos de hechizo, 44 espadas y 36 hachas. | mismo inventario | enum raíz `TYPE` | OBSERVADO | Repetir parser respetando secciones anidadas. |
| Town Portal Scroll combina rareza 3, valor 100, un uso y efecto `OPENPORTAL`. | `ITEMS/items.dat` | líneas 22–48 | OBSERVADO | Leer el registro. |
| Light Handaxe combina profundidad, rareza, valor 115, daño `3:6`, alcance, velocidad y ventana de mercader `0:4`. | `ITEMS/items.dat` | líneas 5160–5184 | OBSERVADO | Leer el registro. |
| Un artefacto puede combinar requisito, armadura, varios efectos pasivos permanentes y no ser comprable. | `ITEMS/items.dat` | White Wizard's Castoff, líneas 12163–12206 | OBSERVADO | Leer el registro. |
| Armas avanzadas pueden tener requisitos múltiples, bonus porcentuales y sockets. | `ITEMS/items.dat` | Beck's Wolfbind, líneas 12209–12259 | OBSERVADO | Leer el registro. |
| Existen modificadores de drop mágico, oro, crítico, bloqueo, robo de vida/maná, resistencias y reducción de requisitos. | `ITEMS/items.dat` | tipos de `EFFECT`; ejemplos desde líneas 7981, 12103, 12312, 12716 | OBSERVADO | Buscar los tipos y revisar su contexto. |

## Modelo mental

```text
profundidad de mazmorra
  -> filtra prototipos por MINIMUM/MAXIMUM_DEPTH
  -> pondera por RARITY
  -> instancia base (tipo, modelo, valor, daño/armadura)
  -> aplica efectos, sockets y condición de identificado
  -> coloca como drop, inventario de contenedor o mercader
```

La secuencia y las probabilidades exactas siguen siendo inferidas.

## Qué ve y hace el jugador

- Compara daño/armadura, velocidad, requisitos y efectos.
- Decide identificar, equipar, engarzar, consumir, alimentar a la mascota o vender.
- El valor económico convive con restricciones de profundidad, rareza y disponibilidad.
- Los efectos alteran combate y también la calidad futura del loot (`PERCENTMAGICALDROP`, `PERCENTGOLDDROP`).

## Incertidumbres

- Fórmula de precio de compra y venta a partir de `VALUE`.
- Significado exacto y escala de `RARITY` y `MERCHANT_MINIMUM/MAXIMUM`.
- Generación de afijos aleatorios y orden de aplicación.
- Qué campos se copian al `.FFD` y cuáles se reconstruyen desde el prototipo.

## Opciones de inspiración sin aprobación automática

- A: loot profundo con muchos modificadores y economía totalmente offline.
- B: menos modificadores, pero cada uno cambia decisiones visibles.
- C: prototipos simples con artesanía/sockets que el jugador controla.

## Pregunta breve para el autor

¿Prefieres la emoción de encontrar muchas variaciones aleatorias o menos objetos con identidad y decisiones de mejora más controladas?
