---
# Metainformació del document
title: Laravel 
titlepage: true
subtitle: Ejercicio Assets
author:
- Pepe Devesa

...
## Enunciado

1. **Estructura común (todas las páginas)**
   * Usa un **layout** Blade compartido con:
     * **Título de la página**.
     * **Barra de navegación** (enlace a Home, Services, Contact).
     * **Footer**.
   * Implementa la navbar y el footer como **partials**
   * Aplica **CSS** para dar formato (puedes reutilizar el CSS de la práctica anterior).

2. **Home (landing)**
   * Muestra el **nombre de la empresa** (H1).
   * Incluye una **imagen centrada** de portada.

3. **Contact**
   * Presenta un **mapa** (imagen estática).
   * Añade datos típicos de contacto: **teléfono** (`tel:`), **email** (`mailto:`), **dirección** (texto)...

4. **Services**
   * Crea una **rejilla de tarjetas** (mín. 3).
   * Cada **tarjeta** representará una **ciudad**, con:
     * **Imagen**.
     * **Precio**.
     * **Duración del viaje** (nº de días).
     * **Descripción breve**.
     * ***Botón/enlace** a alguna página de interés de la ciudad.
\begin{figure}
\centering
\subfigure[Ciudades]{\includegraphics[width=0.5\linewidth]{./img/city.png}}
\end{figure}
5. **Rutas**
   * Define las rutas **`/`**, **`/contact`** y **`/services`** para mostrar las vistas con Blade.
