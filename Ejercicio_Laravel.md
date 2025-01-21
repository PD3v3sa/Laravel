---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Ejercicio de clase
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

Vamos a agilizar nuestra técnica:
Vamos a crear un ejemplo desde cero, en concreto, el ejercicio es una aplicación web de frutas donde realizaremos un CRUD, trabajaremos con un base de datos relacional, en este caso MySQL.

![Fruteria](image.png)

Tendremos que crear para la tabala _Fruta_:

* controladores
* migracion
* modelo
* faker con solo nombres de frutas
* control de acceso
* añadir el campo imagen
* Por supuesto, plantillas.

:::note
La imagen es orientativa, por supuesto, dejar rienda suelta a la creatividad.
:::