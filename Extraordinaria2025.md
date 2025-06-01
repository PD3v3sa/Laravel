---
# Metainformació del document
title: Evaluación ExtraOrdinaria 
titlepage: true
subtitle: 
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
header-right: Curs 2024-2025
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
:::important
* El ejercicio de `Laravel` se entregará por *github*.
* **Laravel:** eliminiar del fichero gitignore el `.env`.
* Subir una captura de pantalla con la ejecución en el fichero README.md.
* El ejercicio de PHP se comprimirá y se entregará por medio de `aules`.
* Los 2 ejercicios valen 10 puntos,cada uno, hay que sacar un 3 como mínimo en cada uno para hacer la media.
:::

# Laravel

* Permiso de recogida de Alumnado

Se os pasa un script con los datos de los alumnos, la estructura de la tabla es la siguiente

`````sql
CREATE TABLE `alumnos` (
  `id` int(11) NOT NULL,
  `NIA` int(11) DEFAULT NULL,
  `Nombre` varchar(50) DEFAULT NULL,
  `Apellidos` varchar(100) DEFAULT NULL,
  `NombrePadre` varchar(100) DEFAULT NULL,
  `NombreMadre` varchar(100) DEFAULT NULL,
  `Curso` varchar(10) DEFAULT NULL,
  `Aula` varchar(10) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

`````
* Crear una Base de datos llamada `escuela`.
* Ejecutar el script que se os adjunta.
* Se os pide un mantenimiento como el siguiente, tal que, introducimos el nombre del alumnado y nos muestre los datos.

\begin{figure}
\centering
\subfigure[Listado de libros]{\includegraphics[width=1\linewidth]{../img/extraordinaria.png}}
\end{figure}

1. Crearemos los `modelos`y `controladores` pertinentes.
2. Organizar las distintas vistas que creéis en carpetas.
3. utilizar una `plantilla` para el diseño de las vistas.
4. El botón `ENVIAR` no es necesario.

# PHP

Se os pasa El siguiente mantenimiento:

\begin{figure}
      \centering
      \subfigure[Principal]{\includegraphics[width=0.7\linewidth]{../img/ExtraPHP1.png}}
      \end{figure}

**Se os pide:**

Tenéis que hacer el mantenimiento, solo, de `actualizar` datos del empleado y el `borrado`. Botones `amarillo` y `rojos` de la imagen.

1. Cuando pulséis el botón `amarillo` saldra el siguiente mantenimiento:

\begin{figure}
\centering
\subfigure[Edición]{\includegraphics[width=0.7\linewidth]{../img/ExtraPHP2.png}}
\end{figure}

Modificaréis los datos pertinentes, guardar y volveréis a la pantalla `principal` con las modifcaciones realizadas.

2. Cuando pulséis el botón `rojo` saldra el siguiente mantenimiento:


\begin{figure}
\centering
\subfigure[Borrado]{\includegraphics[width=0.7\linewidth]{../img/ExtraPHP3.png}}
\end{figure}
 ... y eliminaréis o no el registro seleccionado

## Parte lógica
1. El diseño no se puede modificar sólo la lógica.
2. Se os proporciona script con modelo y datos de los empeados y las imagenes.

## Parte Técnica
1. Respetar el `MVC`, que se os pasa.



