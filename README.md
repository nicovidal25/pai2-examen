
# Examen PAI2 - One Page Responsive Site

Este proyecto es un ejemplo de una página web "one page" responsiva que cumple con los requisitos del examen PAI2. En él se utilizan HTML, CSS y JavaScript para crear una interfaz interactiva con animaciones y secciones diferenciadas. Además, se integra un mapa de Google mediante un `<iframe>`.

## Estructura del Proyecto

- **index.html**: Contiene la estructura y el contenido del sitio.
- **styles.css**: Hoja de estilos externa con el diseño, animaciones y reglas responsivas.
- **JavaScript**: Código incluido en el HTML para manejar eventos (por ejemplo, activar animación al hacer click).

## HTML – Etiquetas Clave y Estructura

- `<!DOCTYPE html>`: Declara el documento como HTML5.
- `<html lang="es">`: Define el idioma del contenido.
- `<head>`: 
  - `<meta charset="UTF-8">`: Codificación de caracteres.
  - `<meta name="viewport" content="width=device-width initial-scale=1.0">`: Hace que la página sea responsiva.
  - `<link href="https://fonts.googleapis.com/css?family=Roboto&display=swap" rel="stylesheet">`: Importa la fuente Roboto.
  - `<link rel="stylesheet" href="styles.css">`: Enlaza la hoja de estilos.
- `<body>`: Contiene todo el contenido visible.
  - **Menú de navegación**:
    - `<header>` y `<nav class="navbar">` con una lista `<ul class="menu">` de enlaces (anclas) a cada sección.
  - **Secciones del sitio**:
    - `<main>` agrupa todas las secciones:
      - `<section id="inicio">`: Contiene el banner de la sección de inicio.
      - `<section id="shake">`: Incluye dos columnas (una con rectángulo amarillo y otra con azul) con animaciones de "shake" y texto debajo de cada caja.
      - `<section id="transicion">`: Muestra un rectángulo rojo que se expande de 50% a 100% de ancho mediante `transition`.
      - `<section id="accion">`: Contiene un rectángulo verde que, al hacer click, activa una animación de traslación y cambio de color.
      - `<section id="contacto">`: Dividida en dos partes: formulario de contacto y un mapa embebido mediante `<iframe>`.
  - **Footer**:
    - `<footer>` contiene un enlace a la página de FADU.
- **JavaScript**:
  - Se añade un `eventListener` al elemento con `id="actionRect"` para activar la animación cuando se haga click.

## CSS – Conceptos y Técnicas Utilizadas

- **Reset Básico**: Se eliminan márgenes y paddings para lograr un diseño consistente.
- **Tipografía**: Se aplica la fuente Roboto a todo el documento.
- **Layout y Responsividad**:
  - Uso de Flexbox (`display: flex;`) para organizar elementos en contenedores (por ejemplo, `.menu`, `.shake-container`, `.contact-wrapper`).
  - Media queries (no incluidas en este ejemplo, pero recomendadas) para ajustar el orden de los elementos en pantallas pequeñas.
- **Animaciones y Transiciones**:
  - `@keyframes` se utiliza para definir animaciones:
    - Ejemplo: `colorChange` para el banner, `shake-horizontal` y `shake-vertical` para los rectángulos de la sección shake, y `moveAndColor` para el rectángulo de acción.
  - Propiedad `transition` para cambios suaves de estilo (por ejemplo, en el rectángulo rojo de la sección transición).
- **Mapa Embebido**:
  - Se utiliza un `<iframe>` para insertar el mapa de Google. Es fundamental obtener el código de "Insertar mapa" desde Google Maps (el enlace debe comenzar con `https://www.google.com/maps/embed?...`).

## JavaScript – Interactividad

- Se añade un evento `click` al rectángulo verde (`#actionRect`) para que, al hacer click, se añada la clase `animate-action`, la cual activa la animación definida en CSS.

```js
const actionRect = document.getElementById('actionRect');
actionRect.addEventListener('click', function() {
  this.classList.add('animate-action');
});
```
