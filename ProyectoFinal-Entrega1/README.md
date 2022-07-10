# Entrega 1 - Severo Tonarelli

## Equipo: Martina Severo y Santiago Tonarelli

<br>

### **Objetivos Generales:**

#### - Entender el problema de negocio e identificar los elementos a ser considerados para el planteamiento de un Modelo de Data Science.

#### - Describir los datos de negocio y las relaciones entre datos mediante el Análisis Exploratorio de Datos.

#### - Construir una presentación ejecutiva para la alta gerencia mostrando los resultados obtenidos.

<br>

### **Objetivos Específicos:**

#### - Desarrollar las instancias de Data Acquisition y Data Wrangling en tu trabajo final.

#### - Lograr una articulación en equipo y una división de tareas adecuadas a los objetivos.

#### - Realizar Filtrado

#### - Describir qué significa cada variable, cómo se comporta.

#### - Especificar las distribuciones y relaciones (géneros, sexo, edad, IVA, tipo de empresa).

<br>

### **Se debe entregar:**

#### - Presentación de la empresa, organización o problema específico.

#### - Preguntas y objetivos de la investigación.

#### - Conformación del equipo de trabajo.

#### - Indicación de la fuente del dataset y los criterios de selección (Data Acquisition).

#### - Generación del primer Data Wrangling y EDA, apuntado a sus datos (insights) univariado, bivariado y multivariado.

#### - Análisis de componentes principales.

#### - Contar la historia de sus datos

#### - Filtros aplicados a los datos. Distribución. Dataset final para analizar.

#### - Palttear objetivos u objetivo para esos datos.

<br>

# Introducción

Spotify es conocido como el proveedor de servicios de transmisión de música más grande del mundo, superando los 365 millones de usuarios activos por mes, incluyendo 165 millones de suscriptores que pagan por su uso.

Como un servicio de transmisión de música popular, es usado a diario por muchas personas mundialmente. Como forma de dar valor a esta aplicación y mantener a sus usuarios satisfechos y atraidos a usarla, Spotify ofrece recomendaciones inteligentes y personales a dichos usuarios basándose en su historial y lo que escuchan. Muchas empresas usan este tipo de sistemas de recomendación con el objetivo de proporcionar una experiencia más personalizada al usuario.

Dentro de sus funcionalidades, esta aplicación permite la búsqueda de música mediante varios parámetros, como pueden ser artista, álbum, género, lista de reproducción, entre otros. A su vez, los usuarios pueden crear, editar y compartir listas de reproducción, así como también compartir canciones en las redes sociales. Spotify ofrece acceso a más de 70 millones de canciones, 2,2 millones de podcasts y 4 mil millones de listas de reproducción.

Desarrollaremos un análisis básico del conjunto de datos de 600.000 canciones de Spotify. Como idea principal, prepararemos el dataframe para entrenar un modelo que será capaz de recomendar una lista de canciones cuando le brindemos solo una, siendo similar a la radio de Spotify.

<br>

# Descripción de los datos

Yamac Eren Ay hizo una recopilación de un conjunto de datos de Spotify, conteniendo detalles de 600.000 canciones, mediante el uso de la API web de Spotify. Dicho conjunto se encuentra disponible en Kaggle, pudiendo ser accedido a través del siguiente link: https://www.kaggle.com/code/prathamsharma123/spotify-eda-recommendation-system/data

Algunas de las funciones de audio que describen canciones/pistas son:

* `Loudness`: qué tan fuerte es la canción.
* `Popularity`: Cuán popular es la canción.
* `Acousticness`: Si la canción es acústica o no.
* `Tempo`: El tempo de la canción, medido en pulsaciones por minuto (BPM).
* `Energy`: Cuán enérgica es la canción.
* `Liveness`: Si una audiencia en vivo está presente o si la canción está grabada en un estudio.
* `Valence`: Qué tan positiva es la música.
* `Danceability`: Que tan bailable es la canción.
* `Energy`: Que tan enérgica es la canción.
* `Speechiness`: Para identificar si la canción está cantada o no.
* `Instrumentalness`: Cantidad de sonidos instrumentales que contendrán las canciones.

<br>

# Resumen

Mediante el uso de un diagrama de dispersión, observamos que cuando el nivel de popularidad es alto, el volumen tiene tendencia a aumentar a un rango entre 0 y -10.

Durante este análisis, creamos 3 marcos de datos:

* `df` es el marco completo.
* `df2` es un marco de datos filtrado, categorizado por popularidad. Para que fuera más claro en el caso de análisis sólidos o dibujo de gráficos pesados, eliminamos todas las filas entre 30 < `popularidad` < 70.
* `df3` es el mismo marco que df, con la diferencia de que eliminamos todas las columnas innecesarias para crear gráficos.

Para entrenar nuestro modelo de recomendación, usaremos el original_df.
