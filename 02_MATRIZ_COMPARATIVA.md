# Matriz de sistemas — FATE × DOFUS Retro × DOFUS 3

Esta matriz comienza deliberadamente incompleta. **No** define lo que tendrá el juego propio. «Pista» indica información inicial a validar; «?» requiere investigación. Una misma categoría puede implementarse de formas incompatibles en referentes distintos.

| Sistema | FATE: pista existente | DOFUS Retro: pista existente | DOFUS 3: pista existente | Pregunta de diseño, NO decisión |
|---|---|---|---|---|
| Bucle central del jugador | Referente de combate de acción elegido preliminarmente por el usuario | ? | ? | ¿Qué acciones deberían ocupar la mayor parte de la sesión? |
| Movimiento y cámara | OBSERVADO: clic izquierdo mueve/ataca/interactúa; `Ctrl` corre; `Shift` mantiene posición al atacar. Cámara pendiente | ? | ? | ¿Control libre, selección de casilla, híbrido u otra cosa? |
| Ritmo de combate | OBSERVADO: acción en tiempo real con alcance, velocidad de arma, cast time y feedback de impacto; timings exactos pendientes | ? | ? | ¿Qué tiene que sentir el jugador: reflejos, planeación, ambas? |
| Recursos de habilidades | OBSERVADO: 53 hechizos con maná, cast time, requisitos y efectos; cooldown/recuperación exactos pendientes | ? | ? | ¿Qué limita usar habilidades? |
| Clases e identidad de personaje | ? | ? | ? | ¿Qué hace realmente distinta una clase/build? |
| Estadísticas y fórmulas | OBSERVADO: Fuerza→daño, Destreza→hit/esquiva, Vitalidad→vida/stamina, Magia→maná/daño mágico; fórmulas numéricas pendientes | ? | ? | ¿Profundidad vs legibilidad? |
| Efectos de estado y sinergias | OBSERVADO: efectos instantáneos/temporales/pasivos, exclusividad, duración, bonus por habilidad y tipos de daño | ? | ? | ¿Qué combinaciones generan decisiones interesantes? |
| Equipamiento y modificaciones | OBSERVADO: 717 objetos, 1,327 efectos, requisitos, artefactos, sockets y bonus planos/porcentuales | ? | ? | ¿Cuánto peso tendrán loot, crafteo y especialización? |
| Economía | OBSERVADO: `VALUE`, rareza, profundidad, compra habilitada y ventanas de mercader; fórmula final de compra/venta pendiente | ? | ? | ¿Economía offline, compartida o ambas? |
| Botín y progresión | OBSERVADO: filtros por profundidad/rareza y modificadores de oro/drop mágico; algoritmo de selección pendiente | ? | ? | ¿Cómo se recompensa el tiempo y el riesgo? |
| Mazmorras / mundo | OBSERVADO: nueve plantillas controlan topología, pits, oscuridad, geometría, props, colisión, luz y audio; generador pendiente | ? | ? | ¿Exploración infinita, zonas diseñadas o mezcla? |
| IA / enemigos | OBSERVADO: 138 monstruos con radios, velocidades, valentía, ataques, hechizos, minions y rol `MAGE`; estados exactos pendientes | ? | ? | ¿Qué comportamiento hace divertidos los encuentros? |
| Mascotas / compañeros | Presencia de mascota en `.FFD` reportada | ? | ? | ¿Papel activo, utilitario, cosmético, ninguno? |
| Mundo social / multijugador | ? | ? | ? | ¿Juego individual, cooperativo, MMO? **Sin decidir** |
| Interfaz y claridad | ? | `core.swf` con abundantes pantallas reportadas | ? | ¿Qué información se debe mostrar durante combate y exploración? |
| Guardado y persistencia | OBSERVADO: `.FFD` contiene personaje, mascota, inventario, quest y entidades activas; mapa binario pendiente | ? | ? | ¿Qué estados persisten y por cuánto tiempo? |
| Modificabilidad / data-driven | `[ITEM]`, `[MONSTER]`, `[SPELL]` en `.dat` | ? | ? | ¿Editor y mods para usuarios, datos cerrados u otro enfoque? |
| Rendimiento técnico | Motor x86 nativo, Direct3D 8 | Cliente Flash/AS reportado | Cliente Unity/IL2CPP inferido a partir de salida Cpp2IL; revisar evidencias | ¿Qué tecnología permite prototipar la visión de forma sostenible? |

## Cómo se completa cada fila
1. Crear una ficha por **juego y sistema** (`05_PLANTILLA_FICHA_MECANICA.md`).
2. Distinguir **regla verificable**, **experiencia observada** y **opinión del analista**.
3. Registrar versiones, condiciones y casos límite; no extrapolar a versiones distintas sin evidencia.
4. Proponer **varias** rutas originales cuando haya conflicto entre referentes.
5. Marcar cada propuesta `PENDIENTE_AUTOR` hasta que el creador la evalúe.

## Tensiones interesantes a investigar, sin resolverlas por anticipado
- Acción en tiempo real vs decisiones tácticas con ventanas de acción.
- Progresión por loot vs progresión por clase/equipamiento/artesanía.
- Exploración procedural vs contenido cuidadosamente diseñado.
- Combate legible vs diversidad de estados y efectos.
- Sistemas offline modificables vs economía validada en servidor.
- Complejidad de interfaz vs aprendizaje gradual.

No escoger todavía la solución «correcta» a estas tensiones.
