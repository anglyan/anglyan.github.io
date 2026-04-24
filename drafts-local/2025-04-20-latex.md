---
layout: post
title:  "Latex, Overleaf y arXiv"
categories: recursos
---

Busca en un repositorio como arXiv y lo más probable es que encuentres papers
que tiene un formato muy parecido al que encuentras en revistas científicas (por
ejemplo [éste](https://arxiv.org/abs/2412.10477) de los míos) y que claramente
no están escritos con un procesador de texto como Word. Lo más probable es
que estén escritos usando [LaTeX](https://es.wikipedia.org/wiki/LaTeX).


LaTeX es un sistema de composición de texto en el que el contenido se combina con códigos
que te permiten describir cómo diferentes partes del texto debes aparecer en el pdf. Si
en un procesador como Word lo que ves es my parecido a cómo va a imprimirse, en el
caso de LaTeX, el siguiente fragmento de texto sin formato:

{% highlight latex %}
\documentclass{article}
\begin{document}

   \section*{Leyes de Gauss}
   
   Las leyes de Gauss en sistema internacional:
   
   \begin{itemize}
   \item Ley de Gauss para el campo eléctrico:
   \begin{equation}
   \nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon_0}
   \end{equation}
   \item Ley de Gauss para el campo magnético:
   \begin{equation}
   \nabla \cdot \mathbf{B} = 0
   \end{equation}
   \end{itemize} 
   
\end{document}
{% endhighlight %}

se transforma en el siguiente PDF:

![PDF output of a latex document](/assets/images/latex_sample.png){: width="500" .center-image}

La ventaja de LaTeX radica en el uso de templates que describen con precisión este proceso
de transformación. Como usuario puedes centrarte en el contenido sin tener que preocuparte
del formato. El uso de LaTeX es común en campos como la física, la computación
y la inteligencia artificial. Por ejemplo, muchas conferencias de machine learning o inteligencia
artificial requiren el uso de templates, hasta el punto que no seguir las instrucciones al pie
hace que tu paper sea automáticamente rechazado. 

Desde el punto de vista estético, el estilo de las ecuaciones es fantástico, y
una vez que se te hace el ojo es muy difícil volver a ecuaciones generadas por otros programas.

## Overleaf

Una de las cosas que me ha ayudado más en los últimos años es la popularización de 
[Overleaf](https://www.overleaf.com/). Overleaf es un editor de LaTeX online que te permite
colaborar en documentos ([wiki en español](https://es.wikipedia.org/wiki/Overleaf)). Aparte
de no tener que preocuparte de cómo instalar LaTeX en tu ordenador, Overleaf viene con una
lista enorme de templates, incluyendo las de muchos publishers. Si quieres escribir un paper
para una revista del American Institute of Physics, puedes rápidamente empezar a escribir tu
trabajo usando el formato específico de esa revista. Como el template contiene todas las
secciones que necesitas para escribir tu trabajo, no tienes que aprender a user LaTeX desde
cero. La mayoría de las dudas se pueden resolver con una búsqueda rápida en Google.


Incluso si mi primera versión de un trabajo es en Word (por ejemplo porque mis colaboradores no
trabajen con LaTeX), antes de enviar un manuscrito lo suelo convertir en LaTeX y uso el template del
publisher o la conferencia. Cuando varios de los autores trabajan en LaTeX, Overleaf se ha convertido
en la forma más práctica de poder escribir el manuscrito de manera conjunta. La mayoría de
mis colaboradores que trabajan en inteligencia artificial usan Overleaf para casi todo, incluyendo
escribir proyectos de investigación.

A efectos prácticos, Overleaf funciona
de manera parecida a Google drive: puedes compartir el enlace con colaboradores, tienes una copia online privada, y puedes bajarte el pdf compilado. Mi recomendación es sin embargo no
dejarlo todo en la cloud: como en Overleaf puedes bajarte todos los ficheros del projecto, una de las
cosas que hago justo antes de enviar un paper es asegurarme de que puedo crear el mismo documento
en mi ordenador. De esa manera me aseguro de que tengo una copia completa y si hay información que
no quiero poner en la cloud, puedo añadirla una vez que tengo mi copia local.

## Cómo instalar LaTeX en tu ordenador

Es posible usar LaTeX tanto en Windows como Linux o Mac, y las instrucciones de cómo instalar LaTeX
están disponibles [aquí](https://www.latex-project.org/get/#tex-distributions) (en inglés).

Una de las principales diferencias para alguien acostumbrado a usar un procesador de texto es que 
los documentos se escriben en un fichero de texto con la extensión `.tex`. Existen editores
específicos que te hacen la vida más fácil, por ejemplo resaltando en diferentes colores
las diferentes partes del texto para diferenciar los códigos del contenido. 

Algunas de las
distribuciones de LaTeX vienen con una serie de programas instalados, que incluyen editores
específicos para LaTeX. Uno que uso prácticamente a diario es [LaTeXiT](https://www.chachatelier.fr/latexit/),
que te permite rápidamente
crear imágenes de ecuaciones generadas en LaTeX. Está incluido en mi distribución de TexLive
para Mac.




