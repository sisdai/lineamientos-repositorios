# Recomendaciones para estructurar un repositorio de datos bajo el marco de ciencia abierta

# Introducción

La *ciencia abierta* se refiere a la práctica de la ciencia de manera en que las personas tengan la posibilidad de *colaborar y contribuir* en los procesos de investigación, siendo estos últimos accesibles para todas las personas interesadas. 

Los proyectos de ciencia abierta generalmente se desarrollan bajo términos y licencias que permiten la reutilización, redistribución y reproducción tanto de la recolección, limpieza y análisis de datos, como de las metodologías y resultados obtenidos en los procesos de investigación.

Principalmente la ciencia abierta se basa en los principios de *inclusión, impacialidad, equidad, y distribución* (Bezjak *et al.*, 2019). 

Aunado a lo anterior, Vicente-Sáez y Martínez-Fuentes (2018) comprenden la ciencia abierta como:

* Conocimiento
* Conocimiento transparente
* Conocimiento accesible
* Conocimiento compartido
* Conocimiento de desarrollo colaborativo

Por lo anterior, el presente documento tiene como objetivo establecer una serie de recomendaciones para estructurar un repositorio de datos bajo el marco de la ciencia abierta.

# Tabla de contenido

1. [Introducción](#introducción)
2. [Recomendaciones básicas](#recomendaciones-básicas)
3. [Archivos que recomendamos compatir en tu repositorio](#i-archivos-que-recomendamos-compatir-en-tu-repositorio)
4. [La organización de tus archivos](#ii-la-organización-de-tus-archivos)
5. [Lo que necesita mi repositorio para ser funcional y reproducible](#iii-lo-que-necesita-mi-repositorio-para-ser-funcional-y-reproducible)
6. [Licencias](#iv-licencias)
7. [Versionamiento](#v-versionamiento)
8. [Guía de contribución](#vi-guía-de-contribución)
9. [Recomendaciones adicionales](#vii-recomendaciones-adicionales)
10. [Referencias](#referencias)

# Recomendaciones básicas

En el marco de ciencia abierta es importante estructurar de una manera clara y precisa los repositorios para que la persona usuaria pueda consultar nuestros datos y/o procesos, es por eso que te compartimos lo siguiente para que consideres incluirlo en tu repositorio. 

### Consideración 

Esta breve guía de recomendaciones no pretender ser exhaustiva, sino que busca ser una guía de buenas prácticas generales para estructurar un repositorio de datos. Si requieres consultar una guía más detallada, te recomendamos consultar alguna guía como [The Turing Way](https://the-turing-way.netlify.app/welcome.html), que ahonda en buenas prácticas para la ciencia de datos.

## I. Archivos que recomendamos compatir en tu repositorio

### Datos
Los datos son el motor de tu proyecto, así que es esencial que los incluyas en tu repositorio. Aunque puedes compartir los datos en cualquier formato, recomendamos utilizar formatos que promuevan la interoperabilidad. Esto significa que los datos pueden ser leídos por diferentes programas o lenguajes de programación y no necesitan un software específico. Esto se puede lograr mediante el uso de formatos de datos abiertos.

 - Algunos ejemplos son: *Comma Separated Values* (.cvs), *Archivos de texto plano* (.txt), *JavaScript Object Notation* (.json), etc.

Si tu proyecto no incluye estos archivos porque la forma en que obtienes los datos es a través de una API, te recomendamos que incluyas un archivo que contenga el código que utilizaste para obtenerlos.

### Metadatos

Los metadatos son datos que describen tus datos. Éstos describen el contenido, la calidad, el estado, la condición, el origen, la disponibilidad y otras características de los datos, de manera que son importantes porque permiten a las personas usuarias entender y evaluar los datos, así como encontrarlos y reutilizarlos. 

También puedes optar por incluir un **"diccionario de las variables"** para que las personas usuarias puedan entender el significado de cada una de las variables que utilizaste en tu proyecto, por ejemplo:

| Variable | Descripción | Tipo de dato |
| -------- | ----------- | ------------ |
| `id` | Identificador único de cada observación | Numérico |
| `nombre` | Nombre de la persona | Texto |
| `edad` | Edad de la persona | Numérico |
| `sexo` | Sexo de la persona | Categórico |
| `fecha_nacimiento` | Fecha de nacimiento de la persona | Fecha |


### Código y procesamientos

Los archivos que contienen el procesamiento de tus datos son igualmente importantes para tu repositorio, ya que forman la base de tu proyecto.

En ocasiones, los procesamientos de datos pueden ser difíciles de interpretar, especialmente para aquellas personas no familiarizadas con el lenguaje de programación que utilizaste. Por ello, puedes considerar la posibilidad de añadir comentarios en tu código que expliquen lo que estás haciendo. No es necesario entrar en detalles minuciosos para cada paso, pero nombrar las variables de manera descriptiva y fácil de entender, evita ambigüedades y puede simplificar la tarea de "leer" tu código.

Si optas por no incluir comentarios directamente en tu código, te sugerimos que incluyas un archivo con una breve explicación de lo que hace tu código en el archivo `README.md` de tu repositorio. De este modo, tanto expertos como no expertos podrán entender el propósito y la funcionalidad de tu código.

## II. La organización de tus archivos

En esta seccion la clave es mantener una estructura de directorios clara y sobretodo aquí toma mucha importancia la coherencia y el orden con el que acomodememos nuestros archivos.

Primero, considera las siguientes recomendaciones para facilitar la búsqueda, el acceso y la comprensión de los archivos de tu proyecto:

* Mantener los nombres de los archivos y carpetas cortos, pero descriptivos.
* Utilizar guiones bajos (_) o guiones (-) en lugar de espacios para separar las palabras en los nombres de los archivos.
* Evitar caracteres especiales o acentos en los nombres de los archivos.
* Usar fechas en los nombres de los archivos para indicar cuándo se crearon o modificaron. Utiliza algún formato convencional como `YYYY-MM-DD` o `YYYYMMDD`.

A continuación, te sugerimos una estructura de directorios que puedes usar como punto de partida para organizar tus archivos. No olvides que puedes adaptarla a tus necesidades y de acuerdo con el paradigma de programación que utilices, por ejemplo, programación orientada a objetos, programación funcional, programación modular, etc.

a) Las carpetas mínimas que te recomendamos incluir son:

- **/datos**: En esta carpeta puedes incluir los datos que utilizaste en tu proyecto. Te recomendamos que incluyas subcarpetas para los datos crudos (como vienen de origen), otra para los datos limpios (si realizaste algunos procesos para la limpieza y estructuración de tus datos) y otra para los datos auxiliares (estos son datos que te ayudan en algún procesamiento, por ejemplo: algunos diccionarios de variables, diccionarios de claves geográficas, etc.).

- **/codigo**: En esta carpeta puedes incluir el código que utilizaste para procesar tus datos, ya sean scripts, notebooks, etc.

- **/salidas-procesamientos**: En esta carpeta puedes incluir los resultados de tus procesamientos de datos. Te sugerimos que incluyas subcarpetas si generas diferentes tipos de salidas.

b) Los arcchivos mínimos que te recomendamos incluir son:

- **README.md**: Este archivo es muy importante porque aparece en la página principal de tu repositorio y es el primer acercamiento que tienen las personas usuarias con el contenido de tu proyecto. Se trata de una descripción general de tu proyecto, más adelante te compartimos algunos puntos que puedes incluir en este archivo.

- **LICENSE**: Este archivo es importante porque permite que las personas usuarias sepan cómo pueden utilizar tu proyecto. Existen diferentes tipos de licencias, por lo que te recomendamos que elijas la que mejor se adapte a tus necesidades. 

- **Archivo de requerimientos para instalar dependencias**: Este archivo es importante porque permite que las personas usuarias sepan qué bibliotecas o dependencias necesitan para ejecutar tu proyecto.

- **.gitignore**: Este archivo es importante porque permite generar un filtro para no compartir archivos que no son necesarios para el proyecto. Por ejemplo, si utilizas Jupyter Notebook, puedes incluir en este archivo la extensión .ipynb_checkpoints/ para que no se compartan los archivos de checkpoints que genera Jupyter Notebook, ya que estos no son relevantes para el funcionamiento de tu proyecto.

- **Archivo con código de tu proyecto principal**: Este archivo es importante porque es el código principal que ejecuta tu proyecto, puedes ponerlo en la carpeta raíz o en la carpeta de código.

Puedes visualizar lo anterior aquí:

```
Carpeta raíz
│   Archivo "README.md"
│   Archivo "LICENSE"
│   Archivo de requerimientos para instalar dependencias
│   Archivo ".gitignore"
│   Archivo con código de tu proyecto principal
│
└───datos
│   │
│   └───datos_crudos
│   │
│   └───datos_limpios
│   │
│   └───datos_auxiliares
│
│   │   diccionario-variables.csv
│
└───codigo
│
└───salidas-procesamientos

```

## III. Lo que necesita mi repositorio para ser funcional y reproducible

**a )** Para que un proyecto pueda ejecutarse correctamente, es esencial especificar las bibliotecas o dependencias utilizadas. Puedes optar por cualquiera de las siguientes opciones, o bien, nuetra recomendación sería llevar a cabo ambas:

- En tu archivo `README.md`, puedes incluir una lista de las principales dependencias y sus respectivas versiones en una sección que puedes llamar `Dependencias` o `Requerimientos`. 

- Genera un archivo que contenga el listado de dependencias y sus versiones correspondientes; este archivo puede ser un `requirements.txt` para el caso de proyectos en Python, o un `sessionInfo.txt` para el caso de proyectos en R. 

```
# Python (requirements.txt)
matplotlib==3.3.4
numpy==1.20.1
pandas==1.2.2
seaborn==0.11.1
```

```
# R (sessionInfo.txt)
R version 4.0.3 (2020-10-10)
Platform: x86_64-apple-xxxxx.0 (64-bit)
Running under: macOS Big Sur 10.16

Matrix products: default
BLAS:   /Library/Frameworks/R.framework/Versions/4.0/Resources/lib/libRblas.dylib
LAPACK: /Library/Frameworks/R.framework/Versions/4.0/Resources/lib/libRlapack.dylib

locale:
 [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C               LC_TIME=en_US.UTF-8       
 [4] LC_COLLATE=en_US.UTF-8     LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
```


**b)** Es también importante explicitar el lenguaje de programación y la versión utilizados en tu proyecto; puedes hacerlo en el archivo `README.md`. Algunos ejemplos son:

- [Python 3.11.0](https://www.python.org/downloads/release/python-3110/)
- [R 4.0.3](https://cran.r-project.org/bin/windows/base/old/4.0.3/)
- [Julia 1.5.3](https://julialang.org/downloads/oldreleases/#v153_family)
- [C++ 11](https://isocpp.org/std/the-standard)

También es válido omitir lo anterior si tu proyecto está albergado en una plataforma que permite la ejecución de código sin necesidad de generar un ambiente local, como por ejemplo [Google Colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true), [RStudio Cloud](https://rstudio.cloud/) o [Binder](https://mybinder.org/); Si este es tu caso, te recomendamos que explicites, por lo menos, las principales dependencias en el archivo `README.md` de tu repositorio ya que independientemente que no cuentes con un archivo de requemientos como tal, la persona usuaria necesita saber las **dependencias necesarias** para ejecutar el proyecto, incluso en Binder, es necesario un archivo "requirements.txt".

**c)** Una documentación adecuada es fundamental para que tu proyecto sea funcional y reproducible.  En esta parte vamos a retomar la importancia del archivo `README.md` de tu repositorio para recomendarte algunos puntos importantes en los que hay que tener claridad:

En este archivo puedes incluir una breve descripción de tu proyecto, los objetivos, los datos que utilizaste, el código que utilizaste, los resultados de tus procesamientos, etc. Aquí hay algunas ideas sobre algunas secciones que puedes incluir en tu archivo `README.md`:

| Sección | Descripción |
| --- | --- |
|Explica el propósito de tu proyecto. | ¿Qué problemas estás tratando de resolver?|
|Describe la estructura de tu proyecto. |¿Qué archivos y directorios contiene tu repositorio?| 
|  |¿Qué función cumple cada uno de ellos?|
|Explica cómo ejecutar tu proyecto.| ¿Qué comandos se deben ejecutar? ¿En qué orden?|

## IV. Licencias

Las licencias más comúnmente utilizadas en proyectos de ciencia abierta son licencia MIT, licencia GNU General Public, licencia Apache, licencia Creative Commons, la licencia BSD, entre otras. Puedes consultar más información sobre licencias en el siguiente [enlace](https://choosealicense.com/).

## V. Versionamiento

Si tu proyecto tiene diferentes versiones, es importante que lo especifiques en el archivo `README.md` de tu repositorio. Esto proporciona más detalles sobre cómo los usuarios deben manejar las versiones de su proyecto. Puedes ahondar más en el tema en el siguiente [enlace](https://semver.org/lang/es/).

## VI. Guía de contribución

Una guía para contribuciones incluye las instrucciones que deben seguirse para colaborar en tu proyecto. Esta información puede ser presentada en un documento específico o directamente en una sección del archivo`README.md`. Esto podría incluir detalles sobre qué tipos de contribuciones son bienvenidas (por ejemplo, mejoras al código, corrección de errores, adición de nuevas funcionalidades), cómo deben ser presentadas (por ejemplo, a través de pull requests), y cualquier lineamiento que deban seguir los contribuyentes.

## VII. Recomendaciones adicionales

* Si estás trabajando con archivos que contienen datos personales o información sensible que no deseas compartir, pero son necesarios para algún proceso de tus datos, te recomendamos emplear un archivo `.gitignore`. Esto evitará que estos archivos se suban a tu repositorio. Informa a los usuarios sobre el motivo por el cual estos archivos no están disponibles y, si fuera necesario, cómo pueden solicitar acceso a los mismos.

* Al trabajar con scripts, es posible que utilices *rutas absolutas* para acceder a los archivos que se encuentran en nuestro equipo. Sin embargo, esto puede generar problemas cuando otras personas intenten ejecutar tu código en su propia máquina.
Si en tu código utilizas *rutas absolutas*, es importante que las cambies a *rutas relativas*. Esto permitirá que otras personas puedan correr tu código en su propia máquina sin necesidad de cambiar todas las rutas de los archivos.

Por ejemplo:

```python
# Ruta absoluta
ruta = "C:/Users/usuaria/Desktop/Proyecto/datos/datos_crudos/datos.csv"

# Ruta relativa
ruta = "datos/datos_crudos/datos.csv"
```

Espero que estas sugerencias te resulten útiles para organizar tu proyecto.
Recuerda, la clave de un buen proyecto es mantenerlo organizado, documentado, y accesible. ¡Buena suerte! 

# Referencias

Bezjak, S., Clyburne-Sherin, A., Conzett, P., Fernandes, P. L., Görögh, E., Helbig, K., … Wobbe, T. (2019). *Open Science Training Handbook.* Zenodo. https://doi.org/10.5281/zenodo.1212496

Vicente-Sáez, R., & Martínez-Fuentes, C. (2018). Open Science now: A systematic literature review for an integrated definition. *Journal of Business Research*, 88, 428–436. https://doi.org/10.1016/j.jbusres.2018.03.036 

Feria-Basurto, L., & Martínez-Camacho, H. (2021). Ciencia abierta, ¿Qué es y cómo formamos en bibliotecas?: Revisión de una iniciativa latinoamericana. 
 
