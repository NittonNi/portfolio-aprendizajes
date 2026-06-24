# Portfolio de Aprendizajes — Nicolás Martínez Riego

Sitio web estático (HTML + CSS + un poco de JavaScript) que presenta el portfolio
de aprendizajes de **Nicolás Martínez Riego**, estudiante de LEINN
(Liderazgo, Emprendimiento e Innovación) en Mondragon Unibertsitatea.

Es una página de scroll vertical con estética editorial: tipografía display
gigante (Anton) sobre fondos crema y negro, con azul marino como acento.

## Estructura

```
portfolio-aprendizajes/
├── index.html      # Toda la página (una sola página, con anclas)
├── styles.css      # Estilos (variables CSS, responsive mobile-first)
├── script.js       # Menú móvil + animaciones fade-in al hacer scroll
├── .nojekyll       # Evita que GitHub Pages procese el sitio con Jekyll
├── README.md       # Este archivo
└── assets/         # Imágenes y logos (ahora con placeholders, ver abajo)
    └── logos/
```

## Verlo en local

No necesita servidor ni instalación: **haz doble clic en `index.html`** y se
abrirá en tu navegador. Todas las rutas son relativas.

> Si prefieres un servidor local (recomendado para que el `lazy-load` de
> imágenes funcione idéntico a producción), desde esta carpeta:
>
> ```bash
> python -m http.server 8000
> ```
> y abre <http://localhost:8000>.

## Sustituir las imágenes (placeholders)

La carpeta `assets/` incluye **placeholders** con los nombres exactos que usa
la web. Mientras una imagen no exista o no sea válida, el sitio muestra
automáticamente un recuadro elegante con el nombre del archivo (no rompe el
diseño). Para personalizar, **sustituye cada archivo por la imagen real
manteniendo el mismo nombre**:

| Archivo | Uso |
|---|---|
| `assets/hero.jpg` | Foto de portada |
| `assets/goxxo.png` | Producto Goxxo |
| `assets/lockfest-1.png` … `lockfest-3.png` | Renders de Lockfest |
| `assets/feelkey-molde-macho.png` | Feelkey: molde macho |
| `assets/feelkey-molde-hembra.png` | Feelkey: molde hembra |
| `assets/feelkey-prototipo.png` | Feelkey: prototipo |
| `assets/pickle-logo.png` | Logo The Pickle Center (negro) |
| `assets/logos/parke.png` | Logo Parke |
| `assets/logos/fvte.png` | Federación Vasca de Tenis |
| `assets/logos/rfet.png` | Real Federación Española de Tenis |
| `assets/logos/zcebra.png` | Zcebra Wild Pickleball |
| `assets/logos/mondragon.png` | Mondragon Unibertsitatea |
| `assets/logos/dupr.png` | DUPR |
| `assets/logos/vitoria-gasteiz.png` | Ayuntamiento de Vitoria-Gasteiz |
| `assets/logos/pickleball-fed.png` | Federación de pickleball |

## Publicar en GitHub Pages (paso a paso)

1. **Crea un repositorio** en GitHub (por ejemplo `portfolio-aprendizajes`).
   Puede ser público.

2. **Sube los archivos.** Desde esta carpeta, en una terminal:

   ```bash
   git init
   git add .
   git commit -m "Portfolio de aprendizajes"
   git branch -M main
   git remote add origin https://github.com/TU-USUARIO/portfolio-aprendizajes.git
   git push -u origin main
   ```

   (Sustituye `TU-USUARIO` por tu usuario de GitHub.)

3. **Activa GitHub Pages:** en el repositorio, ve a
   **Settings → Pages**.
   - En **Source**, elige **Deploy from a branch**.
   - En **Branch**, selecciona **`main`** y carpeta **`/ (root)`**.
   - Pulsa **Save**.

4. Espera 1–2 minutos. GitHub mostrará la URL pública, del estilo:
   `https://TU-USUARIO.github.io/portfolio-aprendizajes/`

> El archivo `.nojekyll` ya está incluido para que GitHub Pages sirva el sitio
> tal cual, sin procesarlo con Jekyll.

## Personalización rápida

- **Colores y tipografías:** variables CSS al inicio de `styles.css` (`:root`).
- **Textos:** directamente en `index.html`.
- **Secciones:** cada bloque es una `<section>` con su `id`; el menú superior
  enlaza a esos `id`.

## Tecnología

100% estático, sin frameworks ni build tools. HTML semántico y accesible,
responsive mobile-first, fuentes de Google Fonts con `preconnect`, imágenes con
`loading="lazy"` y animaciones con `IntersectionObserver`.
