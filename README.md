# Documentación completa de styles.css

Este documento explica en detalle cada sección y línea del archivo `styles.css` de tu proyecto.

---

## 📋 Índice
1. [Variables CSS (Root)](#variables-css-root)
2. [Estilos Generales](#estilos-generales)
3. [Header y Navegación](#header-y-navegación)
4. [Botones](#botones)
5. [Secciones Generales](#secciones-generales)
6. [Sección Hero](#sección-hero)
7. [Sección Featured](#sección-featured)
8. [Sección Productos](#sección-productos)
9. [Sección Consolas (Carousel)](#sección-consolas-carousel)
10. [Sección Galería](#sección-galería)
11. [Sección Ubicación](#sección-ubicación)
12. [Sección Contacto](#sección-contacto)
13. [Footer](#footer)
14. [Media Queries (Responsivos)](#media-queries)

---

## 🎨 Variables CSS (Root)

```css
:root {
    --bg: #07071a;              /* Color de fondo principal - azul muy oscuro */
    --bg2: #0d0d2b;             /* Color de fondo secundario - azul oscuro medio */
    --bg3: #111133;             /* Color de fondo terciario - azul oscuro claro */
    --accent: #00d4ff;          /* Color de acento principal - cian/azul claro */
    --accent2: #e94560;         /* Color de acento secundario - rosa/rojo */
    --accent3: #f7931e;         /* Color de acento terciario - naranja */
    --text: #f0f0f0;            /* Color de texto principal - blanco grisáceo */
    --text-muted: #8888aa;      /* Color de texto apagado - gris azulado */
    --border: rgba(0, 212, 255, 0.15);  /* Color de bordes - cian con transparencia */
    --card: #0d0d2b;            /* Color de tarjetas - igual a bg2 */
    --header-h: 64px;           /* Alto del header */
    --font-pixel: 'Press Start 2P', monospace;  /* Fuente pixel art para títulos */
    --font-body: 'Rajdhani', sans-serif;        /* Fuente para texto del cuerpo */
}
```

**Explicación:** Estas variables definen los colores, fuentes y dimensiones principales del sitio web. Al usar variables CSS, podemos cambiar toda la paleta de colores simplemente modificando estos valores.

---

## 🔧 Estilos Generales

```css
*, *::before, *::after {
    margin: 0; 
    padding: 0; 
    box-sizing: border-box;
}
```
**Explicación:** El selector universal `*` afecta a TODOS los elementos. Esto:
- Elimina márgenes predeterminados de navegadores
- Elimina rellenos predeterminados
- `box-sizing: border-box` hace que los bordes y rellenos se incluyan en el ancho/alto total

```css
html { 
    scroll-behavior: smooth;    /* Desplazamiento suave al ir a anclas */
    font-size: 16px;            /* Tamaño base para cálculos rem */
}
```

```css
body {
    font-family: var(--font-body);  /* Usa la fuente Rajdhani */
    background-color: var(--bg);    /* Fondo azul oscuro */
    color: var(--text);             /* Texto blanco grisáceo */
    line-height: 1.6;               /* Espacio entre líneas - 60% más que el tamaño del texto */
    overflow-x: hidden;             /* Evita barras de desplazamiento horizontal */
}
```

```css
img { 
    max-width: 100%;        /* Las imágenes no se pueden hacer más grandes que su contenedor */
    height: auto;           /* Mantiene la proporción de la imagen */
    display: block;         /* Evita espacios en blanco debajo de imágenes */
}

a { text-decoration: none; }    /* Elimina subrayado de enlaces */
ul { list-style: none; }        /* Elimina viñetas de listas */
```

---

## 🔝 Header y Navegación

```css
header {
    position: sticky;               /* Se queda pegado al desplazar */
    top: 0;                         /* Pegado a la parte superior */
    z-index: 1000;                  /* Aparece encima de otros elementos */
    background: rgba(7, 7, 26, 0.92);  /* Fondo semi-transparente */
    backdrop-filter: blur(12px);    /* Efecto de desenfoque/cristal esmerilado */
    border-bottom: 1px solid var(--border);  /* Línea cian debajo */
    transition: box-shadow 0.3s;    /* Animación suave de sombra */
    height: var(--header-h);        /* Altura de 64px */
}

header.scrolled {
    box-shadow: 0 4px 24px rgba(0, 212, 255, 0.12);  /* Sombra cian cuando se desplaza */
}
```

```css
.header-inner {
    display: flex;              /* Usa flexbox para alineación */
    align-items: center;        /* Centra verticalmente */
    justify-content: space-between;  /* Espacio máximo entre elementos */
    max-width: 1400px;          /* Ancho máximo del contenido */
    margin: 0 auto;             /* Centra horizontalmente */
    padding: 0 24px;            /* 24px de relleno a los lados */
    height: 100%;               /* Ocupa toda la altura del header */
    gap: 16px;                  /* 16px entre elementos (flexbox) */
}
```

### Logo

```css
.logo {
    font-family: var(--font-pixel);     /* Fuente pixel art */
    font-size: clamp(12px, 2vw, 20px);  /* Tamaño responsivo: mín 12px, máx 20px, ideal 2% del ancho */
    white-space: nowrap;                /* El logo no se divide en líneas */
    flex-shrink: 0;                     /* No se encoge en flexbox */
}

.logo-pixel { color: var(--accent); }   /* "Pixel" en cian */
.logo-vault { color: var(--text); }     /* "Vault" en blanco */
```

### Menú de Navegación

```css
.menu-principal { flex: 1; }            /* Ocupa el espacio disponible */

.menu {
    display: flex;              /* Alineación horizontal */
    gap: 0;                     /* Sin espacio entre botones */
    align-items: center;        /* Centra verticalmente */
    justify-content: flex-end;  /* Alinea a la derecha */
}

.menu-btn {
    color: var(--text-muted);       /* Texto grisáceo */
    font-family: var(--font-body);  /* Fuente Rajdhani */
    font-size: 13px;                /* Pequeño */
    font-weight: 600;               /* Semi-negrita */
    padding: 8px 14px;              /* Relleno */
    text-transform: uppercase;      /* TODO EN MAYÚSCULAS */
    letter-spacing: 0.8px;          /* Espacio extra entre letras */
    transition: color 0.25s;        /* Cambio de color animado en 0.25s */
    display: block;
    white-space: nowrap;            /* No se divide en líneas */
}

.menu-btn:hover { color: var(--accent); }  /* Se pone cian al pasar el ratón */
```

### Hamburger (Menú móvil)

```css
.hamburger {
    display: none;              /* Oculto por defecto (para desktop) */
    flex-direction: column;     /* Los tres líneas van en columna */
    gap: 5px;                   /* Espacio entre líneas */
    background: none;           /* Sin fondo */
    border: none;               /* Sin borde */
    cursor: pointer;            /* Cursor de clic */
    padding: 8px;               /* Relleno */
    flex-shrink: 0;             /* No se encoge */
}

.hamburger span {
    width: 24px; height: 2px;   /* Línea del hamburger */
    background: var(--text);    /* Color blanco */
    border-radius: 2px;         /* Esquinas redondeadas */
    display: block;
    transition: background 0.2s;  /* Cambio de color animado */
}

.hamburger:hover span { background: var(--accent); }  /* Se pone cian al pasar */
```

```css
.menu-close {
    display: none;                  /* Oculto por defecto */
    background: none;
    border: none;
    color: var(--text-muted);
    font-size: 20px;                /* X grande */
    cursor: pointer;
    padding: 8px 12px;
    align-self: flex-end;           /* Alinea a la derecha en flexbox */
    margin-bottom: 8px;
}

.menu-close:hover { color: var(--accent2); }  /* Se pone rosa al pasar */
```

```css
.menu-overlay {
    display: none;              /* Oculto por defecto */
    position: fixed;            /* Fijo en la pantalla */
    inset: 0;                   /* Ocupa toda la pantalla (top,right,bottom,left = 0) */
    background: rgba(0,0,0,0.6);  /* Fondo negro semi-transparente */
    z-index: 998;               /* Detrás del menú (999) pero encima del contenido */
}

.menu-overlay.open { display: block; }  /* Se muestra cuando está abierto */
```

---

## 🔘 Botones

```css
.boton-principal {
    background: var(--accent);          /* Fondo cian */
    color: var(--bg);                   /* Texto azul oscuro */
    padding: 12px 28px;                 /* Relleno vertical y horizontal */
    border-radius: 4px;                 /* Esquinas ligeramente redondeadas */
    font-family: var(--font-body);      /* Fuente Rajdhani */
    font-size: 14px;
    font-weight: 700;                   /* Bold */
    text-transform: uppercase;          /* TODO EN MAYÚSCULAS */
    letter-spacing: 1px;                /* Espacio entre letras */
    border: 2px solid var(--accent);    /* Borde cian */
    transition: all 0.25s;              /* Todas las propiedades se animan */
    display: inline-flex;               /* Flexbox inline para centrar contenido */
    align-items: center;
    justify-content: center;
    cursor: pointer;                    /* Cursor de clic */
}

.boton-principal:hover {
    background: transparent;            /* Fondo transparente */
    color: var(--accent);               /* Texto cian */
}
```

```css
.boton-secundario {
    background: transparent;            /* Fondo transparente */
    color: var(--text);                 /* Texto blanco */
    padding: 12px 28px;
    border-radius: 4px;
    font-family: var(--font-body);
    font-size: 14px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    border: 2px solid rgba(255,255,255,0.3);  /* Borde blanco semi-transparente */
    transition: all 0.25s;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.boton-secundario:hover {
    border-color: var(--accent);    /* Borde cian */
    color: var(--accent);           /* Texto cian */
}
```

---

## 📄 Secciones Generales

```css
.seccion {
    padding: 80px 24px;             /* 80px arriba/abajo, 24px izquierda/derecha */
    max-width: 1400px;              /* Ancho máximo */
    margin: 0 auto;                 /* Centra horizontalmente */
    width: 100%;                    /* Usa todo el ancho disponible */
}

.seccion-header {
    text-align: center;             /* Texto centrado */
    margin-bottom: 48px;            /* Espacio debajo */
}

.seccion-tag {
    font-family: var(--font-body);
    font-size: 13px;
    font-weight: 700;
    color: var(--accent);           /* Texto cian */
    text-transform: uppercase;
    letter-spacing: 3px;            /* Muy espaciado */
    margin-bottom: 12px;
}

.seccion h2 {
    font-family: var(--font-pixel);     /* Fuente pixel art */
    font-size: clamp(18px, 3vw, 32px);  /* Tamaño responsivo */
    color: var(--text);
    line-height: 1.4;                   /* Espacio entre líneas */
    margin-bottom: 12px;
}

.subtitulo-seccion {
    color: var(--text-muted);       /* Texto grisáceo */
    font-size: 16px;
    margin-top: 8px;
}
```

---

## 🎬 Sección Hero

La sección hero es la primera sección visible del sitio (debajo del header).

```css
.seccion-hero {
    padding: 0;                         /* Sin relleno (ocupa todo el espacio) */
    max-width: 100%;
    margin: 0;
    background: linear-gradient(135deg, var(--bg) 0%, var(--bg3) 100%);
        /* Gradiente diagonal: azul oscuro a azul más claro */
    border-bottom: 1px solid var(--border);
    min-height: calc(100vh - var(--header-h));  /* Alto de toda la pantalla menos header */
    display: flex;
    align-items: center;                /* Centra verticalmente */
}

.hero-slide {
    display: flex;
    align-items: center;
    gap: 40px;                          /* Espacio entre contenido e imagen */
    max-width: 1400px;
    margin: 0 auto;
    padding: 60px 40px;
    width: 100%;
}

.hero-content {
    flex: 1;                            /* Ocupa espacio igual que la imagen */
    min-width: 0;                       /* Permite que se encoja */
}

.hero-tag {
    font-size: 13px;
    font-weight: 700;
    color: var(--accent);
    text-transform: uppercase;
    letter-spacing: 2px;
    margin-bottom: 20px;
}

.hero-content h2 {
    font-family: var(--font-pixel);
    font-size: clamp(18px, 3.5vw, 36px);
    line-height: 1.5;
    margin-bottom: 20px;
    color: var(--text);
}

.hero-content > p {
    font-size: clamp(15px, 2vw, 18px);
    color: var(--text-muted);
    margin-bottom: 36px;
    max-width: 480px;                  /* No es demasiado ancho */
    line-height: 1.7;
}

.hero-btns {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;                    /* Los botones se envuelven en móvil */
}

.hero-image {
    flex: 1;
    min-width: 0;
    border-radius: 12px;                /* Esquinas muy redondeadas */
    overflow: hidden;                   /* Corta la imagen a las esquinas */
    border: 1px solid var(--border);
    box-shadow: 0 0 40px rgba(0, 212, 255, 0.15);  /* Sombra cian */
}

.hero-image img {
    width: 100%;
    height: auto;
    object-fit: cover;                  /* Rellena sin distorsionar */
}
```

---

## 📌 Sección Featured (Sobre Nosotros)

```css
.seccion-featured {
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    background: var(--bg2);             /* Fondo azul oscuro medio */
    max-width: 100%;
    padding: 80px 24px;
}

.featured-container {
    display: flex;
    gap: 60px;                          /* Gran espacio entre elementos */
    align-items: center;
    max-width: 1400px;
    margin: 0 auto;
}

.featured-text { 
    flex: 1; 
    min-width: 0; 
}

.featured-text h2 {
    font-family: var(--font-pixel);
    font-size: clamp(16px, 2.5vw, 28px);
    margin-bottom: 20px;
    line-height: 1.5;
}

.featured-text > p {
    font-size: 17px;
    color: var(--text-muted);
    margin-bottom: 28px;
    line-height: 1.7;
}

.featured-features {
    display: grid;
    grid-template-columns: 1fr 1fr;     /* Dos columnas iguales */
    gap: 14px;
    margin-bottom: 36px;
}

.feature-item {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 15px;
    color: var(--text);
    font-weight: 600;
}

.feature-icon {
    color: var(--accent);
    font-weight: 700;
    font-size: 16px;
    flex-shrink: 0;                     /* No se encoge */
}

.featured-actions {
    display: flex;
    gap: 14px;
    flex-wrap: wrap;
}

.featured-image {
    flex: 1;
    min-width: 0;
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid var(--border);
    box-shadow: 0 0 30px rgba(0, 212, 255, 0.1);
}
```

---

## 🛍️ Sección Productos

```css
.seccion-productos {
    background: var(--bg);
    border-bottom: 1px solid var(--border);
    max-width: 100%;
    padding: 80px 24px;
}

.tarjetas-productos {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
        /* Crea columnas automáticamente: mínimo 260px, máximo flexible */
    gap: 24px;
    max-width: 1400px;
    margin: 0 auto;
}

.tarjeta {
    background: var(--card);
    border-radius: 10px;
    border: 1px solid var(--border);
    overflow: hidden;
    display: flex;
    flex-direction: column;             /* Contenido en columna */
    transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
        /* Anima transformación, color del borde y sombra */
}

.tarjeta:hover {
    transform: translateY(-6px);        /* Sube 6px al pasar */
    border-color: var(--accent);        /* Borde cian */
    box-shadow: 0 12px 32px rgba(0, 212, 255, 0.15);  /* Sombra cian */
}

.tarjeta img {
    width: 100%; 
    height: 180px;
    object-fit: cover;                  /* Rellena 180px de alto */
}

.tarjeta-body {
    padding: 18px;
    display: flex;
    flex-direction: column;
    flex: 1;                            /* Ocupa el espacio restante */
}

.tarjeta h3 {
    font-family: var(--font-body);
    font-size: 18px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 8px;
}

.tarjeta p {
    font-size: 14px;
    color: var(--text-muted);
    margin-bottom: 12px;
    flex: 1;                            /* Expande para llenar espacio */
    line-height: 1.5;
}

.tarjeta .precio {
    font-size: 22px;
    font-weight: 700;
    color: var(--accent);
    margin-bottom: 14px;
    flex: none;                         /* No se expande */
}

.boton-tarjeta {
    display: block;
    text-align: center;
    background: var(--accent);
    color: var(--bg);
    padding: 10px;
    border-radius: 4px;
    font-weight: 700;
    font-size: 13px;
    text-transform: uppercase;
    letter-spacing: 1px;
    border: 2px solid var(--accent);
    transition: all 0.25s;
    cursor: pointer;
}

.boton-tarjeta:hover {
    background: transparent;
    color: var(--accent);
}
```

---

## 🎮 Sección Consolas (Carousel)

Esta sección muestra las consolas en un carrusel horizontal desplazable.

```css
.seccion-consolas {
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
    max-width: 100%;
    padding: 80px 24px;
}

.consolas-carousel {
    display: flex;
    overflow-x: auto;                   /* Scroll horizontal */
    gap: 20px;
    padding-bottom: 16px;
    scroll-behavior: smooth;            /* Desplazamiento suave */
    -webkit-overflow-scrolling: touch;  /* Desplazamiento fluido en móviles */
    max-width: 1400px;
    margin: 0 auto;
}

/* Personalizar la barra de scroll */
.consolas-carousel::-webkit-scrollbar { 
    height: 6px;                        /* Altura de la barra */
}

.consolas-carousel::-webkit-scrollbar-track { 
    background: var(--bg3);             /* Fondo de la barra */
    border-radius: 3px;
}

.consolas-carousel::-webkit-scrollbar-thumb { 
    background: var(--accent);          /* Deslizador cian */
    border-radius: 3px;
}

.consola-card {
    background: var(--card);
    border-radius: 10px;
    border: 1px solid var(--border);
    width: 260px;
    min-width: 260px;                   /* No se encoge */
    padding: 16px;
    text-align: center;
    transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
    flex-shrink: 0;                     /* No se encoge en flexbox */
}

.consola-card:hover {
    transform: translateY(-6px);        /* Sube al pasar */
    border-color: var(--accent);
    box-shadow: 0 12px 32px rgba(0, 212, 255, 0.15);
}

.consola-card img {
    width: 100%; 
    height: 180px;
    object-fit: cover;
    border-radius: 6px;
    margin-bottom: 14px;
}

.consola-card h3 {
    font-size: 17px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 6px;
}

.consola-card .especificaciones {
    color: var(--accent);               /* Texto cian */
    font-size: 12px;
    font-weight: 600;
    margin-bottom: 8px;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.consola-card .descripcion {
    color: var(--text-muted);
    font-size: 13px;
    margin-bottom: 12px;
    line-height: 1.5;
}

.consola-card .precio {
    color: var(--accent3);              /* Naranja */
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 14px;
}

.boton-consola {
    display: inline-block;
    background: var(--accent);
    color: var(--bg);
    padding: 9px 22px;
    border-radius: 4px;
    font-size: 13px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    border: 2px solid var(--accent);
    transition: all 0.25s;
    cursor: pointer;
}

.boton-consola:hover {
    background: transparent;
    color: var(--accent);
}

.carousel-nav {
    display: flex;
    gap: 12px;                          /* Espacio entre botones */
    justify-content: center;
    margin-top: 24px;
    max-width: 1400px;
    margin-left: auto;
    margin-right: auto;
}

.carousel-btn {
    background: var(--card);
    border: 1px solid var(--border);
    color: var(--text);
    width: 44px; 
    height: 44px;
    border-radius: 50%;                 /* Círculo perfecto */
    font-size: 18px;
    cursor: pointer;
    transition: all 0.25s;
    display: flex; 
    align-items: center; 
    justify-content: center;
}

.carousel-btn:hover {
    background: var(--accent);          /* Fondo cian */
    color: var(--bg);                   /* Texto azul oscuro */
    border-color: var(--accent);
}
```

---

## 🖼️ Sección Galería

```css
.seccion-galeria {
    background: var(--bg);
    border-bottom: 1px solid var(--border);
    max-width: 100%;
    padding: 80px 24px;
}

.galeria-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
        /* Crea columnas automáticamente: mínimo 280px */
    gap: 20px;
    max-width: 1400px;
    margin: 0 auto;
}

.galeria-item {
    border-radius: 8px;
    overflow: hidden;
    border: 1px solid var(--border);
    transition: border-color 0.3s, box-shadow 0.3s;
    cursor: pointer;                    /* Indicador de clickeable */
}

.galeria-item:hover {
    border-color: var(--accent);        /* Borde cian */
    box-shadow: 0 4px 20px rgba(0, 212, 255, 0.15);
}

.galeria-item img {
    width: 100%;
    aspect-ratio: 16/10;                /* Proporción 16:10 */
    object-fit: cover;
    transition: transform 0.3s;
}

.galeria-item:hover img { 
    transform: scale(1.05);             /* Zoom ligero al pasar */
}

.galeria-item p {
    background: var(--card);
    padding: 12px 16px;
    font-size: 14px;
    font-weight: 600;
    color: var(--text);
    border-top: 1px solid var(--border);
}
```

---

## 📍 Sección Ubicación

```css
.seccion-ubicacion {
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
    max-width: 100%;
    padding: 80px 24px;
}

.ubicacion-contenido {
    display: grid;
    grid-template-columns: 1fr 1.5fr;   /* Columna 1 = 1/3, Columna 2 = 2/3 */
    gap: 32px;
    max-width: 1400px;
    margin: 0 auto;
    align-items: start;                 /* Alinea al inicio */
}

.ubicacion-info {
    background: var(--card);
    padding: 28px;
    border-radius: 10px;
    border: 1px solid var(--border);
}

.ubicacion-info h3 {
    font-size: 20px;
    font-weight: 700;
    color: var(--accent);               /* Cian */
    margin-bottom: 20px;
}

.lista-ubicacion li {
    padding: 12px 0;
    border-bottom: 1px solid var(--border);
    font-size: 14px;
    color: var(--text-muted);
    line-height: 1.5;
}

.lista-ubicacion li:last-child { 
    border-bottom: none;                /* Última línea sin borde */
}

.lista-ubicacion strong { 
    color: var(--text);                 /* Blanco */
    font-weight: 600;
}

.mapa {
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid var(--border);
    box-shadow: 0 4px 24px rgba(0,0,0,0.4);
}

.mapa iframe { 
    width: 100%; 
    height: 380px;                      /* Alto del mapa */
    display: block; 
}
```

---

## 📧 Sección Contacto

```css
.seccion-contacto {
    background: var(--bg);
    border-bottom: 1px solid var(--border);
    max-width: 100%;
    padding: 80px 24px;
}

.formulario-contenedor {
    display: grid;
    grid-template-columns: 2fr 1fr;     /* Formulario ocupa 2/3, redes 1/3 */
    gap: 40px;
    max-width: 1400px;
    margin: 0 auto;
    align-items: start;
}

.formulario {
    display: flex;
    flex-direction: column;             /* Campos en columna */
    gap: 18px;
}

.campo {
    display: flex;
    flex-direction: column;
    gap: 7px;
}

.campo label {
    font-size: 13px;
    font-weight: 700;
    color: var(--text);
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.campo input,
.campo textarea,
.campo select {
    background: var(--bg2);             /* Fondo azul oscuro */
    border: 1px solid var(--border);
    color: var(--text);
    padding: 12px 16px;
    border-radius: 6px;
    font-size: 15px;
    font-family: var(--font-body);
    transition: border-color 0.25s, box-shadow 0.25s;
    outline: none;
    -webkit-appearance: none;           /* Elimina estilos de navegador */
    appearance: none;
}

.campo input::placeholder,
.campo textarea::placeholder { 
    color: var(--text-muted);           /* Placeholder grisáceo */
}

.campo input:focus,
.campo textarea:focus,
.campo select:focus {
    border-color: var(--accent);        /* Borde cian */
    box-shadow: 0 0 0 3px rgba(0, 212, 255, 0.1);  /* Resplandor cian */
}

.campo select option { 
    background: var(--bg2); 
    color: var(--text); 
}

.campo textarea { 
    resize: vertical;                   /* Solo se puede redimensionar verticalmente */
    min-height: 120px;                  /* Altura mínima */
}

.boton-enviar {
    background: var(--accent);
    color: var(--bg);
    border: 2px solid var(--accent);
    padding: 13px 32px;
    font-size: 14px;
    font-weight: 700;
    font-family: var(--font-body);
    text-transform: uppercase;
    letter-spacing: 1px;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.25s;
    align-self: flex-start;             /* Se alinea a la izquierda */
}

.boton-enviar:hover {
    background: transparent;
    color: var(--accent);
}

.redes-sociales {
    background: var(--card);
    padding: 28px;
    border-radius: 10px;
    border: 1px solid var(--border);
}

.redes-sociales h3 {
    font-size: 16px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 18px;
    line-height: 1.4;
}

.iconos-redes {
    display: flex;
    flex-direction: column;             /* Iconos en columna */
    gap: 10px;
}

.red-social {
    background: var(--bg2);
    color: var(--text-muted);
    padding: 12px 18px;
    border-radius: 6px;
    border: 1px solid var(--border);
    transition: all 0.25s;
    font-size: 14px;
    font-weight: 600;
    text-align: center;
    display: block;
}

.red-social:hover {
    border-color: var(--accent);        /* Borde cian */
    color: var(--accent);               /* Texto cian */
    transform: translateX(4px);         /* Se mueve 4px a la derecha */
}
```

---

## 👣 Footer

```css
footer {
    background: var(--bg2);
    border-top: 1px solid var(--border);
    padding: 48px 24px 0;               /* Sin padding inferior */
}

.footer-contenido {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
        /* Columnas automáticas: mínimo 220px */
    gap: 32px;
    max-width: 1400px;
    margin: 0 auto;
    padding-bottom: 32px;
}

.footer-logo span {
    font-family: var(--font-pixel);
    font-size: 16px;
    color: var(--accent);               /* Cian */
    display: block;
    margin-bottom: 8px;
}

.footer-logo p { 
    color: var(--text-muted); 
    font-size: 13px; 
}

.footer-links h4,
.footer-contacto h4 {
    color: var(--text);
    margin-bottom: 14px;
    font-size: 13px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.footer-links ul li { 
    margin-bottom: 10px; 
}

.footer-links ul li a { 
    color: var(--text-muted);
    font-size: 14px; 
    transition: color 0.2s;
}

.footer-links ul li a:hover { 
    color: var(--accent);               /* Se pone cian */
}

.footer-contacto p { 
    color: var(--text-muted); 
    font-size: 14px; 
    margin-bottom: 6px; 
}

.footer-bottom {
    text-align: center;
    padding: 18px 24px;
    border-top: 1px solid var(--border);
}

.footer-bottom p { 
    color: var(--text-muted); 
    font-size: 13px; 
}
```

---

## 📱 Media Queries (Responsivos)

### Tablet (máximo 900px)

```css
@media (max-width: 900px) {

    /* Mostrar hamburger, ocultar nav de escritorio */
    .hamburger { display: flex; }
    .menu-close { display: block; }

    /* Menú mobile */
    .menu-principal {
        position: fixed;                /* Fijo en la pantalla */
        top: 0;
        right: -280px;                  /* Oculto a la derecha inicialmente */
        width: 280px;
        height: 100vh;                  /* Altura total */
        background: var(--bg2);
        border-left: 1px solid var(--border);
        z-index: 999;
        display: flex;
        flex-direction: column;
        padding: 16px;
        transition: right 0.3s ease;    /* Animación suave */
        overflow-y: auto;               /* Scroll si es necesario */
    }

    .menu-principal.open { right: 0; }  /* Se muestra */

    .menu {
        flex-direction: column;         /* Items en columna */
        gap: 4px;
        align-items: stretch;           /* Ocupa ancho completo */
    }

    .menu-btn {
        font-size: 14px;
        padding: 14px 16px;
        border-radius: 6px;
        display: block;
        transition: background 0.2s, color 0.2s;
    }

    .menu-btn:hover {
        background: rgba(0, 212, 255, 0.08);  /* Fondo cian muy débil */
        color: var(--accent);
    }

    /* Hero responsivo */
    .hero-slide {
        flex-direction: column;         /* Contenido y imagen en columna */
        padding: 48px 24px 40px;
        min-height: auto;
        gap: 32px;
    }

    .hero-content { order: 1; }
    .hero-image { order: 2; width: 100%; }

    /* Títulos del hero más pequeños */
    .hero-content h2 { font-size: clamp(16px, 4vw, 26px); }
    .hero-content > p { max-width: 100%; }

    /* Featured responsivo */
    .featured-container {
        flex-direction: column;         /* Una columna */
        gap: 32px;
    }

    .featured-features { grid-template-columns: 1fr; }  /* Una columna */

    /* Ubicación responsiva */
    .ubicacion-contenido { grid-template-columns: 1fr; }  /* Una columna */

    /* Contacto responsivo */
    .formulario-contenedor { grid-template-columns: 1fr; }  /* Una columna */

    /* Consolas más pequeñas */
    .consola-card { width: 240px; min-width: 240px; }

    /* Secciones con padding reducido */
    .seccion { padding: 60px 20px; }
    .seccion-hero, .seccion-featured, .seccion-productos,
    .seccion-consolas, .seccion-galeria, .seccion-ubicacion,
    .seccion-contacto { padding: 60px 20px; }
}
```

### Móvil (máximo 600px)

```css
@media (max-width: 600px) {

    :root { --header-h: 56px; }         /* Header más bajo */

    .header-inner { padding: 0 16px; }  /* Padding horizontal reducido */

    .logo { font-size: 11px; }          /* Logo más pequeño */

    /* Hero móvil */
    .hero-slide { 
        padding: 36px 16px 32px; 
        gap: 24px; 
    }
    
    .hero-content h2 { font-size: clamp(14px, 5vw, 22px); }
    .hero-content > p { font-size: 15px; }
    
    .hero-btns { 
        flex-direction: column;         /* Botones ocupan ancho completo */
        gap: 12px; 
    }
    
    .hero-btns .boton-principal,
    .hero-btns .boton-secundario { 
        width: 100%; 
        text-align: center; 
    }

    /* Secciones con padding muy reducido */
    .seccion, .seccion-hero, .seccion-featured, .seccion-productos,
    .seccion-consolas, .seccion-galeria, .seccion-ubicacion,
    .seccion-contacto { padding: 48px 16px; }

    .seccion h2 { font-size: clamp(14px, 5vw, 22px); }

    /* Featured mobile */
    .featured-actions { 
        flex-direction: column;         /* Botones apilados */
    }
    
    .featured-actions .boton-principal,
    .featured-actions .boton-secundario { 
        width: 100%; 
        text-align: center; 
    }

    /* Productos: 1 columna */
    .tarjetas-productos { grid-template-columns: 1fr; }

    /* Consolas más pequeñas */
    .consola-card { width: 220px; min-width: 220px; }

    /* Galería: 1 columna */
    .galeria-grid { grid-template-columns: 1fr; }

    /* Formulario con tamaño más grande para móviles */
    .campo input, .campo textarea, .campo select { 
        font-size: 16px;                /* Previene zoom en móvil */
    }
    
    .boton-enviar { 
        width: 100%; 
        text-align: center; 
        align-self: stretch; 
    }

    /* Mapa más pequeño */
    .mapa iframe { height: 260px; }

    /* Footer centrado */
    .footer-contenido { 
        text-align: center; 
        gap: 24px; 
    }
    
    .footer-logo span { font-size: 13px; }

    /* Iconos redes sociales apilados */
    .iconos-redes { flex-direction: column; }

    /* Botones del carrusel más pequeños */
    .carousel-nav { gap: 16px; }
    .carousel-btn { 
        width: 40px; 
        height: 40px; 
        font-size: 16px; 
    }
}
```

### Pantallas muy pequeñas (máximo 380px)

```css
@media (max-width: 380px) {
    .logo { font-size: 10px; }          /* Logo muy pequeño */
    .hero-content h2 { font-size: 13px; }  /* Título hero muy pequeño */
    .consola-card { width: 200px; min-width: 200px; }  /* Consolas más pequeñas */
}
```

---

## 🎯 Resumen de características clave

1. **Diseño responsivo**: Funciona perfectamente desde móviles hasta escritorio
2. **Tema oscuro**: Paleta de colores oscura con acentos cian, rosa y naranja
3. **Efectos hover**: Transiciones suaves en botones, tarjetas y enlaces
4. **Flexbox y Grid**: Uso moderno de CSS para layouts flexibles
5. **Carrusel**: Scroll horizontal para consolas
6. **Formulario accesible**: Campos con estados focus adecuados
7. **Variables CSS**: Fácil personalización de colores y dimensiones

---

## 📝 Notas importantes

- Los `clamp()` permiten que los tamaños de fuente se adapten automáticamente según el tamaño de la pantalla
- La barra de desplazamiento de las consolas se personaliza con `::-webkit-scrollbar`
- El menú móvil se desliza desde la derecha
- Todos los colores usan variables CSS para mantener consistencia

¡Espero que esta documentación te ayude a entender completamente tu CSS! 🚀
