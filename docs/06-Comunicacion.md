# Comunicación

El trabajo estadístico no termina cuando entendemos la estructura de los datos. Nuestro trabajo estará incompleto a menos que logremos llevar aquello que destilamos de la evidencia a la combinación correcta de palabras e imagenes que logren recrear el mensaje en otra mente.  

La mayoría de los usos a continuación requieren cierta familiaridad con los sistemas de control de versiones (por ejemplo, GIT) y plataformas online basadas en dichos sistemas (por ejemplo, GitHub). Dicho material excede a la complejidad de este libro[^git].

## Ciencia reproducible

## Gráficos

## RMarkdown

Markdown es un lenguage de marcado ligero que permite agregar marcajes sencillos al texto plano (`.md`), para convertirlo en un poderoso conjunto de operaciones que pueden exportarse a formatos de publicación profesional como `.html`, `.pdf` y `.tex`[^markdown-wiki]. *RMarkdown* es la implementación de Markdown dentro de Rstudio. RMarkdown posee toda la funcionalidad de Markdown y además permite introducir trozos de código.  

Los archivos de Rmarkdown son archivos de texto con extensión `.Rmd`. Podemos crearlo dentro de Rstudio desde el mismo menú con el que abrimos scripts.  

![Abrir una ventana de Rmd](img/rmarkdown-01.png)

Al abrirlo, un navegador nos permitirá seleccionar opciones (como el título, autor, etc). No me centraré en esa ventana debido a que todas estas opciones pueden modificarse en el encabezado del nuevo archivo `.Rmd`.   

## Texto

Markdown es un lenguaje que permite escribir de manera veloz, con muy pocas distracciones. La funcionalidad para editar la presentación de texto es limitada, pero es más que suficiente para el 99% de las cosas que necesitamos al escribir. Los siguientes ejemplos están ordenados segun cómo se escriben en Rmarkdown y cómo es el render.


`Lo esencial es *invisible* a los ojos.` $\rightarrow$ Lo esencial es *invisible* a los ojos.  
`Lo esencial es **invisible** a los ojos.` $\rightarrow$ Lo esencial es **invisible** a los ojos. 
`Lo esencial es ~~in~~visible a los ojos.` $\rightarrow$ Lo esencial es ~~in~~visible a los ojos. 

Si tienes familiaridad con $\LaTeX$ es posible utilizarlo para fórmulas matemáticas en línea con la frase que se está escribiendo. Por ejemplo, un supuesto de los modelos lineales generales es $\mathcal{E}_i \sim \  \mathcal{N}(\mu,\,\sigma^{2})$. Utilzar $\LaTeX$ en RMarkdown es tan sencillo como englobar el código utilizando el símbolo `$`. Si queremos utilizar una ecuación, por ejemplo, utilizamos los entornos `\begin{equation}` y `\end{equation}` y escribimos sin necesidad de utilizar el símbolo `$`.  

Para utilizar resaltado tipo `código` en línea utilizamos palabras envueltas en *backticks* (`` ` ``)[^backticks]. Podemos utilizar código de R en la línea en la que estamos escribiendo de la forma `r`+`espacio`+`función deseada`. Por ejemplo, si combinamos con $\LaTeX$ y le preguntamos a R cuánto es $\pi$, nos dará el resultado en la misma línea así: $\pi$ = 3.1415927[^en-mi-pc].

## Separando líneas y párrafos

La belleza de Rmarkdown es que acomoda el texto y las figuras automáticamente, por lo que no debemos preocuparnos por el número de líneas y demás problemas que aparecen con un editor de texto tradicional. Sin embargo, en ciertas ocasiones realmente deseamos forzar un quiebre, un espacio extra. Para separar párrafos, basta con terminar la línea que se está escribiendo con dos espacios. Por ejemplo,  

*No te des por vencido, ni aún vencido, no te sientas esclavo, ni aún esclavo;*  

Puede transformarse en:  

*No te des por vencido, ni aún vencido,*  
*no te sientas esclavo, ni aún esclavo;*  

Si agregamos dos espacios entre las palabras deseadas[^normalmente].  

Las listas de objetos son un caso puntual muy útil:

```
# Listas no numeradas
* item 1
* item 2
+ sub-item
* item 3
    * sub-item
    * sub-item

```
Se ve así:  

* item 1
* item 2
+ sub-item
* item 3
    * sub-item
    * sub-item

```
# Listas numeradas
1. item 1
1. item 2
1. item 3
    a) item 3a
    a) item 3b
```
Se ve así:  

En las listas numeradas no debemos mantener la cuenta. Simplemente `1. ` y escribimos lo que necesitamos, Markdown hace el resto!  

Otra posibilidad es utilizar texto resaltado. Para resaltar texto utilizamos el símbolo mayor (>) seguido de un espacio. Esta opción no es recomendada para uso extensivo, pero puede resaltar una frase corta de un modo interesante. Por ejemplo,  

> R es genial.

Cuando terminamos una sección o deseamos una marca física entre párrafos, podemos usar 3 asteriscos (*).  

```
# Línea
***
```

Se ve:  

***

## Trozos de código

En Rmarkdown podemos mezclar texto y código de R. La siguiente figura muestra cómo se ve en mi computadora:  

![El párrafo previo en mi editor](img/rmarkdown-code-chunk.png)

Cuando estos trozos se agregan al documento final, corren en la consola de R y el output se incluye en los resultados. Por ejemplo, el siguiente trozo:


```r
summary(cars)
```

```
##      speed           dist       
##  Min.   : 4.0   Min.   :  2.00  
##  1st Qu.:12.0   1st Qu.: 26.00  
##  Median :15.0   Median : 36.00  
##  Mean   :15.4   Mean   : 42.98  
##  3rd Qu.:19.0   3rd Qu.: 56.00  
##  Max.   :25.0   Max.   :120.00
```

## Links e imágenes

Los links e imágenes pueden incluirse utilizando corchetes ([]) y paréntesis. Por ejemplo,

```
# Imágenes
![descripcion de mi imagen](link)
# URLs
[descripción de mi link](link)
```
El link puede ser un directorio dentro de nuestra computadora (`imagenes/vacaciones/.png`) o via `www` con un link externo, como ![el logo de Rstudio](https://www.rstudio.com/wp-content/uploads/2016/09/RStudio-Logo-Blue-Gray-250.png)

## Encabezado YAML

Los encabezados son útiles para diversos archivos, ciertamente necesarios para la organización de documentos más complejos. Rmarkdown utiliza un encabezado conocido como YAML y tiene la siguiente forma:

```
--- 
title: "Un mundo feliz"
author: "Aldous Huxley"
date: "1932"
output: html_document
---
```

Por ejemplo, el encabezado de este libro es el siguiente[^encabezado]:

```
--- 
title: "Introducción a estadística con R"
author: "Matias Andina"
date: "2018-07-28"
site: bookdown::bookdown_site
documentclass: book
---

```

Notarán algunas variaciones, por ejemplo, en la fecha. El llamado a `Sys.Date()` permite que cada vez que este libro se compila, se use la fecha de sistema para el compilado., De este modo, no tengo que actualizarlo manualmente cada vez que edito el libro.  

## Otros proyectos con RStudio

* Presentaciones de diapositivas con Markdown y `R presentation`.
* Usando el paquete `blogdown`, Websites como [este](http://matiasandina.netlify.com)
* Usando el paquete `bookdown`, libros como éste ([y otros!](bookdown.org))

## Notas

Mucha tecnología cotidiana detrás de los servicios de publicación está principalmente desarrollada alrededor del idioma inglés. Problemas inesperados pueden aparecer incluso cuando hacemos todo bien utilizando R, Rstudio y Rmarkdown. Por ejemplo, mientras escribía este libro tuve un problema con el nombre de mis archivos que contenían tilde (por ejemplo, el archivo de este capítulo era "Comunicación.Rmd"). La inconveniente `ó` provocó que el link a ciertas imágenes del capítulo (`www. .../Comunicación/imagen-01.png`) no pudiera ser encontrado y dichas imágenes no aparecieran. La solición de compromiso es (como en muchas otras direcciones de internet) no utilizar caracteres que no existen en inglés (por ejemplo, la ñ, o palabras con tildes).

## Recursos

* Cheatsheet oficial de Rmarkdown en español por Rstudio [aquí](https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-spanish.pdf)

[^encabezado]: El encabezado que muestro es una porción que es comparable con un documento clásico. El encabezado real contiene ciertas especificaciones para que este libro pueda ser publicado online y entiendo que no aportan al ejemplo.
[^markdown-wiki]: Puedes encontrar más información sobre Markdown[aquí](es.wikipedia.org/markdown)
[^git]: Puedes aprender sobre GIT [aquí](https://git-scm.com/book/es/v1/Empezando)
[^normalmente]: Normalmente suelo agregar un enter y escribir en la siguiente línea. Aunque no es necesrario, me ayuda a visualizar el render antes de tiempo.
[^backticks]: Los backtics son difícilies de encontrar en el teclado en español, puedes probar ALT+96.
[^en-mi-pc]: Para lograr esto el formato debe ser `` $\pi$ = 3.1415927 ``
