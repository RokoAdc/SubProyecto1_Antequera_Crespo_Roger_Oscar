# SubProyecto1_Antequera_Crespo_Roger_Oscar
SubProyecto1 Maestria en Ciencia de Datos

# Predicción de Precios de Bienes Raíces en Australia - Regresión Avanzada

## Índice

- [Índice](## Índice)
- [Introducción](## Introducción)
 -[Métodos Utilizados](### Métodos Utilizados)
 -[Tecnologías](### Tecnologías)
-[Descarga y Configuración]## (Descarga y Configuración)
 -[Requisitos Previos](### Requisitos Previos)
-[Declaración del Problema](## Declaración del Problema)
 -[Objetivo Comercial](### Objetivo Comercial)
-[Procesos y Análisis](## Procesos y Análisis:)
 -[Configuración e Instalación](### Configuración e Instalación)
 -[Entendimiento de los Datos](### Entendimiento de los Datos)
 -[Análisis de Datos](### Análisis de Datos)
 -[Manipulación y Limpieza de Datos](### Manipulación y Limpieza de Datos)
 -[Preparación de Datos y Modelado](### Preparación de Datos y Modelado)
 -[Construcción del Modelado](### Construcción del Modelado)
 -[Ridge Regression](#### Ridge Regression)
 -[Lasso Regression](#### Lasso Regression)
 -[ElasticNet Regression](#### ElasticNet Regression)
 -[Las Variables Más Significativas Son:](#### Las Variables Más Significativas Son:)
 -[Conclusiones](### Conclusiones)

## Introducción

El siguiente trabajo realizado está orientado a la predicción de precios de bienes raíces tomando en cuenta un dataset de Australia. Para tal motivo se utiliza la Regresión Avanzada mediante 3 modelos que son básicos en este ámbito que son Regresión Ridge, Lasso y Elastic Net.
Para tal motivo se realizará un análisis de la data, un tratamiento de la misma y la evaluación de todos los modelos para ver cual se ajusta mejor a los datos.
La regresión avanzada mejora de la precisión de las predicciones: Las técnicas de regresión avanzada, como la regresión polinómica, la regresión Ridge, la regresión Lasso, la regresión Elastic Net, entre otros, pueden capturar relaciones no lineales y patrones más complejos en los datos, lo que a menudo resulta en predicciones más precisas.
Manejo de multicolinealidad: Cuando las variables predictoras están altamente correlacionadas entre sí, la regresión avanzada, como la regresión Ridge y Lasso, puede ayudar a reducir la multicolinealidad y mejorar la estabilidad de los coeficientes del modelo.
Selección de características: Algunas técnicas avanzadas, como Lasso y Elastic Net, pueden utilizarse para realizar selección automática de características, lo que significa que el modelo seleccionará automáticamente las características más relevantes y eliminará las menos importantes.
Regularización: Las técnicas avanzadas a menudo incluyen términos de regularización (como la regularización L1 y L2) que ayudan a prevenir el sobreajuste y a mejorar la capacidad del modelo para generalizar a nuevos datos.

### Métodos Utilizados
Entre los métodos que se utilizan tenemos la Regresión Ridge, Lasso y Elastic Net
Regresión Ridge: La regresión Ridge introduce un término de penalización L2 en la función objetivo para evitar el sobreajuste. Ayuda a controlar la multicolinealidad al reducir los coeficientes de características menos importantes, lo que puede mejorar la estabilidad del modelo.
Regresión Lasso: La regresión Lasso introduce un término de penalización L1 en la función objetivo. Además de evitar el sobreajuste y la selección de características, Lasso puede usarse para realizar una selección automática de características al establecer algunos coeficientes a cero.
Regresión Elastic Net: Elastic Net combina las penalizaciones L1 y L2 de Ridge y Lasso, lo que permite un enfoque más equilibrado entre la regularización y la selección de características.

### Tecnologías
El proyecto esta programado en Python por lo cual requerimos las siguientes librerías base:
* Python
* Pandas
* Matploit
* Seaborn
* sklearn con sus respectivos modelos

## Descarga y Configuración

### Requisitos Previos
Este proyecto necesita Google COLAB para su ejecución. 
Para este motivo se debe ingresar al siguiente Link:
https://colab.research.google.com/?hl=es
Dentro de este enlace se deberá escoger Nuevo Cuaderno para empezar con el proyecto.
El correr el código dentro de este notebook será mucho más ágil ya que no utilizaremos recursos de nuestro pc en sí. 
Una vez terminado el código debemos dirigirnos a la sección “Archivo” y desde ahí “Descargar” el archivo. ipynb para poder ejecutar en cualquier ambiente.

## Declaración del Problema
Una empresa de vivienda con sede en EE. UU. llamada Surprise Housing ha decidido ingresar al mercado australiano. La empresa utiliza el análisis de datos para comprar casas a un precio inferior a sus valores reales y venderlas a un precio más alto. Con el mismo propósito, la empresa ha recopilado un conjunto de datos de la venta de casas en Australia. Los datos se proporcionan en el archivo CSV a continuación.
La compañía está buscando posibles propiedades para comprar e ingresar al mercado. Debe construir un modelo de regresión utilizando la regularización para predecir el valor real de las posibles propiedades y decidir si invertir en ellas o no.

### Objetivo Comercial

La empresa quiere saber:
Qué variables son significativas para predecir el precio de una casa, y
Qué tan bien esas variables describen el precio de una casa.
Además, determine el valor óptimo de lambda para la regresión de Ridge y Lasso.



## Procesos y Análisis:

### Configuración e Instalación.
Dentro de este punto se extraen las librerías necesarias para el proyecto. 
### Entendimiento de los Datos.
Acá en primer lugar extraemos la información de nuestros datos para verificar que tipo de datos son. Entre ellos podemos encontrar datos int64, float64 y object, es decir, valores numéricos y categóricos.
Posterior a verificar los datos, verificamos cuantos valores nulos tenemos en nuestro dataset. Al tener una gran cantidad de variables es conveniente extraer información porcentual de aquellas variables que contienen valores nulos. Se aplica un gráfico para visualización de aquellas variables. Si bien tenemos un valor significativo, hay algunas variables que requieren un tratamiento especial como la variable PoolQC ya que muchos de estos datos faltantes en si no lo son ya que representan valores vacíos o 0.
### Análisis de Datos.
En primer lugar, debemos eliminar la variable Id ya que esta variable contiene datos únicos por lo que no es una característica informativa.
Dentro de este punto también realizamos un análisis univariable. En este caso aplicaríamos esto a la variable dependiente ya que debemos verificar si esta tiene un comportamiento Normal.
Una vez verificada que nuestra variable SalePrice tiene un sesgo, debemos aplicar una función que permita normalizar nuestra variable.
Una de las suposiciones fundamentales de muchos modelos estadísticos es que las variables siguen una distribución normal o aproximadamente normal. Cuando una variable tiene un comportamiento no normal, como una distribución sesgada o asimétrica, la aplicación de una transformación logarítmica puede ayudar a acercarla a una distribución más normal.
Una vez verificado la variable dependiente procedemos a analizar las variables independientes para verificar cuales son categóricas y cuales son numéricas.
Después procedemos a verificar el grado de asociación que tienen nuestras variables para ver si es posible aplicar la regresión al modelo ya que si no tuviera una correlación entre variables podríamos definir que la regresión no es ideal para predecir el comportamiento de la información.
Claramente se puede ver que si existen factores principales que hacen que nuestra variable dependiente SalePrice sea afectada por otras en gran y menor medida.
Con las variables con mayor valor como OverallQual o GrLivArea, procedemos a analizar gráficos que permitan ver la dependencia de estas variables.

### Manipulación y Limpieza de Datos.
Como se menciono anteriormente, dentro de nuestro dataset tenemos valores que en si no son nulos. Estos valores tienen el valor de 0 o son valores vacíos. 
Es por tal motivo que aquellos registros serán llenados con los valores ya mencionados.
Posterior a dicho proceso, llenaremos con la moda y mediana aquellos valores que si sean nulos. 
Cuando hablamos de regresiones, debemos contar con datos que son paramétricos, es decir, que nuestros valores categóricos deben ser tratados ya que de otra forma solo tomaríamos nuestros valores numéricos para el análisis del dataset.
Es por eso que a través de labelencoder codificaremos etiquetas categóricas en valores numéricos para posteriormente crear variables ficticias mediante dummies.
### Preparación de Datos y Modelado.
En este paso simplemente dividimos nuestro dataset en datos de training y datos de testing. Ya que normalizamos nuestra variable dependiente en un inicio, también debemos realizarlo en este punto con todas nuestras variables independientes y es por tal motivo que se realizara una estandarización. 
### Construcción del Modelado
Se debe incluir las librerías necesarias para poder ejecutar los modelos a los datos definidos.
Como se menciono anteriormente utilizaremos 3 Regresiones y posterior a eso poder analizar cual de estos es mejor para nuestra data.
Para poder medir el mejor modelo aplicable a nuestra información utilizaremos las métricas comunes utilizadas para evaluar el rendimiento de modelos de regresión.
El MSE mide el promedio de los errores cuadrados entre las predicciones del modelo y los valores reales en el conjunto de prueba. Cuanto menor sea el valor del MSE, mejor será el ajuste del modelo a los datos.
R^2 es una medida que indica la proporción de la varianza en la variable dependiente que es explicada por el modelo. Es un valor entre 0 y 1, donde 0 indica que el modelo no explica nada de la varianza en los datos, y 1 indica que el modelo explica toda la varianza. Cuanto más cercano a 1 sea el valor de R^2, mejor será el ajuste del modelo a los datos.
En el contexto de Regresion, "alpha" (también conocido como "lambda" en algunos contextos) es un hiperparámetro que controla la regularización en el modelo. La regularización es una técnica utilizada en el aprendizaje automático para prevenir el sobreajuste (overfitting), que ocurre cuando un modelo se ajusta demasiado a los datos de entrenamiento y tiene dificultades para generalizar bien a datos nuevos o no vistos.
#### Ridge Regression
En este caso nuestro Alpha, con datos estandarizados, tiene un valor de:
Optimal Alpha: 100.0
Una vez calculado nuestro Alpha o lambda procedemos a aplicar el modelado para obtener 2 valores cruciales en la regresión que son MSE y R^2
Ridge MSE: 0.10695084917449449
Ridge R^2: 0.8930491508255055
#### Lasso Regression
En el caso de Lasso obtenemos el siguiente valor para Alpha:
Optimal Alpha: 0.01
Es por tanto que nuestro MSE y R^2 seran:
Lasso MSE: 0.09872436502535398
Lasso R^2: 0.901275634974646
#### ElasticNet Regression
Para Elstic Net necesitamos 1 valor aparte de Alpha el cual es L1 Ratio.
El parámetro L1_ratio en el contexto de la regresión Elastic Net representa la mezcla entre la penalización L1 (Lasso) y la penalización L2 (Ridge) en el modelo.
Por tanto, obtenemos los siguientes valores:
Optimal Alpha: 0.1
Optimal L1 Ratio: 0.1
Es asi que podemos calcular MSE y R^2:
Elastic Net MSE: 0.09867881547538596
Elastic Net R^2: 0.9013211845246141
#### Las Variables Más Significativas Son:
Según nuestro diagrama de correlación y el análisis que se realizaron a cada una de esas variables podemos ver que las variables mas importantes para la predicción del precio de un bien raíz en Australia son:
* OverallQuall
* TotalBsmtSF
* 1stFlrSF
* GrLivArea
* GarageCars
* GarageArea

### Conclusiones

En cuanto al valor MSE podemos deducir que nuestro modelo de Regresión Lasso y Elastic Net tienen mejores resultados.
En cuanto a R2 de la misma forma podemos deducir que ambos modelos hacen que nuestros valores se ajusten mucho mejor que Ridge.
En sí, se puede deducir que el modelo ganador seria Elastic Net. Esto debido a que dicha regresión combina las penalizaciones de Ridge y Lasso. Elastic Net encuentra un equilibrio entre la selección de características y la estabilidad del modelo. 
Cuando se tiene características altamente correlacionadas en los datos, Ridge y Lasso pueden tener problemas para manejar la multicolinealidad. Elastic Net es más robusto en este sentido porque puede incluir características correlacionadas en el modelo, aunque con coeficientes más pequeños.
Elastic Net proporciona un mayor control sobre el sobreajuste en comparación con Ridge, ya que la penalización L1 ayuda a reducir aún más la complejidad del modelo y eliminar características menos relevantes. Esto puede ser ventajoso en conjuntos de datos grandes con muchas características, donde es fundamental evitar el sobreajuste.
En el caso nuestro, si vemos que existen variables que no son relevantes por lo que en un futuro se podría ampliar dicho análisis y se podría eliminar esas variables para poder obtener datos más exactos.

