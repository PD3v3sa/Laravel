---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: EXAMEN
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
:::tip
**CRITERIOS DE CALIFICACIÓN:**

* Estructura del proyecto: 1 pto.

* Migracion:               1 pto.

* seeder:                  2 ptos. 

* faker:                   1 pto.

* rutas/controllers:       1 pto.

* uso de eloquent:         1 pto. facade/DB: 0,5 ptos.

* Diseño del proyecto:     2 ptos.

* Diseño para las API:     1 pto. 

:::
El examen va aconsistir en hacer el `mantenimiento` de un videoclub, para ello tendréis que crear un proyecto que le llamaréis `blockbuster`.
Tendréis que crear una migración con los campos de la tabla `peliculas`. Para ver los campos de la tabla se os adjunta un fichero **peliculas.php**. Éste fichero contiene un array con los campos y su contenido, por lo tanto, también tendréis que crear el `seed` para cargar esos mismos datos automáticamente.

:::caution
Como podréis observar las imagenes son enlaces a webs. Esta práctica puede ser ilegal por el tema de los derechos de autor. 
:::

1. Tendréis que crear una pantalla de presentación con **el listado de todas las películas**. 

\begin{figure} 
\centering 
\subfigure[imdb]{\includegraphics[width=5cm,angle=30]{../img/video1.png}}
\subfigure[movistar]{\includegraphics[width=0.3\linewidth]{../img/video2.png}} 
\subfigure[prime]{\includegraphics[width=6cm,angle=30]{../img/video3.png}} 
\subfigure[netflix]{\includegraphics[width=0.3\linewidth]{../img/video4.png}} 
\caption{Listados.} 
\end{figure}


   
2. Tendréis crear un pantalla para **dar de alta** una película.
   
3. SOLO se podrá **actualizar** o **borrar** desde la pantalla de **edición**, donde veremos el contenido del registro y la imagen de la cartelera.


\begin{figure} 
\centering 
\subfigure[movistar]{\includegraphics[width=0.3\linewidth]{../img/detall1.png}}
\subfigure[imdb]{\includegraphics[width=0.3\linewidth]{../img/detall2.png}} 
\subfigure[prime]{\includegraphics[width=0.3\linewidth]{../img/detall3.png}} 
\caption{Detalles.} 
\end{figure}
Además tendréis que crear la pantalla de **inicio** que será un desplegable con usuarios random, es decir tendréis que crear otra `migración` con los campos **nombre** y **e_mail** para los usuarios (tabla usuarios). Rellenar los campos, 10 usuarios, con  **faker**.

4. Modificar la tabla películas y añadir la columna de `protagonista`.

5. Personalizar los errores de las páginas el 404, 500, etc...
 
6. Crear una búsqueda de películas por **director**

7. Permitir la descarga de películas con `JSON` tanto individual como por cualquier criterio(id, director, título).