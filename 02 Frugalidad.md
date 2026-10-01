# 7 - Atributos de Calidad del Software

Esta séptima clase se enfoca en cómo evaluar la calidad de un sistema y de qué manera el arquitecto debe dominar y gestionar los aspectos técnicos que determinan el éxito de un software a largo plazo.

A continuación, tienes el resumen completo del **Video 7**:

### **1. Requisitos Funcionales vs. No Funcionales**

Para diseñar un sistema de calidad, es indispensable entender la diferencia y el valor de estos dos tipos de requerimientos:

* **Requisitos Funcionales (Lo que hace el sistema):** Definen los problemas específicos que el sistema debe resolver. Establecen quién tiene la necesidad, qué se espera como resultado, cómo se verifica la solución, cuáles son los límites generales y qué fallas o excepciones conocidas de negocio se deben manejar. Se dividen en capacidades directas del usuario, procesos en segundo plano (*background*), control de acceso y cumplimiento o regulación (*compliance*). El arquitecto debe entenderlos para dimensionar globalmente el problema, pero no son su foco principal de atención.
* **Requisitos No Funcionales (Cómo se comporta el sistema):** Son el verdadero centro de atención de la arquitectura de software. Representan los atributos de calidad que permiten que un sistema sobreviva, mantenga su integridad y mejore a lo largo del tiempo. Su dominio ayuda al arquitecto a identificar los riesgos y las restricciones del proyecto.

Como alternativa para levantar requerimientos, se menciona el **método de Amazon ("working backwards" o trabajar desde atrás)**, el cual consiste en proponer soluciones primero para recibir preguntas y retroalimentación directa de los usuarios; de esta forma, la especificación final del producto se basa en feedback real y no en presunciones iniciales.

### **2. Las Tres Categorías de los Requisitos No Funcionales**

Los atributos no funcionales se estructuran bajo tres grandes pilares:

1. **Atributos de calidad técnicos:** Suelen ser identificados por palabras que terminan en **"-idad"** (en español), tales como la seguridad, usabilidad, mantenibilidad y extensibilidad. El arquitecto debe controlar el espectro de estos atributos, conocer sus restricciones y usarlos como herramientas de negociación para la toma de decisiones.
2. **El Costo:** Es un criterio fundamental para decidir qué camino técnico tomar (tema que se profundizará en las siguientes clases).
3. **El Impacto:** Parte de la premisa de que "no hay balas de plata ni almuerzos gratis", lo que significa que cada decisión arquitectónica tiene contrapesos y consecuencias. Permite cuantificar el costo de los errores en el sistema (sean puntuales, consistentes o acumulados en el tiempo) mediante una **función de pérdida**. Esta función mide pérdidas que no siempre son económicas, sino también reputacionales o regulatorias.

### **3. Gestión de Riesgos y Mitigación**

Una vez identificados los requisitos funcionales, no funcionales y el impacto de los posibles fallos, el arquitecto puede construir una **tabla de riesgos** utilizando frameworks especializados.

* Estos frameworks permiten clasificar los riesgos según su **criticidad y ocurrencia**.
* Ayudan a priorizar qué riesgos deben resolverse previamente durante la etapa de diseño/planeación, y cuáles se pueden aceptar una vez que el sistema esté en producción.
* Para los riesgos que no se resuelven directamente, se elabora un **plan de mitigación** o se definen controles operativos colaborando con otras áreas de la organización para determinar cómo debe actuar el sistema si el riesgo se materializa.

### **4. Las Restricciones: Límites Dinámicos**

Las restricciones son límites impuestos al diseño de tu solución. Es fundamental entender que **no todas las restricciones se conocen al principio**; muchas son dinámicas y se van autoimponiendo a raíz de tus propias decisiones como arquitecto.

* *Por ejemplo:* Si decides utilizar una **base de datos relacional**, autolimitas tu diseño a esquemas que debes planear y estructurar previamente. En cambio, si eliges una **base de datos no relacional o documental**, ganas una enorme flexibilidad en el esquema pero pierdes la capacidad de realizar análisis de datos de forma directa con lenguajes estructurados como SQL.

**Reto Práctico del Video 7**

El instructor te propone realizar dos actividades enfocadas en el problema técnico que elegiste para este curso:

1. Elaborar una **lista de riesgos conocidos** sobre dicho problema.
2. Identificar qué **restricciones** técnicas, organizacionales o de diseño limitarán las soluciones que vas a poder proponer.

---

# 8 - El Costo como Requisito No Funcional

En esta clase se analiza un tema que históricamente los arquitectos de software solían ignorar, pero que hoy en día es un pilar fundamental del diseño: **el costo como un requisito no funcional**.

Aquí tienes el resumen completo del **Video 8**:

### **1. El Cambio de Paradigma en los Costos**

Antiguamente, con arquitecturas tradicionales como las monolíticas, el costo de operación de un sistema en el tiempo se percibía como algo prácticamente constante. Sin embargo, la llegada de los sistemas distribuidos, el big data, el streaming, la alta demanda y la inteligencia artificial distribuyen y aumentan los costos de manera inesperada.

Por ello, la tarea del arquitecto es **etiquetar las cargas de trabajo** según su criticidad (críticas, importantes y accesorias) para aplicar optimizaciones específicas. Las **cargas críticas** son aquellas que deben mantenerse funcionando sin importar qué ocurra (por ejemplo, el movimiento de dinero en un banco o el software de un hospital), mientras que las importantes y accesorias son las candidatas ideales para ser optimizadas.

### **2. El Costo Total de Operación (TCO)**

El **TCO (Total Cost of Ownership)** representa la cantidad total de dinero y recursos necesarios no solo para construir un sistema, sino para mantenerlo operativo a lo largo del tiempo. Se compone de:

* **CAPEX (Costo de Capital/Construcción):** Es la inversión inicial necesaria para construir el sistema y desplegarlo en producción. Con el tiempo, el CAPEX disminuye, pero nunca llega a cero debido a gastos de mantenimiento, configuración y adaptación.
* **OPEX (Costo Operacional):** Es el gasto continuo de operar el sistema en producción. Al inicio es muy bajo (entornos de desarrollo o pruebas), pero incrementa conforme entran más usuarios reales y, eventualmente, tiende a estabilizarse gracias a eficiencias y optimizaciones técnicas.
* **Costo Humano:** Los recursos invertidos en el uso del sistema y en la capacitación de las personas para que puedan operarlo de manera eficiente.

### **3. Estrategias de Optimización de Costos**

El arquitecto cuenta con diversas herramientas y decisiones estratégicas para optimizar los costos:

* **Comprar vs. Construir (Buy vs. Build):** Es una de las primeras decisiones de optimización. Implica evaluar si es mejor adquirir software externo y adaptarlo o construirlo desde cero. Para decidirlo, se debe analizar el TCO global de la solución externa, su curva de aprendizaje, mantenimiento, costos de capacitación y cómo se integrará con el ecosistema de la organización.
* **Optimizaciones Técnicas:** Uso de algoritmos más eficientes, estructuras de datos adecuadas al dominio, sistemas de más bajo nivel o herramientas de proveedores *cloud* que automatizan tareas recurrentes reduciendo costos.
* **Paralelización y Precisión:** Ejecutar trabajos por lotes (*batch*) o paralelizar cargas. También es válido aceptar soluciones menos precisas para problemas de agregación o analítica, siempre que el arquitecto sea consciente de los costos ocultos que esto conlleva.

### **4. Gobernanza, Presupuesto y Observabilidad**

Para sostener estas optimizaciones a largo plazo, se requiere un **framework de gobernanza** que estandarice las mediciones de manera consistente. Esto incluye:

* **Presupuestos:** Decisiones que limitan el costo de construcción del sistema (CAPEX).
* **Proyecciones:** Estimaciones a futuro del costo de operación y mantenimiento (OPEX) utilizando datos históricos.
* **Observabilidad:** Una herramienta clave que permite entender qué falló y por qué falló en ejecución. Se apoya en tres pilares esenciales: **métricas** (medidas directas o indirectas del estado del sistema), **logs** (registros de eventos históricos) y **trazas** (flujo de control entre componentes).
  * *Advertencia:* La observabilidad no es gratuita; es un subsistema que consume recursos y genera costos significativos debido a la enorme cantidad de eventos medidos, el almacenamiento y la retención de datos.

**Reto Práctico del Video 8**

El instructor te propone elaborar un **presupuesto proyectado** para resolver el problema técnico que planteaste en las clases anteriores, calculando el costo en horas de trabajo humano o de inteligencia artificial, junto con una estimación del costo operativo aproximado al primer mes, a los 3 meses y a los 6 meses de operación.

---

# 9 - Alineando el Costo con la Estrategia

En esta clase se aborda la importancia de alinear las decisiones y costos técnicos con la estrategia de negocio, evitando la desconexión entre el equipo técnico y el de negocio.

A continuación, tienes el resumen completo del **Video 9**:

### **1. Alinear el Diseño con la Estrategia**

El deber fundamental de un arquitecto de software es alinear sus diseños con la estrategia de la compañía. Esta estrategia es el plan de juego que guía al negocio hacia el éxito. Al comprenderla a fondo, el arquitecto puede identificar las **dimensiones de ingresos** del negocio, lo que le permite priorizar y tomar decisiones de diseño alineadas.

Para lograr este entendimiento, es obligatorio desarrollar un **lenguaje ubicuo** (un lenguaje común) que permita una comunicación fluida entre el área de negocio y el equipo técnico encargado de abstraer esos conceptos en software.

### **2. Tipos de Estrategias de Negocio**

El arquitecto debe identificar en cuál de las siguientes estrategias se encuentra su compañía para guiar su toma de decisiones técnicas:

* **Estrategia de Exploración:** Propia de empresas que están descubriendo su mercado. En este escenario se pueden aceptar más riesgos en el diseño de los sistemas y se priorizan herramientas innovadoras que ofrezcan ventajas competitivas.
* **Estrategia de Expansión:** Se da cuando la empresa ya encontró un nicho o servicio específico. Aquí se invierte en el desarrollo de productos más estables y que aporten mayor valor al mercado.
* **Estrategia de Ahorro:** Ocurre cuando la compañía necesita recortar gastos. En este caso, el motor principal de decisión técnica será el control de costos por encima de la adición de nuevas funcionalidades.

### **3. Dimensiones de Ingresos y Niveles de Servicio**

La estrategia de la empresa define sus **dimensiones de ingresos**, es decir, las razones exactas por las cuales los clientes o usuarios están pagando por el sistema. Conocerlas permite al arquitecto identificar los casos de uso prioritarios, los requerimientos no funcionales asociados y los rangos aceptables para cubrirlos, utilizando los **niveles de acuerdo de servicio (SLAs)** como una herramienta clave.

Los clientes suelen pagar por:

* **Ventaja competitiva:** Funcionalidades únicas en el mercado que solo tu sistema provee.
* **Cumplir una regulación:** Adquisiciones obligatorias por parte de los clientes, donde los niveles de servicio están atados a normativas.
* **Disponibilidad:** El sistema debe estar activo y presente en todo momento, incluso cuando los interesados no lo estén usando de forma activa.
* **Cumplimiento:** Aspectos que no reportan ingresos directos al usuario, pero que son necesarios para enmarcar sus cargas de trabajo.

### **4. El Problema de la Torre de Babel y cómo crear un Lenguaje Ubicuo**

No desarrollar un entendimiento común entre el equipo técnico y el de negocio conduce al **problema de la Torre de Babel**. En este escenario, las personas comparten un objetivo común pero hablan lenguajes tan distintos que no logran trabajar de manera exitosa, lo que provoca que el software construido no refleje los objetivos de negocio iniciales.

Para construir este lenguaje común y resolver ambigüedades de contexto o interpretaciones, se proponen las siguientes prácticas:

* **Apoyarse en Inteligencia Artificial:** Usar la IA para analizar las discusiones con el equipo de negocio y extraer los sustantivos y verbos clave que explican de qué se habla y cómo se utiliza.
* **Crear un Glosario:** Especificar términos comunes, poco comunes, sinónimos, antónimos, abreviaturas y especializaciones de contexto para unificar el entendimiento del equipo.

**Reto Práctico del Video 9**

El instructor te propone como ejercicio **construir un glosario del contexto de tu problema** donde detalles los términos más y menos comunes, abreviaturas, sinónimos y antónimos para consolidar un entendimiento unificado en tu equipo.

---

# 10 - Retando el Exito

Este décimo y último video cierra el ciclo conceptual del curso abordando el **mindset necesario** para que un arquitecto de software se adapte al cambio y aprenda a cuestionar sus propios aciertos.

### **1. El peligro de la autocomplacencia**

Es común que los arquitectos caigan en la autocomplacencia una vez que logran diseños estables, lo que los lleva a reutilizar de manera sistemática patrones conocidos para resolver problemas distintos. Esto genera un gran riesgo: dejar de adoptar ideas innovadoras para solucionar nuevos desafíos.

Parafraseando a la pionera del software Grace Hopper, las palabras más peligrosas para un arquitecto son: **"Siempre lo hemos hecho así"**. Aunque un arquitecto tenga un historial de éxitos consistentes con sus herramientas habituales, no debe estancarse en ellas, ya que el cambio es constante y siempre habrá personas aprovechando esas transformaciones para obtener ventajas competitivas.

### **2. La Serendipia en la Arquitectura**

La innovación nunca se detiene; siempre surgen nuevos métodos, técnicas y herramientas. Al mantener un marco de pensamiento abierto y explorar qué ocurre fuera del diseño y del problema actual, se puede alcanzar la **serendipia**, definida como la serie de hallazgos exitosos que se obtienen a pesar de no haberlos buscado activamente. Históricamente, este enfoque de exploración abierta ha permitido descubrir medicinas, inventos y métodos completos que dieron resultados extraordinarios sin haber estado planificados originalmente.

### **3. Innovación sistemática apoyada en Inteligencia Artificial**

La IA es una herramienta excelente para realizar innovación de manera sistemática. Un arquitecto puede utilizar modelos de IA para desafiar, profundizar y mejorar de manera iterativa sus documentos, especificaciones y diagramas mediante prompts estructurados como:

* *¿Hay una forma mejor de hacer esto?*
* *¿Existe alguna herramienta que complemente las que estoy usando?*
* *¿Qué detalles no se tienen en cuenta en esta especificación?*

Los nuevos modelos de IA, especialmente aquellos basados en **DeepSeek y razonamiento lógico**, son capaces de estructurar secuencias de pasos para resolver problemas complejos y mantener conversaciones consistentes a largo plazo. Aunque la IA no reemplaza la interacción con expertos de negocio, desarrolladores o pares técnicos, sí expande enormemente el espectro de opciones e ideas del arquitecto para adoptar nuevas técnicas.

---

### **Reto Práctico del Video 10**

El instructor te propone consolidar todos los subproductos que generaste en las clases anteriores (descripción del problema, espacio de solución, alternativas, riesgos, restricciones, estrategia, presupuesto y costos asociados) e **introducirlos en una conversación con un modelo de IA**. El objetivo es utilizar la tecnología para retar tus propuestas, descubrir aspectos que tal vez pasaste por alto y enriquecer el desarrollo de un producto de calidad.

---

🎓 ¿Te gustaría que recopilemos los resúmenes de los 10 videos de este curso de arquitectura en una **guía de estudio en formato PDF** estructurada y lista para descargar?
