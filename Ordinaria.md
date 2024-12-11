---
# Metainformació del document
title: Evaluación Ordinaria 
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
Los alumnnos que tengan que recuperar todo el módulo harán:

* **1 Evaluación** Las 3 preguntas.
* **Todo** El ejercicio de **Laravel**. Obligatoria 3 y podrán elegir entre la 1 y la 2. 
* **BBDD** El ejercico de BBDD. Solo tendrán 2 horas.
* **BBDD** y **Laravel** los dos ejercicios... 
* **Laravel** El ejercicio de Laravel

* Estructura del proyecto: 1 pto.

* Migracion:               1 pto.

* seeder:                  2 ptos. 

* faker:                   1 pto.

* rutas/controllers:       1 pto.

* uso de eloquent:         1 pto. facade/DB: 0,5 ptos.

* Diseño del proyecto:     2 ptos.

* Diseño para las API:     1 pto. 
:::
# Evaluación

1. Realiza un programa que vaya pidiendo números **hasta** que se introduzca un numero **negativo** y nos diga:
* Cuantos números se han introducido.
* La media de los impares.
* ...y el mayor de los pares. 

El número negativo sólo se utiliza para indicar el final de la introducción de datos pero no se incluye en el cómputo. **Utiliza sesiones**.
\begin{figure} 
\centering 
\subfigure[sesiones]{\includegraphics[width=0.5\linewidth]{../img/sesiones.png}}
\end{figure}
2. Con el vector que se adjunta `comunidades` que consta de las distintas comunidades autónomas y sus provincias con el número de casos de COVID(imaginario), tenéis que hacer una presentación mostrando las Comunidad Autónoma y las provincias, si los números de casos son menors de 500 mostrar en verde sino en rojo. 

El ejemplo os puede dar una idea... preferible mejorar el diseño.

\begin{figure} 
\centering 
\subfigure[COVID]{\includegraphics[width=0.5\linewidth]{../img/comunidades.png}}
\end{figure}

3. Una empresa está desarrollando una aplicación para llevar la gestión integral de un hotel. 
El primer paso será definir la clase **Habitacion** con los atributos y métodos necesarios. Sobre cada habitación
se necesita saber:
   * Su número. 
   * el tipo – clásica, superior o suite – 
   * y su estado – libre, reservada u ocupada. 
* La clase debe almacenar información sobre el número total de habitaciones y sobre el número de habitaciones que quedan libres. 
* Siempre que se crea una habitación nueva, su estado es “libre”. 
* El método reserva debe poner el estado en “reservada” en caso de que esté libre (y debe decrementar el total de habitaciones libres); por el contrario, en caso de estar ya “reservada” u “ocupada”, se debe mostrar el correspondiente mensaje de error. 
* El método ocupa debe poner el estado en “ocupada”, independientemente del estado que tuviera anteriormente. 

El siguiente código del programa principal debe dar la salida que se muestra:


````php
<?php
include 'Habitacion.php';
$h1 = new Habitacion(237, "clásica");
$h2 = new Habitacion(418, "suite");
$h3 = new Habitacion(217, "superior");
$h2->reserva();
$h3->ocupa();
echo "Hay ".$h1->getTotalHabitaciones()." habitaciones.<br>";
echo "Quedan ".$h1->getHabitacionesLibres()." libres.<br>";
echo $h2."<br>";
$h2->reserva();
echo $h3."<br>";
$h3->reserva();
?>
````
`````
Hay 3 habitaciones.
Quedan 1 libres.
Habitación numero 418, suite, reservada
Esa habitación ya está reservada.
Habitación numero 217, superior, ocupada
Esa habitación ya está ocupada, no se puede reservar.
`````

# BBDD
4. Dada la estructura de ladase de datos que se adjunta crear un mantenimiento de la tabla **personas**
Se adjuntan unas capturas de pantalla muy sencillas... Por supuesto así no. 
\begin{figure} 
\centering 
\subfigure[Listar]{\includegraphics[width=0.3\linewidth]{../img/listar.png}}
\subfigure[Editar]{\includegraphics[width=0.3\linewidth]{../img/editar.png}} 
\subfigure[Insertar]{\includegraphics[width=0.3\linewidth]{../img/insertar.png}} 
\caption{Detalles.} 
\end{figure}
Recordar después de cada operación se ha de redireccionar al inicio con ls cambios realizados.

# Laravel
El examen va aconsistir en hacer el `mantenimiento` de una pasteleria, para ello tendréis que crear un proyecto que le llamaréis `lamoderna`.
Tendréis que crear una migración con los campos de la tabla `pasteles`. Los campos se tendrán que crear mediante migración y por lo tanto, también tendréis que crear el `seed` para cargar esos mismos datos automáticamente mediate un faker.

* El `nombre` empezara por 'Pastel de '+ nombre de mujer. 

* el `Sabor` se excogerá un de un array aleatorio con los siguientes datos 'chocolate','vainilla','cheesecake'.

* La `Fecha` de creación...

* y un campo string vacio, `imagen` para cuando editemos introducir la URL de un pastel, por ejemplo: "https://www.elmira.es/media/elmira/images/2022/07/23/2022072318393623204.jpg".

* en la pantalla de **Editar** y **Listar** deberá aparecer la imagen del pastel.

* Crear un enlace para descargar de las `API's`.

\begin{figure} 
\centering 
\subfigure[Listar]{\includegraphics[width=0.3\linewidth]{../img/index_pasteles.png}}
\subfigure[Editar]{\includegraphics[width=0.3\linewidth]{../img/vista_edit.png}} 
\subfigure[Insertar]{\includegraphics[width=0.3\linewidth]{../img/vista_create.png}} 
\caption{Detalles.} 
\end{figure}