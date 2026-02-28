# Creaciones LuFran — Kit de Herramientas Digital

Todo lo que necesitás para gestionar y hacer crecer tu emprendimiento de kits beauty artesanales.

---

## Archivos incluidos

| Archivo | Qué es | Para qué sirve |
|---------|--------|-----------------|
| `landing-creaciones-lufran.html` | Landing page (sitio web) | Tu página de presentación con productos, precios y botón de WhatsApp |
| `Calendario_Contenido_CreacionesLuFran.xlsx` | Calendario de contenido | Plan de publicaciones para 4 semanas en Instagram, TikTok y Facebook |
| `Guia_Completa_CreacionesLuFran.docx` | Guía de gestión | Bio para redes, respuestas de WhatsApp, scripts para Reels, FAQ, sorteos y revendedoras |
| `Calculadora_y_Pedidos_CreacionesLuFran.xlsx` | Control del negocio | Calculadora de costos/ganancias, control de pedidos, stock y resumen mensual |
| `plantillas-stories-lufran.html` | Plantillas de stories | 6 diseños listos para usar en Instagram Stories |
| `logo_lufran.png` / `.svg` | Logo principal | Para foto de perfil en redes sociales y materiales |
| `marca_agua_lufran.png` / `.svg` | Marca de agua | Para superponer en fotos de productos |

---

## Guía de la Landing Page

### Estructura del HTML

El archivo `landing-creaciones-lufran.html` es una página autocontenida (todo el CSS y JS están dentro del mismo archivo). Está organizada en secciones que podés identificar fácilmente con los comentarios en el código:

```
<!-- NAV -->        → Barra de navegación superior
<!-- HERO -->       → Pantalla principal con frase y botón
<!-- PRODUCTS -->   → Tarjetas de productos con precios
<!-- BENEFITS -->   → Sección "¿Por qué elegirnos?"
<!-- ABOUT -->      → Historia de Creaciones LuFran
<!-- PROCESS -->    → Pasos para comprar
<!-- CTA -->        → Llamado a la acción final con botón de WhatsApp
<!-- FOOTER -->     → Pie de página con redes sociales
```

### Cómo abrir y editar en VS Code

1. Abrí VS Code
2. `File → Open File` → seleccioná `landing-creaciones-lufran.html`
3. Instalá la extensión **Live Server** (de Ritwick Dey) si no la tenés: te permite ver los cambios en vivo en el navegador
4. Click derecho en el archivo → `Open with Live Server`
5. Cada vez que guardes (`Ctrl+S`), el navegador se actualiza solo

### Cambios frecuentes que vas a querer hacer

#### Cambiar el número de WhatsApp

Buscá todas las apariciones de `5492614174684` y reemplazalas por tu número nuevo. El formato es: `549` + código de área sin 0 + número sin 15.

```
Ctrl+H  →  Buscar: 5492614174684  →  Reemplazar: tu nuevo número  →  Reemplazar todo
```

#### Cambiar precios

Buscá el texto del precio que querés cambiar, por ejemplo:

```html
<!-- Precio del Kit Beauty -->
<span class="product-price">$7.000 <small>Unidad</small></span>
```

Cambiá `$7.000` por el nuevo precio.

#### Cambiar "Consultá" por un precio fijo

Buscá la tarjeta del producto (ej: Kit de Dormir) y reemplazá:

```html
<!-- ANTES -->
<span class="product-price">Consultá <small>Por WhatsApp</small></span>

<!-- DESPUÉS -->
<span class="product-price">$12.000 <small>Unidad</small></span>
```

#### Agregar un producto nuevo

Copiá una tarjeta completa `<div class="product-card">...</div>` y pegala debajo de la última. Después cambiá el nombre, descripción, precio, color de fondo y el link de WhatsApp.

El color de fondo de la tarjeta se cambia en esta línea:

```html
<div class="product-img-bg" style="background: linear-gradient(135deg, #fde8ef 0%, #f5d5e0 100%);"></div>
```

Algunos colores sugeridos para nuevos productos:

```
Rosa:    #fde8ef → #f5d5e0
Lila:    #e8dff0 → #d5c8e6
Verde:   #e3ede8 → #d0e0d7
Fucsia:  #fce4ec → #f8bbd0
Dorado:  #fff3e0 → #ffe0b2
Celeste: #e3f2fd → #bbdefb
```

#### Agregar fotos reales de productos

Reemplazá el emoji por una imagen. Buscá:

```html
<span class="product-emoji">✨</span>
```

Y reemplazalo por:

```html
<img src="tu-foto.jpg" alt="Kit Beauty" style="width: 100%; height: 100%; object-fit: cover; position: relative; z-index: 1;">
```

Importante: la foto tiene que estar en la misma carpeta que el archivo HTML o usar una URL externa.

#### Cambiar textos

Todos los textos están en español plano dentro del HTML. Buscá con `Ctrl+F` la frase que querés cambiar y editala directamente. Por ejemplo, para cambiar la frase principal del hero:

```html
<h1>Cuidado personal con <em>amor artesanal</em></h1>
```

#### Cambiar colores de la marca

Los colores están definidos al inicio del CSS dentro de `:root`. Si querés cambiar la paleta completa, modificá estas variables:

```css
:root {
    --rose: #c4a082;        /* Color principal (dorado rosado) */
    --rose-light: #e8d5c4;  /* Versión clara */
    --rose-pale: #faf6f2;   /* Fondo muy claro */
    --rose-deep: #8b6f5a;   /* Versión oscura */
    --charcoal: #2d2926;    /* Texto oscuro */
    --warm-gray: #6b6462;   /* Texto secundario */
    --cream: #fffcf9;       /* Fondo general */
    --sage: #a8b5a0;        /* Acento verde */
    --sage-light: #e8ede5;  /* Verde claro */
}
```

#### Agregar el link de Instagram cuando tengas la cuenta

Buscá `href="#"` junto a `Instagram` y reemplazá `#` por tu URL:

```html
<!-- ANTES -->
<a href="#" title="Instagram">📷</a>

<!-- DESPUÉS -->
<a href="https://instagram.com/creaciones.lufran" target="_blank" title="Instagram">📷</a>
```

Hacé lo mismo con TikTok y Facebook.

#### Cambiar el texto del mensaje de WhatsApp

Los botones envían un mensaje automático. El texto está codificado en la URL después de `?text=`. Para cambiarlo, reemplazá el texto después de `?text=` usando [este codificador](https://www.urlencoder.org/):

```html
<!-- Ejemplo: cambiar el mensaje del botón principal -->
<a href="https://wa.me/5492614174684?text=Tu%20mensaje%20nuevo%20aquí" ...>
```

---

## Despliegue en GitHub Pages

### Tu página está publicada en:
```
https://crisgomez79.github.io/creaciones-lufran/
```

### Cómo se subió (pasos ya realizados)

1. Se creó un repositorio en GitHub llamado `creaciones-lufran` en la cuenta `crisgomez79`
2. Se subieron todos los archivos con Git desde la terminal:
   ```bash
   git init
   git add .
   git commit -m "Landing page Creaciones LuFran"
   git branch -M main
   git remote add origin https://github.com/crisgomez79/creaciones-lufran.git
   git push -u origin main
   ```
3. Se activó GitHub Pages en `Settings` → `Pages` → Source: `Deploy from a branch` → Branch: `main` / `(root)`

### Cómo actualizar la página cuando hagas cambios

Si modificás el archivo `index.html` (cambiar precios, textos, imágenes, etc.), ejecutá estos 3 comandos en la terminal desde la carpeta del proyecto:

```bash
git add .
git commit -m "Descripción de lo que cambiaste"
git push
```

**Ejemplo práctico:** cambiaste el precio del Kit Beauty:

```bash
git add .
git commit -m "Actualizo precio Kit Beauty"
git push
```

Esperá 1-2 minutos y los cambios se van a ver en la página.

### Si agregás imágenes nuevas

1. Poné la imagen nueva en la carpeta `img/`
2. Referenciala en el HTML: `<img src="img/nombre_imagen.png">`
3. Subí los cambios:
   ```bash
   git add .
   git commit -m "Agrego imagen nueva"
   git push
   ```

### Dominio personalizado (opcional)

Si querés que la URL sea `creacioneslufran.com` en lugar de `crisgomez79.github.io/creaciones-lufran`:
1. Comprá el dominio (ej: en Nic.ar cuesta ~$2.500/año para `.com.ar`)
2. En GitHub: `Settings` → `Pages` → `Custom domain` → escribí tu dominio
3. En tu proveedor de dominio: agregá un registro CNAME apuntando a `crisgomez79.github.io`

---

## Resumen rápido: hice cambios, y ahora qué?

```bash
git add .
git commit -m "Lo que cambiaste"
git push
```

Esperá 1-2 minutos. Listo.

---

## Tips para editar con VS Code

### Extensiones recomendadas

| Extensión | Para qué sirve |
|-----------|-----------------|
| **Live Server** | Ver cambios en vivo en el navegador |
| **Prettier** | Formatear el código automáticamente |
| **Auto Rename Tag** | Al cambiar una etiqueta HTML, cambia la de cierre sola |
| **Color Highlight** | Muestra el color real al lado de los códigos hex (#c4a082) |
| **HTML CSS Support** | Autocompletado de clases CSS |

### Atajos útiles

```
Ctrl+F          → Buscar texto
Ctrl+H          → Buscar y reemplazar
Ctrl+S          → Guardar (y actualizar Live Server)
Ctrl+Z          → Deshacer cambio
Ctrl+Shift+Z    → Rehacer cambio
Alt+Shift+F     → Formatear código
Ctrl+/          → Comentar/descomentar línea
```

### Cómo buscar una sección rápido

Cada sección tiene un comentario HTML que la identifica:

```
Ctrl+F → escribí "PRODUCTS" → te lleva directo a la sección de productos
Ctrl+F → escribí "CTA" → te lleva al botón final de WhatsApp
```

---

## Paleta de colores de la marca

| Color | Hex | Uso |
|-------|-----|-----|
| Crema | `#faf6f2` | Fondo principal |
| Rosa cálido | `#c4a082` | Color principal de marca |
| Rosa claro | `#e8d5c4` | Fondos sutiles, bordes |
| Marrón | `#8b6f5a` | Acentos, textos secundarios |
| Carbón | `#2d2926` | Texto principal, botones |
| Gris cálido | `#6b6462` | Texto secundario |
| Sage | `#a8b5a0` | Acento verde, variedad |
| Blanco cálido | `#fffcf9` | Fondo alternativo |

---

## Estructura de carpetas sugerida

Si vas a usar Git y VS Code, organizá tus archivos así:

```
lufran-web/
├── index.html              ← Tu landing page (renombrada)
├── README.md               ← Este archivo
├── assets/
│   ├── logo_lufran.png
│   ├── logo_lufran.svg
│   ├── marca_agua_lufran.png
│   └── fotos/
│       ├── kit-beauty.jpg
│       ├── kit-dormir.jpg
│       └── set-spa.jpg
└── docs/
    ├── Calendario_Contenido.xlsx
    ├── Guia_Completa.docx
    ├── Calculadora_y_Pedidos.xlsx
    └── plantillas-stories.html
```

---

## Soporte

Si necesitás ayuda con algo, volvé a este chat y preguntame. Puedo ayudarte a modificar la página, agregar secciones nuevas, crear más contenido o resolver cualquier problema técnico.

**Creaciones LuFran** — Hecho con cariño en Mendoza 🧵
