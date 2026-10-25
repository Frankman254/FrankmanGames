# FrankmanGames — Plan de investigación para producir arte, modelos, animaciones y audio

**Estado:** rutas de producción posibles, NO selección de estilo, proveedor, técnica o motor.

## 1. El problema que planteó el creador

«¿Cómo vamos a modelar personajes, casas, cuevas, montañas, equipables y todo el resto solos?» No se resuelve afirmando que una IA produce miles de modelos. Hay que construir un **pipeline repetible y coherente**, con coste conocido de cada activo, aunque aún no tengamos un artista de tiempo completo.

La diferencia decisiva no es solo obtener un modelo bonito: es tenerlo optimizado para un juego, con escala, colisiones, UV, materiales, rig (si corresponde), animaciones, LOD, pivotes, variantes, exportación limpia y permiso legal de uso.

## 2. Estrategias para evaluar

| Método | Qué aporta | Limitación | Recomendación metodológica |
|---|---|---|---|
| Modelado original en Blender | Control de identidad, topología y animación | Horas de aprendizaje/producción | Probar con un personaje y un entorno pequeño |
| Kits modulares propios | Casas, cuevas, ruinas y arquitectura componibles | Repetición si la identidad modular no varía | Definir lenguaje modular y piezas maestras |
| Activos CC0/licenciados | Arrancar prototipos y estudiar escenas | Estilos mezclados, licencia por activo | Mantener registro de procedencia y uso permitido |
| Generación asistida por IA (conceptos) | Iterar siluetas, paletas, criaturas, biomas | No entrega necesariamente recursos 3D válidos | Tratar conceptos como referencia artística, no asset final |
| Modelos 3D generados por IA | Acelerar formas preliminares | Topología, materiales, rig, retopología y licencias | Someter a mismo control de calidad que cualquier modelo |
| Encargos externos puntuales | Resolver un personaje base, rig, música o animación clave | Coste monetario y dependencia | Valorar uso focalizado en piezas que definan identidad |

**Fuentes verificadas** para evaluar licencias iniciales: Blender permite uso comercial de obras creadas con él: https://www.blender.org/support/faq/ . Kenney declara CC0 para sus paquetes de assets: https://kenney.nl/support . Poly Haven declara CC0 en sus modelos/texturas/HDRI: https://polyhaven.com/license . El agente debe comprobar la licencia **de cada recurso concreto**, no asumir que todas las plataformas/marketplaces son CC0.

## 3. Pipeline conceptual de un personaje 3D

`Brief de personaje -> silueta y referencias originales -> arte conceptual aprobado -> blockout 3D -> escultura/modelado -> retopología/UV -> materiales/texturas -> rig -> animación -> exportación -> importación -> pruebas de cámara y combate -> correcciones -> versión optimizada`.

**Puertas de calidad** que deberían estudiarse:
- Silueta reconocible incluso sin textura y en la cámara realmente elegida.
- Volúmenes y proporciones coherentes; no deformaciones en articulaciones.
- Pivotes, escala, esqueleto y nombres consistentes.
- Animaciones de locomoción, hechizo, impacto, caída y transición consistentes.
- Compatibilidad de materiales/formatos con tecnologías candidatas.
- Licencia o autoría registrada y posibilidad de distribución comercial.
- Presupuesto de rendimiento medible una vez exista prototipo autorizado.

No fijar ahora triángulos, número de huesos, tamaño de texturas o formatos exclusivos: dependen de plataforma, cámara, estilo y benchmark.

## 4. Equipamiento y visualización del personaje

Preguntas:
- ¿Las armas aparecen realmente en el cuerpo? ¿Y las armaduras o accesorios?
- ¿Un ítem cambia el modelo, textura, partículas o solo estadísticas?
- ¿Los personajes comparten un esqueleto o familias de rigs?
- ¿Una habilidad necesita animación única por arma o puede reutilizarse?
- ¿Cómo afectan tamaños corporales y especies al número de animaciones?
- ¿Cómo se comunica la rareza sin saturar el arte?

Una armadura que cambia visualmente puede multiplicar el coste en modelado, clipping, rigs, QA y sincronización en red. **El creador debe elegir cuánto importa esta personalización visual.**

## 5. Movimiento y «no se vea robótico»

El creador exige una mejora percibida en expresividad respecto a FATE. Investigar opciones:
- Transiciones suaves entre reposo, desplazamiento y combate.
- Aceleración/desaceleración coherente con fantasía del personaje.
- Animaciones direccionales y mezcla de locomoción.
- Anticipación y recuperación de ataques; reacciones al impacto.
- Alineación de pies y cuerpo con superficies; cuidado con deslizamiento de pies.
- Respuesta del objeto/arma al contacto (audio, hit-stop moderado, efectos).
- Reacción convincente de criaturas enormes al entorno y al daño.

No confundir física realista con animación satisfactoria: un RPG estilizado puede usar animaciones expresivas y físicas selectivas.

## 6. Pipeline de escenarios

**Opciones para estudiar, sin seleccionar:** mundo construido a mano, kit modular, terreno procedural acotado, combinación de sectores con piezas reutilizables. Para cada opción describir identidad visual, repetición, coste de creación, streaming, colisiones, navegación IA, variación climática, iluminación y producción de secretos.

El problema no es solo «hacer montañas»: hay que hacer montañas **navegables, legibles, con rendimiento, interesantemente explorables y coherentes con la historia**.

## 7. Audio y música como pilares jugables

El testimonio de FATE da relevancia excepcional a música y ambientalización. No relegar audio al final del desarrollo. Investigar:

- Mapa emocional de escenas: ciudad/refugio, exploración, tensión, enemigo intimidante, combate, descubrimiento, fracaso, calma, recompensa.
- Capas musicales variables según estado sin cambios bruscos molestos.
- Sonidos que revelan criaturas o lugares antes de que se vean.
- Silencios y momentos de reposo que hacen significativa la música posterior.
- Audio de feedback de hechizos distinguible para multijugador.
- Espacialización y mezcla que no tape sonidos críticos.
- Identidad musical propia con compositor, sonidos originales o licencias adecuadas.

**No utilizar pistas de FATE/DOFUS dentro del producto** sin licencias expresas. Las referencias musicales sirven para describir atmósferas, no para copiarlas.

## 8. Prueba de viabilidad artística (solo planificación por ahora)

Antes de producir un catálogo enorme, pedir al equipo de arte/IA una hoja de costes hipotéticos y un «paquete representativo» para aprobación futura:
- Un personaje con dos conjuntos de movimientos.
- Una criatura pequeña y una enorme.
- Una arma y un equipable con diferencia visual.
- Un módulo de cueva, una construcción y una pieza natural.
- Tres estados de audio: exploración, amenaza y calma.

**Aún no producir estos recursos.** Primero acordar estilo, cámara, nivel de detalle, herramientas y restricciones legales con el autor. El paquete solo sirve para estimar y probar un pipeline cuando se autorice.

## 9. Registro de licencias de assets, obligatorio cuando se usen

`asset_id | título | autor | origen/URL | licencia y versión | fecha de descarga | ámbito de uso | modificaciones | créditos necesarios | formato | responsable | aprobado para distribuir`.

Esto aplica también a música, voces, efectos, recursos adquiridos y salidas de IA sujetas a términos de plataforma. Separar material de investigación de recursos finales del juego.
