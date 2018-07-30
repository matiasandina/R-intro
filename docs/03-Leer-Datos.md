# Leer Datos

En este capítulo vamos a focalizarnos en las diversas formas de entrar datos a R.


## Datasets de base

R contiene datasets que pueden ser utilizados directamente. Para dar un vistazo a los paquetes 



```r
paquetes <- library(help = "datasets")
head(paquetes$info[[2]])
```

```
## [1] "AirPassengers           Monthly Airline Passenger Numbers 1949-1960"   
## [2] "BJsales                 Sales Data with Leading Indicator"             
## [3] "BOD                     Biochemical Oxygen Demand"                     
## [4] "CO2                     Carbon Dioxide Uptake in Grass Plants"         
## [5] "ChickWeight             Weight versus age of chicks on different diets"
## [6] "DNase                   Elisa assay of DNase"
```

Para ver la lista completa con toda la información, entrar `paquetes` en la consola nos abrirá una ventana. Utilizar datos que vienen con la instalación R nos facilitará avanzar hacia modelado y comunicación. Por ejemplo, en muchas ocasiones utilizaremos el dataset `iris`, que contiene información sobre la longitud de pétalos y sépalos en tres plantas distintas.  

Si bien importar datos es crucial, recomiendo que los usuarios menos experimentados continuen con el siguiente capítulo. 

A continuación se darán detalles más específicos para importar datos a R.

## Importar datos de manera manual

Rstudio posee una pestaña en donde tenemos el *Entorno* y un botón que nos permite importar datasets (ver figura). Desaconsejo utilizar esta pestaña de manera recurrente debido a que es de poca utilidad para leer archivos grandes. Además, aprender a importar archivos usando código nos permite leer múltiples archivos con gran velocidad, tarea prácticamente imposible si utilizamos los cuadros de diálogo.   

![Importar manualmente](img/manual_import_01.PNG)

Luego recibiremos la posibilidad de seleccionar el archivo y modificar parámetros en sendos cuadros de diálogo.

## Archivos de texto

La gran ventaja de mantener archivos de texto (por ejemplo, `.csv` o `.txt`) es que una enorme cantidad de software es capaz de leerlos y no están ligados a un sistema operativo. Estos archivos son normalmente livianos y es fácil mantenerlos como *sólo lectura*, es decir, archivos en los que no cambiamos la información, sólo accedemos a ella. Si nuestros datos están guardados en un archivo de texto de sólo lectura, es menos probable que ocurra corrupción de datos o que, con el paso del tiempo, los mismos no puedan abrirse porque el software se ha discontinuado.  

R tiene funciones genéricas para abrir este tipo de archivos en una tabla como `read.table(...)`. Esta función presume pocas cosas en la estructura de datos, por lo que permite especificar un montón de parámetros y nos brinda variabilidad (ver `help(read.table)`). Sin embargo, en general conocemos la estructura de nuestros datos (por ejemplo, la primera fila es el título de las columnas o es un archivo separado por comas). Por lo tanto, usaremos llamadas del estilo:


```r
datos <- read.csv(file = 'nombre_de_archivo.csv')
```

Es común que las computadoras en español utilicen el separador `;` en vez de `,` para archivos `.csv`. En ese caso, podemos especificar:


```r
datos <- read.csv(file = 'nombre_de_archivo.csv', sep = ';')
```

Un archivo separado por tabulaciones (`.txt`) puede leerse como:


```r
datos <- read.table(file = 'nombre_de_archivo.txt', sep = '\t')
```


### Importar múltiples archivos de texto

Normalmente tendremos múltiples archivos de texto, probablemente llamados de manera seriada en una carpeta dentro de nuestro working directory (por ejemplo, tendremos `resultados/sujeto001.csv`, `resultados/sujeto002.csv`, ... `resultados/sujeto154.csv`).


```r
# Obtener lista de archivos dentro de la carpeta 'resultados'

lista_nombres <- list.files(path = 'resultados')

# leer todos los archivos en una nueva lista

lista_archivos <- lapply(lista_nombres, read.csv())
```

Esta estrategia nos ahorra tener que escribir 154 llamadas a `read.csv()` con el nombre de archivo correcto. También facilita el acceso a todas las tablas en un único objeto, la lista `lista_archivos`. 

## Otros formatos

### Desde la web

Es posible utilizar una URL para leer datos. Es necesario conocer la dirección directa al archivo de texto y su extensión.


```r
datos <- read.table("http://www.algunapagina.com/datos/nombre-archivo.txt")
```


### SAS

Si jugaron con los cuadros de diálogo para importar datos de forma manual, probablemente se toparon con el paquete `haven`, por ejemplo podemos leer desde SAS usando:  


```r
library(haven)
dataset <- read_sas(...)
```

También es posible usar `foreign` y la función `read.ssd()`.

### SPSS

R puede leer datos directamente de spss: 

* El paquete `foreign` contiene la función `read.spss()`. 
* El paquete `haven` y la función `read_spss()`.  

### Excel

En algún momento tendremos que leer datos en la forma `.xls` o `.xlsx`. Existen distintos paquetes que permiten realizar la tarea, por ejemplo:

* `readxl` contiene la función `read_excel()`, entre otras.
* `xlsx` contiene la función `read.xlsx()`, entre otras.


