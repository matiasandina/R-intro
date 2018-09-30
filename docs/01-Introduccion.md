# Introducción



La organización de este libro esta fuertemente vinculada al análisis de datos. En general, el análisis suele presentarse en tres etapas: Lectura, modelado y comunicación de resultados. 

`Lectura > Modelado > Comunicación`

En lo que resta de este capítulo, vamos a transitar parte de la organización y contenido del libro, las convenciones que vamos a utilizar y los requisitos para obtener los programas necesarios. El contenido a desarrollar es de nivel básico. Sugiero que los usuarios que ya hayan instalado R o se sientan cómodos con la instalación de programas y sistema de archivos se salteen lo siguiente. 

## Términos

Existen ciertos términos en inglés que no poseen una traducción satisfactoria al español y serán utilizados inglés. La decisión es arbitraria, aunque intento mantenerme dentro de anglicismos aceptados, recomiendo tratarlos como términos técnicos. En el anexo de este capítulo pueden encontrar una tabla con los términos técnicos.

Un caso especial son los nombres nativos de objetos o propiedades de R. Estos términos aparecerán normalmente `resaltados en el texto`. Un ejemplo son las tablas que vamos a usar para acceder a datos, llamadas `data.frame`. Por ahora, no es necesario preocuparse al respecto, las piezas del rompecabezas se van a unir luego. 

## Dónde encontrar ayuda

Una gran forma de resolver los problemas que tenemos cuando escribimos código es goolgear el problema exacto. R normalmente nos mostrará errores de la forma:


```
Error: error message here
```

Copiar y pegar el error particular es de gran ayuda. Existen diversos foros especializados. Afortunadamente existe material en español (aunque es limitado). Un gran sitio para empezar es:  

**StackOverflow** en español!
https://es.stackoverflow.com/


## Sistema Operativo

Afortunadamente, vivimos en un mundo con diversidad de sistemas operativos. R es compatible con *Windows*, *Mac OS* y *Linux*. Este libro está escrito utilizando *Windows 10* por lo que es posible que algunos ejemplos funcionen distinto en otros sistemas operativos. Haré mis mayores esfuerzos para asegurar compatibilidad entre distintos sistemas.

## Directorios

Los directorios son direcciones en nuestra computadora. Para que nuestra computadora localice un archivo o un programa, estos tienen una dirección en el disco duro. Normalmente el sistema de archivos es jerárquico, con secuencias de contenedores. Por ende, los directorios son también conocidos como *carpetas* o *ficheros*. Por ejemplo, en mi sistema, los archivos de R se encuentra en este directorio `C:\Program Files\R\R-3.4.0`. Todos los archivos contenidos en esa carpeta serán localizados a partir de esa dirección (y el nombre del archivo). Es importante entender que siempre contaremos con un *working directory* o directorio en el que estamos trabajando. Este directorio funciona como todos los demás, funcionando como un atajo.

## Traducción de contenido

Una parte del material de referencia en este libro está en inglés. Para aquellos lectores que encuentren muy dificultoso el idioma, aconsejo intentar la traducción del material usando el traductor de [Google](translate.google.com) o, si el navegador lo permite, habilitar la traducción de manera directa sobre el contenido.  

## R

Un lenguaje de programación es una serie de reglas que están diseñadas para realizar procesos en una computadora [^LenguajeWiki]. R es un lenguaje de programación. En ese sentido, no se diferencia de ningún otro (ej. C, Python). A su vez, como todo lenguaje, el set de reglas es particular y lleva tiempo incorporarlo. La mejor forma de naturalizarse con un idioma es hablarlo y, fundamentalmente en este caso, leerlo y escribirlo! Afortunadamente, el dominio de un idioma facilita el dominio de otro(s).  

R nació en 1993 en Auckland. Sin embargo, su origen puede rastrearse hasta un lenguaje previo llamado S, creado por John Chambers y colaboradores en *Bell Laboratories* durante la década de 1970 [^RWiki]. Actualmente, la diversidad de proyectos que pueden abarcarse en R es altísima, desde hacer análisis de estadística pura hasta escribir libros, como éste.  

En este libro voy a usar mayoritariamente R para hablar del lenguaje. Una excepción es la instalación del programa en sí mismo (ver Instalar R).

El copyright del software R es mantenido por la fundación R ( [R Foundation]((https://www.r-project.org/foundation/)) ) bajo una licencia pública [GNU General Public License version 2.0](https://www.gnu.org/licenses/gpl-2.0.html).  Algunas traducciones *no oficiales* de la licencia pueden encontrarse [aquí](https://www.gnu.org/licenses/translations.html). 

La fundación R es una organización sin fines de lucro que trabaja en pos del interés público. Fue fundada por los miembros del *R Development Core Team* para proveer. Sus  objetivos son:  

* Proveer apoyo al proyecto R y otras innovaciones en estadística computacional. 
* Asegurar su continuo desarollo, así como también el desarrollo de futuras innovaciones en software estadístico. 
* Proveer un punto de referencia para individuos, instituciones y empresas que deseen interactuar con la comunidad de desarrollo de R. 
* Mantener y administrar el copyright del software R y su documentación.[^R_Fund]

Podemos pensar a R estando dividido en dos marcos conceptuales:

1. El sistema de "base" R descargado desde CRAN.
1. El conjunto de paquetes externos que agregan funcionalidad.

En la siguientes secciones realizaremos la descarga e instalación de R. En el próximo capítulo trabajaremos con agregar funcionalidad utilizando paquetes externos.

## Instalar R

Para instalar R debemos dirigirnos a la colección de paquetes en CRAN (del inglés, Comprehensive R Archive Network). CRAN es un repositorio global donde se puede acceder al software y a los paquetes que la comunidad produce. Veremos pronto que R provee limitada funcionalidad de base y los paquetes son una parte fundamental del uso diario. 

1. La instalación comienza entrando en `https://cran.r-project.org/` 
1. Seleccionar el link correcto de descarga. El link depende del sistema operativo.  


![Links para descargar R en CRAN](img/CRAN_download.png)


3. Hacer clic en *Install R for the first time* (instalar R por primera vez).  


![Instalar por primera vez](img/Windows_First.png)

4. Hacer clic en *Download R 3.4.3 for Windows* para descargar el ejecutable. Al momento de escribir este libro la versión 3.4.3 es la última disponible en CRAN.  


![Descargar](img/Windows_download.png)

5. Instalar desde el `.exe` (El cuádro de dialogo permite seleccionar idioma español).  


### Terminal de R

Si fantaseamos con escribir desde un terminal, es posible ejecutar R de ese modo. En mi caso, el acceso al terminal se encuentra en `C:\Program Files\R\R-3.4.0\bin` y la aplicación es `Rterm`. Como pueden ver, estoy utilizando una versión desactualizada, `R version 3.4.0 (2017-04-21) -- "You Stupid Darkness"`. 

![Terminal de R en mi sistema](img/R_term.png)

### Interfaz gráfica

Si bien el terminal (o *consola*) es seductor, en muchas ocasiones es conveniente tener una interfaz gráfica. Podemos acceder a la interfaz `RGui` desde `C:\Program Files\R\R-3.4.0\bin\i386` o directamente si hemos creado un acceso directo en el escritorio durante nuestra instalación. La interfaz gráfica se ve de este modo:  


![Interfaz Gráfica de R](img/RGui.png)

Como podemos ver, la interfaz permite acceso a mayores opciones pero, en esencia, se asemeja al terminal. Afortunadamente, existe una versión ampliamente mejorada de esta experiencia, se llama Rstudio (ver Instalar Rstudio). Rstudio es la interfaz gráfica que utilizaremos en este libro. 

## Instalar Rstudio

Rstudio es un software que integra una serie de herramientas gráficas y variabilidad de opciones a R. De este modo, ganamos versatilidad y comodidad en el uso. En el día a día, abrir Rstudio es, a fines prácticos, abrir R. Para instalar Rstudio, podemos seguir los siguientes pasos:

1. Ir a `https://www.rstudio.com/products/rstudio/download/`
1. Hacer clic en Descargar software.
1. Seleccionar la version compatible con el sistema operativo.
1. Instalar desde el `.exe` descargado.

![Descargar Rstudio](img/Rstudio_download.PNG)

### La experiencia

Al abrir Rstudio nos encontraremos con un programa que tiene principalmente dos áreas, una de entrada (consola) y una de salida (exploradores):

![Rstudio al abrir](img/Rstudio_open.PNG)

Podemos hacer un intento rápido para graficar el histograma de una distribución Normal con media 0 y desvío estándar 1. Puedes copiar y pegar el siguiente código en la consola.


```r
set.seed(123)
ejemplo <- rnorm(n = 10000, mean = 0, sd = 1)
hist(ejemplo, col='orange', breaks=40, 
     ylab = "Frecuencia", main = "Histograma ejemplo")
```

<img src="01-Introduccion_files/figure-html/hist_ejemplo-1.png" width="576" style="display: block; margin: auto;" />

En la ventana de Rstudio se vería así:  

![Así se ve en Rstudio](img/Rstudio_hist.png)


Normalmente usaremos Rstudio con 4 zonas principales: 

* Editor de scripts.
* Terminal o consola.
* Explorador de entorno e historial.
* Explorador de archivos y gráficos. 

![Rstudio al iniciar un script](img/Rstudio_script.PNG)

En los próximos capítulos ahondaremos en la funcionalidad de cada uno.

### Preferencias

Rstudio permite personalizar la *experiencia R* de modo de obtener virtualmente infinitas combinaciones. Para mayor información visitar la página de [Rstudio](https://support.rstudio.com/hc/en-us/articles/200549016-Customizing-RStudio)


## Resumen

* La organización del análisis estadístico procede `Lectura > Modelado > Comunicación`
* R es un lenguaje de programación orientado a objetos que permite realizar las tres etapas.
* El software R es de dedistribución gratuita y con funcionalidad dividida en:
    * Base R.
    * Paquetes externos descargados de un repositorio.  
* Rstudio es una interfaz gráfica gratuita que permite trabajar con R.


## Anexo {-}

La suguiente tabla muestra ciertos terminos que serán utilizados en inglés.


Término en inglés   Descripción                                                     
------------------  ----------------------------------------------------------------
CRAN                Colección de paquetes en CRAN (Comprehensive R Archive Network) 
dataset             set de datos                                                    
pipes               uso técnico para el operador %>%                                
render              generación de contenido multimedia                              
software            programa                                                        
subset              subconjunto o porción                                           
working directory   Directorio desde donde R está trabajando en la sesión (getwd()) 



[^LenguajeWiki]: Mayor descripción en lenguajes de programación [aquí](https://es.wikipedia.org/wiki/Lenguaje_de_programaci%C3%B3n).

[^RWiki]: Historia e información sobre R [aquí](https://es.wikipedia.org/wiki/R_(lenguaje_de_programaci%C3%B3n). Para aquellos curiosos que tienen una consola a mano y se aventuran al inglés: `contributors()`

[^R_Fund]: La traducción es de mi autoría, la información original en inglés puede encontrarse [aquí](https://www.r-project.org/foundation/).
