---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Blog
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
# Crea un proyecto Laravel llamado **blog**.
#  Edita esta migración de la tabla usuarios para dejarla igual que el ejemplo de la biblioteca (únicamente con los campos login y password, además del id y los timestamps).
# Crea una nueva migración llamada crear_tabla_posts, que creará una tabla llamada posts con estos campos:

* Id autonumérico
* Título del post (string)
* Contenido del post (text)
* Timestamps para gestionar automáticamente la fecha de creación o modificación del post

Lanza las migraciones y comprueba que se crean las tablas correspondientes con los campos asociados en la base de datos.

# Crear el PostController 
* La vista `posts.index`, por su parte, recibirá el listado de posts y mostrará los títulos de cada uno, y un botón Ver para mostrar su ficha (posts.show).
* Debes mostrar el listado de posts ordenado por título en orden ascendente, y paginado de 5 en 5.

Para simular la inserción y la modificación, vamos a crear dos métodos adicionales en el controlador, que usaremos de forma temporal:

* Un método llamado **nuevoPrueba**, que cada vez que lo llamemos creará un post con un título al azar (por ejemplo, “Título X”, siendo X un entero aleatorio), y un contenido al azar (“Contenido X”). Puedes emplear la función rand de PHP para generar estos números aleatorios para título y contenido.

* Un método llamado **editarPrueba**, que recibirá como parámetro un id y modificará el título y contenido del post otros generados aleatoriamente, como en el punto anterior.
Estos dos métodos (especialmente el primero) nos servirán para crear una serie de posts de prueba que luego nos servirán para probar el listado y la ficha de los posts.



> Nota: los métodos nuevoPrueba y editarPrueba que has creado en PostController NO son métodos estándar de un controlador de recursos, y de ninguna manera estarán disponibles a través de Route::resource en routes/web.php. Por eso debes definir a mano una ruta para cada uno de ellos en ese archivo, a través de Route::get, y esas rutas deben definirse ANTES de la de recursos (Route::resource) porque de lo contrario no se emparejarán correctamente. 


# Relaciones
* Crea una relación **uno a muchos** entre el modelo de **Usuario** y el modelo de **Post**, ambos ya existentes en la aplicación, de forma que un post es de un usuario, y un usuario puede tener muchos posts. 
* Deberás definir una nueva migración de modificación sobre la tabla posts que añada un nuevo campo usuario_id, y establecer a partir de él la relación, como hemos hecho en el ejemplo con autores y libros.
* Crea desde phpMyAdmin una serie de usuarios de prueba en la tabla usuarios, y asocia algunos de ellos a los posts que haya.
* Modifica la vista posts/index.blade.php para que, junto al título de cada post, entre paréntesis, aparezca el login del usuario que lo creó.

# seeders y Fakers

* Crea un seeder llamado **UsuariosSeeder**. Crea con esto 3 usuarios de prueba, con logins que sean únicos y de una sola palabra (usa el faker), y passwords también de una sola palabra, sin encriptar (para poderlos identificar después, llegado el caso).
* Crea otro seeder llamado **PostsSeeder** define con el faker títulos aleatorios (frases) y contenidos aleatorios (textos largos). Usa el seeder para crear 3 posts para cada uno de los usuarios existentes.

Ejemplo de ejecución:

\begin{figure}
\centering
\subfigure[post]{\includegraphics[width=0.7\linewidth]{../img/post.png}}
\end{figure}

# Auténticación

Protege los posts que solo puedan ser manipulados por los creadores. El resto de usuarios puede leer todos los posts.