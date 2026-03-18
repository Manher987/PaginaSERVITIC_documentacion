# 📚 DOCUMENTACIÓN COMPLETA - PROYECTO SERVITIC

**Versión:** 1.0  
**Fecha:** Marzo 2026  
**Autor:** Documentación para estudiantes  
**Objetivo:** Guía completa de HTML, CSS y JavaScript para el sitio web SERVITIC

---

## 📋 ÍNDICE

1. [Introducción](#introducción)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [HTML - Estructura y Semántica](#html-estructura-y-semántica)
4. [CSS - Estilos y Diseño](#css-estilos-y-diseño)
5. [JavaScript - Interactividad](#javascript-interactividad)
6. [Diseño Responsive](#diseño-responsive)
7. [Buenas Prácticas](#buenas-prácticas)
8. [Ejercicios Prácticos](#ejercicios-prácticos)
9. [Recursos Adicionales](#recursos-adicionales)
10. [Glosario de Términos](#glosario-de-términos)

---

## 🎯 INTRODUCCIÓN

### ¿Qué es este proyecto?

SERVITIC es un sitio web profesional de una empresa ficticia de servicios tecnológicos. Este proyecto ha sido diseñado con fines educativos para enseñar los fundamentos del desarrollo web moderno.

### Tecnologías Utilizadas

- **HTML5**: Estructura y contenido semántico
- **CSS3**: Estilos, diseño responsive y animaciones
- **JavaScript (Vanilla)**: Interactividad sin frameworks

### Características Principales

✅ Diseño responsive (se adapta a móviles, tablets y desktop)  
✅ Navegación suave entre secciones  
✅ Formulario de contacto funcional  
✅ Efectos hover en elementos interactivos  
✅ Código semántico y accesible  
✅ Sin dependencias externas (no requiere librerías)

---

## 📁 ESTRUCTURA DEL PROYECTO

```
proyecto-servitic/
│
├── index.html          # Archivo HTML principal
├── styles.css          # Hoja de estilos
├── documentacion.md    # Este documento
└── README.md           # Instrucciones básicas (opcional)
```

### Organización Recomendada para Proyectos Grandes

```
proyecto-web/
│
├── index.html
├── css/
│   ├── styles.css
│   ├── responsive.css
│   └── animations.css
├── js/
│   ├── main.js
│   └── formulario.js
├── img/
│   ├── logo.png
│   └── servicios/
├── fonts/
│   └── custom-font.woff2
└── docs/
    └── documentacion.md
```

---

## 🏗️ HTML - ESTRUCTURA Y SEMÁNTICA

### 1. Estructura Básica del Documento HTML

#### DOCTYPE
```html
<!DOCTYPE html>
```

**¿Qué hace?**  
Declara que el documento usa HTML5 (la versión más moderna de HTML).

**Importancia:**  
- Debe ser SIEMPRE la primera línea del documento
- Sin esto, el navegador entra en "modo quirks" (comportamiento antiguo e inconsistente)
- En versiones antiguas de HTML la declaración era mucho más larga

**Ejemplo de DOCTYPE antiguo (HTML 4.01):**
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
```

---

#### Etiqueta HTML Root
```html
<html lang="es">
```

**Atributos:**
- `lang="es"`: Indica el idioma del contenido (español)

**Beneficios:**
- Ayuda a lectores de pantalla (accesibilidad)
- Mejora el SEO (buscadores identifican el idioma)
- Navegadores pueden ofrecer traducción automática

**Otros idiomas:**
- `lang="en"` → Inglés
- `lang="fr"` → Francés
- `lang="de"` → Alemán
- `lang="ca"` → Catalán

---

### 2. Sección HEAD - Metadatos

#### Meta Charset
```html
<meta charset="UTF-8">
```

**Función:**  
Define la codificación de caracteres del documento.

**UTF-8:**  
- Estándar universal que soporta TODOS los idiomas
- Incluye caracteres especiales: ñ, á, é, ü, 中文, 日本語, emojis 😊
- Sin esto: los acentos pueden aparecer como �� o caracteres extraños

**Problema común:**
```html
<!-- Sin UTF-8 -->
Descripción → DescripciÃ³n
Tecnología → TecnologÃ­a
```

---

#### Meta Viewport
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

**Función:**  
Controla cómo se visualiza la página en dispositivos móviles.

**Parámetros:**
- `width=device-width`: El ancho se ajusta al ancho del dispositivo
- `initial-scale=1.0`: Zoom inicial al 100% (sin zoom)

**Sin esta etiqueta:**
- En móviles, la página aparece muy pequeña (como si fuera desktop)
- Usuario debe hacer zoom manualmente
- Experiencia de usuario pésima

**Parámetros adicionales opcionales:**
```html
<meta name="viewport" content="
  width=device-width, 
  initial-scale=1.0, 
  maximum-scale=5.0,
  user-scalable=yes
">
```

---

#### Title
```html
<title>SERVITIC - Servicios Tecnológicos y Mantenimiento Informático</title>
```

**Usos:**
1. Aparece en la pestaña del navegador
2. Marcadores/favoritos guardan este texto
3. Buscadores lo muestran en resultados (SEO)
4. Redes sociales lo usan al compartir

**Buenas Prácticas:**
- Máximo 60 caracteres (Google trunca el resto)
- Incluir palabras clave relevantes
- Formato: `Nombre Página - Descripción Breve - Empresa`

**Ejemplos:**
```html
<!-- Bueno -->
<title>SERVITIC - Servicios IT y Mantenimiento Informático</title>

<!-- Malo: muy largo -->
<title>SERVITIC - Empresa de Servicios Tecnológicos, Mantenimiento Informático, Reparación de Computadoras, Redes, Seguridad...</title>

<!-- Malo: muy genérico -->
<title>Inicio</title>
```

---

#### Link a CSS
```html
<link rel="stylesheet" href="styles.css">
```

**Atributos:**
- `rel="stylesheet"`: Indica que es una hoja de estilos
- `href="styles.css"`: Ruta al archivo CSS

**Rutas:**
```html
<!-- Misma carpeta -->
<link rel="stylesheet" href="styles.css">

<!-- Carpeta css -->
<link rel="stylesheet" href="css/styles.css">

<!-- Carpeta padre -->
<link rel="stylesheet" href="../styles.css">

<!-- URL externa -->
<link rel="stylesheet" href="https://cdn.ejemplo.com/styles.css">
```

**Alternativa (no recomendada):**
```html
<style>
  body { color: red; }
</style>
```
❌ Mezcla HTML con CSS (difícil de mantener)

---

### 3. Etiquetas Semánticas HTML5

#### ¿Qué es HTML Semántico?

HTML semántico usa etiquetas que **describen el significado** del contenido, no solo su apariencia.

**Comparación:**

```html
<!-- ❌ NO SEMÁNTICO (HTML antiguo) -->
<div id="header">
  <div id="nav">
    <div class="menu-item">Inicio</div>
  </div>
</div>
<div id="content">
  <div class="article">
    <div class="title">Título</div>
    <div class="text">Contenido...</div>
  </div>
</div>
<div id="footer">
  <div class="copyright">© 2026</div>
</div>

<!-- ✅ SEMÁNTICO (HTML5 moderno) -->
<header>
  <nav>
    <a href="#inicio">Inicio</a>
  </nav>
</header>
<main>
  <article>
    <h1>Título</h1>
    <p>Contenido...</p>
  </article>
</main>
<footer>
  <p>© 2026</p>
</footer>
```

**Ventajas del HTML Semántico:**

1. **Accesibilidad:** Lectores de pantalla entienden mejor la estructura
2. **SEO:** Buscadores identifican la importancia de cada sección
3. **Mantenimiento:** Código más legible para otros desarrolladores
4. **Estándares:** Sigue las mejores prácticas web modernas

---

#### Etiquetas Semánticas Principales

| Etiqueta | Uso | Ejemplo |
|----------|-----|---------|
| `<header>` | Cabecera de página o sección | Logo y menú principal |
| `<nav>` | Menú de navegación | Enlaces del menú |
| `<main>` | Contenido principal (solo 1 por página) | Todo el contenido central |
| `<section>` | Sección temática del contenido | Servicios, Contacto |
| `<article>` | Contenido independiente | Post de blog, producto |
| `<aside>` | Contenido complementario | Sidebar, anuncios |
| `<footer>` | Pie de página | Copyright, enlaces legales |
| `<figure>` | Contenido ilustrativo | Imágenes con caption |
| `<figcaption>` | Descripción de figure | Texto bajo imagen |

---

#### HEADER
```html
<header>
  <div class="logo">SERVITIC</div>
  <nav>
    <ul>
      <li><a href="#inicio">Inicio</a></li>
    </ul>
  </nav>
</header>
```

**Características:**
- Contiene la cabecera de la página
- Típicamente: logo, menú de navegación
- Puede haber múltiples `<header>` (uno por página, otros por sección)

**Alternativa antigua:** `<div id="header">`

---

#### NAV
```html
<nav>
  <ul>
    <li><a href="#servicios">Servicios</a></li>
    <li><a href="#contacto">Contacto</a></li>
  </ul>
</nav>
```

**Función:**
- Indica una sección de navegación
- Solo para navegación **principal o importante**
- No usar para cualquier grupo de enlaces

**Cuándo SÍ usar `<nav>`:**
- Menú principal del sitio
- Tabla de contenidos
- Breadcrumbs (migas de pan)
- Paginación

**Cuándo NO usar `<nav>`:**
- Enlaces en el footer (usar solo `<footer>`)
- Enlaces dentro de un artículo
- Botones de redes sociales

---

#### MAIN
```html
<main>
  <section id="servicios">...</section>
  <section id="contacto">...</section>
</main>
```

**Reglas:**
- **Solo UNO por página**
- Contiene el contenido principal
- Excluye: header, footer, navegación lateral

**Beneficios de accesibilidad:**
```html
<!-- Lector de pantalla: "Saltar al contenido principal" -->
<a href="#main">Ir al contenido</a>
<main id="main">
  <!-- Contenido aquí -->
</main>
```

---

#### SECTION
```html
<section id="servicios">
  <h2>Nuestros Servicios</h2>
  <p>Descripción...</p>
</section>
```

**Características:**
- Agrupa contenido temáticamente relacionado
- Típicamente tiene un encabezado (h2, h3)
- Representa una sección genérica del documento

**Diferencia con `<div>`:**
- `<section>`: tiene significado semántico
- `<div>`: contenedor genérico sin significado

---

#### ARTICLE
```html
<article class="service-card">
  <h3>Mantenimiento Informático</h3>
  <p>Descripción del servicio...</p>
</article>
```

**Características:**
- Contenido independiente que tiene sentido por sí solo
- Podría distribuirse de forma independiente
- Ejemplos: post de blog, noticia, producto, comentario

**Cuándo usar `<article>`:**
- Post de blog
- Noticia
- Producto en catálogo
- Comentario de usuario
- Widget independiente

**Diferencia `<section>` vs `<article>`:**
- `<section>`: Agrupa contenido relacionado
- `<article>`: Contenido independiente y reutilizable

---

#### FOOTER
```html
<footer>
  <div class="footer-info">
    <p>Email: info@servitic.com</p>
    <p>© 2026 SERVITIC</p>
  </div>
</footer>
```

**Contenido típico:**
- Copyright
- Enlaces legales (Privacidad, Cookies, Términos)
- Información de contacto
- Redes sociales
- Mapa del sitio

**Múltiples footers:**
```html
<article>
  <h2>Artículo</h2>
  <p>Contenido...</p>
  <footer>
    <p>Autor: Juan | Fecha: 2026</p>
  </footer>
</article>
```

---

### 4. Formularios HTML

#### Estructura Básica
```html
<form action="procesar.php" method="POST">
  <label for="nombre">Nombre:</label>
  <input type="text" id="nombre" name="nombre" required>
  
  <button type="submit">Enviar</button>
</form>
```

**Atributos del FORM:**
- `action`: URL donde se envían los datos
- `method`: GET (datos en URL) o POST (datos ocultos)

**En nuestro proyecto:**
```html
<form class="contact-form">
  <!-- Sin action ni method: JavaScript maneja el envío -->
</form>
```

---

#### INPUT - Tipos y Atributos

**Tipos principales:**

```html
<!-- Texto normal -->
<input type="text" name="nombre">

<!-- Email (valida formato) -->
<input type="email" name="email">

<!-- Teléfono (teclado numérico en móviles) -->
<input type="tel" name="telefono">

<!-- Contraseña (oculta texto) -->
<input type="password" name="clave">

<!-- Número -->
<input type="number" name="edad" min="0" max="120">

<!-- Fecha -->
<input type="date" name="nacimiento">

<!-- Color -->
<input type="color" name="favorito">

<!-- Archivo -->
<input type="file" name="documento" accept=".pdf,.doc">

<!-- Checkbox -->
<input type="checkbox" name="acepto" value="si">

<!-- Radio button -->
<input type="radio" name="sexo" value="m"> Masculino
<input type="radio" name="sexo" value="f"> Femenino
```

**Atributos importantes:**

| Atributo | Descripción | Ejemplo |
|----------|-------------|---------|
| `id` | Identificador único | `id="email"` |
| `name` | Nombre del campo al enviar | `name="email"` |
| `placeholder` | Texto de ejemplo | `placeholder="ejemplo@mail.com"` |
| `required` | Campo obligatorio | `required` |
| `disabled` | Campo deshabilitado | `disabled` |
| `readonly` | Solo lectura | `readonly` |
| `value` | Valor predeterminado | `value="Madrid"` |
| `min`, `max` | Valores mínimo/máximo | `min="0" max="100"` |
| `pattern` | Validación con regex | `pattern="[0-9]{9}"` |
| `autocomplete` | Autocompletado | `autocomplete="email"` |

---

#### LABEL - Etiquetas de Formulario
```html
<label for="email">Email:</label>
<input type="email" id="email" name="email">
```

**Importancia del atributo `for`:**
- Conecta el label con el input mediante el ID
- Al hacer clic en el label, el input se activa
- **Crucial para accesibilidad** (lectores de pantalla)

**Ejemplo sin label (MAL):**
```html
<input type="email" placeholder="Email">
<!-- ❌ Lectores de pantalla no saben qué es este campo -->
```

**Ejemplo con label (BIEN):**
```html
<label for="email">Email:</label>
<input type="email" id="email">
<!-- ✅ Lectores de pantalla: "Email, campo de texto" -->
```

---

#### TEXTAREA
```html
<textarea id="mensaje" name="mensaje" rows="5" cols="30"></textarea>
```

**Diferencias con INPUT:**
- Permite múltiples líneas
- Tamaño ajustable por el usuario (por defecto)
- Requiere etiqueta de cierre: `</textarea>`

**Atributos específicos:**
- `rows`: Número de líneas visibles
- `cols`: Número de columnas (caracteres por línea)
- `maxlength`: Límite de caracteres

---

#### BUTTON
```html
<button type="submit">Enviar</button>
<button type="button">Acción JS</button>
<button type="reset">Limpiar</button>
```

**Tipos:**
- `submit`: Envía el formulario (por defecto)
- `button`: No hace nada (usar con JavaScript)
- `reset`: Limpia todos los campos

**Alternativa (antigua):**
```html
<input type="submit" value="Enviar">
```

---

### 5. Listas HTML

#### Lista No Ordenada (UL)
```html
<ul>
  <li>Elemento 1</li>
  <li>Elemento 2</li>
  <li>Elemento 3</li>
</ul>
```

**Renderizado:**
- ● Elemento 1
- ● Elemento 2
- ● Elemento 3

---

#### Lista Ordenada (OL)
```html
<ol>
  <li>Primer paso</li>
  <li>Segundo paso</li>
  <li>Tercer paso</li>
</ol>
```

**Renderizado:**
1. Primer paso
2. Segundo paso
3. Tercer paso

**Atributos:**
```html
<!-- Empezar en 5 -->
<ol start="5">
  <li>Paso 5</li>
  <li>Paso 6</li>
</ol>

<!-- Números romanos -->
<ol type="I">
  <li>Capítulo I</li>
  <li>Capítulo II</li>
</ol>

<!-- Orden inverso -->
<ol reversed>
  <li>3</li>
  <li>2</li>
  <li>1</li>
</ol>
```

---

#### Lista de Definiciones (DL)
```html
<dl>
  <dt>HTML</dt>
  <dd>Lenguaje de marcado para crear páginas web</dd>
  
  <dt>CSS</dt>
  <dd>Lenguaje para dar estilo a páginas web</dd>
</dl>
```

**Elementos:**
- `<dl>`: Definition List
- `<dt>`: Definition Term (término)
- `<dd>`: Definition Description (descripción)

---

### 6. Enlaces (Anchor)

```html
<!-- Enlace externo -->
<a href="https://google.com">Google</a>

<!-- Enlace interno (ancla) -->
<a href="#servicios">Ver Servicios</a>

<!-- Email -->
<a href="mailto:info@servitic.com">Contactar</a>

<!-- Teléfono -->
<a href="tel:+34900123456">Llamar</a>

<!-- Nueva pestaña -->
<a href="https://google.com" target="_blank" rel="noopener">Google</a>

<!-- Descargar archivo -->
<a href="documento.pdf" download>Descargar PDF</a>
```

**Atributos importantes:**

| Atributo | Uso |
|----------|-----|
| `href` | URL de destino |
| `target="_blank"` | Abre en nueva pestaña |
| `rel="noopener"` | Seguridad con target="_blank" |
| `download` | Descarga en vez de navegar |
| `title` | Tooltip al pasar el mouse |

**Anclas (navegación interna):**
```html
<!-- Enlace -->
<a href="#contacto">Ir a Contacto</a>

<!-- Destino -->
<section id="contacto">
  <h2>Contacto</h2>
</section>
```

---

### 7. Entidades HTML

Caracteres especiales que necesitan codificación:

| Entidad | Resultado | Descripción |
|---------|-----------|-------------|
| `&copy;` | © | Copyright |
| `&reg;` | ® | Registrado |
| `&trade;` | ™ | Marca registrada |
| `&nbsp;` |   | Espacio sin separación |
| `&lt;` | < | Menor que |
| `&gt;` | > | Mayor que |
| `&amp;` | & | Ampersand |
| `&quot;` | " | Comillas |
| `&apos;` | ' | Apóstrofe |
| `&euro;` | € | Euro |
| `&#8364;` | € | Euro (código numérico) |

**¿Por qué son necesarias?**

```html
<!-- ❌ PROBLEMA -->
<p>Usa la etiqueta <p> para párrafos</p>
<!-- El navegador confunde el <p> interno con etiqueta HTML -->

<!-- ✅ SOLUCIÓN -->
<p>Usa la etiqueta &lt;p&gt; para párrafos</p>
<!-- Renderiza: Usa la etiqueta <p> para párrafos -->
```

---

## 🎨 CSS - ESTILOS Y DISEÑO

### 1. Anatomía de una Regla CSS

```css
selector {
  propiedad: valor;
  otra-propiedad: otro-valor;
}
```

**Ejemplo:**
```css
h1 {
  color: blue;
  font-size: 24px;
  text-align: center;
}
```

---

### 2. Tipos de Selectores

#### Selector de Etiqueta
```css
p {
  color: black;
}
/* Aplica a TODOS los <p> */
```

#### Selector de Clase
```css
.destacado {
  background: yellow;
}
/* Aplica a elementos con class="destacado" */
```

```html
<p class="destacado">Texto destacado</p>
```

#### Selector de ID
```css
#header {
  background: blue;
}
/* Aplica solo a id="header" */
```

```html
<header id="header">...</header>
```

#### Selector Descendiente
```css
nav a {
  color: white;
}
/* Aplica a <a> que estén DENTRO de <nav> */
```

#### Selector Hijo Directo
```css
nav > ul {
  list-style: none;
}
/* Aplica a <ul> que sean hijos DIRECTOS de <nav> */
```

#### Selector de Atributo
```css
input[type="email"] {
  border-color: blue;
}
/* Aplica a inputs con type="email" */
```

#### Selector Múltiple
```css
h1, h2, h3 {
  font-family: Arial;
}
/* Aplica a h1, h2 y h3 */
```

#### Pseudo-clases
```css
a:hover { color: red; }           /* Mouse encima */
a:active { color: green; }        /* Al hacer clic */
a:visited { color: purple; }      /* Enlace visitado */
input:focus { border: 2px solid blue; } /* Campo enfocado */
li:first-child { font-weight: bold; }   /* Primer hijo */
li:last-child { font-style: italic; }   /* Último hijo */
li:nth-child(2) { color: red; }   /* Segundo hijo */
li:nth-child(odd) { background: #f0f0f0; } /* Impares */
li:nth-child(even) { background: white; }  /* Pares */
```

#### Pseudo-elementos
```css
p::first-line { font-weight: bold; }  /* Primera línea */
p::first-letter { font-size: 2em; }   /* Primera letra (drop cap) */
p::before { content: "→ "; }          /* Antes del contenido */
p::after { content: " ←"; }           /* Después del contenido */
```

---

### 3. Especificidad CSS

La especificidad determina qué estilo se aplica cuando hay conflicto.

**Orden de prioridad (de mayor a menor):**

1. `!important` (evitar usarlo)
2. Estilos inline: `<p style="color: red">`
3. IDs: `#header`
4. Clases, atributos, pseudo-clases: `.clase`, `[type]`, `:hover`
5. Etiquetas, pseudo-elementos: `div`, `::before`

**Cálculo de especificidad:**

| Selector | Especificidad | Peso |
|----------|---------------|------|
| `*` | 0,0,0,0 | Ninguno |
| `p` | 0,0,0,1 | 1 |
| `.clase` | 0,0,1,0 | 10 |
| `#id` | 0,1,0,0 | 100 |
| `style=""` | 1,0,0,0 | 1000 |
| `!important` | ∞ | Infinito |

**Ejemplos:**

```css
/* Especificidad: 0,0,0,1 */
p { color: blue; }

/* Especificidad: 0,0,1,0 */
.texto { color: red; }

/* Especificidad: 0,1,0,0 */
#principal { color: green; }

/* Especificidad: 0,0,1,1 */
p.texto { color: purple; }

/* Especificidad: 0,1,1,1 */
#principal p.texto { color: orange; }
```

**¿Cuál gana?**
```html
<p id="principal" class="texto">Hola</p>
```

```css
p { color: blue; }              /* 0,0,0,1 */
.texto { color: red; }          /* 0,0,1,0 ← GANA */
#principal { color: green; }    /* 0,1,0,0 ← GANA MÁS */
```

El texto será **verde** (#principal tiene mayor especificidad).

---

### 4. Box Model (Modelo de Caja)

Todos los elementos HTML son cajas rectangulares:

```
┌─────────────────────────────────────┐
│        MARGIN (exterior)            │
│  ┌───────────────────────────────┐  │
│  │   BORDER (borde)              │  │
│  │  ┌─────────────────────────┐  │  │
│  │  │ PADDING (interior)      │  │  │
│  │  │  ┌───────────────────┐  │  │  │
│  │  │  │    CONTENT        │  │  │  │
│  │  │  │    (contenido)    │  │  │  │
│  │  │  └───────────────────┘  │  │  │
│  │  └─────────────────────────┘  │  │
│  └───────────────────────────────┘  │
└─────────────────────────────────────┘
```

**Propiedades:**

```css
.caja {
  /* Contenido */
  width: 200px;
  height: 100px;
  
  /* Padding (interior) */
  padding: 20px;
  
  /* Border */
  border: 2px solid black;
  
  /* Margin (exterior) */
  margin: 10px;
}
```

**Tamaño total:**
- Con `box-sizing: content-box` (default):  
  Ancho total = 200 + (20×2) + (2×2) = 244px
  
- Con `box-sizing: border-box` (recomendado):  
  Ancho total = 200px (incluye padding y border)

---

### 5. Unidades de Medida

#### Absolutas (tamaño fijo)
- `px`: Píxeles (1px = 1 punto en pantalla)
- `pt`: Puntos (1pt = 1/72 pulgadas)
- `cm`, `mm`, `in`: Centímetros, milímetros, pulgadas

#### Relativas (escalables)
- `%`: Porcentaje del elemento padre
- `em`: Relativo al font-size del padre (se acumula)
- `rem`: Relativo al font-size del root (`<html>`) **← RECOMENDADO**
- `vw`: % del ancho de viewport (1vw = 1% del ancho de ventana)
- `vh`: % del alto de viewport (1vh = 1% del alto de ventana)
- `vmin`: El menor de vw o vh
- `vmax`: El mayor de vw o vh

**Ejemplos:**

```css
html {
  font-size: 16px; /* Base */
}

body {
  font-size: 1rem;     /* 16px */
  padding: 2rem;       /* 32px */
  width: 80vw;         /* 80% del ancho de ventana */
  max-width: 1200px;   /* Máximo 1200px */
}

.titulo {
  font-size: 2rem;     /* 32px */
  margin-bottom: 1rem; /* 16px */
}

.subtitulo {
  font-size: 1.5rem;   /* 24px */
}
```

**¿Por qué usar REM?**
- Escalable (usuarios pueden cambiar tamaño base)
- Accesible (respeta preferencias del usuario)
- Responsive (se ajusta proporcionalmente)
- Predecible (no se acumula como EM)

---

### 6. Colores en CSS

#### Hexadecimal
```css
color: #ff0000;  /* Rojo */
color: #00ff00;  /* Verde */
color: #0000ff;  /* Azul */
color: #fff;     /* Blanco (forma corta) */
color: #000;     /* Negro (forma corta) */
```

**Formato:** `#RRGGBB`
- RR: Red (00-FF)
- GG: Green (00-FF)
- BB: Blue (00-FF)

#### RGB
```css
color: rgb(255, 0, 0);    /* Rojo */
color: rgb(0, 255, 0);    /* Verde */
color: rgb(0, 0, 255);    /* Azul */
```

#### RGBA (con transparencia)
```css
background: rgba(0, 0, 0, 0.5);  /* Negro 50% transparente */
background: rgba(255, 0, 0, 0.8); /* Rojo 80% opaco */
```

**Alpha:** 0 (transparente) a 1 (opaco)

#### HSL (Hue, Saturation, Lightness)
```css
color: hsl(0, 100%, 50%);    /* Rojo */
color: hsl(120, 100%, 50%);  /* Verde */
color: hsl(240, 100%, 50%);  /* Azul */
```

- **Hue:** 0-360 (0=rojo, 120=verde, 240=azul)
- **Saturation:** 0-100% (0=gris, 100=color puro)
- **Lightness:** 0-100% (0=negro, 50=normal, 100=blanco)

#### Nombres de Colores
```css
color: red;
color: blue;
color: white;
color: black;
color: tomato;
color: skyblue;
```

200+ nombres disponibles.

---

### 7. Tipografía

#### Font Family
```css
font-family: 'Segoe UI', Arial, sans-serif;
```

**Familias genéricas:**
- `serif`: Con serifas (Times New Roman)
- `sans-serif`: Sin serifas (Arial)
- `monospace`: Ancho fijo (Courier)
- `cursive`: Manuscrita
- `fantasy`: Decorativa

**Fuentes web (Google Fonts):**
```html
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
```

```css
body {
  font-family: 'Roboto', sans-serif;
}
```

#### Font Size
```css
font-size: 16px;
font-size: 1rem;
font-size: 1.5em;
font-size: 120%;
```

#### Font Weight
```css
font-weight: normal;  /* 400 */
font-weight: bold;    /* 700 */
font-weight: 100;     /* Thin */
font-weight: 300;     /* Light */
font-weight: 500;     /* Medium */
font-weight: 600;     /* Semi-bold */
font-weight: 900;     /* Black */
```

#### Line Height
```css
line-height: 1.6;     /* Sin unidad (recomendado) */
line-height: 24px;    /* Píxeles */
line-height: 150%;    /* Porcentaje */
```

**Legibilidad:** 1.4-1.8 es ideal.

#### Text Align
```css
text-align: left;     /* Izquierda */
text-align: center;   /* Centrado */
text-align: right;    /* Derecha */
text-align: justify;  /* Justificado (evitar en web) */
```

#### Text Transform
```css
text-transform: uppercase;    /* MAYÚSCULAS */
text-transform: lowercase;    /* minúsculas */
text-transform: capitalize;   /* Primera Letra Mayúscula */
```

#### Letter Spacing
```css
letter-spacing: 1px;   /* Más espacio entre letras */
letter-spacing: -1px;  /* Menos espacio */
```

#### Text Decoration
```css
text-decoration: none;        /* Sin decoración */
text-decoration: underline;   /* Subrayado */
text-decoration: line-through; /* Tachado */
text-decoration: overline;    /* Línea superior */
```

---

### 8. Backgrounds (Fondos)

#### Background Color
```css
background-color: #fff;
background-color: rgba(0,0,0,0.5);
```

#### Background Image
```css
background-image: url('imagen.jpg');
background-repeat: no-repeat;
background-position: center;
background-size: cover;
```

**Background Size:**
- `cover`: Cubre todo el contenedor (puede recortar)
- `contain`: Muestra toda la imagen (puede dejar espacios)
- `100% 100%`: Estira la imagen
- `auto`: Tamaño original

#### Linear Gradient
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

**Dirección:**
- `to right`: Izquierda → Derecha
- `to bottom`: Arriba → Abajo
- `45deg`: 45 grados
- `135deg`: Diagonal

**Múltiples colores:**
```css
background: linear-gradient(90deg, 
  red 0%, 
  yellow 50%, 
  green 100%
);
```

#### Radial Gradient
```css
background: radial-gradient(circle, #667eea, #764ba2);
```

---

### 9. Borders y Border Radius

#### Border
```css
border: 2px solid black;
```

**Sintaxis:** `grosor estilo color`

**Estilos:**
- `solid`: Línea continua
- `dashed`: Guiones - - -
- `dotted`: Puntos · · ·
- `double`: Línea doble
- `groove`, `ridge`, `inset`, `outset`: Efectos 3D

**Lados individuales:**
```css
border-top: 2px solid red;
border-right: 1px dashed blue;
border-bottom: 3px dotted green;
border-left: none;
```

#### Border Radius
```css
border-radius: 10px;     /* Todas las esquinas */
border-radius: 50%;      /* Círculo (si width = height) */
border-radius: 10px 20px 30px 40px; /* Cada esquina */
```

**Esquinas individuales:**
```css
border-top-left-radius: 10px;
border-top-right-radius: 20px;
border-bottom-right-radius: 30px;
border-bottom-left-radius: 40px;
```

---

### 10. Box Shadow

```css
box-shadow: offset-x offset-y blur spread color;
```

**Ejemplo:**
```css
box-shadow: 0 4px 15px rgba(0,0,0,0.1);
```

**Parámetros:**
- `offset-x`: Desplazamiento horizontal (negativo = izquierda)
- `offset-y`: Desplazamiento vertical (negativo = arriba)
- `blur`: Difuminado (0 = definida, 50+ = muy difusa)
- `spread` (opcional): Expande/contrae la sombra
- `color`: Color de la sombra

**Múltiples sombras:**
```css
box-shadow: 
  0 2px 5px rgba(0,0,0,0.1),
  0 4px 20px rgba(0,0,0,0.2);
```

**Sombra interna:**
```css
box-shadow: inset 0 2px 10px rgba(0,0,0,0.3);
```

---

### 11. Display

Controla cómo se renderiza un elemento.

```css
display: block;
display: inline;
display: inline-block;
display: flex;
display: grid;
display: none;
```

#### Block
- Ocupa todo el ancho disponible
- Empieza en nueva línea
- Respeta width, height, margin, padding
- Ejemplos: `<div>`, `<p>`, `<h1>`

#### Inline
- Solo ocupa el ancho de su contenido
- No empieza en nueva línea
- NO respeta width, height, margin-top, margin-bottom
- Ejemplos: `<span>`, `<a>`, `<strong>`

#### Inline-Block
- Híbrido: en línea pero respeta width/height
- Útil para botones, imágenes con texto

#### Flex
- Sistema de layout unidimensional (fila o columna)
- Distribución flexible de elementos

#### Grid
- Sistema de layout bidimensional (filas y columnas)
- Más potente que Flexbox

#### None
- Oculta el elemento completamente
- Como si no existiera en el HTML

---

### 12. Flexbox

Flexbox es un sistema de layout para organizar elementos en una dimensión (fila o columna).

#### Contenedor Flex
```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}
```

**Propiedades del contenedor:**

| Propiedad | Valores | Descripción |
|-----------|---------|-------------|
| `flex-direction` | `row`, `row-reverse`, `column`, `column-reverse` | Dirección principal |
| `justify-content` | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly` | Alineación en eje principal |
| `align-items` | `flex-start`, `flex-end`, `center`, `stretch`, `baseline` | Alineación en eje transversal |
| `flex-wrap` | `nowrap`, `wrap`, `wrap-reverse` | Permite saltar a nueva línea |
| `gap` | `1rem`, `20px` | Espacio entre items |

**Visualización:**

```css
/* flex-direction: row (default) */
[1] [2] [3] [4]

/* flex-direction: column */
[1]
[2]
[3]
[4]

/* justify-content: space-between */
[1]              [2]              [3]

/* justify-content: center */
        [1] [2] [3]

/* align-items: center */
    [1]  (centrado verticalmente)
```

#### Items Flex
```css
.item {
  flex: 1;
  flex-grow: 1;
  flex-shrink: 1;
  flex-basis: 200px;
  align-self: center;
}
```

**Propiedades del item:**

| Propiedad | Descripción |
|-----------|-------------|
| `flex-grow` | Cuánto crece el item (default: 0) |
| `flex-shrink` | Cuánto se encoge (default: 1) |
| `flex-basis` | Tamaño base antes de distribuir espacio |
| `align-self` | Alineación individual (sobrescribe align-items) |
| `order` | Orden de aparición |

**Shorthand:**
```css
flex: grow shrink basis;
flex: 1;        /* grow=1, shrink=1, basis=0 */
flex: 1 0 200px; /* grow=1, shrink=0, basis=200px */
```

---

### 13. CSS Grid

Grid es un sistema de layout bidimensional para crear diseños complejos.

#### Contenedor Grid
```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: auto;
  gap: 1rem;
}
```

**Definir columnas:**
```css
/* 3 columnas iguales */
grid-template-columns: 1fr 1fr 1fr;

/* Columnas de tamaños específicos */
grid-template-columns: 200px 1fr 300px;

/* Repetir patrón */
grid-template-columns: repeat(3, 1fr);

/* Responsive automático */
grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
```

**Unidad FR (Fracción):**
- `1fr`: 1 parte del espacio disponible
- `2fr 1fr`: Primera columna el doble de ancha

**Ejemplo responsive:**
```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}
```

**Comportamiento:**
- Pantalla ancha: 4 columnas
- Tablet: 2-3 columnas
- Móvil: 1 columna
- ¡Sin media queries!

---

### 14. Position

Controla el posicionamiento de elementos.

```css
position: static;
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

#### Static (default)
- Posición normal en el flujo del documento
- No responde a top, right, bottom, left

#### Relative
- Relativo a su posición original
- Puede moverse con top/right/bottom/left
- NO sale del flujo (deja espacio vacío)

```css
.relativo {
  position: relative;
  top: 20px;
  left: 30px;
}
```

#### Absolute
- Relativo al ancestro posicionado más cercano
- Sale del flujo (otros elementos lo ignoran)
- Si no hay ancestro posicionado, relativo a `<body>`

```css
.padre {
  position: relative; /* Referencia para el hijo */
}

.hijo {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

**Uso común:** Posicionar íconos, badges, overlays

#### Fixed
- Relativo a la ventana del navegador
- Permanece fijo al hacer scroll
- Sale del flujo

```css
.header-fijo {
  position: fixed;
  top: 0;
  width: 100%;
}
```

#### Sticky
- Híbrido: relative + fixed
- Se comporta como relative hasta alcanzar un umbral
- Luego se "pega" como fixed

```css
.menu-pegajoso {
  position: sticky;
  top: 0;
}
```

**Z-Index:**
```css
.elemento {
  position: relative; /* Necesario para z-index */
  z-index: 10;
}
```

Controla el orden de apilamiento (valores mayores = más cerca).

---

### 15. Transitions (Transiciones)

Animación suave entre estados.

```css
.elemento {
  transition: property duration timing-function delay;
}
```

**Ejemplo:**
```css
.boton {
  background: blue;
  transition: background 0.3s ease;
}

.boton:hover {
  background: darkblue;
}
```

**Propiedades:**

| Propiedad | Valores | Ejemplo |
|-----------|---------|---------|
| `property` | `all`, `color`, `transform`, etc. | `background` |
| `duration` | Tiempo en segundos | `0.3s`, `500ms` |
| `timing-function` | `ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out` | `ease` |
| `delay` | Retraso antes de iniciar | `0.1s` |

**Múltiples propiedades:**
```css
transition: 
  background 0.3s ease,
  transform 0.5s ease-in-out,
  opacity 0.2s linear;
```

**Shortcut:**
```css
transition: all 0.3s ease;
/* Anima TODAS las propiedades que cambien */
```

---

### 16. Transform

Aplica transformaciones 2D/3D sin afectar el flujo.

```css
transform: translate(10px, 20px);
transform: scale(1.5);
transform: rotate(45deg);
transform: skew(10deg, 20deg);
```

#### Translate (Mover)
```css
transform: translateX(50px);   /* Derecha */
transform: translateY(-20px);  /* Arriba */
transform: translate(50px, -20px); /* X, Y */
```

#### Scale (Escalar)
```css
transform: scale(1.2);      /* 120% */
transform: scaleX(1.5);     /* Solo ancho */
transform: scaleY(0.8);     /* Solo alto */
```

#### Rotate (Rotar)
```css
transform: rotate(45deg);   /* Horario */
transform: rotate(-90deg);  /* Antihorario */
```

#### Skew (Inclinar)
```css
transform: skewX(20deg);
transform: skewY(10deg);
```

#### Múltiples transformaciones
```css
transform: translateY(-5px) scale(1.1) rotate(2deg);
```

**Ventajas de Transform:**
- Más performante que margin/position
- No afecta otros elementos
- Usa aceleración de GPU
- Animaciones más suaves

---

### 17. Media Queries

CSS condicional para diseño responsive.

```css
@media (condición) {
  /* Estilos que aplican si se cumple la condición */
}
```

**Ejemplos:**

```css
/* Móviles (hasta 768px) */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}

/* Tablets (768px - 1024px) */
@media (min-width: 768px) and (max-width: 1024px) {
  .container {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Desktop (1024px+) */
@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
  }
}

/* Orientación */
@media (orientation: landscape) {
  .header {
    height: 60px;
  }
}

/* Pantallas retina */
@media (min-resolution: 2dppx) {
  .logo {
    background-image: url('logo@2x.png');
  }
}

/* Impresión */
@media print {
  .no-imprimir {
    display: none;
  }
}
```

**Breakpoints comunes:**
- 320px: Móviles pequeños
- 480px: Móviles grandes
- 768px: Tablets
- 1024px: Laptops
- 1200px: Desktops
- 1440px: Desktops grandes

**Estrategias:**

1. **Mobile First:**
```css
/* Estilos base para móviles */
.container { width: 100%; }

/* Tablet+ */
@media (min-width: 768px) {
  .container { width: 80%; }
}

/* Desktop+ */
@media (min-width: 1024px) {
  .container { width: 1200px; }
}
```

2. **Desktop First:**
```css
/* Estilos base para desktop */
.container { width: 1200px; }

/* Tablet- */
@media (max-width: 1024px) {
  .container { width: 90%; }
}

/* Móvil- */
@media (max-width: 768px) {
  .container { width: 100%; }
}
```

---

## ⚡ JAVASCRIPT - INTERACTIVIDAD

### 1. Introducción a JavaScript

JavaScript es el lenguaje de programación que añade interactividad a las páginas web.

**Características:**
- Lenguaje interpretado (no compilado)
- Orientado a objetos
- Basado en eventos
- Dinámicamente tipado

**Dónde escribir JavaScript:**

```html
<!-- 1. Inline (no recomendado) -->
<button onclick="alert('Hola')">Click</button>

<!-- 2. Script interno -->
<script>
  console.log('Hola');
</script>

<!-- 3. Script externo (recomendado) -->
<script src="main.js"></script>
```

---

### 2. Variables y Tipos de Datos

#### Declaración de Variables

```javascript
// var (antiguo, evitar)
var nombre = "Juan";

// let (puede cambiar)
let edad = 25;
edad = 26;

// const (no puede cambiar)
const PI = 3.14159;
```

#### Tipos de Datos

```javascript
// String (texto)
let nombre = "Ana";
let apellido = 'García';
let mensaje = `Hola ${nombre}`;  // Template literal

// Number (número)
let entero = 42;
let decimal = 3.14;
let negativo = -10;

// Boolean (verdadero/falso)
let activo = true;
let visible = false;

// Array (lista)
let colores = ['rojo', 'verde', 'azul'];
let numeros = [1, 2, 3, 4, 5];

// Object (objeto)
let persona = {
  nombre: 'Juan',
  edad: 30,
  activo: true
};

// Null y Undefined
let vacio = null;
let noDefinido;
```

---

### 3. Operadores

```javascript
// Aritméticos
let suma = 5 + 3;        // 8
let resta = 10 - 4;      // 6
let multiplicacion = 3 * 4;  // 12
let division = 20 / 5;   // 4
let modulo = 10 % 3;     // 1 (resto)
let potencia = 2 ** 3;   // 8

// Comparación
5 == '5'   // true (igualdad débil)
5 === '5'  // false (igualdad estricta)
5 != '5'   // false
5 !== '5'  // true
10 > 5     // true
10 < 5     // false
10 >= 10   // true
10 <= 5    // false

// Lógicos
true && false  // AND (false)
true || false  // OR (true)
!true          // NOT (false)

// Asignación
let x = 5;
x += 3;  // x = x + 3 (8)
x -= 2;  // x = x - 2 (6)
x *= 2;  // x = x * 2 (12)
x /= 3;  // x = x / 3 (4)
```

---

### 4. Condicionales

```javascript
// If-else
let edad = 18;

if (edad >= 18) {
  console.log('Eres mayor de edad');
} else {
  console.log('Eres menor de edad');
}

// If-else if-else
let nota = 85;

if (nota >= 90) {
  console.log('Excelente');
} else if (nota >= 70) {
  console.log('Bien');
} else if (nota >= 50) {
  console.log('Aprobado');
} else {
  console.log('Reprobado');
}

// Operador ternario
let mensaje = edad >= 18 ? 'Mayor' : 'Menor';

// Switch
let dia = 'lunes';

switch (dia) {
  case 'lunes':
    console.log('Inicio de semana');
    break;
  case 'viernes':
    console.log('Fin de semana');
    break;
  default:
    console.log('Día normal');
}
```

---

### 5. Bucles

```javascript
// For
for (let i = 0; i < 5; i++) {
  console.log(i);  // 0, 1, 2, 3, 4
}

// While
let contador = 0;
while (contador < 5) {
  console.log(contador);
  contador++;
}

// Do-while (ejecuta al menos una vez)
let num = 0;
do {
  console.log(num);
  num++;
} while (num < 5);

// For...of (arrays)
let colores = ['rojo', 'verde', 'azul'];
for (let color of colores) {
  console.log(color);
}

// For...in (objetos)
let persona = { nombre: 'Ana', edad: 25 };
for (let clave in persona) {
  console.log(`${clave}: ${persona[clave]}`);
}

// forEach
colores.forEach(function(color, index) {
  console.log(`${index}: ${color}`);
});
```

---

### 6. Funciones

```javascript
// Declaración de función
function saludar(nombre) {
  return `Hola ${nombre}`;
}

let mensaje = saludar('Ana');  // "Hola Ana"

// Función con múltiples parámetros
function sumar(a, b) {
  return a + b;
}

let resultado = sumar(5, 3);  // 8

// Parámetros por defecto
function saludar(nombre = 'Usuario') {
  return `Hola ${nombre}`;
}

saludar();        // "Hola Usuario"
saludar('Juan');  // "Hola Juan"

// Función anónima
let multiplicar = function(a, b) {
  return a * b;
};

// Arrow function (ES6)
let dividir = (a, b) => {
  return a / b;
};

// Arrow function (forma corta)
let cuadrado = x => x * x;
let suma = (a, b) => a + b;
```

---

### 7. DOM (Document Object Model)

El DOM es una representación del documento HTML que JavaScript puede manipular.

#### Seleccionar Elementos

```javascript
// Por ID
let elemento = document.getElementById('header');

// Por clase (devuelve el primero)
let elemento = document.querySelector('.clase');

// Por clase (devuelve todos)
let elementos = document.querySelectorAll('.clase');

// Por etiqueta
let parrafos = document.getElementsByTagName('p');

// Selector CSS complejo
let enlace = document.querySelector('nav a[href="#contacto"]');
```

#### Manipular Contenido

```javascript
// Obtener/cambiar texto
let titulo = document.getElementById('titulo');
console.log(titulo.textContent);  // Leer
titulo.textContent = 'Nuevo título';  // Cambiar

// Obtener/cambiar HTML
let contenedor = document.getElementById('contenedor');
console.log(contenedor.innerHTML);  // Leer
contenedor.innerHTML = '<p>Nuevo contenido</p>';  // Cambiar
```

#### Manipular Atributos

```javascript
let enlace = document.querySelector('a');

// Obtener atributo
let href = enlace.getAttribute('href');

// Cambiar atributo
enlace.setAttribute('href', 'https://nuevo.com');

// Propiedades directas
enlace.href = 'https://nuevo.com';
enlace.target = '_blank';

let imagen = document.querySelector('img');
imagen.src = 'nueva-imagen.jpg';
imagen.alt = 'Descripción';
```

#### Manipular Estilos

```javascript
let caja = document.getElementById('caja');

// Cambiar un estilo
caja.style.backgroundColor = 'blue';
caja.style.color = 'white';
caja.style.fontSize = '20px';

// Múltiples estilos
Object.assign(caja.style, {
  backgroundColor: 'blue',
  color: 'white',
  padding: '20px'
});
```

#### Manipular Clases

```javascript
let elemento = document.querySelector('.caja');

// Añadir clase
elemento.classList.add('activo');

// Quitar clase
elemento.classList.remove('activo');

// Toggle (alternar)
elemento.classList.toggle('activo');

// Verificar si tiene clase
if (elemento.classList.contains('activo')) {
  console.log('Está activo');
}
```

#### Crear y Eliminar Elementos

```javascript
// Crear elemento
let nuevoParrafo = document.createElement('p');
nuevoParrafo.textContent = 'Nuevo párrafo';
nuevoParrafo.classList.add('texto');

// Añadir al DOM
let contenedor = document.getElementById('contenedor');
contenedor.appendChild(nuevoParrafo);

// Insertar en posición específica
contenedor.insertBefore(nuevoParrafo, contenedor.firstChild);

// Eliminar elemento
let elementoAEliminar = document.getElementById('viejo');
elementoAEliminar.remove();

// O desde el padre
let padre = document.getElementById('contenedor');
let hijo = document.getElementById('hijo');
padre.removeChild(hijo);
```

---

### 8. Eventos

Los eventos permiten responder a interacciones del usuario.

#### addEventListener

```javascript
let boton = document.getElementById('miBoton');

boton.addEventListener('click', function() {
  alert('¡Hiciste clic!');
});

// Arrow function
boton.addEventListener('click', () => {
  alert('¡Hiciste clic!');
});

// Función externa
function manejarClick() {
  alert('¡Hiciste clic!');
}
boton.addEventListener('click', manejarClick);
```

#### Eventos Comunes

```javascript
// Click
elemento.addEventListener('click', function() {});

// Doble click
elemento.addEventListener('dblclick', function() {});

// Mouse encima
elemento.addEventListener('mouseover', function() {});

// Mouse sale
elemento.addEventListener('mouseout', function() {});

// Mouse se mueve
elemento.addEventListener('mousemove', function(e) {
  console.log(`X: ${e.clientX}, Y: ${e.clientY}`);
});

// Tecla presionada
document.addEventListener('keydown', function(e) {
  console.log(`Tecla: ${e.key}`);
});

// Tecla liberada
document.addEventListener('keyup', function(e) {});

// Formulario enviado
formulario.addEventListener('submit', function(e) {
  e.preventDefault();  // Evita envío
});

// Input cambia
input.addEventListener('input', function(e) {
  console.log(e.target.value);
});

// Scroll
window.addEventListener('scroll', function() {
  console.log(window.scrollY);
});

// Página cargada
window.addEventListener('load', function() {
  console.log('Página cargada');
});

// DOM cargado (sin imágenes)
document.addEventListener('DOMContentLoaded', function() {
  console.log('DOM listo');
});
```

#### Objeto Event

```javascript
elemento.addEventListener('click', function(event) {
  // Elemento que disparó el evento
  console.log(event.target);
  
  // Tipo de evento
  console.log(event.type);
  
  // Coordenadas del mouse
  console.log(event.clientX, event.clientY);
  
  // Tecla presionada
  console.log(event.key);
  
  // Evitar comportamiento por defecto
  event.preventDefault();
  
  // Detener propagación
  event.stopPropagation();
});
```

---

### 9. Proyecto SERVITIC - JavaScript

#### Navegación Suave

```javascript
// Seleccionar todos los enlaces internos
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  // Añadir listener a cada uno
  anchor.addEventListener('click', function (e) {
    // Prevenir comportamiento por defecto (salto brusco)
    e.preventDefault();
    
    // Obtener el destino (elemento con el id)
    const target = document.querySelector(this.getAttribute('href'));
    
    // Verificar que existe
    if (target) {
      // Scroll suave hacia el elemento
      target.scrollIntoView({
        behavior: 'smooth',
        block: 'start'
      });
    }
  });
});
```

**Explicación paso a paso:**

1. `document.querySelectorAll('a[href^="#"]')`: Selecciona todos los enlaces (`<a>`) cuyo `href` empiece por `#`
2. `.forEach(anchor => {})`: Itera cada enlace encontrado
3. `anchor.addEventListener('click', ...)`: Añade un listener de click a cada enlace
4. `e.preventDefault()`: Evita el salto brusco por defecto
5. `this.getAttribute('href')`: Obtiene el valor del href (ej: "#servicios")
6. `document.querySelector(...)`: Busca el elemento con ese id
7. `target.scrollIntoView({...})`: Hace scroll suave hacia el elemento

---

#### Manejo de Formulario

```javascript
// Seleccionar el formulario
document.querySelector('.contact-form').addEventListener('submit', function(e) {
  // Prevenir el envío real del formulario
  e.preventDefault();
  
  // En un caso real, aquí validarías y enviarías los datos
  // Por ahora, solo mostramos un mensaje
  alert('Gracias por tu mensaje. Nos pondremos en contacto contigo pronto.');
  
  // Limpiar el formulario
  this.reset();
});
```

**Mejora: Validación personalizada**

```javascript
document.querySelector('.contact-form').addEventListener('submit', function(e) {
  e.preventDefault();
  
  // Obtener valores
  let nombre = document.getElementById('nombre').value;
  let email = document.getElementById('email').value;
  let mensaje = document.getElementById('mensaje').value;
  
  // Validar
  if (nombre.trim() === '') {
    alert('Por favor, ingresa tu nombre');
    return;
  }
  
  if (email.trim() === '') {
    alert('Por favor, ingresa tu email');
    return;
  }
  
  if (mensaje.trim().length < 10) {
    alert('El mensaje debe tener al menos 10 caracteres');
    return;
  }
  
  // Si todo está bien
  console.log('Datos válidos:', { nombre, email, mensaje });
  alert('¡Mensaje enviado!');
  this.reset();
});
```

---

## 📱 DISEÑO RESPONSIVE

### Principios del Diseño Responsive

1. **Fluid Grid**: Usar porcentajes en vez de píxeles fijos
2. **Flexible Images**: Imágenes que se adaptan al contenedor
3. **Media Queries**: CSS condicional según el dispositivo

### Estrategias

#### 1. Mobile First

Diseñar primero para móviles, luego añadir complejidad para pantallas grandes.

```css
/* Estilos base (móviles) */
.container {
  width: 100%;
  padding: 1rem;
}

/* Tablet (768px+) */
@media (min-width: 768px) {
  .container {
    width: 90%;
    padding: 2rem;
  }
}

/* Desktop (1024px+) */
@media (min-width: 1024px) {
  .container {
    width: 1200px;
    margin: 0 auto;
  }
}
```

**Ventajas:**
- Mejor rendimiento en móviles (carga menos CSS)
- Fuerza a priorizar contenido esencial
- Progresivo enhancement

---

#### 2. Desktop First

Diseñar primero para desktop, luego simplificar para móviles.

```css
/* Estilos base (desktop) */
.container {
  width: 1200px;
  margin: 0 auto;
}

/* Tablet (1024px-) */
@media (max-width: 1024px) {
  .container {
    width: 90%;
  }
}

/* Móvil (768px-) */
@media (max-width: 768px) {
  .container {
    width: 100%;
    padding: 1rem;
  }
}
```

---

### Técnicas Responsive

#### Imágenes Flexibles

```css
img {
  max-width: 100%;
  height: auto;
}
```

#### Tipografía Responsive

```css
/* Usando vw (viewport width) */
h1 {
  font-size: calc(1.5rem + 2vw);
}

/* Con clamp() */
h1 {
  font-size: clamp(1.5rem, 4vw, 3rem);
  /* min: 1.5rem, preferido: 4vw, max: 3rem */
}
```

#### Grid Responsive

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}
```

**Se adapta automáticamente:**
- Desktop: 4 columnas
- Tablet: 2-3 columnas
- Móvil: 1 columna

---

### Puntos de Interrupción (Breakpoints)

```css
/* Extra small (móviles pequeños) */
@media (max-width: 576px) { }

/* Small (móviles) */
@media (min-width: 576px) { }

/* Medium (tablets) */
@media (min-width: 768px) { }

/* Large (laptops) */
@media (min-width: 1024px) { }

/* Extra large (desktops) */
@media (min-width: 1200px) { }

/* Extra extra large (desktops grandes) */
@media (min-width: 1440px) { }
```

---

## ✅ BUENAS PRÁCTICAS

### HTML

1. **Usar HTML5 semántico**
   - `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
   - No: `<div id="header">`, `<div class="nav">`

2. **Un solo `<h1>` por página**
   - Jerarquía lógica: h1 → h2 → h3

3. **Atributo `alt` en imágenes**
   ```html
   <img src="logo.png" alt="Logo de SERVITIC">
   ```

4. **Labels en formularios**
   ```html
   <label for="email">Email:</label>
   <input type="email" id="email">
   ```

5. **Cerrar todas las etiquetas**
   - Excepto auto-cerradas: `<img>`, `<br>`, `<input>`

6. **Indentar correctamente**
   ```html
   <div>
     <p>Texto</p>
   </div>
   ```

---

### CSS

1. **Usar clases, no IDs**
   - IDs para JavaScript y anclas
   - Clases para estilos

2. **Metodología BEM (opcional)**
   ```css
   .card { }
   .card__title { }
   .card__title--highlighted { }
   ```

3. **Unidades relativas (rem, em, %)**
   - No píxeles fijos para tamaños de fuente

4. **Mobile First o Desktop First (consistente)**

5. **Evitar `!important`**
   - Solo en casos extremos

6. **Comentar secciones**
   ```css
   /* ========== Header ========== */
   ```

7. **Agrupar propiedades relacionadas**
   ```css
   .elemento {
     /* Posicionamiento */
     position: relative;
     top: 0;
     
     /* Caja */
     width: 100px;
     padding: 1rem;
     
     /* Tipografía */
     font-size: 1rem;
     color: black;
     
     /* Visual */
     background: white;
     border: 1px solid gray;
   }
   ```

---

### JavaScript

1. **Usar `const` por defecto, `let` si cambia**
   - No `var`

2. **Nombres descriptivos**
   ```javascript
   // Mal
   let x = 5;
   function a() {}
   
   // Bien
   let precioTotal = 5;
   function calcularDescuento() {}
   ```

3. **Comentar código complejo**
   ```javascript
   // Calcula el precio final con descuento del 20%
   let precioFinal = precioBase * 0.8;
   ```

4. **Evitar variables globales**
   - Usar funciones y scope local

5. **Usar `===` en vez de `==`**
   ```javascript
   // Mal
   if (edad == '18') { }
   
   // Bien
   if (edad === 18) { }
   ```

6. **DRY (Don't Repeat Yourself)**
   - No duplicar código
   - Crear funciones reutilizables

---

### Accesibilidad

1. **Contraste de colores**
   - Mínimo 4.5:1 para texto normal
   - Herramienta: https://webaim.org/resources/contrastchecker/

2. **Textos alternativos**
   - Alt en imágenes
   - Labels en formularios

3. **Navegación por teclado**
   - No eliminar `:focus` sin reemplazarlo

4. **Estructura lógica**
   - HTML semántico
   - Jerarquía de encabezados

5. **ARIA (cuando sea necesario)**
   ```html
   <button aria-label="Cerrar menú">×</button>
   ```

---

### Rendimiento

1. **Minimizar archivos**
   - CSS y JS minificados para producción

2. **Optimizar imágenes**
   - Formato WebP
   - Lazy loading: `<img loading="lazy">`

3. **CSS externo, no inline**

4. **JavaScript al final del `<body>`**
   - O usar `defer`/`async`

5. **Evitar librerías innecesarias**
   - Vanilla JS cuando sea posible

---

## 💪 EJERCICIOS PRÁCTICOS

### Nivel Básico

1. **Cambiar colores**
   - Modifica la paleta de colores del sitio
   - Usa una herramienta como Coolors.co

2. **Añadir un nuevo servicio**
   - Copia una tarjeta de servicio
   - Cambia el título y descripción

3. **Modificar espaciados**
   - Experimenta con padding y margin
   - Observa cómo afecta al diseño

4. **Añadir efectos hover**
   - Crea efectos diferentes en las tarjetas
   - Prueba `scale()`, `rotate()`, cambios de color

5. **Crear una nueva sección**
   - Añade "Testimonios" o "Clientes"
   - Usa las mismas técnicas del proyecto

---

### Nivel Intermedio

6. **Menú hamburguesa**
   ```javascript
   const menuBtn = document.getElementById('menu-btn');
   const nav = document.querySelector('nav');
   
   menuBtn.addEventListener('click', () => {
     nav.classList.toggle('active');
   });
   ```

7. **Validación de formulario**
   - Validar que el email sea válido
   - Verificar que el mensaje tenga mínimo 10 caracteres
   - Mostrar mensajes de error personalizados

8. **Botón "Volver arriba"**
   ```javascript
   const btnArriba = document.getElementById('btn-arriba');
   
   window.addEventListener('scroll', () => {
     if (window.scrollY > 300) {
       btnArriba.style.display = 'block';
     } else {
       btnArriba.style.display = 'none';
     }
   });
   
   btnArriba.addEventListener('click', () => {
     window.scrollTo({ top: 0, behavior: 'smooth' });
   });
   ```

9. **Carrusel de imágenes**
   - Crear un slider automático
   - Botones anterior/siguiente
   - Indicadores de posición

10. **Modal/Lightbox**
    - Al hacer clic en imagen, abre en grande
    - Cerrar con X o clic fuera

---

### Nivel Avanzado

11. **Animaciones al scroll**
    ```javascript
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    });
    
    document.querySelectorAll('.service-card').forEach(card => {
      observer.observe(card);
    });
    ```

12. **Modo oscuro**
    ```javascript
    const toggleDark = document.getElementById('toggle-dark');
    
    toggleDark.addEventListener('click', () => {
      document.body.classList.toggle('dark-mode');
      localStorage.setItem('darkMode', 
        document.body.classList.contains('dark-mode')
      );
    });
    
    // Cargar preferencia
    if (localStorage.getItem('darkMode') === 'true') {
      document.body.classList.add('dark-mode');
    }
    ```

13. **Filtro de servicios**
    - Botones para filtrar por categoría
    - Mostrar/ocultar servicios dinámicamente

14. **Enviar formulario a servidor**
    ```javascript
    form.addEventListener('submit', async (e) => {
      e.preventDefault();
      
      const datos = {
        nombre: document.getElementById('nombre').value,
        email: document.getElementById('email').value,
        mensaje: document.getElementById('mensaje').value
      };
      
      try {
        const respuesta = await fetch('/api/contacto', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify(datos)
        });
        
        if (respuesta.ok) {
          alert('¡Mensaje enviado!');
        }
      } catch (error) {
        console.error('Error:', error);
      }
    });
    ```

15. **Lazy loading de imágenes**
    ```html
    <img 
      src="placeholder.jpg" 
      data-src="imagen-real.jpg" 
      class="lazy"
      alt="Descripción"
    >
    ```
    
    ```javascript
    const lazyImages = document.querySelectorAll('.lazy');
    
    const imageObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          const img = entry.target;
          img.src = img.dataset.src;
          img.classList.remove('lazy');
          imageObserver.unobserve(img);
        }
      });
    });
    
    lazyImages.forEach(img => imageObserver.observe(img));
    ```

---

## 📚 RECURSOS ADICIONALES

### Documentación Oficial

1. **MDN Web Docs** (Más completa)
   - https://developer.mozilla.org/es/
   - Documentación de HTML, CSS y JavaScript

2. **W3Schools** (Más simple)
   - https://www.w3schools.com/
   - Tutoriales con ejemplos interactivos

3. **CSS-Tricks**
   - https://css-tricks.com/
   - Artículos y guías de CSS

4. **Can I Use**
   - https://caniuse.com/
   - Compatibilidad de características en navegadores

---

### Herramientas de Diseño

1. **Generador de Gradientes**
   - https://cssgradient.io/

2. **Generador de Sombras**
   - https://box-shadow.dev/

3. **Paletas de Colores**
   - https://coolors.co/
   - https://color.adobe.com/

4. **Fuentes Web**
   - https://fonts.google.com/

5. **Iconos**
   - https://fontawesome.com/
   - https://heroicons.com/

---

### Aprendizaje Interactivo

1. **Flexbox Froggy**
   - https://flexboxfroggy.com/
   - Juego para aprender Flexbox

2. **Grid Garden**
   - https://cssgridgarden.com/
   - Juego para aprender CSS Grid

3. **CSS Battle**
   - https://cssbattle.dev/
   - Retos de CSS

4. **FreeCodeCamp**
   - https://www.freecodecamp.org/
   - Cursos completos gratuitos

---

### Validadores

1. **Validador HTML**
   - https://validator.w3.org/

2. **Validador CSS**
   - https://jigsaw.w3.org/css-validator/

3. **Lighthouse (Chrome DevTools)**
   - Auditoría de rendimiento, accesibilidad, SEO

4. **WAVE**
   - https://wave.webaim.org/
   - Evaluador de accesibilidad

---

### Frameworks (para después de dominar lo básico)

1. **CSS**
   - Tailwind CSS
   - Bootstrap
   - Bulma

2. **JavaScript**
   - React
   - Vue.js
   - Svelte

---

## 📖 GLOSARIO DE TÉRMINOS

### A

**Accessibility (Accesibilidad)**: Diseño que permite el uso a personas con discapacidades.

**API (Application Programming Interface)**: Interfaz que permite comunicación entre sistemas.

**Attribute (Atributo)**: Información adicional en etiquetas HTML. Ej: `href`, `src`, `class`.

---

### B

**Breakpoint**: Punto donde el diseño cambia (media query).

**Browser (Navegador)**: Software para acceder a páginas web (Chrome, Firefox, Safari).

**Box Model**: Modelo de caja CSS (margin, border, padding, content).

---

### C

**Class (Clase)**: Atributo reutilizable para estilos CSS.

**CSS (Cascading Style Sheets)**: Lenguaje para dar estilo a HTML.

**Content (Contenido)**: Texto, imágenes y elementos dentro de una página.

---

### D

**Declaration (Declaración)**: Propiedad y valor en CSS. Ej: `color: red;`

**DOM (Document Object Model)**: Representación de HTML que JavaScript puede manipular.

**DRY (Don't Repeat Yourself)**: Principio de no duplicar código.

---

### E

**Element (Elemento)**: Componente HTML. Ej: `<p>`, `<div>`, `<header>`

**Event (Evento)**: Acción del usuario que JavaScript puede detectar. Ej: click, scroll.

---

### F

**Flexbox**: Sistema de layout CSS unidimensional.

**Framework**: Estructura de código pre-construida (Bootstrap, React).

**Function (Función)**: Bloque de código reutilizable en JavaScript.

---

### G

**Grid**: Sistema de layout CSS bidimensional.

---

### H

**HTML (HyperText Markup Language)**: Lenguaje de marcado para estructura web.

**Hover**: Estado cuando el cursor está sobre un elemento.

---

### I

**ID**: Identificador único para un elemento HTML.

**Inline**: Elemento que no ocupa línea completa. Ej: `<span>`, `<a>`

---

### J

**JavaScript**: Lenguaje de programación para interactividad web.

---

### L

**Layout**: Disposición de elementos en la página.

**Library (Librería)**: Conjunto de funciones reutilizables. Ej: jQuery.

---

### M

**Media Query**: CSS condicional según características del dispositivo.

**Method (Método)**: Función asociada a un objeto.

---

### P

**Padding**: Espacio interior de un elemento (entre contenido y borde).

**Property (Propiedad)**: Característica CSS que se puede estilizar. Ej: `color`, `width`

**Pseudo-class**: Estado especial de un elemento. Ej: `:hover`, `:focus`

---

### R

**Responsive**: Diseño que se adapta a diferentes tamaños de pantalla.

**Root**: Elemento raíz (`<html>`).

---

### S

**Selector**: Patrón que identifica elementos HTML para aplicar estilos.

**Semantic HTML**: HTML que describe el significado del contenido.

**Specificity**: Peso de un selector CSS (determina qué estilo prevalece).

---

### T

**Tag (Etiqueta)**: Elemento HTML. Ej: `<p>`, `<div>`

**Transition**: Animación suave entre estados CSS.

---

### V

**Variable**: Contenedor de datos en JavaScript.

**Viewport**: Área visible de la página web.

---

### W

**Wrapper**: Contenedor que envuelve otros elementos.

---

---

## 🎓 CONCLUSIÓN

Esta documentación cubre los fundamentos del desarrollo web moderno utilizados en el proyecto SERVITIC. 

**Próximos pasos:**

1. Practica modificando el código existente
2. Completa los ejercicios propuestos
3. Crea tus propios proyectos desde cero
4. Explora frameworks cuando domines lo básico
5. Nunca dejes de aprender

**Recuerda:**
- La práctica constante es clave
- No tengas miedo de experimentar
- Los errores son oportunidades de aprendizaje
- La comunidad de desarrolladores está para ayudar

---

**¿Preguntas?**

Consulta:
- MDN Web Docs
- Stack Overflow
- Comunidades de Discord/Slack de desarrollo web

**¡Buena suerte en tu viaje como desarrollador web!** 🚀
