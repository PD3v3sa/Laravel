---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Assets
author:
- Pepe Devesa

...


# Incluir recursos estáticos (assets)

Los **assets** son los recursos estáticos de una aplicación web: CSS, JavaScript, imágenes, fuentes, etc. Laravel ofrece varias formas de gestionarlos.

1. **Carpeta public**

Todo lo que esté en public/ es accesible directamente desde el navegador. Es la raíz web de la aplicación.

\begin{figure}
\centering
\subfigure[assets]{\includegraphics[width=0.2\linewidth]{./img/assets.png}}
\end{figure}

## Incluir imagenes

Queremos mostrar tarjetas en la página de servicios.


Laravel tiene una función llamada `asset()` que nos permite generar la URL correcta para acceder a los recursos estáticos. Así que lo mejor utilizar la función `asset()`:

```php
<div class="card">
    <h2>Servicio 1</h2>
    <img src="{{ asset('assets/images/servicios.png') }}" alt="Servicio" width="128px">
    <p>Descripicion del servicio</p>
</div>
```
> Las imágenes deben estar en public/assets/images/ y la función asset() generará la URL correcta para acceder a ellas.

## Incluir archivos CSS

Igual que hemos incluido las imágenes, podemos incluir archivos CSS. En la carpeta `assets/css/` creamos un archivo `style.css` y lo enlazamos en el layout. Este archivo contendrá los estilos CSS que queramos aplicar a la aplicación.

Aunque CSS no es objetivo del curso, vamos a ver cómo incluirlo en el layout. Y pondremos alagunas reglas para mejorar el diseño de nuestra web.

**landing.blade.php**

```php
<link rel="stylesheet" href="{{ asset('assets/css/style.css') }}">
```

El fichero puede tener el siguiente contenido de prueba:

```css
h1 {
    color: darkblue;
}
````
Mejorar el diseño.