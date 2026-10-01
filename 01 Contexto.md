# 1 - El Rol del Arquitecto de Software

El video introduce el rol del arquitecto de software a través del caso real de los accidentes de los aviones **Boeing 737 Max** en 2018 y 2019, donde cientos de personas murieron debido a que un sistema automatizado (el MCAS) falló al confiar en un solo sensor sin redundancia ni posibilidad real de intervención humana. Este suceso no fue un bug de programación, sino una **decisión de arquitectura** en la que alguien priorizó la rapidez y los costos sobre la seguridad y el criterio técnico.

A partir de este ejemplo, se explica que las decisiones de un arquitecto impactan directamente en la **escalabilidad, seguridad, privacidad, acceso e incluso en la ética** de cualquier sistema, sin importar el tipo de empresa. Por ello, el rol va más allá de realizar diagramas; se centra en  **diseñar sistemas** , lo que implica abstraer la complejidad, cuestionar supuestos, negociar con los interesados ( *stakeholders* ) y entender que cada línea de código tiene consecuencias reales. El objetivo del curso es construir un **marco de decisiones** con impacto inmediato que ayude a identificar los aspectos más importantes de un proyecto a largo plazo, haciendo énfasis en cómo se comunican dichas decisiones.

Para solucionar el problema de que los equipos suelan olvidar la estructura y el propósito del código con el paso de los años, se propone una práctica inicial muy sencilla: agregar un archivo llamado **`architector.md`** (con el nombre escrito en mayúsculas a propósito para llamar la atención del equipo) en la raíz del repositorio. Este documento debe funcionar como un folleto de presentación y no como un diccionario exhaustivo, incluyendo el propósito del código, un pequeño mapa de los módulos para facilitar intervenciones rápidas sin tener que leer todo el código, conceptos clave, restricciones y posibles riesgos conocidos.

Finalmente, el instructor del curso se presenta como  **Nicolás Borquez** , quien programa desde los 9 años (iniciando con Logo), ha fundado tres empresas de tecnología en Latinoamérica y acumula ocho años de experiencia como arquitecto de software para startups y grandes corporaciones, invitando a los estudiantes a dejar la "adicción al código" para obtener una perspectiva más amplia del desarrollo de software.

---

# 2 - Arquitectura de Software en la Era de la AI

En esta clase se analiza el impacto, las oportunidades y los desafíos que representa la inteligencia artificial en el ámbito de la arquitectura de software, estructurando el tema en varios puntos clave:

### **1. La IA como herramienta inevitable**

La inteligencia artificial se ha consolidado como una herramienta fundamental a la cual los profesionales deben adaptarse para maximizar su valor. Su adopción es masiva: diversas empresas aseguran que **más del 90% de su nuevo código es desarrollado por bots automáticos**, mientras que gigantes de la industria como Google reportan que **más del 25% de su código nuevo es generado mediante modelos automáticos**.

### **2. El Modelo de Adopción de Innovación de Rogers**

Para entender cómo las personas y las organizaciones asimilan esta tecnología, se utiliza el modelo de Rogers, el cual clasifica a la población en cinco perfiles:

* **Innovadores:** Aquellos dispuestos a adoptar la tecnología de inmediato, incluso si no está completamente probada.
* **Visionarios:** Quienes comprenden la tecnología y buscan usarla para resolver problemas que actualmente no tienen una solución rápida.
* *El vacío (masa crítica):* Un punto de quiebre donde, si no se alcanza un número suficiente de usuarios, la tecnología tiende a desaparecer o ser reemplazada.
* **Pragmáticos:** Constituyen la gran masa de la población; adoptan soluciones que ya están consolidadas para resolver sus problemas habituales.
* **Conservadores:** Personas u organizaciones con procesos muy estandarizados que esperan a que la mayoría ya esté utilizando la tecnología antes de implementarla.
* **Escépticos:** Quienes dudan de la innovación o se resisten a adoptarla, usualmente debido a la regulación o por simple aversión al cambio.

### **3. Implicaciones en el Desarrollo de Software**

La introducción de la IA en el flujo de trabajo diario trae consigo importantes consecuencias estructurales:

* **Ciclos de desarrollo sumamente cortos:** Se ha pasado de planificar en meses (con metodologías en cascada) a semanas (con metodologías ágiles), y ahora el tiempo se mide en días o incluso menos gracias a la IA.
* **Atención extrema al detalle:** Debido a la automatización, es imperativo revisar minuciosamente cada producto construido con IA para evitar fallos.
* **Nuevos patrones de desarrollo y costos:** Integrar la IA requiere establecer estándares diarios de trabajo y asumir nuevos centros de costos, ya que el uso de estas herramientas tiene un precio.
* **Incertidumbre en la calidad:** No se tiene certeza de si los estándares de calidad globales bajarán (debido a la generación masiva de código automático sin revisar) o subirán (gracias a que los desarrolladores dispondrán de más tiempo para realizar revisiones exhaustivas).

### **4. El Verdadero Rol del Arquitecto frente a la IA**

Ante este panorama, la única alternativa es la adaptación y el desarrollo de un criterio de diseño sobresaliente. Citando el célebre artículo de Frederick Brooks de 1986, *"No Silver Bullet"*, se recuerda que **"los grandes diseños provienen de grandes diseñadores"**, marcando la diferencia en arquitectura como la que existe entre ser un Salieri o un Mozart.

La arquitectura se define formalmente como **el estudio de la estructura de un sistema, sus propiedades y sus relaciones**. Se enfatiza la palabra *sistema* por encima de *software*, ya que este último es solo una de sus partes.

La diferencia fundamental de responsabilidades radica en que:

* La **IA** se enfoca principalmente en la generación de código y, en ocasiones, del software.
* El **arquitecto de software** se preocupa por la estructura general, las propiedades del sistema, sus relaciones, los canales de comunicación, la estrategia global y, en última instancia, también del código.

EJERCICIO: entre visionario y pragmatico

---

# 3 - Limites de la Arquitectura de Software

Esta clase profundiza en los alcances de la disciplina, abordando qué problemas resuelve, cuáles quedan fuera de su control y cómo un arquitecto debe priorizar su día a día.

### **1. ¿Qué problemas soluciona realmente la arquitectura?**

Un sistema de software puede realizar sus tareas de manera matemáticamente correcta, pero aun así ser un fracaso rotundo si es **difícil de usar, difícil de extender** (agregarle nuevas funciones) o **difícil de mantener** porque su código es incomprensible para nuevos desarrolladores.

La arquitectura de software no se enfoca en el programa que funciona en sí, sino en todos esos **aspectos fundamentales que lo rodean**: la seguridad, la facilidad de mantenimiento, la documentación, los manuales y el costo acumulado a lo largo del tiempo. Maximizar todos estos aspectos a la vez es imposible debido a la falta de tiempo, presupuesto o estabilidad organizacional. Por ello, el rol exige una **negociación constante** con las personas y los sistemas, entendiendo que cada decisión tiene un **costo de oportunidad**: elegir una opción siempre implica renunciar a los beneficios de otra.

### **2. Problemas incidentales vs. esenciales (Fred Brooks)**

Retomando el célebre artículo de Fred Brooks de 1986, se dividen los problemas del desarrollo en dos categorías:

* **Problemas incidentales o accidentales:** Detalles prácticos de la implementación de los conceptos de un sistema, tales como escribir código, hacer pruebas (*testing*) o desplegar la aplicación.
* **Problemas esenciales:** Los conceptos abstractos y complejos de los que debe encargarse el arquitecto de software. Entre ellos destacan:
  1. **La complejidad del sistema:** Que se divide en niveles. Hay problemas **triviales** (respuestas automáticas directas), **simples** (requieren poco pensamiento), **complicados** (muchos factores que, al estandarizarse con reglas claras como el pago de impuestos, se vuelven sencillos de resolver) y **complejos** (involucran actores que cambian las condiciones mientras intentas resolverlos; hacer software entra en esta categoría).
  2. **La conformidad:** La necesidad de que el sistema responda de forma consistente y confiable ante reglas que validan sus salidas.
  3. **La tolerancia al cambio:** Diseñar estrategias para que el sistema se adapte de forma continua a las variaciones del entorno.
  4. **La invisibilidad (incertidumbre):** Lidiar con "lo que no sabemos que no sabemos" buscando medidas para mitigar ese desconocimiento.

A pesar de que el arquitecto no pasa todo su tiempo programando, la "verdad" de un sistema está en el **código fuente**. Por lo tanto, es indispensable que el arquitecto sepa programar, desplegar y entender todo el ciclo de vida del desarrollo.

### **3. La Matriz de Eisenhower para priorizar**

Para gestionar la carga de trabajo y el enfoque técnico, se propone el uso de la **Matriz de Eisenhower**, la cual clasifica las tareas en cuatro cuadrantes:

* **Cuadrante 1 (Importante y Urgente):** Tareas que aportan impacto y valor inmediato, y cuyo valor se acumula en el tiempo. Los problemas importantes son obvios para los arquitectos experimentados (tienen impacto real en el equipo/organización y se pueden delegar en personas de confianza), mientras que los urgentes se detectan analizando costos (si no se resuelven ya, ponen en riesgo a la empresa). **Aquí es donde el arquitecto debe centrar su atención principal**.
* **Cuadrante 2 (Importante pero No Urgente):** Tareas con impacto a largo plazo que no ponen en riesgo el sistema en lo inmediato.
* **Cuadrante 3 (Urgente pero No Importante):** Situaciones que requieren una solución rápida y simple para mantener la continuidad operativa y poder volver a enfocarse en lo verdaderamente importante.
* **Cuadrante 4 (Ni Importante ni Urgente):** Accesorios o experimentos interesantes de explorar, pero sin un impacto real garantizado.

Como cierre, se nos invita a diseñar una **lista de chequeo** para saber identificar con precisión cuándo un problema es verdaderamente Importante y Urgente, sugiriendo como lectura complementaria el libro *"The Checklist Manifesto"*.

EJERCICIO:

C1 Importante y Urgente: Respaldo de sistema RM COBOL en servidor sparc de 1985 que si falla no tiene alternativa de restaurar en otro servidor

---

# 4 - Responsabilidades del Arquitecto de Software

En este cuarto video se detallan las **cuatro responsabilidades fundamentales** de un arquitecto de software: **entender, diseñar, convencer e intervenir**. Cada una de estas dimensiones define el impacto real que tiene el rol dentro de cualquier tipo de organización.

### **1. Entender el contexto**

Para tomar decisiones acertadas, el arquitecto primero debe comprender a fondo el entorno organizacional y técnico en el que se mueve. Esto incluye identificar los requerimientos funcionales y no funcionales, alinearse con la estrategia de negocio y evaluar la capacidad del equipo para ejecutar los diseños.

Dependiendo del tipo de organización, la tolerancia al riesgo varía significativamente:

* **Startups:** Buscan activamente el riesgo y están dispuestas a tomar decisiones altamente innovadoras para sobrevivir.
* **Microempresas:** El riesgo es aceptable, pero no se busca con determinación; se centran en el valor inmediato de su producto o servicio.
* **Empresas en crecimiento o establecidas:** Tienen roles y procesos estables, y el espacio para la innovación es controlado.
* **Entidades públicas:** Son sumamente aversas al riesgo y priorizan seguir procesos estructurados antes que la innovación.

### **2. Diseñar con valor**

El diseño arquitectónico consiste en generar abstracciones, modelos, flujos de trabajo y políticas que den valor real a la organización. Esto abarca la elección de estilos arquitectónicos, la definición de **contenedores** (las divisiones físicas del software para producción) y la estructuración de componentes. Al diseñar componentes, se deben evaluar sus fronteras, dependencias, patrones, métricas de desempeño y estrategias de prueba.

Para lograrlo, el arquitecto dispone de diversas herramientas:

* Estándares y modelos como **TOGAF, C4 model, UML, patrones de software** y los **Architectural Decision Records (ADRs)**.
* Arquitecturas de referencia de proveedores y modelos estandarizados de gestión de riesgos.
* Frameworks de decisión de proveedores de nube e **inteligencia artificial**.

### **3. Convencer y generar cultura**

Un gran diseño no sirve de nada si el arquitecto no logra convencer a la organización de su valor. Al hacerlo, el arquitecto ayuda a **generar cultura**, entendida como "todas las decisiones que toman las personas sin que nadie les diga que deben hacerlo".

* **Convencimiento interno:** El arquitecto debe validar sus propias ideas creando productos de calidad, aplicando diseños consistentes, documentando decisiones y realizando pruebas de concepto.
* **Convencimiento externo:** Implica alinear en la misma visión a todos los involucrados (*stakeholders*): directores, desarrolladores, testers, facilitadores, analistas y operadores.

### **4. Intervenir (Programación)**

El rol requiere intervención directa a través de la programación. Aunque no es necesario ser el mejor desarrollador de la compañía, es indispensable saber programar para entender cómo el equipo ejecuta los diseños y para solucionar los problemas que estos puedan causar en producción. Sin esta capacidad técnica, el arquitecto simplemente **no tiene control de su propia arquitectura**.

Al final de la clase, se propone como ejercicio elegir un **problema importante pero no urgente** (concepto del Cuadrante 2 de la matriz de la clase pasada) para resolverlo, diseñando una solución y codificándola a lo largo del curso.

EJERCICIO: Desarrollo de nuevo modulo de compras para subsanar el sistema actual que pierde informacion

---

# 5 - Arquitectura y Metodologias de Desarrollo de Software

Este quinto video se centra en la relación entre la **arquitectura de software y las metodologías de desarrollo**, los subproductos que se generan en el proceso, las malas prácticas más comunes y las herramientas técnicas para asegurar la calidad del diseño.

### **1. Arquitectura y Metodologías de Desarrollo**

El arquitecto de software debe integrarse o adaptarse a la metodología de la organización, buscando generar productos de valor lo más rápido posible. El desarrollo de software es un **ciclo continuo de entrega de valor**, ya que los sistemas necesitan evolucionar y adaptarse constantemente; no es un proceso que termine al entregar el software.

* **Evolución histórica:** Se ha pasado de metodologías como la de cascada (donde el valor se entregaba tras muchos meses) a **metodologías ágiles**, que priorizan ciclos más cortos y una retroalimentación continua con el cliente.
* **Enfoques informales:** Existen prácticas como los *spikes* de arquitectura o tareas específicas de diseño, aunque cuando no hay una metodología definida, la inercia de los equipos suele ser simplemente "sentarse y codificar".
* **Criterios de aceptación:** Son comprobaciones esenciales para asegurar que lo desarrollado cumpla con las especificaciones y promesas de valor acordadas.

### **2. Automatización, IA y Comunicación**

Las metodologías de desarrollo actuales incorporan niveles de automatización que impactan la generación de subproductos (como tareas, definiciones de diseño y documentos) y los canales de comunicación del equipo. Esta comunicación puede ser **síncrona** (en la oficina) o **asíncrona**, con diferentes intervalos de tiempo entre actividades. Con el uso de IA, los ciclos de retroalimentación pueden llegar a ser instantáneos.

### **3. Malas Prácticas (Antipatrones) en el Desarrollo y la Arquitectura**

El instructor identifica varios bloqueos y patrones de comportamiento que degradan la calidad del sistema:

* **La ilusión de productividad:** Es la entrega rápida de subproductos que parecen terminados pero no tienen la calidad necesaria para producción, lo que genera iteraciones constantes sin un avance real. Con las herramientas de **Inteligencia Artificial**, este riesgo aumenta: se tiende a aceptar directamente lo que entregan los bots sin revisarlo a fondo. Históricamente, esto ya ocurría con herramientas *low-code* o herramientas CASE, donde los desarrolladores alcanzaban un **80% de avance automatizado**, pero aplicaban soluciones cuestionables (*hacks*) para intentar cubrir un 10% adicional sin lograr resolver el 100% de la tarea original.
* **Dependencia de proveedores (*Vendor lock-in*):** Limita la innovación y la calidad del equipo a lo que el proveedor decida entregar.
* **Cargas analíticas en sistemas operacionales:** Intentar extraer reportes históricos o datos agregados de bases de datos que no fueron diseñadas para ese propósito.
* **Resume Driven Development (RDD):** Cuando el equipo o el arquitecto toman decisiones técnicas priorizando cómo se verá el proyecto en su hoja de vida en lugar de buscar el resultado real para el negocio.
* **Parálisis por análisis:** Bloqueo en el avance del desarrollo porque los arquitectos retrasan excesivamente la toma de decisiones.
* **Sistemas infinitamente personalizables:** Tratar de solucionar o prever de forma genérica problemas sumamente complejos que todavía no se han presentado (sobreingeniería).

### **4. Fitness Functions: Una solución sistemática**

Para combatir estas malas prácticas y asegurar que las decisiones de diseño se mantengan alineadas con los objetivos del negocio, se utilizan las **`fitness functions`** (funciones de aptitud). Funcionan de manera similar a las pruebas unitarias, pero actúan como **índices compuestos** que el arquitecto evalúa de forma constante. Están conformadas por:

1. Pruebas unitarias y métricas técnicas.
2. **Ingeniería del caos:** Introducción de fallas programadas en producción para medir la resiliencia del sistema ante eventos inesperados.
3. Escaneos automáticos de seguridad.
4. Monitoreo y observabilidad.

Como ejercicio práctico, el instructor propone analizar qué modificaciones o flexibilizaciones hace tu organización a la metodología de desarrollo estándar (como saltarse ceremonias ágiles o relajar criterios de prueba) para entender cómo entregar tus productos de arquitectura con la máxima calidad requerida.

---

# 6 - Expectativas y Comunicacion en la Arquitectura de Software

En esta clase se aborda a fondo cómo gestionar las expectativas y cómo estructurar una comunicación efectiva en la arquitectura de software.

Aquí tienes el resumen completo del **Video 6**:

### **1. El Espacio del Problema vs. El Espacio de la Solución**

Una de las tareas fundamentales del arquitecto es guiar las conversaciones separando claramente estos dos ámbitos:

* **El Espacio del Problema:** Corresponde a los requisitos, ideas, intenciones y retos que vas descubriendo al hablar con el cliente. No es la solución en sí, sino lo que el sistema debe solucionar. Se explora utilizando preguntas de tipo **¿por qué?**, **¿para qué?** y **¿qué?**. Estas preguntas ayudan a identificar la urgencia, la prioridad, el contexto de fondo y restricciones ocultas como la regulación.
  * *El error clásico:* Es muy común que las personas presenten un requerimiento mezclando ambos espacios al incluir una arquitectura implícita (por ejemplo: *"necesitamos un microservicio de detección de fraude"*). Mientras un desarrollador con poca experiencia se apresuraría a programar un modelo de IA, un arquitecto experimentado preguntará primero **"¿qué consideramos fraude?"** para delimitar el problema real antes de escribir código.
* **El Espacio de la Solución:** Se refiere a las opciones técnicas y de diseño que tienes para responder a las necesidades identificadas. Este espacio se aborda principalmente con preguntas del tipo **¿cómo?**.

### **2. Carga Cognitiva y la Ley de Conway**

La comunicación arquitectónica está influenciada por dos factores clave:

* **La Carga Cognitiva:** Es la serie de conceptos e ideas que una persona debe retener activamente en su mente para poder dialogar, preguntar o responder sobre un contexto determinado.
* **La Ley de Conway:** Este principio señala que las organizaciones tienden a diseñar sistemas que reflejan sus propias estructuras de comunicación interna. Dado que cada empresa se comunica de manera distinta (por ejemplo, de forma distribuida y asíncrona, o mediante estructuras centralizadas y jerárquicas), el arquitecto tiene el deber de detectar, adoptar y adaptarse a estos estándares para entender y hacerse entender.

### **3. Documentación Colaborativa y Efectiva**

Bajo la premisa de que "el medio es el mensaje", se promueve el uso de **hipertexto e hipermedia** para facilitar la comunicación. Los documentos técnicos tradicionales ya no son funcionales por sí solos; para tener valor real deben incorporar:

* Interacciones y comentarios directos.
* Control de cambios para revisar su evolución histórica.
* Plantillas estructuradas.
* Solicitudes de retroalimentación en secciones muy específicas.

El arquitecto debe **evitar el conformismo del "por mí está bien"**, donde los involucrados solo consumen pasivamente una presentación sin involucrarse realmente. Asimismo, es crucial establecer **fechas de corte** para recibir comentarios y evitar caer en la parálisis por análisis con documentos que nadie lee.

### **4. Diagramas y Estándares de Comunicación Visual**

Después de los documentos, los diagramas representan el medio de comunicación más importante para el rol. Se destacan las siguientes herramientas de diagramación:

* **C4 Model:** Permite comunicar abstracciones que se vuelven progresivamente más concretas conforme se descubre el espacio del problema.
* **Diagramas de Secuencia:** Ideales para visualizar el flujo dinámico de la información y los mensajes entre los actores del sistema.
* **Estándares de Procesos de Negocio:** Permiten modelar formalmente las actividades, tareas, paralelizaciones y sistematizaciones necesarias para cumplir un objetivo de negocio.
* **UML:** Útil para modelar estructuras, estados, secuencias y despliegues físicos de software.


**Reto Práctico del Video 6**

El instructor propone reescribir el problema técnico que elegiste en las clases anteriores separando de forma estricta el **espacio del problema** del **espacio de la solución**. Para lograrlo, recomienda utilizar herramientas como:

1. **La técnica de los 5 porqués:** Para indagar de manera iterativa hasta hallar la causa raíz de la situación.
2. **La técnica de los 6 sombreros para pensar:** Para evaluar el escenario desde múltiples puntos de vista.

---
