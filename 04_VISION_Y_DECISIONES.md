# Visión creativa y decisiones — registro controlado por el autor

## Única orientación creativa ya expresada por el autor
- Quiere explorar un **juego propio** inspirado en aspectos de FATE: Undiscovered Realms, DOFUS Retro y DOFUS 3.
- En una conversación anterior escogió inicialmente la dirección **«combate en tiempo real como FATE, con sistemas RPG inspirados en DOFUS»**. Es una orientación a examinar con él, **no una lista de mecánicas obligatorias**.
- El autor especificó que las propuestas concretas del asistente **no deben convertirse en reglas aprobadas** sin contrastarlas con sus intereses y visión.
- Le interesa evaluar el uso de **JavaScript/TypeScript** y medir rendimiento antes de escoger tecnología. **No se ha elegido motor.**

## Registro de decisiones
| ID | Tema | Estado | Decisión del autor | Fecha | Evidencia de aprobación |
|---|---|---|---|---|---|
| V-001 | Identidad general del proyecto | EXPLORACIÓN | RPG original que estudia tres referentes | 2026-10-25 | Conversación del autor |
| V-002 | Ritmo de combate | ORIENTACIÓN PRELIMINAR | Explorar acción en tiempo real estilo FATE + sistemas RPG; detalles pendientes | 2026-10-24 | Preferencia previa del autor |
| V-003 | Motor gráfico | NO DECIDIDO | — | — | — |
| V-004 | Lenguaje | EVALUACIÓN | JS/TS es candidato; comparar por prototipo | — | — |
| V-005 | Multijugador | NO DECIDIDO | — | — | — |
| V-006 | Sistema de clases | NO DECIDIDO | — | — | — |
| V-007 | Economía | NO DECIDIDO | — | — | — |
| V-008 | Mazmorras y mundo | NO DECIDIDO | — | — | — |
| V-009 | Dirección artística | NO DECIDIDO | — | — | — |

### Estados permitidos
`EXPLORACIÓN` · `ORIENTACIÓN PRELIMINAR` · `PROPUESTA` · `NO DECIDIDO` · `APROBADO POR AUTOR` · `RECHAZADO POR AUTOR` · `POSTERGADO`

**Regla innegociable del proceso:** solo una afirmación explícita del autor permite pasar a `APROBADO POR AUTOR`. El criterio de un agente o del coordinador no basta. Los agentes pueden añadir propuestas como filas nuevas, pero nunca autoaprobarlas.

## Cómo capturar la visión sin imponer ideas
En lugar de empezar por una lista infinita de mecánicas, presentar al autor **tensiones de experiencia** y ejemplos de funcionamiento: qué emoción busca, qué acciones se repiten, qué oportunidades tiene el jugador, qué complejidad quiere, cómo desea progresar, y qué cosas de cada referente querría conservar o evitar.

Preguntas abiertas para sesiones futuras (no bloquear el avance documental):
1. ¿Cuál es la sensación irrenunciable que buscas cuando juegas FATE y cuando juegas DOFUS?
2. ¿Qué parte de FATE disfrutas más: explorar, combatir, mejorar loot, mascotas, progresión u otra?
3. ¿Qué parte de Retro y de DOFUS 3 te gustaría distinguir por separado?
4. ¿Qué experiencias nunca quisieras que tu propio juego reprodujera?
5. ¿Qué formato imaginas inicialmente: aventura para un jugador, cooperativo, persistente, otro? (Aún abierto).

## Formato para registrar una propuesta
```markdown
### P-000 — Título
- Problema o experiencia que queremos lograr:
- Referente(s) y evidencia:
- Variante A:
- Variante B:
- Variante C (si corresponde):
- Costes, riesgos y conflictos:
- Experimento mínimo para validarla:
- Opinión expresada por el autor:
- Estado: PROPUESTA
```

## Gate previo a desarrollar
Una mecánica pasa a implementación cuando tiene: propósito jugable, comportamiento descrito, criterios de prueba y aprobación del autor sobre la dirección. La elección de motor se considera una decisión distinta.
