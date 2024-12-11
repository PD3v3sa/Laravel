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

# Ejercicios propuestos - Parte 1

## Creación 
Crea un proyecto Laravel llamado `blog`. Ponlo en marcha con el comando `php artisan serve`
## Github
Subirlo al Github
# Ejercicios propuestos - Parte 2

## Ejercicio 1
Sobre el proyecto blog, edita el fichero `routes/web.php` y añade una nueva ruta a la URL posts. Al acceder a esta ruta `(http://ip:port/posts)`, deberemos ver un mensaje con el texto `Listado de posts`.

## Ejercicio 2
Sobre el proyecto blog anterior, vamos a añadir estos dos cambios:

* Añade una nueva ruta parametrizada a `posts/{id}`, de manera que el parámetro id sea numérico (es decir, sólo contenga dígitos del 0 al 9) y obligatorio. Haz que la ruta devuelva el mensaje `Ficha del post XXXX`, siendo XXXX el id que haya recibido como parámetro.

* Pon un nombre a las tres rutas que hay definidas hasta ahora: a la página de inicio ponle el nombre `inicio`, a la del listado la llamaremos `posts_listado` y a la de ficha que acabas de crear, la llamaremos `posts_ficha`.

## Ejercicio 3
Continuamos con el proyecto blog. En este caso vamos a definir una plantilla y una serie de vistas que la utilicen.

Comenzaremos definiendo una plantilla llamada `plantilla.blade.php` en la carpeta de vistas del proyecto (resources/views). 

* Define una cabecera con una sección `yield` para el *título*, y otra para el *contenido* de la página, como la del ejemplo que hemos visto anteriormente.

* Define en un archivo aparte en la subcarpeta `partials`, llamado `nav.blade.php`, una barra de navegación que nos permita acceder a estas direcciones de momento:

    * Página de inicio
    * Listado de posts

Incluye la barra de navegación en la plantilla base que has definido antes. 
A partir de la plantilla base, define otras dos vistas en una subcarpeta posts, llamadas:

* posts/listado.blade.php  

* posts/ficha.blade.php. 

Como título de cada página pon un breve texto de lo que son (por 
ejemplo, `Listado posts y Ficha post`), y como contenido de 
momento deja un encabezado h1 que indique la página en la que estamos: 
“Listado de posts” o “Ficha del post XXXX”, donde XXXX será el 
identificador del post que habremos pasado por la URL (y que deberás 
pasar a la vista). 

 Haz que las rutas correspondientes de `routes/web.php` que ya has 
 definido rendericen estas vistas en lugar de devolver texto plano.

## Ejercicio 4

Incorpora ahora los estilos de `Bootstrap`` siguiendo los pasos vistos en estos apuntes:

* Instala con composer la librería `laravel/ui`, y utilízala para incorporar Bootstrap al proyecto.

* Descarga Bootstrap con `npm install`, y actualiza los archivos CSS y JavaScript con `npm run dev`.

* Incorpora los estilos /css/app.css a la plantilla base del proyecto, para que los utilicen todas las vistas que heredan de ella.

* Edita el archivo partials/nav.blade.php para modificar la barra de navegación y dejarla con un estilo particular de Bootstrap. Puedes consultar esta página para tomar ideas de algunos diseños que puedes aplicar en la barra de navegación.
* Renombra el archivo welcome.blade.php a inicio.blade.php y cámbialo para que también herede de la plantilla base. Añade algún texto introductorio como contenido. Puede quedarte más o menos así (la barra de navegación superior puede variar en función del estilo que hayas querido darle)
\begin{figure}
\centering
\subfigure[Barra de navegación]{\includegraphics[width=0.5\linewidth]{../img/1_blog.png}}
\end{figure}

# Ejercicios propuestos - Controladores

## Ejercicio 1
Sobre el proyecto blog de la sesión anterior, vamos a añadir estos cambios:

* Crea un controlador de recursos (opción -r) llamado `PostController`, que nos servirá para gestionar toda la lógica de los posts del blog.

* Asigna automáticamente con el método resource cada ruta a su función correspondiente del controlador, en el archivo routes/web.php. Limita con only las acciones sólo a las funciones de listado (index), ficha (show), creación (create) y edición (edit).

* Renombra las vistas de listado y ficha de un post a index.blade.php y show.blade.php, dentro de su carpeta posts, y haz que los métodos correspondientes del controlador de posts rendericen estas vistas. Para los métodos create y edit, simplemente devuelve un texto plano indicando “Nuevo post” y “Edición de post”, por ejemplo.

* Haz los cambios adicionales que sean convenientes (por ejemplo, en el menú de navegación) para que los enlaces sigan funcionando, y prueba que las cuatro rutas (listado, ficha, creación y edición) funcionan adecuadamente.

## Ejercicio 2

Sobre el proyecto blog anterior, vamos a añadir estos cambios:

* Haz que las funciones de create y edit del controlador de posts, en lugar de mostrar un mensaje de texto plano indicando que ahí va un formulario, redirijan a la página de inicio, usando la instrucción redirect.

# Ejercicios propuestos - Modelo de Datos

## Ejercicio 1

Sobre el proyecto blog de la sesión anterior, vamos a añadir estos cambios:

* Crea una base de datos llamada blog en tu servidor de bases de datos a través de phpMyAdmin. Modifica también el archivo .env del proyecto para acceder a dicha base de datos con las credenciales adecuadas, similares a las del ejemplo de la biblioteca (cambiando el nombre de la base de datos).

* Elimina todas las migraciones existentes, salvo la de `create_users_table`. Edita esta migración de la tabla usuarios para dejarla igual que el ejemplo de la biblioteca (únicamente con los campos login y password, además del id y los timestamps).

* Crea una nueva migración llamada crear_tabla_posts, que creará una tabla llamada posts con estos campos:

    * Id autonumérico
    
    * Título del post (string)
    
    * Contenido del post (text)
    
    * Timestamps para gestionar automáticamente la fecha de creación o modificación del post
    
* Lanza las migraciones y comprueba que se crean las tablas correspondientes con los campos asociados en la base de datos.

* Opcionalmente, puedes desactivar las migraciones de Sanctum en el proyecto Laravel, como se ha explicado al final de este documento, si al crear las migraciones aparece alguna otra tabla no deseada, como la de los _personal_access_tokens_. Recuerda ejecutar **`php artisan migrate:fresh`** de nuevo para borrar el rastro de esas tablas.

## Ejercicio 2
Modifica si no lo has hecho aún el modelo `User` que viene por defecto para que se llame Usuario. Crea un nuevo modelo llamado `Post` para los posts de nuestro blog. Asegúrate de que se ubica en la carpeta `App\Models` del proyecto.
Después, modifica los métodos del controlador PostController creado en sesiones anteriores, de este modo:

* El método `index` debe obtener todos los posts de la tabla, y mostrar la vista `posts.index` con ese listado de posts.
    * La vista `posts.index`, por su parte, recibirá el listado de posts y mostrará los títulos de cada uno, y un botón Ver para mostrar su ficha (posts.show).
    
    * Debes mostrar el listado de posts ordenado por título en orden ascendente, y paginado de 5 en 5.
    
* El método `show` debe obtener el post cuyo id se pasará como parámetro, y mostrarlo en la vista posts.show.

    * La vista `posts.show` recibirá el objeto con el post a mostrar, y mostraremos el título, contenido y fecha de creación del post, con el formato que quieras.
    
* El método `destroy` eliminará el post cuyo id recibirá como parámetro, y devolverá la vista `posts.index` con el listado actualizado. Para probar este método, recuerda que debes definir un formulario en una vista (lo puedes hacer para cada post mostrado en la vista posts.index) que envíe a la ruta `posts.destroy` usando un método _DELETE_.

* Crea una relación **uno a muchos** entre el modelo de `Usuario` y el modelo de `Post`, ambos ya existentes en la aplicación, de forma que un post es de un usuario, y un usuario puede tener muchos posts. 
Deberás definir una nueva migración de modificación sobre la tabla posts que añada un nuevo campo usuario_id, y establecer a partir de él la relación, como hemos hecho en el ejemplo con autores y libros.

* Crea desde phpMyAdmin una serie de usuarios de prueba en la tabla usuarios, y asocia algunos de ellos a los posts que haya.

* Modifica la vista posts/index.blade.php para que, junto al título de cada post, entre paréntesis, aparezca el login del usuario que lo creó.

## Ejercicio 3

* Crea un `seeder` llamado `UsuariosSeeder`. Crea con esto 3 usuarios de prueba, con logins que sean únicos y de una sola palabra (usa el faker), y passwords también de una sola palabra, sin encriptar (para poderlos identificar después, llegado el caso).

* Crea otro `seeder` llamado `PostsSeeder` con un faker títulos aleatorios (frases) y contenidos aleatorios (textos largos). Usa el seeder para crear 3 posts para cada uno de los usuarios existentes.

Utiliza la opción `php artisan migrate:fresh --seed` para borrar todo contenido previo y poblar la base de datos con estos nuevos elementos. Comprueba después desde la página del listado de posts, y desde phpMyAdmin, que la información que aparece es correcta.

## Ejercicio 4 (OPCIONAL)

Añade al proyecto blog un nuevo `modelo` llamado `Comentario`, junto con su migración y controlador asociados. Cada comentario tendrá como campo el contenido del comentario, y estará relacionado uno a muchos con el modelo Usuario, de forma que un usuario puede tener muchos comentarios, y cada comentario pertenece a un usuario. También tendrá una relación uno a muchos con el modelo Post, de modo que un comentario pertenece a un post, y un post puede tener muchos comentarios. Por lo tanto, la migración de los comentarios deberá tener como campos adicionales la relación con el usuario (usuario_id) y con el post al que pertenece (post_id).

Aplica la migración para reflejar la nueva tabla en la base de datos, y utiliza un seeder y un fake para crear 3 comentarios en cada post, con el usuario que sea. A la hora de aplicar todo esto, borra los contenidos previos de la base de datos (migrate:fresh --seed).

En la ficha de los posts (vista `posts/show.blade.php`), añade el código necesario para mostrar el login del usuario que ha hecho el post, y el listado de comentarios asociado al post, mostrando para cada uno el login del usuario que lo hizo, y el texto del comentario en sí. Utiliza también la librería Carbon para mostrar la fecha de creación del post (o la de los comentarios, como prefieras) en formato d/m/Y.

\begin{figure}
\centering
\subfigure[Comentarios]{\includegraphics[width=0.5\linewidth]{../img/comentarios.png}}
\end{figure}
