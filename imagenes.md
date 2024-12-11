---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Imagenes
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
Mostrar una imagen desde una carpeta de almacenamiento en el desarrollo web implica recuperar el archivo de imagen de la ubicación de almacenamiento y representarlo en la página web. Los pasos específicos involucrados dependerán del lenguaje de programación, el marco y el entorno del servidor que se utilice.

En este tutorial, aprenderemos cómo mostrar imágenes desde la carpeta Almacenamiento en Laravel. Para mostrar una imagen de la carpeta de almacenamiento en Laravel, puedes seguir estos pasos:

# Guardar la imagen en la carpeta de almacenamiento

Cargar el archivo de imagen en el directorio `storage/app/public` o en cualquier otra ubicación dentro de la carpeta de almacenamiento.

# Crea un enlace simbólico 

Laravel no permite el acceso directo a los archivos almacenados en la carpeta de almacenamiento por razones de seguridad. Para que las imágenes sean accesibles, debe crear un enlace simbólico desde la carpeta public a la carpeta storage. Ejecute el siguiente comando en su terminal:
``````
php artisan storage:link
``````
Esto creará un enlace simbólico de `public/storage` a `storage/app/public`.

# Mostrar la imagen en una vista

En su archivo de visualización, utilice la función auxiliar `asset()` para generar la URL de la imagen. La función asset() genera la URL completa de la imagen mediante el enlace simbólico. Por ejemplo:
``````
<img src="{{ asset('storage/images/image.jpg') }}" alt="Image">
``````
Reemplace `storage/images/image.jpg` con la ruta real a su archivo de imagen dentro de la carpeta storage.

