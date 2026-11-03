---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Estilos y javascript
author:
- Pepe Devesa
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


Pulsar el botón y que aprezca :
\begin{figure}
\centering
\subfigure[detalle]{\includegraphics[width=1\linewidth]{../img/detalle.png}}
\end{figure}