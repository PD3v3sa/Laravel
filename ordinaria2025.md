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
* Los 2 ejercicios se entregarán por *github*.
* **Laravel:** eliminiar del fichero gitignore el `.env`.
* **PHP:** No subir la carpeta de imagenes.
* En los dos casos hay que subir una captura de pantalla con la ejecución en el fichero README.md.
:::

# Laravel

Vamos a crear el mantenimiento(_reducido_) del préstamo de libros...

## En cuanto a la **parte lógica.**

* En primer lugar, si el **usuario es admin** tendrá derecho a toda la funcionalidad del sistema, en caso contrario solo podrá ver los libros que hay en la biblioteca.
* Tendremos un mantenimiento para **crear nuevos libros** titulo, autor, editorial y carátula(_dirección url_)
\begin{figure}
\centering
\subfigure[nuevo libro]{\includegraphics[width=0.5\linewidth]{../img/nuevo.png}}
\end{figure}

* **Listado de Libros**
\begin{figure}
\centering
\subfigure[Listado de libros]{\includegraphics[width=0.7\linewidth]{../img/listado25.png}}
\end{figure}

 Como vemos en la imagen solo mostramos el título, autor, y editorial, además tendremos dos acciones:

   * `Historial de préstamos`

   Mostrará un listado con loss socios que se han llevado prestado el libro alguna vez. con la fecha de préstamo y devoulción
      \begin{figure}
      \centering
      \subfigure[Historial de prestamos]{\includegraphics[width=0.7\linewidth]{../img/historial.png}}
      \end{figure}
      
   * `Préstamos`

       Muestra si ese socio tiene más libros prestados:

\begin{figure}
\centering
\subfigure[Prestamos por socio]{\includegraphics[width=0.7\linewidth]{../img/prestecsoci.png}}
\end{figure}

   * `Detalles del libro`
   En esta pantalla si que veremos la carátula del libro
    \begin{figure}
      \centering
      \subfigure[Detalles del libro]{\includegraphics[width=0.7\linewidth]{../img/detalles2025.png}}
      \end{figure}

* **Listado de Socios**
Lista de socios con un enlace a su historial de préstamos(_misma pantalla que préstamos_)

\begin{figure}
      \centering
      \subfigure[Listado de socios]{\includegraphics[width=0.7\linewidth]{../img/listSocios.png}}
      \end{figure}


* **Listado de préstamos**

 Nada

## En cuanto a la **parte técnica**.

1. Crearemos los `modelos`y `controladores` pertinentes.
2. Organizar las distintas vistas que creéis en carpetas.
3. utilizar una `plantilla` para el diseño de las vistas.
4. Crear las `migraciones` para, usuario(login,password),libros(id,titulo,autor,editorial y las fechas), socios(id,nombre,email,y las fechas), prestamos(libro_id,socio_id).
5. Crear los `seeder` y los `faker` para los socios al menos 10. También para el usuario(admin,admin)
6. Si es el usuario `admin` indicarlo en la barra `navs`. 
7. Implementar la opción de `cerrar e iniciar sesión`.
8. Tanto en el **Historial de préstamos** como en **Préstamos** debe de aparcer el nombre del libro y/o usuario, respectivamente, como en las imagenes.
9. El diseño es orientativo.
10. Para subir a `github` eliminiar del archivo `.env`

# PHP

Vamos a Realizar un mantenimiento como el de la figura:

\begin{figure}
      \centering
      \subfigure[PHP]{\includegraphics[width=0.7\linewidth]{../img/phpcrud.png}}
      \end{figure}

**Se os pide:**

Tenéis que hacer el mantenimiento solo de `actualizar` datos del empleado y el `borrado`.

## Parte lógica
1. El diseño tiene que ser idéntico, puede variar color o algún detalle. pero tanto la lista de empleados como la ficha debe de estar todo en la misma pantalla.
2. Se os proporciona script con modelo y datos de los empeados.
3. Las imagenes son cosa vuestra.

## Parte Técnica
1. Tendréis que tener utilizar la técnica del `MVC`, todo organizado en carpetas y bien estructurado. La estructura debe seguir el siguiente modelo:
\begin{figure}
\centering
\subfigure[MVC]{\includegraphics[width=0.3\linewidth]{../img/mvc.png}}
\end{figure}
