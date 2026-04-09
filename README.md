# Proyectos-
Depositarios de Proyectos realizados con Python para  Ciencia de Datos
Descripción del proyecto
Trabajas para la tienda online Ice que vende videojuegos por todo el mundo. 

Las reseñas de usuarios y expertos, (user_score, critic_score) los géneros, las plataformas (por ejemplo, Xbox o PlayStation) y los datos históricos sobre las ventas de juegos están disponibles en fuentes abiertas. Tienes que identificar patrones que determinen si un juego tiene éxito o no. 
Identificar plataforma 

Esto te permitirá detectar proyectos prometedores y planificar campañas publicitarias.

Delante de ti hay datos que se remontan a 2016. Imaginemos que es diciembre de 2016 y estás planeando una campaña para 2017.

Lo importante es adquirir experiencia de trabajo con datos. Realmente no importa si estás pronosticando las ventas de 2017 en función de los datos de 2016 o las ventas de 2027 en función de los datos de 2026.

El dataset contiene una columna "rating" que almacena la clasificación ESRB de cada juego. El Entertainment Software Rating Board (la Junta de clasificación de software de entretenimiento) evalúa el contenido de un juego y asigna una clasificación de edad como Adolescente o Adulto.
Instrucciones para completar el proyecto

- [x] Paso 1. Abre el archivo de datos y estudia la información general
Ruta de archivo:
/datasets/games.csv . Descarga el dataset

Paso 2. Prepara los datos
- [x] Reemplaza los nombres de las columnas (ponlos en minúsculas).
- [x] Convierte los datos en los tipos necesarios.
- [x] Describe las columnas en las que los tipos de datos han sido cambiados y explica por qué.
- [x] Si es necesario, elige la manera de tratar los valores ausentes:
    - [x] Explica por qué rellenaste los valores ausentes como lo hiciste o por qué decidiste dejarlos en blanco.
    - [x] Year, crític score , user score , rating 
    - [x] ¿Por qué crees que los valores están ausentes? Brinda explicaciones posibles.

1) No se registró el dato
El dato nunca se capturó
2) No aplica
El dato no tiene sentido para ese registro
Ejemplo:
Ventas en Japón = 0 o vacío porque el juego nunca salió ahí
3)Falta de disponibilidad histórica
Datos antiguos incompletos
Ejemplo:
Juegos viejos sin critic_score

En year_of_realise se completa algunos años tomando en cuenta el año que se indica en name para imputar 

La suma de las ventas globales para años ausentes solo representa el 0,01% de las ventas globales por lo que podemos rellenar lo que está en blanco por cero o eliminarlas completamente, se decide eliminar para que el cero no nos afecte el promedio.

Se declara una nueva variable llamada popularidad en donde esta es la razón entre las ventas globales y el número de juegos que se tuvieron por año esto representa la penetración que se tiene en el mercado por plataforma.

De igual manera realizar agrupaciones por marca en vez de plataforma dado que son menos variables concentradas 31 agrupaciones obtenidas de plataforma vs 6 De marca 
    * Presta atención a la abreviatura TBD: en user_score significa "to be determined" (a determinar). 
    * Se remplaza vacíos por la mediana obtenida por cada año 
    * En rating se remllaza valores por moda jerárquica 
    * Especifica cómo piensas manejar estos casos.
- [x] Calcula las ventas totales (la suma de las ventas en todas las regiones) para cada juego y coloca estos valores en una columna separada.Se llama global_sales

Paso 3. Analiza los datos
- [x] Mira cuántos juegos fueron lanzados en diferentes años. ¿Son significativos los datos de cada período? , agrupamiento de year of release y contar usar un valué counts.

Primero: compara contra un promedio o tendencia

✔️ Idea:

Si un año tiene muchos más juegos que el promedio → probablemente es significativo.
egla clásica:
	•	media + 1σ → alto
	•	media + 2σ → muy significativo (outlier)
  Se usó técnica de agrupamiento por top , media y Lower incluida en la base de datos 

- [x] Gráfico de línea en donde se ve la tendencia de la venta de juegos cada año 
Cálculo de num_games por año 
- [x] Observa cómo varían las ventas de una plataforma a otra. Elige las plataformas con las mayores ventas totales y construye una distribución basada en los datos de cada año. Busca las plataformas que solían ser populares pero que ahora no tienen ventas. 
- [ ] ¿Cuánto tardan generalmente las nuevas plataformas en aparecer y las antiguas en desaparecer?
  Ciclo de vida de plataforma 
- [x] Determina para qué período debes tomar datos. Para hacerlo mira tus respuestas a las preguntas anteriores. Los datos deberían permitirte construir un modelo para 2017.
- [x] Trabaja solo con los datos que consideras relevantes. Ignora los datos de años anteriores.
- [x] ¿Qué plataformas son líderes en ventas? ¿Cuáles crecen y cuáles se reducen? Elige varias plataformas potencialmente rentables.
- [x] Crea un diagrama de caja para las ventas globales de todos los juegos, desglosados por plataforma. ¿Son significativas las diferencias en las ventas? ¿Qué sucede con las ventas promedio en varias plataformas? 
Se hizo por región jp, na, eu, other 

Describe tus hallazgos.
- [x] Mira cómo las reseñas de usuarios y profesionales afectan las ventas de una plataforma popular (tu elección). 

user_score, critic_score: indicador de reseñas 

- [x] Crea un gráfico de dispersión y calcula la correlación entre las reseñas y las ventas. 

Saca conclusiones.

* Teniendo en cuenta tus conclusiones compara las ventas de los mismos juegos en otras plataformas.
- [x] Echa un vistazo a la distribución general de los juegos por género. ¿Qué se puede decir de los géneros más rentables? ¿Puedes generalizar acerca de los géneros con ventas altas y bajas?

Paso 4. Crea un perfil de usuario para cada región
Para cada región (NA, UE, JP) determina:
- [x] Las cinco plataformas principales. Describe las variaciones en sus cuotas de mercado de una región a otra.
Se hace por marca : Gráfico de bigotes 
Nintendo , Sony y Microsoft

- [x] Los cinco géneros principales. Explica la diferencia.
- [x] Si las clasificaciones de ESRB afectan a las ventas en regiones individuales.
Aplicar 
Boxplots de ventas por rating
	•	Promedios / medianas de ventas por rating
	•	ANOVA si quieres probar si las medias cambian entre categorías
	•	Kruskal-Wallis si las ventas están muy sesgadas o llenas de outliers
	•	Eta cuadrada (η²) para medir qué tanto explica rating la variación de ventas

Importante
No conviertas rating a números tipo:
E=1, T=2, M=3
y luego saques correlación. Eso sería forzar un orden que no necesariamente existe. Sería como medir la elegancia de una corbata con regla de albañil.

Paso 5. Prueba las siguientes hipótesis:
- [x] — Las calificaciones promedio de los usuarios para las plataformas Xbox One y PC son las mismas.
- [x] — Las calificaciones promedio de los usuarios para los géneros de Acción y Deportes son diferentes.

Establece tu mismo el valor de umbral alfa.
Explica:
— Cómo formulaste las hipótesis nula y alternativa.
— Qué criterio utilizaste para probar las hipótesis y por qué.

Paso 6. Escribe una conclusión general
Formato: Completa la tarea en Jupyter Notebook. 
Descripción de datos
— Name (Nombre)
— Platform (Plataforma)
— Year_of_Release (Año de lanzamiento)
— Genre (Género)
— NA_sales (ventas en Norteamérica en millones de dólares estadounidenses)
— EU_sales (ventas en Europa en millones de dólares estadounidenses)
— JP_sales (ventas en Japón en millones de dólares estadounidenses)
— Other_sales (ventas en otros países en millones de dólares estadounidenses)
— Critic_Score (máximo de 100)
— User_Score (máximo de 10)
— Rating (ESRB)
Es posible que los datos de 2016 estén incompletos.

¿Cómo será evaluado mi proyecto?

Lee atentamente estos criterios de evaluación de proyectos antes de empezar a trabajar.

Esto es lo que buscan los revisores de proyecto cuando evalúan tu proyecto:

- [x] ¿Cómo describirías los problemas identificados en los datos?
- [x] ¿Cómo se prepara un dataset para el análisis?
- [x] ¿Cómo creas gráficos de distribución y cómo los explicas?
- [x] ¿Cómo calculas la desviación estándar y varianza?
- [x] ¿Formulas las hipótesis alternativas y nulas?
- [x] ¿Qué métodos aplicas a la hora de probarlos?
- [x] ¿Explicas los resultados de tus pruebas de hipótesis?
- [x] ¿Sigues la estructura del proyecto y mantienes tu código ordenado y comprensible?
- [x] ¿A qué conclusiones llegas?
- [x] ¿Has dejado comentarios claros y relevantes en cada paso?

Todo lo que necesitas para completar este proyecto se encuentra en las hojas informativas y los resúmenes de los capítulos anteriores.

Desarrollo:   
##Objetivo del proyecto:   
El objetivo de este proyecto es analizar la base de datos de los ventas de video juegos de la empresa Ice para diferentes plataformas como es Nintendo, Xbox, Wii, etc y que se han vendido a lo largo de diferentes años conforme a la preferencia de los compradores  en las regiones de Norteamérica, Europa, Japón y otras partes.   
 
La finalidad del estudio del análisis de la información es la de establecer  el top o ranking de los video juegos que más ventas hallan tenido a lo largo de estos años identificando los juegos que ya no se venden así como de los que actualmente se venden de manera consistente, identificar el tipo de género de video juego que se vendeu no con  más preferencia por parte de los compradores así como la identificación de algún patrón de compra y al final establecer alguna recomendación de estrategia de marketing o enfoque de venta que pueda implementar la empresa Ice para mejorar sus ventas.

Como parte del análisis de igual manera se desea saber si:

— Las calificaciones promedio de los usuarios user_score para las plataformas Xbox One y PC son las mismas.
— Las calificaciones promedio de los usuarios user_score para los géneros de Acción y Deportes son diferentes.
— Si las clasificaciones de ESRB afectan a las ventas en regiones individuales es decir en Norte América , Japón , Europa y otros.

Dentro de las herramientas de análisis se desarrollarán gráficos visuales y tablas estadísticas que permitan presentar la información analizada y llegar a conclusiones finales y recomendaciones.

Estrategia de análisis:
Como estrategia de análisis del proyecta se realiza en cuatro partes:

1.- Aplicación de proceso ETL (Extraction, Transformation and Load), para realizar la Carga del data frame, aplicar la Preparacion, Limpieza y Visualización preliminar de la estructura de los datos que conforma el data frame games, realizando  la consulta de las descripciones estadísticas básicas de cada columnas y tipo de dato empleado en cada una de ellas. 

En esta sección se  identificaran valores nulos y duplicados explícitos en todo el data frame identificado como  df_games y sus duplicados  implícitos que posiblemente existan en columnas name, genre y platform que por ser columnas del tipo texto se deba hacer una limpieza preliminar de caracteres de espacios (aplicación de métodos strip) y homologación a minúsculas (método lower) para poder agrupar de manera consistente y sin repeticiones. 
Lo anterior permite realizar un análisis adecuado de la información sin duplicados que sesguen el análisis.

2.- Análisis numérico de la información.
En esta sección se realizará la parte de la estadística descriptiva del conjunto de datos de df_games proporcionado por la compañía Ice.
Se agrupará información, se crearán variables nuevas que permitan  complementar el data frame original  y se elabore diferentes visualizaciones gráficas que permitan entender el comportamiento de las variables que se analicen.
Dentro de las variables nuevas a crear están:
global_sales
avg_sales
Estás variables considera las regiones de Norteamérica , Japón , Europa y otros y sus diferentes segmentaciones mediante agrupaciones de género y plataformas.
