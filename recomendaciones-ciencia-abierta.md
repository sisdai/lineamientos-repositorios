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
3. [¿Qué archivos comparto?](#i-¿qué-archivos-comparto?)
4. [¿Cómo organizo mis archivos?](#ii-¿cómo-organizo-mis-archivos?)
5. [¿Qué necesita mi repositorio para funcionar?](#iii-¿qué-necesita-mi-repositorio-para-funcionar?)
6. [Licencias](#iv-licencias)
7. [Referencias](#referencias)

# Recomendaciones básicas

En el marco de ciencia abierta es importante estructurar de una manera clara y precisa los repositorios para que la persona usuaria pueda consultar nuestros datos y/o procesos, es por eso que te compartimos lo siguiente para que consideres incluirlo en tu repositorio:

## I. ¿Qué archivos comparto?

### Datos
Principalmente, los datos son el motor de tu proyecto, por lo que es crucial incluirlos en tu repositorio. El formato en que compartes los datos puede ser cualquiera. Sin embargo, para contribuir a la accesibilidad, te recomendamos utilizar formas de almacenamiento de datos que permitan la interoperabilidad, es decir, que puedan ser leídos por diferentes programas o lenguajes de programación y no requieran de un software específico. Esto se puede lograr a través del uso de formatos de datos abiertos.

 - Algunos ejemplos son: *Comma Separated Values* (.cvs), *Archivos de texto plano* (.txt), *JavaScript Object Notation* (.json), etc.

Si tu proyecto no incluye estos archivos porque la forma en que obtienes los datos es a través de una API, te recomendamos que incluyas un archivo que contenga el código que utilizaste para obtenerlos.

### Metadatos

Los metadatos son datos que describen a tus datos. En el caso de los datos de investigación, los metadatos describen el contenido, la calidad, el estado, la condición, el origen, la disponibilidad y otras características de los datos. Los metadatos son importantes porque permiten a las personas entender y evaluar los datos, así como encontrarlos y reutilizarlos. 

También puedes optar por incluir un **"diccionario de las variables"** para que las personas usuarias puedan entender el significado de cada una de las variables que utilizaste en tu proyecto.

### Código y procesamientos

Los archivos que contienen los procesamientos de datos también son importantes para tu repositorio, ya que constituyen la esencia de tu proyecto.

En ocasiones, los procesamientos de datos pueden ser difíciles de interpretar, especialmente para aquellas personas no familiarizadas con el lenguaje de programación que utilizaste. Por lo tanto, es importante que incluyas comentarios en tu código que expliquen qué es lo que estás haciendo. No es necesario ahondar demasiado en cada paso, pero una buena práctica consiste en nombrar las variables de manera que sean descriptivas y fáciles de entender, no usar ambigüedades y evitar el uso de abreviaturas que solo tú entiendas.

En caso de no incluir comentarios directamente en tu código, te recomendamos que incluyas un archivo con una breve explicación de lo que hace tu código en el archivo `README.md` de tu repositorio. De este modo, tanto expertos como no expertos podrán entender el propósito y la funcionalidad de tu código.

## II. ¿Cómo organizo mis archivos?

En esta seccion la clave es mantener una estructura de directorios clara y sobretodo aquí toma mucha importancia la coherencia y el orden con el que acomodememos nuestros archivos.

Inicialmente, las siguientes recomendaciones son parte de un sistema de nomenclatura para facilitar la búsqueda, acceso y comprensión de los archivos de tu proyecto:

* Mantener los nombres de los archivos y carpetas cortos, pero descriptivos.
* Utilizar guiones bajos (_) o guiones (-) en lugar de espacios para separar las palabras en los nombres de los archivos.
* Evitar caracteres especiales o acentos en los nombres de los archivos.
* Usar fechas en los nombres de los archivos para indicar cuándo se crearon o modificaron.
* Incluir versiones en los nombres de los archivos -si es necesario- para indicar diferentes versiones de un mismo archivo.

Posteriormente, te compartimos una estructura de directorios que puedes utilizar para organizar tus archivos. Recuerda que esta estructura es solo una recomendación y puedes adaptarla a tus necesidades y al tipo de paradigma de programación que utilizas, por ejemplo, programación orientada a objetos, programación funcional, programación modular, etc.

Como mínimo te recomendamos incluir las siguientes carpetas:

- **datos**: En esta carpeta puedes incluir los datos que utilizaste en tu proyecto. Te recomendamos que incluyas subcarpetas para los datos crudos (como vienen de origen), otra para los datos limpios (si realizaste algunos procesos para la limpieza y estructuración de tus datos) y otra para los datos auxiliares (estos son datos que te ayudan por ejemplo algunos diccionarios de variables, diccionarios de claves geográficas, etc.).

- **codigo**: En esta carpeta puedes incluir el código que utilizaste para procesar tus datos, ya sean scripts, notebooks, etc.

- **salidas-procesamientos**: En esta carpeta puedes incluir los resultados de tus procesamientos de datos. Te recomendamos que incluyas subcarpetas si tienes diferentes salidas de acuerdo con tus procesamientos. 

Como mínimo te recomendamos incluir los siguientes archivos:

- **README.md**: Este archivo es muy importante porque aparece en la página principal de tu repositorio y es el primer acercamiento que tienen las personas usuarias con el contenido de tu proyecto. En este archivo puedes incluir una breve descripción de tu proyecto, los objetivos, los datos que utilizaste, el código que utilizaste, los resultados de tus procesamientos, etc. Adicionalmente dejar explicita la manera en la cual pueden ponerse en contacto con el equipo de trabajo para sumar al proyecto.

- **LICENSE**: Este archivo es importante porque permite que las personas usuarias sepan cómo pueden utilizar tu proyecto. Existen diferentes tipos de licencias, por lo que te recomendamos que elijas la que mejor se adapte a tus necesidades. 

- **Archivo de requerimientos para instalar dependencias**: Este archivo es importante porque permite que las personas usuarias sepan qué bibliotecas o dependencias necesitan para ejecutar tu proyecto.

- **.gitignore**: Este archivo es importante porque permite generar un filtro para no compartir archivos que no son necesarios para el proyecto. Por ejemplo, si utilizas Jupyter Notebook, puedes incluir en este archivo la extensión .ipynb_checkpoints/ para que no se compartan los archivos de checkpoints que genera Jupyter Notebook.

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

## III. ¿Qué necesita mi repositorio para funcionar?

**a )** Es importante recordar que para que un proyecto pueda ser ejecutado, es necesario que el repositorio explicite la serie de bibliotecas o dependecias que se utilizaron en el proyecto. 

Te compartimos estas opciones y puedes utilizar la que más se adapte a tus necesidades, o bien, nuetra recomendación sería llevar a cabo ambas:

- Crear un listado de las dependencias y el número de la versión que se utilizó en el proyecto. Esta información puede ser parte de tu documento `README.md` en alguna sección que se llame `Dependencias` o `Requerimientos`. 

- Crear un archivo que contenga un listado de la información de las dependencias y versiones utilizadas en el proyecto; este archivo puede ser un `requirements.txt` para el caso de proyectos en Python, o un `sessionInfo.txt` para el caso de proyectos en R. 

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
```


**b)** También es necesario que pongas de manifiesto el lenguaje de programación y la versión que utilizaste para el proyecto; algunos ejemplos son:

- [Python 3.11.0](https://www.python.org/downloads/release/python-3110/)
- [R 4.0.3](https://cran.r-project.org/bin/windows/base/old/4.0.3/)
- [Julia 1.5.3](https://julialang.org/downloads/oldreleases/#v153_family)
- [C++ 11](https://isocpp.org/std/the-standard)

También es válido omitir lo anterior si tu proyecto está albergado en una plataforma que permite la ejecución de código sin necesidad de generar un ambiente local, como por ejemplo [Google Colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true), [RStudio Cloud](https://rstudio.cloud/) o [Binder](https://mybinder.org/); Si este es tu caso, te recomendamos que explicites, por lo menos, las principales dependencias en el archivo `README.md` de tu repositorio ya que independientemente que no cuentes con un archivo de requemientos como tal, la persona usuaria necesita saber las dependencias necesarias para ejecutar el proyecto, incluso en Binder, es necesario un archivo "requirements.txt".


## IV. Licencias

Las licencias más comúnmente utilizadas en proyectos de ciencia abierta son licencia MIT, licencia GNU General Public, licencia Apache, licencia Creative Commons y la licencia BSD. Puedes consultar más información sobre licencias en el siguiente [enlace](https://choosealicense.com/).

## V. Versionamiento

Si tu proyecto tiene diferentes versiones, es importante que lo especifiques en el archivo `README.md` de tu repositorio. Esto proporciona más detalles sobre cómo los usuarios deben manejar las versiones de su proyecto. 

## VI. Guía de contribución

Una guía de contribución se refiere, ya sea a un documento o de manera explícita en el archivo `README.md`, a las instrucciones que se deben seguir para contribuir al proyecto. Esto podría incluir detalles sobre qué tipos de contribuciones son bienvenidas (por ejemplo, mejoras al código, corrección de errores, adición de nuevas funcionalidades), cómo deben ser presentadas (por ejemplo, a través de pull requests), y cualquier lineamiento que deban seguir los contribuyentes.


## VII. Otras recomendaciones

a) Es importante considerar que si estás trabajando con archivos que contienen datos personales o información sensible, te recomendamos que utilices un archivo `.gitignore` para que estos archivos no sean subidos a tu repositorio. 

b) 


# Referencias

Bezjak, S., Clyburne-Sherin, A., Conzett, P., Fernandes, P. L., Görögh, E., Helbig, K., … Wobbe, T. (2019). *Open Science Training Handbook.* Zenodo. https://doi.org/10.5281/zenodo.1212496

Vicente-Sáez, R., & Martínez-Fuentes, C. (2018). Open Science now: A systematic literature review for an integrated definition. *Journal of Business Research*, 88, 428–436. https://doi.org/10.1016/j.jbusres.2018.03.036 

Feria-Basurto, L., & Martínez-Camacho, H. (2021). Ciencia abierta, ¿Qué es y cómo formamos en bibliotecas?: Revisión de una iniciativa latinoamericana. 
 
