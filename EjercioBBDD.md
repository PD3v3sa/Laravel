---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Ejercicios con la BBDD
author:
- Pepe Devesa
lang: va

# portada
titlepage-rule-height: 2
#titlepage-rule-color: EE0000
titlepage-text-color: 0F0E0E
titlepage-background: ../img/logo.png

# configuració de l'índex
toc: true
toc-own-page: true
toc-title: Continguts
toc-depth: 2

# capçalera i peu
header-left: \thetitle
header-right: Curs 2023-2024
footer-left: IES Salvador Gadea
footer-right: \thepage/\pageref{LastPage}

# Les figures que apareguen on les definim i centrades
float-placement-figure: H
caption-justification: centering
# No volem numerar les linies de codi
listings-disable-line-numbers: true

# Configuracions dels paquets de latex
header-includes:
# imatges i subfigures
- \usepackage{graphicx}
- \usepackage{subfigure}
- \usepackage{lastpage}

# caixes d'avisos
- \usepackage{awesomebox}
- \usepackage{lastpage}
# text en columnes
- \usepackage{multicol}
- \setlength{\columnseprule}{1pt}
- \setlength{\columnsep}{1em}

page-background: ../img/agua.png
page-background-opacity: 0.5


# definició de les caixes d'avis
pandoc-latex-environment:
   noteblock: [note]
   tipblock: [tip]
   warningblock: [warning]
   cautionblock: [caution]
   importantblock: [important]


...
# Ejercicio Propuesto BBDD y REST
 Sobre la bbdd de la Biblioteca generar:

* En la inserción de un libro insertar también el autor, insertar un desplegable que cargue los autores de la bbdd.
\begin{figure}
\centering
\subfigure[nuevo libro]{\includegraphics[width=0.5\linewidth]{../img/nuevo_libro.png}}
\end{figure}

 * El listado de todos los libros junto a su autor.

 \begin{figure}
\centering
\subfigure[listado libros]{\includegraphics[width=0.5\linewidth]{../img/listado_libros.png}}
\end{figure}

 * Un filtro de libros que muestre los libros de un autor en concreto

 \begin{figure}
\centering
\subfigure[Filtro por autor]{\includegraphics[width=0.5\linewidth]{../img/filtro_autor.png}}
\end{figure}
Resultado:
\begin{figure}
\centering
\subfigure[Resultado del Filtro por autor]{\includegraphics[width=0.5\linewidth]{../img/result_filtro.png}}
\end{figure}

* El enlace Rest para que los programadores puedan descargarse solo los libros y autor, así como uno en concreto.