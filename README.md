# **README.md — Carrusel Fullscreen con Bootstrap 5**

## Vista general del proyecto

Este proyecto implementa un carrusel a pantalla completa (_fullscreen carousel_) utilizando **Bootstrap 5**.
Las imágenes se expanden al alto completo del navegador (**100vh**) y utilizan `object-fit: cover` para mantener proporciones sin deformarse.

El resultado es una experiencia visual fluida, elegante y perfecta para:

- Landing pages
- Portadas de sitios web
- Banners rotativos
- Presentaciones tipo slideshow
- Proyectos educativos y demostraciones

### **Captura principal (Pantalla completa)**

> Reemplaza `captura1.jpg` con tu screenshot real.

```
docs/captura1.jpg
```

---

# **Contenido**

1. [Características principales](#características-principales)
2. [Capturas del carrusel](#capturas-del-carrusel)
3. [Estructura del proyecto](#estructura-del-proyecto)
4. [Código base](#código-base-del-carrusel)
5. [Cómo personalizarlo](#cómo-personalizarlo)
6. [Requisitos](#requisitos)
7. [Problemas comunes y soluciones](#problemas-comunes-y-soluciones)
8. [Licencia](#licencia)

---

# **Características principales**

## **1. Imágenes a pantalla completa (100vh)**

Cada imagen ocupa todo el alto visible del navegador, independientemente del dispositivo o resolución:

```css
.carousel-item img {
  width: 100%;
  height: 100vh;
  object-fit: cover;
}
```

Esto crea una sensación real de portada tipo _hero banner_.

---

## **2. Transiciones suaves tipo Fade**

Bootstrap permite aplicar un efecto visual más elegante:

```html
<div class="carousel slide carousel-fade" ...></div>
```

Este efecto evita cortes bruscos entre imágenes.

---

## **3. Textos con fondo semitransparente**

Para maximizar la legibilidad, el texto del carrusel incluye una capa suave oscura:

```css
.carousel-caption {
  background: rgba(0, 0, 0, 0.4);
  padding: 15px;
  border-radius: 10px;
}
```

Ideal para presentaciones, títulos o mensajes de bienvenida.

---

## **4. Soporte para cualquier cantidad de imágenes**

El ejemplo incluye **5 imágenes**, pero es completamente escalable.

### Captura mostrando transición

```
docs/captura2.jpg
```

---

# **Capturas del carrusel**

### **Imagen 1 (Pantalla completa)**

```
docs/captura1.jpg
```

### **Imagen 2 (Transición fade)**

```
docs/captura2.jpg
```

### **Imagen 3 (Caption centrado)**

```
docs/captura3.jpg
```

### **Estructura en dispositivos móviles**

```
docs/captura4.jpg
```

### **Indicadores y controles Bootstrap**

```
docs/captura5.jpg
```

---

# **Estructura del proyecto**

````
/
├── index.html
├── README.md
├── assets/
├── css/
│   └── bootstrap.min.css
├── js/
│   └── bootstrap.bundle.min.js
└── img/
   ├── 1.jpg
   ├── 2.jpg
   ├── 3.jpg
   ├── 4.jpg
   └── 5.jpg

---

# **Código base del carrusel**

A continuación se incluye la estructura completa del carrusel, lista para integrarse en cualquier proyecto:

```html
<div id="galeria" class="carousel slide carousel-fade" data-bs-ride="carousel">
  <div class="carousel-indicators">
    <button
      type="button"
      data-bs-target="#galeria"
      data-bs-slide-to="0"
      class="active"
    ></button>
    <button
      type="button"
      data-bs-target="#galeria"
      data-bs-slide-to="1"
    ></button>
    <button
      type="button"
      data-bs-target="#galeria"
      data-bs-slide-to="2"
    ></button>
    <button
      type="button"
      data-bs-target="#galeria"
      data-bs-slide-to="3"
    ></button>
    <button
      type="button"
      data-bs-target="#galeria"
      data-bs-slide-to="4"
    ></button>
  </div>

  <div class="carousel-inner">
    <!-- Repetir bloques según cantidad de imágenes -->
    <div class="carousel-item active">
      <img src="assets/img/1.jpg" alt="Imagen 1" />
      <div class="carousel-caption">
        <h3>Primera imagen</h3>
        <p>Texto explicativo sobre el carrusel</p>
      </div>
    </div>
    <!-- ...más imágenes -->
  </div>

  <!-- Controles -->
  <button
    class="carousel-control-prev"
    type="button"
    data-bs-target="#galeria"
    data-bs-slide="prev"
  >
    <span class="carousel-control-prev-icon"></span>
  </button>

  <button
    class="carousel-control-next"
    type="button"
    data-bs-target="#galeria"
    data-bs-slide="next"
  >
    <span class="carousel-control-next-icon"></span>
  </button>
</div>
````

---

# **Cómo personalizarlo**

## **Cambiar duración entre imágenes**

Agregar dentro del `div` principal:

```html
data-bs-interval="5000"
```

(5000 ms = 5 segundos)

---

## **Desactivar auto-play**

```html
data-bs-ride="false"
```

---

## **Cambiar textos**

Solo edita dentro de `.carousel-caption`.

---

## **Cambiar cantidad de imágenes**

1. Agregar o duplicar `.carousel-item`
2. Ajustar indicadores:

```html
data-bs-slide-to="0" data-bs-slide-to="1" ...
```

---

# **Requisitos**

- Bootstrap 5
- Navegador moderno compatible con HTML5
- Carpeta `/assets/` con CSS, JS e imágenes
- Opcional: carpeta `/docs/` con capturas para documentación

---

# **Problemas comunes y soluciones**

### **1. “El carrusel pega un salto”**

Causa:
Diapositivas fuera de `.carousel-inner` o `</div>` mal cerrado.

Solución:
Verificar estructura jerárquica.

---

### **2. Las imágenes se ven deformadas**

Causa: imagen muy vertical.

Solución:
Mantener formato horizontal (1920x1080 recomendado).

---

### **3. No funcionan los botones prev/next**

Causa más común: Bootstrap JS no cargado.

Verificar ruta:

```
assets/js/bootstrap.bundle.min.js
```

---

# **Licencia**

Proyecto educativo y demostrativo sin restricciones de uso.
Puedes modificarlo, reutilizarlo y distribuirlo libremente.
