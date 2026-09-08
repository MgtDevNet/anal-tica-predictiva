# Analítica vs Machine learning
**Analítica**: Es aplicación a la data para tomar mejores decisiones en organizaciones por medio de estadística, machine learning o deep learning. Su objetivo final es tomar buenas decisiones para mejorar la empresa y tiene un resultado económico, no es simplemente un caso práctico de machine learnig cualquiera. No es simplemente hacer un modelo, es ver que el modelo mejore mis métricas como empresa para mejorar.  

Por ejemplo, por medio de estadística, machine o deep learning poder identificar y tratar de solucionar la razón y el donde se generan las caídas de la aplicación de bancolmbia para reducir el tiempo en minutos de la aplicación caída y reducir la cantidad de dinero generada por multas debido a esto. Notese que el objetivo es reducir el índicador del tiempo en minutos de la aplicación caída y por ende reducir la cantidad de dinero a pagar ante la super intendencia.

Entender los modelos por debajo y de una manera matemática es el trabajo de un ingeniero de machine learning, no de una persona de analítica. Es necesario, pero no es el objetivo de la analítica. 

**¿ Como yo con la data puedo tomar mejores decisiones?** resolver o ayudar a resolver un problema organizacional. Correr una herramienta no significa hacer analítica, una persona que sabe correr un modelo de machine learning no significa hacer analítica. 

## Página de cursos profesor
[cursos](jdvelasq.github.io/courses)

Además, el profesor dará acceso al datacampo por lo que es recomendable hacer los cursos y tracks principalmente en lo que estemos más flojos y sacar las certificaciones. En caso de que se acabe el tiempo, se puede hablar con el para volver a habilitar el datacamp. 

Hay que estar a la par con la información y teoría que esta presentada en los cursos para las clases. Va muy de la mano con minería de datos. 

Sería bastante útil tener estudiado el tema de la proxima sesión. 

También recomienda la página de pluralsight luego de terminar con datacamp, pues data camp es bastanta básico. Además, las personas que dan los cursos en pluralsight son personas muy tesas y tiene muy buenos tracks. 

[https://www.pluralsight.com/](pluralsight)

 
# Clase 1
## ¿Por qué las organizaciones necesitan analítica?

En las organizaciones hay 2 tipos de tareas: 

1. Repetitivas: simples y no requiren un habilidad cognitiva compleja, pero pueden ser aburridoras y el volumenes grande puede ser desbordante. Por tanto, lo que puede ser decisivo es el volúmen de los datos. 

2. Complejas: requieren un pensamiento complejo y experiencia que requieren habilidades cognitivas complejas. Tiene sesgos mentales y subjetividad. 

¿Inteligencia? la entendemos como características que exhiben los seres inteligentes. Capacidad de **ver relaciones** que permanecen ocultar entre los demás. Es lo que hace una persona exitosa para ver ese tipo de problemas. 

Nosotros tenemos grándes volúmenes de datos con conocimiento implícito que con analítica puedo descubrir patros e insights y con esto poder tomar decisiones informadas, objetivas y oportunas que ayuden a mi organización y generar valor. 

**LA ANALÍTICA TRANSFORMA DATOS EN CONOCIMIENTO PARA APOYAR MEJORES DECISIONES**

¿Cómo aporta valor la analítica en las organizaciones?

Los sistemas de recomendación, identificación de clientes con características específicas, identificación de fallas, etc es lo que puede conseguirse gracias a la analítica. 

**Definición de analítica predictiva**: Rama de conocimiento enfocada en el uso de métodos estadíticos, minería de datos y aprendizaje de máquinas apra construir modelos que, a partir de datos históricos y actuales, estiman resultados, comportamiento o eventos aún no observados. Luego, la analítica predictiva aprende patrones a partir de datos conocidos para estimar resultados aún no observados. 


Desde tiempos ancestrales se ha querido predecir diferentes tipos de situaciones, por ello, entra el surgimiento de la neurociencia: 

¿Cómo aprende el cerebro a partir de la experiencia?

El aprendizaje se produce mediante la modificación de jla eficiencia de las conexiones interneuronales (y la creación de nuevas conexiones) para la transmisión de impulsos electroquímicos, lo que modula tanto la percepción como la respuesta antes los estímulos del medio.
El aprendizaje puede entenderse como un proceso de **adaptación de las conexiones entre neuronas**

¿Cómo puede representarse matemáticamente el comportamiento básico de una neurona biológica?

Una neurona puede representarse como como una unidad de cómputo que combina múltiples entradas y produce una salida según una regla de activaición 

Célula de McCulloch-Pitts: modelo matemático simplificado de una neurona aritificial que recibe varias entradas, las combinay produce una salida binaria según si la suma de dichas entradas supera un umbral. 

Este modelo permite representar patrones binarios, las entradas son x1, x2, x3 y F la salida

[!celula]()

cuando una conexión inhibitoria (apaga la neurona y esta en negro) vale 1 la salida de la neurona siempre es cero

y si el valor es menor al 1 dentro del círculo entonces es cero. 


El término de intelincia artificial, su conceptción inicial planteaba que aspectos del aprendizaje, el razonamiento y la inteligencia humana podían describirse formalmente y ser simulado por máquinas.

* Reconocimiento de imágenes. 
* Procesamiento de Lenguajes.
* Planteamiento,  monitoreo, diagnóstico y control.

* Predicciones. 

### Modelos de lentes de Brunswik
Como seres humanos ¿cómo poder hacer predicciones? el modelo de lentes e sun modelo de juicio y decisión que representa como una persona usa y combina múltiples señales observales e imperfectas del entorno para estimar una variable o estado qeno puede observar directamente. 

Resolver un problema puede representarse computacionalmente como la búsqueda de una secuencia de operaciones que transforme el estado actual en el estado objetivo

### Perceptrón de Rosenblatt
¿Como puede una máquina aprender automáticamente clasificar ejemplo a partir de los datos?

Perceptrón: Combina múltiples entradas ponderadas y ajustables y produce una salida mediante una función de decisión. Sus pesos se actualizan automáticamente a partir de los errores de clasificación observados durante el entrenamiento. Ya no se codifican las reglas sino que el sistema aprende la relación intrínseca que hay. 

La máquina ya no necesita recibir todas las reglas explíticamente: puede aprender una regla de clasificación ajustando sus parámetros a partir de ejemplos. 

### Adaptive Linear Combiner (ADALINE)
Modelo de neurona artificial que calcula una combinación lineal poderosa ...

### MADALINE (Multiple ADALINE)
Una de las primeras redes reuronales multicapa, desarrollada por Bernard Widrows y Marcian Hoff, formada por múltiples unidades ADALINE conectadas entre si para realizar tareas de clasificación y reconocimiento de patrones más complejas que las que puede abordar una sola neurona.

Reconocimiento invariante de patrones: Capacidad de un sistema para identificar un mismo patrón aunque su represetnación cambie debido a transformaciones como la traslación, la rotación o la escala. 

### sistemas expertos
¿como un amáquina usa el conocimiento de expertos humanos para resolver problemas especializados?

sis dema de IA basado en conocimiento que representa explicitamente la experiencia de especialistas mediante hechos y reglas (cálculo de predicados) y utiliza un mecanismo de inferencia para resolver problemas y apoyar decisiones en un dominio específico. 

Características: 

* Ampliamente usados. 
* Desarrollo rápido.
* Basjos costos de mantenimiento. 
* Mejoramiento fácil. 

los verdaderos problemas son: 

¿Como adquirir conocimiento de los expertos?
¿Cómo extraer conocimiento de na masa de datos previamente recolectada?
¿Cómo representar datos y conocimiento incompleos, ambiguos, incorrectos o contradictorios?

Sistemas expertos $\rightarrow$ experto $\rightarrow$ conocimiento
$\rightarrow$ reglas
$\rightarrow$ sistema

Aprendizaje a partir de datos: 

...

TAREA: Empezar a cubrir el material del curso con el tema de machine learning. 


-------------------------------------
### Durante décadas se intento enseñarles a las máquinas como pensar. Entonces empezamos a dejas que los datos les enseñaran

1989 - Data Minig: Descubrir patrones ocultos en grandes bases de datos (extraer conocmiento útil para tomas decisiónes): 
* Descubrimiento de reglas de asociación. 
* Clasificación. 
* Regresión.
* Agrupamiento. 
* Detección de anomalías.

En analística reemplaza la nueva pregunta del negocio por la construcción de un modelo que descubre el conocimiento dentro de los datos. 

1989 - KDD (Knowledge Discobery in Databases): Proceso iterativo para descrubrir conocimiento útil en bases de datos, que comprenden la selección, preparación, transformación, minería e interpretación de los datos. 

![imagen](/imágenes/proceso_kdd.png)


1995 - Statistitical Machine Learning: Enfoque para construri modelos que aprendan relaciones y patrones a partir de datos, utilizando principios estadísticos para realizar predicciones o clasificaciones y generalizar a observaciones no utilizadas durante el entrenamiento. Pero ojo, no conocemos la forma funcional de la relación entre las variables. 

1996 - CRISP-DM: Metologia estántdar para planificar, desarrollar e implementar proyectos de minería de datos, transformando problemas de negocio en soluciones analísticas mediante un proceso sistemático y repetible. Incorpora el entendimiento y estandariza el desarrollo de proyectos de minería de datos. El problema es que esta metología se creo bajo etapas de desarrollo de software viejas. 

![imagen](/imágenes/proceso_cris.png)

2001 - Ensemble Learning(Modelos de ensamble)
Ensemble learning (Aprendizaje por conjunto): Combina las predicciones de múltiples modelos para obtener un modelo conjutno con mayor precisión, estabilidad o capacidad de generalazación que sus componenete individuales. 

ejemplo: 

* Random Forest: Muchos árboles entrenados sobre muestras diferentes - votación promedio. 

* Gradient Boosting: árboles construidos secuencialmente, donde cada nuevo modelo intneta corregir los errores de los anteriores. 

En lugar de depedner de un solo modelos, los métodos de ensamble combinan múltiles modelos paramejorar la capacidad predictiva y de generalización.


Losa modelos ya podían aplicarse a la data mediante diferentes técnicas y algortimos. El siguiente problema era hacerlo a escala. Acá nacen las técnicas de big data. 

2005 - Hadoop/MapReduce

Big data: Grandes datos (definición circular) viene a resolver 2 cosas: 

1. se tiene una BD muy grande donde se hacen operaciones de lectura (lenta), escritura (más lenta aún) y búsqueda (más lenta que las dos anteriores)

¿como agilisarlo? Particionanndo la tabla en varios campos y establecimiento de campos para estas particiones

ejemplo: Si se tienen muchos estudiantes. particionar por la letra que empieze el nombre, se tendrán tantas tablas como letras del diccionario

Esto es lo que se llama **Almacenamiento distribuido**. Luego, cuando el cálculo es complejo lo que se quiere hacer es paralelizar para poder ser más eficiente y es lo que se conoce como **Procesamiento distribuido**. 

Los sistemas de big data COMBINAN AMBOS PARADIGMAS de tal manera que el sistema es más eficiente, pero también más propenso a fallos. 

![big data](/imágenes/big_data.png)

El corazón de la paralelización es el algoritmo MapReduce = mapper + reduce 


![map](/imágenes/map.png)

2006 - Business analytics: Campo interdisciplinario que integra datos, métodos mátemáticos, estadísticos y computacionesl con técnicas de simulación, optimización y apoyo  a la deicisión 

### Tipos de analítica

* Descriptiva: Análisis para toma de decisiones operativas

* Diagnóstica: Buscar la razón de un suceso. Identificar causas y factores. 

* Predictiva: uso de técnicas de modelatdo predictivo, aprendizaje de máquinas y minería de datos para pronósticas resultados de un proceso en un contexto organizacional. 

* Prescriptiva: Uso de técnicas de simulación , optimización y análisis de riesgo e incertidumbre para la toma de decisiones organizacionales. Es el paso donde se toman las decisiones a partir de las predicciones. 

predictiva me da el valor del futuro, pero prescriptiva me dice que se debe hacer para tomar las decisión optima.

2008 - pig latin
Apache Pig: Lenguaje de alto nivel similar a SQL que permite desarrollar aplicaciones para ele análisis de grandes volúmenes de datos automáticamente a programas. 

2009 - Datos semi-estructurados y datos NOSQL

Bases de dsatos NoSQL: sistemas de gestión de bases de datos no relcionales diseñados para almacenar graqdnes volúmenes de datos estructurados, semiestructurados. 

2009 - 2012 Open Data Sciencie
Movimiento basado en software de código abierto qeu impulsó la adopción de lenguajes como  python y R, junto con sus ecossitemas de bibliotecas, para el desarrollo de aplicaciones de ciencia de datos. 

![data science](/imágenes/data_science.png)

2011-2012 auge del deep-learnign
Usar redes neuronales aritifciales con múltiples capas para aprender representaciones jerárquiecas y patrones complejos a partir de gradnes volúmenes de datos, permitiendo realizar tareas e clasificación y regresión y generación de información

**Big Data Analytics**: Disciplina que aplica métodos matemáticos, estadísticos y computacionales para descubrir conocimiento, identificar patrones y apoyar la toma de decisiones medieante el análisis de grandes volúmenes dedatos estructurados, semi-estructurados y no estructurados.

Los algoritmos estadísticos y de machine learning comienzan a ejecutarse en arquitecturas distribuidas. 

spark es para manejar big data  en python, sin embargo, hay que usar también el deep learning

2014 - Apache Spark
Motor de procesamiento distribuido de código abierto que permite el proesamiento y análisis e datos mediante computación en memoria, y que soporta aplicaciones de analítica, aprendizaje autmático y procesamieknto de flujos de datos. 

Spark reconstruye el ecossitema de Big Data sobre una arquitectura de procesamiento en memoria. 

ejemplo: Cao de american express.

problema: identificar clietnes con riesgo de abandonar antes de que cancelen. 

predicción: probabilidad de que una cuenta se cierre proximamente. 

Decisión: Intervenir antes mediante acciones de retención. 

Resultado: Se logró identificar el 24% de las cuentas cerrarían en los proximos 4 meses en Australia. 

2015 - Tensorflow
Plataforma de código abierto para computación numérica y aprendizaje automático desarrollada por Google, que permite contruir, entrenar y ejecutar modelos mediante operaciones sobre tensores, aprovechando diferente recursos computaciones como CPU y GPU. Facilita la implementación los modelos 

2016 - Machine Learning Operations (MLops)
Disciplina que integra personas, procesos y tecnologías para automatizar, desplegar, monitorear y gestionar el ciclo de la vida de los modelos de aprendizaje automático, garantizand su calidad, reproducibilidad, confiabilidad y operación continua en entornos de producción 

* Unifica el ciclo de machine learning y liberación de software. 

* Pruebas automáticas de artefactos en ML (validación, pruebas de modelos)

...

2023 - 2024 - Multimodal Foundation Models
Modelo capaz de procesar, relacionar y genrar información proveniente de múltiples modadlidades

2025-2026 AI augmented Predective Modeling
Ayudar a crear, evaluar e interpretar modelos predictivios

La analítica predictiva evoluciónó desde construir máquinas capaces de anticipar resultado hasta construir ecosistemas capaces de aprender de los datos y asistir al analista 

---------------------------------
Nota: ojo, para las clases hay que estudiar previamente el material del curso. 

Cerca de 3 horas de video por semana. 

