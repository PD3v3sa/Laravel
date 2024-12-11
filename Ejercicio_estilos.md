---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Estilos y javascript
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

# Ejercicio recomendado: introducción a Laravel 

Crea un proyecto con Laravel llamado **festicortos** con una plantilla general en la que se añadirá un menú con 3 entradas: 

* `Home`: que llevará a la página inicial 

* `Lista de cortos`: que llevará  al listado de cortos como muestra la imagen que se adjunta.

* `Lista de libros`: donde se mostrará una tabla con el contenido del array de libros visto en clase.


Dado el siguiente array:
`````php
$cortos = [ 
       [ 
           'id' => 1, 
           'titulo' => 'El corto más cortante', 
           'director' => 'María Martín', 
           'sinapsis' => 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' 
       ], 
       [ 
           'id' => 2, 
           'titulo' => 'Sin más', 
           'director' => 'Pepa Pérez', 
           'sinapsis' => 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' 
       ], 
       [ 
           'id' => 3, 
           'titulo' => 'Más o menos', 
           'director' => 'Juan Jiménez', 
           'sinapsis' => 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' 
       ], 
       [ 
           'id' => 4, 
           'titulo' => 'Tira pa\' ya', 
           'director' => 'Sofía Sofín', 
           'sinapsis' => 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' 
       ], 
       [ 
           'id' => 5, 
           'titulo' => 'Miedo', 
           'director' => 'Pepe Parrilla', 
           'sinapsis' => 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' 
       ] 
   ]; 
```````
\begin{figure}
\centering
\subfigure[cortos]{\includegraphics[width=1\linewidth]{../img/cortos.png}}
\end{figure}