# telecom-analysis
Sprint 6 - Final Project. Analisis de ConnectaTel. Empresa de Telecomunicaciones ops en Mexico y Colombia. analisis de segmento de clientes vs uso de llamadas y sms, comportamientos atipicos (fraudes, errores), comportamiento por edad, identificacion de patrones para diseñar planes, optimizacion de oferta y satisfaccion de cliente. 


Análisis de Comportamiento y Segmentación de Clientes - ConnectaTel

Objetivo del Proyecto

Este proyecto analiza cómo usan realmente los servicios móviles (llamadas y mensajes) los clientes de ConnectaTel en México y Colombia, tomando datos registrados hasta el año 2024. La idea principal es entender los patrones de consumo según el tipo de plan y la edad, detectar usuarios con comportamientos fuera de lo común y dividir la base de clientes en grupos claros para proponer mejoras en los planes actuales y estrategias de retención.

Datasets Utilizados

Para el análisis se integraron tres tablas principales:

plans.csv (2 filas, 8 columnas): Contiene la información comercial de los planes disponibles (Basico y Premium), su precio mensual, los minutos, mensajes y GB incluidos, y el costo por consumo adicional.

users_latam.csv (4,000 filas, 8 columnas): Reúne los datos de cada cliente, como su identificador, nombre, edad, ciudad, fecha de registro, plan contratado y fecha de cancelación en caso de haber dado de baja el servicio.

usage.csv (40,000 filas, 6 columnas): Registra el historial real de actividad de los usuarios, detallando cada llamada (con su duración en minutos) y cada mensaje enviado (con su longitud en caracteres).

Etapas del Análisis

El trabajo se desarrolló paso a paso siguiendo este flujo:

Carga y revisión inicial: Importación de las tres bases de datos en Python y revisión de su estructura, columnas y tipos de datos.

Revisión de calidad de datos: Búsqueda de valores faltantes, datos erróneos o de relleno (-999 en la edad y "?" en la ciudad) y fechas fuera de rango (registros del año 2026 en las fechas de alta).

Limpieza y estandarización: Reemplazo de las edades inválidas por la mediana (48 años), conversión de los símbolos "?" y fechas futuras a valores nulos para no distorsionar los cálculos, y verificación de los nulos esperados en llamadas y mensajes.

Resumen de consumo por cliente: Agrupación de toda la actividad de usage.csv por usuario para calcular el total de mensajes, llamadas y minutos consumidos, uniendo luego esa información con la tabla de clientes.

Gráficos de distribución y valores atípicos: Creación de histogramas por tipo de plan y diagramas de caja (boxplots) para identificar qué variables tienen consumos extremos y evaluar sus límites mediante el rango intercuartílico (IQR).

Segmentación de clientes: Clasificación de los usuarios según su nivel de actividad (Bajo uso, Uso medio y Alto uso) y por rangos de edad (Joven, Adulto y Adulto Mayor), visualizando el peso de cada grupo.

Conclusiones y recomendaciones: Resumen ejecutivo con los hallazgos principales y sugerencias prácticas para mejorar la oferta comercial y la captura de datos de la empresa
