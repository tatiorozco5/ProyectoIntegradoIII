# Proyecto Integrado III

## Enlaces
- Planner: https://github.com/users/tatiorozco5/projects/3
- Repositorio: https://github.com/tatiorozco5/ProyectoIntegradoIII.git
- Google Colab: https://colab.research.google.com/drive/1iV63Iy-8FO_D7eFZI8G1ChEUIEfh_pu1?usp=sharing
- Dataset: https://www.datos.gov.co/Ambiente-y-Desarrollo-Sostenible/Actividades-de-apoyo-realizadas-por-las-Fuerzas-Mi/shu7-uqse/about_data

## Título del proyecto

Análisis de las actividades de apoyo realizadas por las Fuerzas Militares en temas ambientales y de desarrollo sostenible en Colombia.

## Descripción del problema

En Colombia, muchas zonas del país presentan problemáticas ambientales relacionadas con la deforestación, minería ilegal, tráfico de fauna, contaminación de fuentes hídricas y ocupación indebida de áreas protegidas. Para enfrentar estas situaciones, las Fuerzas Militares desarrollan actividades de apoyo orientadas a la protección del medio ambiente y los recursos naturales.
Sin embargo, no siempre existe un análisis detallado que permita identificar cómo se distribuyen estas actividades en el territorio, cuáles departamentos presentan mayor intervención, qué tipos de acciones son más frecuentes y cómo ha evolucionado el apoyo ambiental a lo largo del tiempo. La ausencia de este análisis dificulta la toma de decisiones estratégicas y la priorización de recursos para la protección ambiental.
El dataset seleccionado contiene información sobre las actividades de apoyo realizadas por las Fuerzas Militares en temas ambientales en Colombia, lo que permite realizar un análisis exploratorio para identificar patrones, tendencias y zonas de mayor intervención.
Además, este análisis puede servir como apoyo para entidades gubernamentales y organizaciones ambientales interesadas en evaluar el impacto de las acciones de protección ambiental y fortalecer las estrategias de sostenibilidad y conservación del territorio colombiano.

## Objetivo
Analizar las actividades de apoyo ambiental realizadas por las Fuerzas Militares en Colombia mediante técnicas de exploración de datos, con el fin de identificar patrones, tendencias y distribución geográfica de las intervenciones ambientales registradas en el dataset.

## Objetivos especificos

-	Identificar los departamentos o regiones con mayor número de actividades ambientales registradas. 
-	Analizar cuáles son los tipos de actividades de apoyo más frecuentes. 
-	Evaluar el comportamiento temporal de las actividades registradas. 
-	Detectar posibles patrones o concentraciones de actividades ambientales. 
-	Generar visualizaciones y métricas que permitan comprender el impacto y alcance de las intervenciones.

## Pregunta de investigación

¿Qué departamentos presentan mayor concentración de actividades ambientales y cuáles son las intervenciones más utilizadas por las Fuerzas Militares para apoyar la protección ambiental en Colombia?

## Métricas para evaluar el éxito del análisis
Para evaluar el éxito del análisis se utilizarán las siguientes métricas:

- Número de actividades por departamento:	Permite identificar las regiones con mayor concentración de actividades ambientales
- Frecuencia por tipo de intervención:	Ayuda a determinar cuáles son las actividades ambientales más realizadas
- Tendencia temporal de actividades:	Permite analizar el comportamiento y evolución de las actividades a través del tiempo
- Calidad de los datos:	Evalúa la presencia de valores nulos, duplicados y consistencia de la información
- Hallazgos y visualizaciones generadas:	Mide la capacidad del análisis para identificar patrones y representar la información de forma clara


## Impacto esperado del proyecto

Se espera que este proyecto permita identificar los departamentos con mayor concentración de actividades ambientales realizadas por las Fuerzas Militares, así como reconocer las intervenciones más frecuentes utilizadas para apoyar la protección del medio ambiente en Colombia.
Además, el análisis facilitará la detección de patrones geográficos y temporales en las actividades registradas, contribuyendo a una mejor comprensión del comportamiento de las acciones ambientales desarrolladas en el país.
A partir de las métricas y visualizaciones generadas, el proyecto aportará información útil para apoyar la toma de decisiones, fortalecer estrategias de sostenibilidad y promover el uso del análisis de datos como herramienta para el seguimiento y evaluación de iniciativas ambientales.


## Fuente de datos principal

- Nombre del dataset:	Actividades de apoyo realizadas por las Fuerzas Militares en temas ambientales
- Fuente: Portal de Datos Abiertos del Gobierno de Colombia
- Origen:	https://www.datos.gov.co
- Enlace del dataset: https://www.datos.gov.co/Ambiente-y-Desarrollo-Sostenible/Actividades-de-apoyo-realizadas-por-las-Fuerzas-Mi/shu7-uqse/about_data
- Tipo de acceso: Datos abiertos públicos
- Formato disponible: CSV, JSON, API
- Formato utilizado en el proyecto:	CSV
- Entidad responsable:	Ministerio de Defensa Nacional / Datos Abiertos Colombia
- Temática:	Medio ambiente y sostenibilidad
- Idioma:	Español

## Descripción del dataset
El dataset contiene información relacionada con las actividades de apoyo desarrolladas por las Fuerzas Militares de Colombia en temas ambientales. Los registros permiten identificar aspectos como:
-	Tipo de actividad realizada. 
-	Lugar o departamento donde se ejecutó la actividad. 
-	Fecha de registro. 
-	Información relacionada con operaciones de apoyo ambiental. 
-	Datos de seguimiento y control ambiental. 

La información será utilizada para realizar un análisis exploratorio de datos (EDA) mediante Python y Pandas Profiling, con el fin de identificar patrones, tendencias y comportamiento de las actividades ambientales reportadas.

## Tamaño del dataset

- Número de filas: 1858
- Número de columnas: 11
- Tipo de datos:	Datos tabulares estructurados
- Nivel de actualización:	Dataset actualizado periódicamente por la entidad oficial

# Evidencia de Aprendizaje 2

## I. DESCRIPCIÓN DE NECESIDADES DE LIMPIEZA 

## Necesidades de limpieza identificadas (antes de ejecutar el código):

1. **Duplicados**: El dataset puede contener filas completamente duplicadas debido a cargas múltiples.  
   - Acción: Eliminar duplicados exactos.

2. **Valores nulos**:  
   - `ENTIDAD VINCULADA`: ~12% nulos. Columna categórica relevante para agrupar.  
   - `CANTIDAD DE MEDIOS EMPLEADOS`: ~1.2% nulos. Variable numérica crítica.  
   - `MEDIOS EQUIPOS/PLATAFORMAS EMPLEADOS`: pocos nulos (2 filas).  
   - Fechas (`FECHA DE INICIO`, `FECHA FINAL`): ~2.5% nulos. Esenciales para análisis temporal.  
   - Acción: Imputar categóricas con 'No especificada', numéricas con mediana (robusta a outliers), fechas nulas se eliminan (pocas).

3. **Inconsistencias en valores**:  
   - `DEPARTAMENTO`: mezcla de mayúsculas/minúsculas, 'Bogota D.C.' vs 'Bogotá D.C.'.  
   - `PROCESO DE GESTIÓN DEL RIESGO`: variaciones en mayúsculas.  
   - Acción: Estandarizar con diccionarios y `replace()`.

4. **Tipos de datos**:  
   - Fechas están como `object` → convertir a `datetime`.  
   - Variables categóricas (`DEPARTAMENTO`, `PROCESO`, `ENTIDAD VINCULADA`) → tipo `category` para optimizar memoria.  
   - Numéricas (`CANTIDAD DE MEDIOS EMPLEADOS`, `PERSONAL EMPLEADO`) → `int` o `float`.

5. **Valores atípicos (outliers)**:  
   - En `CANTIDAD DE MEDIOS EMPLEADOS` y `PERSONAL EMPLEADO`. Visualizar con boxplots.  
   - Criterio: No eliminar automáticamente; evaluar si representan eventos reales (ej. desastre grande). Se aplicará **winsorización** (limitar al percentil 99) para no perder información extrema válida.

6. **Granularidad**:  
   - Original: cada fila es una actividad específica (fecha, lugar, proceso).  
   - Necesidad para responder la pregunta: nivel **mensual por departamento y proceso**.  
   - Acción: Agrupar con `groupby` sumando medios y personal, contando actividades.


