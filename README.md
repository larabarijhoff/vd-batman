# VD | DataGeek - La trayectoria de Batman: Un ícono en la cultura geek 

### Historia visual interactiva web de Batman basada en datos
![Batman](public/images/bat_lluvia.jpg)
---

## Referencias: 
- [https://github.com/sveltejs/svelte-scroller](https://github.com/sveltejs/svelte-scroller)

## Fuentes:
- [Página web: "Comichron"](https://comichron.com)
- [Página web: "Comicbook Round Up"](https://comicbookroundup.com)
- [Página web: "IMDb"](https://www.imdb.com)
- [Página web: "Box Office Mojo"](https://www.boxofficemojo.com/)

---
## Setup IDE recomendado:
[VS Code](https://code.visualstudio.com/) + [Svelte](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode).

# Documentación Extra del Código en App.svelte:

## Creación y Dibujo de Gotas de Lluvia

### Variables
- `canvas` y `ctx` son variables para el elemento canvas y su contexto de dibujo.

### Estructura de Datos
- `raindrops` almacena las gotas de lluvia.

### Funciones
- `createRaindrop`: Crea una nueva gota de lluvia con propiedades aleatorias.
- `drawRain`: Dibuja las gotas de lluvia en el canvas, actualizando su posición y reciclando las gotas que salen del área visible.

## Gráficos
Para la creación de los distintos gráficos, utilizamos [Datawrapper](https://www.datawrapper.de/), una herramienta de visualización de datos. Luego de generarlos, los exportamos y los personalizamos en Figma. Esto nos permitió ajustar detalles estéticos y de diseño para asegurarnos de que los gráficos mantuvieran la estética coherente con el resto de la página web.
Este contenido proporciona una documentación clara y detallada sobre la creación y dibujo de las 
