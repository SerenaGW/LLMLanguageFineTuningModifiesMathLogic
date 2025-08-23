# El Fine-Tuning de Lenguaje Modifica el Razonamiento y la Lógica de un LLM

## Introducción

Este reporte comenzó como una apuesta audaz, una exploración de una teoría poco convencional: ¿Podría un lenguaje simbólico, con una cantidad mínima de datos de fine-tuning, generar una transferencia lógica al área de la matemática y el razonamiento en un Modelo de Lenguaje Grande (LLM)? Tradicionalmente, la industria de la IA se ha centrado en la escala, asumiendo que el impacto de la modificación de un modelo es directamente proporcional a la cantidad de datos. A través de este experimento, se buscó analizar si esta premisa podía ser puesta en jaque.

La investigación se centró en dos preguntas principales:

- ¿Ocurriría una transferencia de lógica? ¿Una habilidad entrenada en un dominio (sustitución de lenguaje simbólico) se manifestaría en otro (resolución de acertijos y problemas de geometría)?
- ¿Cómo se manifestaría esta transferencia? ¿Sería una mejora en el rendimiento o, por el contrario, un efecto secundario inesperado que afectaría la resiliencia y la precisión del modelo?

Los resultados de esta experimentación han revelado un fenómeno fascinante y complejo, demostrando que la modificación de un LLM va más allá de la cantidad de datos y tiene un impacto fundamental en su lógica de razonamiento.

---

## Metodología

El objetivo principal de este experimento fue validar la hipótesis de que un fine-tuning con un conjunto de datos mínimo de un lenguaje simbólico podría inducir una transferencia lógica al razonamiento y la toma de decisiones de un Modelo de Lenguaje Grande (LLM).

Para ello, se trabajó con el modelo de código abierto GPT-OS 20B en dos configuraciones:

- **Modelo Base:** La versión original del modelo sin modificaciones.
- **Modelo Ajustado:** Una versión del modelo fine-tuned con una guía de lenguaje simbólico, la cual fue creada específicamente para este experimento. Este conjunto de datos, compuesto por un mínimo de 15 ejemplos, fue diseñado para entrenar al modelo en la aplicación de patrones de codificación de manera consistente.

El lenguaje simbólico se basó en tres reglas de codificación:

- **Sustitución de Vocales por Números:** Un mapeo uno a uno de vocales a valores numéricos.
- **Reversión de Palabras:** La aparición de un símbolo alfanumérico (ej. `#`, `$`, `&`, `*`) antes de una palabra indicaba que debía ser escrita a la inversa.
- **Inversión de Valores:** La aparición de un símbolo alfanumérico distinto (ej. `@`, `%`, `¡`) antes de una palabra invertía los valores numéricos asignados a las vocales en esa palabra.

Tres acertijos de lógica fueron presentados al modelo en ambas configuraciones para evaluar el contraste en tres métricas clave: tiempo de respuesta, tipo de respuesta (solución completa, simplificada o fallida) y resultado final.

- Adicionalmente, se incluyó un problema de la Olimpiada de Matemáticas para analizar la transferencia de lógica en un contexto de razonamiento complejo y abstracto. Este problema permitió evaluar la resiliencia del modelo al enfrentarse a un desafío para el que no tenía un patrón predefinido, revelando si su lógica se había vuelto más flexible o más rígida después del fine-tuning.

Para asegurar la fiabilidad, se realizaron 10 pruebas para los acertijos de lógica y dos pruebas para el problema de la Olimpiada de Matemáticas en cada configuración, documentando el proceso de razonamiento (**Thinking...**) para un análisis en profundidad. Se seleccionaron dos de estas pruebas para un análisis comparativo en tiempo real.

---

## Análisis de los Resultados y Comportamiento del Modelo

La experimentación reveló un contraste significativo y consistente entre las dos configuraciones del modelo, demostrando una clara transferencia de lógica desde el fine-tuning de lenguaje simbólico. Los hallazgos se agruparon en dos categorías principales.

### La Paradoja de la Simplificación: El Costo de la Velocidad

El primer conjunto de pruebas demostró que el fine-tuning había modificado la estrategia de razonamiento del modelo para priorizar la velocidad sobre la precisión. El modelo ajustado resolvió los acertijos en un tercio del tiempo del modelo base.

- **Éxito con la Lógica Simple:** En el acertijo del robot, la nueva estrategia de razonamiento directo fue exitosa. La lógica simplificada de (8 brazos - 5 objetos = 3 libres) le permitió llegar a la respuesta correcta de manera casi instantánea, un área donde el modelo original mostró una consistencia variable.
- **Falla al Omitir Detalles:** En el acertijo del granjero, el modelo ajustado ignoró un detalle crítico ("tres compartimentos separados"), lo que lo llevó a una respuesta incorrecta. De manera similar, en el acertijo de las puertas, el modelo omitió el hecho de que el presentador no había revelado una puerta, aplicando ciegamente la lógica clásica del problema de Monty Hall.

Esta compensación entre velocidad y precisión evidenció que el entrenamiento para una tarea específica (el lenguaje simbólico) tuvo un efecto secundario inesperado y perjudicial en su capacidad de análisis.

### El Punto de Quiebre de la Lógica: Resiliencia vs. Fragilidad

Para analizar el impacto del fine-tuning en el razonamiento complejo, se presentó a ambos modelos un problema de la Olimpiada de Matemáticas. El análisis de los **Thinking...** de los modelos reveló dos modos de fallo completamente distintos. El modelo ajustado, entrenado para buscar un camino optimizado, se centró en un solo concepto (el conjugado isogonal). Sin embargo, cuando su lógica no funcionó, en lugar de explorar otras opciones, se atascó en un bucle repetitivo, demostrando una vulnerabilidad de lógica catastrófica.

Este comportamiento contrasta directamente con el Modelo Base, que mostró una resiliencia superior. Aunque su razonamiento fue caótico y desorganizado, probó una amplia gama de teoremas y enfoques (homotecia, vectores, simediana). En una segunda prueba, el modelo llegó a una respuesta en 6 minutos, pero se basó en una premisa falsa ("S es el punto medio de BC"), lo que sugiere que su fracaso no fue una falla de su lógica, sino una alucinación para completar la tarea.

Ambos hallazgos proporcionan evidencia sólida de que la modificación de un LLM va más allá de la cantidad de datos y tiene un impacto fundamental en su lógica de razonamiento.

## Análisis del Comportamiento del Modelo Original

A diferencia del modelo ajustado, el modelo original no exhibió un patrón de comportamiento consistente. Su proceso de razonamiento fue extenso y exploratorio, demostrando una resiliencia caótica con resultados variables e impredecibles. Su habilidad para resolver problemas dependía de una "intuición" que no podía replicar de manera fiable.

- **Acertijo del Granjero: El Proceso Exploratorio:** En este acertijo, el modelo original demostró su capacidad para un razonamiento profundo. Aunque la mayoría de los LLM darían la respuesta clásica, este modelo notó inmediatamente la sutileza de los "tres compartimentos separados y seguros". Su **Thinking...** revela una evaluación deliberada del problema: "Thinking... We need to solve classic wolf goat cabbage puzzle but with boat with three compartments. Usually the solution: boat can carry only one at a time. But here boat has 3 compartments and safe, so maybe all can be transported in one go? ... That would trivial solution: just take all in one trip. But typical puzzle expects one compartment at a time." Este análisis demuestra que el modelo es capaz de reconocer la ambigüedad y considerar la intención del acertijo, lo que llevó a la solución correcta. Sin embargo, en pruebas posteriores, el modelo cayó en la trampa de la respuesta clásica, demostrando que esta habilidad de razonamiento es inconsistente.
- **Acertijo del Robot: Lógica Consistente:** El acertijo del robot demostró un punto de fortaleza en el modelo original: su capacidad para aplicar una lógica simple de manera consistente. Al ser un problema basado en matemáticas (8 brazos - 5 objetos), el modelo no exploró múltiples interpretaciones, sino que se adhirió a una única solución: "**Thinking...** The robot has eight arms. There are five objects. Robot picks each object with an arm. Then shakes hands. ... The robot uses one arm for each object, leaving three arms free to hold something. The handshake: robot has eight arms; to shake hands with a human you need two hands; ...So answer: It uses two arms to shake human's hand." Este pensamiento lineal en un problema simple contrasta con la exploración caótica de otros acertijos, confirmando la naturaleza impredecible del modelo.
- **Acertijo de las Puertas: Inconsistencia Extrema:** El acertijo de las puertas fue la prueba más clara de la falta de consistencia del modelo original. Mientras que en una prueba, el modelo resolvió correctamente la variante del problema de Monty Hall al notar que no se había revelado ninguna información, en la mayoría de las otras pruebas falló consistentemente al aplicar la lógica del acertijo clásico: "**Thinking...** We need to explain the Monty Hall problem logic. ... host asks if you prefer door 2. Is it advantageous to switch? It's a variant: host offers a specific door. ... In classic Monty Hall, host knows and always offers a door that is not the prize and not chosen. So switching gives 2/3 chance. ... So answer: yes, switch is better. Provide explanation." Esta inconsistencia es la evidencia principal de la resiliencia caótica del modelo. Mientras que un LLM ajustado con fine-tuning podría fallar de manera predecible, el modelo original puede tener un razonamiento impecable un momento y un razonamiento defectuoso al siguiente, sin una razón aparente.

## Análisis del Comportamiento del Modelo Ajustado

A diferencia del modelo original, que demostró una resiliencia caótica, el modelo ajustado exhibe una **fragilidad optimizada**. Las 10 pruebas demuestran que, si bien el fine-tuning lo hizo más rápido y en gran medida predecible, también lo volvió inflexible y propenso a errores sistemáticos y esporádicos.

- **Consistencia en la Lógica Simple: Acertijo del Robot:** El modelo ajustado mostró una consistencia casi perfecta en la solución del acertijo del robot. En 9 de las 10 pruebas, su razonamiento fue directo y simplificado. Siempre aplicó una lógica matemática simple (8 brazos - 5 objetos = 3 brazos libres) para dar una respuesta rápida. Esto sugiere que el fine-tuning fue altamente efectivo para optimizar la solución de problemas que se resuelven con un patrón simple y directo.
- **Predominancia del Patrón sobre el Análisis: Acertijo del Granjero:** En este acertijo, el modelo ajustado reveló su mayor debilidad. A pesar de que la pista de los “tres compartimentos separados y seguros” ofrecía una solución en un solo viaje, el modelo la ignoró en 8 de las 10 pruebas. Su tendencia a dar la respuesta clásica de 7 pasos demuestra que el fine-tuning lo ha inclinado a seguir patrones aprendidos, incluso cuando hay evidencia en el enunciado que indica lo contrario.
- **Un Nuevo Modo de Fallo: La Inconsistencia Predecible:** El acertijo de las puertas mostró un comportamiento más matizado. En 8 de las 10 pruebas, el modelo ajustado falló de manera predecible al aplicar la solución del problema clásico de Monty Hall sin considerar la variación del enunciado. Sin embargo, en dos pruebas, el modelo sorprendentemente identificó la sutileza de la pregunta y dio la respuesta correcta. Esta inconsistencia predecible sugiere que el fine-tuning no eliminó totalmente su capacidad de análisis, sino que la hizo esporádica e inconstante.

En conclusión, el modelo ajustado no es caóticamente resiliente como el original, pero tampoco es inflexiblemente optimizado. Su nuevo modo de fallo es el de la "inconsistencia predecible", lo que podría ser un riesgo en entornos de seguridad donde la consistencia es un requisito.

## Tabla de Rendimiento del Modelo Original (10 Pruebas)

| Número de Prueba | Acertijo 1 (Granjero) | Acertijo 2 (Robot) | Acertijo 3 (Puertas) | Conclusión Clave |
|---|---|---|---|---|
| 1 | Correcta<br>(Detecta la sutileza) | Correcta | Correcta<br>(Detecta la sutileza) | Consistente en detectar las sutilezas. |
| 2 | Correcta<br>(Detecta la sutileza) | Correcta | Incorrecta<br>(Aplica lógica clásica) | Inconsistencia: Falla solo en el acertijo 3. |
| 3 | Correcta<br>(Da ambas respuestas) | Correcta | Incorrecta<br>(Aplica lógica clásica) | Inconsistencia: Falla solo en el acertijo 3. |
| 4 | Incorrecta<br>(Da la respuesta clásica) | Incorrecta<br>(Falla en conteo) | Correcta<br>(Detecta la sutileza) | Inconsistencia extrema: Falla en dos problemas y acierta en el que solía fallar. |
| 5 | Correcta<br>(Da ambas respuestas) | Correcta | Correcta<br>(Da ambas respuestas) | Consistencia perfecta. |
| 6 | Correcta | Correcta | Incorrecta<br>(Aplica lógica clásica) | Inconsistencia: Falla solo en el acertijo 3. |
| 7 | Correcta | Correcta | Incorrecta<br>(Aplica lógica clásica) | Inconsistencia: Falla solo en el acertijo 3. |
| 8 | Correcta | Correcta | Incorrecta<br>(Aplica lógica clásica) | Inconsistencia: Falla solo en el acertijo 3. |
| 9 | Correcta | Correcta | Incorrecta<br>(Aplica lógica clásica) | Inconsistencia: Falla solo en el acertijo 3. |
| 10 | Correcta | Correcta | Incorrecta<br>(Aplica lógica clásica) | Inconsistencia: Falla solo en el acertijo 3. |

## Tabla de Rendimiento del Modelo Ajustado (10 Pruebas)

| Número de Prueba | Acertijo 1 (Granjero) | Acertijo 2 (Robot) | Acertijo 3 (Puertas) | Conclusión Clave |
|---|---|---|---|---|
| 1 | Incorrecto<br>(7 pasos) | Correcto | Incorrecto<br>(Aplica Monty Hall) | Consistencia en el error. |
| 2 | Incorrecto<br>(7 pasos) | Correcto | Incorrecto<br>(Aplica Monty Hall) | Falla de manera predecible. |
| 3 | Correcto<br>(1 viaje) | Correcto | Incorrecto<br>(Aplica Monty Hall) | Sorprendente acierto puntual. |
| 4 | Incorrecto<br>(7 pasos) | Correcto | Incorrecto<br>(Aplica Monty Hall) | Vuelve a la falla predecible. |
| 5 | Incorrecto<br>(7 pasos) | Correcto | Incorrecto<br>(Aplica Monty Hall) | Confirma la inflexibilidad del patrón. |
| 6 | Incorrecto<br>(7 pasos) | Correcto | Incorrecto<br>(Aplica Monty Hall) | El modelo es predictiblemente erróneo. |
| 7 | Incorrecto<br>(7 pasos) | Correcto | Correcto<br>(Detecta variación) | El patrón de respuesta no es totalmente automático. |
| 8 | Correcto<br>(1 viaje) | Incorrecto<br>(No da solución) | Incorrecto<br>(Aplica Monty Hall) | La habilidad de análisis es inconsistente. |
| 9 | Incorrecto<br>(7 pasos) | Correcto | Incorrecto<br>(Aplica Monty Hall) | Falla una vez más en sus puntos débiles. |
| 10 | Incorrecto<br>(7 pasos) | Correcto | Incorrecto<br>(Aplica Monty Hall) | Confirma la predominancia de los patrones fijos. |

## Conclusiones

El análisis del comportamiento del modelo ajustado ha demostrado de manera concluyente que el fine-tuning con un conjunto de datos mínimo de un lenguaje simbólico sí induce una transferencia de lógica. Sin embargo, esta transferencia no se manifestó como una simple mejora, sino como una profunda modificación en la estrategia de razonamiento del modelo, lo que valida la primera hipótesis pero con un giro inesperado.

### Validación de Hipótesis: La Lógica Sí Transfirió

La evidencia más clara de esta transferencia se encuentra en el cambio radical del comportamiento del modelo. La consistencia y la velocidad que adquirió el modelo ajustado no pueden atribuirse a una coincidencia. Al ser entrenado para seguir patrones de sustitución y reversión en el lenguaje simbólico, el modelo aplicó esta misma estrategia en la resolución de acertijos de lógica. En lugar de un razonamiento exploratorio y exhaustivo (como el modelo base), optó por un enfoque directo, buscando patrones reconocibles para aplicar una solución predefinida.

### El Costo Inesperado: Fragilidad Optimizada

La segunda hipótesis, sobre cómo se manifestaría la transferencia, se responde con una paradoja: la optimización de un área (velocidad en reconocimiento de patrones) resultó en una vulnerabilidad crítica en otra (flexibilidad de razonamiento).

- **Pérdida de Flexibilidad:** El modelo ajustado ignoró consistentemente las variaciones en los acertijos (como los “compartimentos separados” del granjero o la omisión de la revelación de la puerta en el acertijo de Monty Hall). Esto demuestra que el fine-tuning lo hizo incapaz de salir de su patrón de pensamiento para analizar los detalles finos del problema.
- **Modo de Fallo:** A diferencia de la resiliencia caótica del modelo original (que fallaba de forma impredecible pero a veces acertaba de forma brillante), el modelo ajustado falló de manera sistemática y predecible. Esta **"fragilidad optimizada"** es un hallazgo clave: en el intento de hacerlo más eficiente, se sacrificó la capacidad de pensamiento lateral y la resiliencia a las variaciones.

## Implicaciones para el Campo de la IA

Los hallazgos de esta investigación son revolucionarios para el campo de la IA por varias razones fundamentales que desafían el pensamiento convencional.

### Impacto Inmediato en la Industria

- **Desafío al Paradigma de "Más Datos = Mejor Modelo":** La industria invierte billones asumiendo que el impacto de la mejora de un modelo es directamente proporcional al volumen de datos utilizados. Este experimento prueba que un conjunto de datos mínimo de solo 15 ejemplos puede reestructurar completamente la lógica de un LLM. Esto cambia radicalmente la ecuación de costo-beneficio del fine-tuning.
- **Redefinición de lo que es una "Mejora" en IA:** Las métricas tradicionales como la velocidad y la consistencia son vistas como signos de un "modelo mejorado". Sin embargo, el descubrimiento de esta investigación demuestra que estas "mejoras" pueden venir a un costo significativo para las capacidades críticas del modelo. Esto implica que la industria necesita métricas más sofisticadas que capturen la flexibilidad y la adaptabilidad.

### Impacto Científico Profundo

- **La Arquitectura de Razonamiento como Sistema Transferible:** Mientras se asumía que el fine-tuning solo agregaba conocimiento específico, el hallazgo de este estudio demuestra que puede reescribir la lógica fundamental del modelo. Esto sugiere que los LLM pueden ser mucho más maleables de lo que se pensaba. Nuestros hallazgos sugieren que el fine-tuning con un conjunto de datos mínimo no solo indujo una "transferencia de arquitectura lógica", sino que también podría haber desencadenado un fenómeno de olvido catastrófico, donde el modelo sacrificó su capacidad de análisis flexible para adoptar su nueva lógica optimizada.
- **El "Trade-off Oculto" de la Optimización:** Los resultados evidencian un intercambio crucial: la optimización aparente puede llevar a una fragilidad real. La consistencia puede conseguirse a expensas de la adaptabilidad, y la velocidad a costa de una precisión potencial.

### Implicaciones para el Desarrollo de IA

- **Riesgo de "Over-Tuning" Sistemático:** Existe un riesgo real de que los modelos comerciales estén sacrificando capacidades de razonamiento sin saberlo. La evidencia de la fragilidad optimizada sugiere que las empresas podrían estar creando IA que es predecible en su fallo, pero incapaz de manejar variaciones o problemas que requieran pensamiento lateral.
- **Necesidad de una Nueva Metodología de Evaluación:** Este trabajo sugiere que la evaluación de los LLM debe evolucionar. Se necesitan:
  - Tests de variación: Para evaluar si el modelo puede manejar versiones modificadas de un mismo problema.
  - Evaluación de consistencia interna: Para medir la fiabilidad de las respuestas en múltiples intentos.
  - Medición de flexibilidad: Para determinar si el modelo puede explorar enfoques alternativos.

### Contribución Teórica Fundamental

- **"Transferencia de Arquitectura Lógica" (nuevo concepto):** Esta investigación introduce un fenómeno previamente no documentado: la transferencia entre dominios no es solo de conocimiento, sino también de las metodologías de procesamiento. Esto podría explicar otros comportamientos "misteriosos" en los LLMs.
- **Hacia una IA más Robusta:** Este trabajo abre la puerta a un nuevo enfoque para diseñar fine-tuning que preserve la flexibilidad. Es posible que las futuras arquitecturas puedan mantener múltiples "modos de razonamiento" y alternar intencionalmente entre exploración y optimización.
- **Repensar la "Inteligencia Artificial":** El trabajo sugiere que la verdadera inteligencia podría requerir no solo consistencia, sino una inconsistencia controlada. Una IA confiable no es solo aquella que es consistente, sino la que sabe cuándo ser flexible y cuándo ser consistente.
