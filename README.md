# Challenge-Telecom
README: Análisis de Evasión de Clientes (Churn)
Introducción
Este proyecto tiene como objetivo identificar los factores clave que influyen en la evasión de clientes (Churn) de una empresa de telecomunicaciones, con el fin de desarrollar un modelo predictivo para mitigar este problema.

Limpieza y Tratamiento de Datos
Se realizó un proceso ETL (Extract, Transform, Load) comenzando con un Análisis Exploratorio de Datos (EDA). Se normalizaron las columnas anidadas utilizando json_normalize para facilitar el análisis. Se identificaron y trataron valores en blanco o vacíos en las columnas 'Churn' (224 vacíos) y 'account.Charges.Total' (11 vacíos), reemplazándolos con valores medios apropiados.

Análisis Exploratorio
Se visualizaron patrones de comportamiento de la variable Churn en relación con las siguientes variables:

Género: No se observó una incidencia significativa.
Edad: Hombres mayores de 60 años presentan una tasa de deserción del 71%.
Tiempo de permanencia (Tenure): Fuerte evasión al inicio de los contratos (60% entre 0 y 1 mes).
Tipo de Contrato: El contrato mes a mes presenta un 43% de abandono.
Tipo de Servicio (Internet Streaming): Los clientes sin servicio tienen un abandono ligeramente mayor (34%) que los que sí lo tienen (30%).
Método de Pago: El "Electronic check" presenta una tasa de evasión del 45%.
Conclusiones
Las variables más relevantes que inciden en el Churn son:

Edad: Mayor en hombres mayores de 60 años.
Tiempo de permanencia: Mayor al inicio del contrato.
Tipo de Contrato: Mayor en contratos mes a mes.
Método de Pago: Mayor en "Electronic check".
Tipo de Servicio: Ligeramente mayor en quienes no tienen Internet Streaming.
El análisis de correlación numérica confirmó que la edad del cliente y el cargo mensual tienen correlación positiva con el Churn, mientras que el tiempo de permanencia tiene correlación negativa.

Recomendaciones
Basado en el análisis, se proponen las siguientes recomendaciones para reducir la evasión de clientes:

Eliminar "Electronic check" como opción de método de pago.
Eliminar o desincentivar los contratos mes a mes, promoviendo contratos de mayor duración.
Ofrecer promociones o períodos de prueba gratuitos (3 a 6 meses) para el servicio de Internet con el fin de fidelizar a los clientes.
Problemas y Soluciones Encontrados
Problema: Columnas con datos anidados.
Solución: Uso de json_normalize para extraer la información.
Problema: Valores en blanco o vacíos en 'Churn' y 'account.Charges.Total'.
Solución: Reemplazo con valores NaN y posterior imputación con valores medios.
Dependencias
Las siguientes bibliotecas fueron utilizadas en este proyecto:

pandas
requests
plotly
numpy
