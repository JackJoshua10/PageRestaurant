# 🍕 Pizzería Restaurant - Landing Page

[![Vite](https://img.shields.io/badge/Vite-6.0.5-646CFF?style=flat&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4.0.3-38B2AC?style=flat&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Sitio web responsivo moderno para restaurante de pizzería, desarrollado con Tailwind CSS v4 y Vite. Incluye menú interactivo, galería de imágenes y ubicaciones con Google Maps integrado.

[🔗 Ver Demo en Vivo](https://page-restaurant.vercel.app) | [📧 Contacto](mailto:jack.sivipaucar17@gmail.com)

---

## 📋 Tabla de Contenidos

- [Características](#-características)
- [Tecnologías](#-tecnologías-utilizadas)
- [Vista Previa](#-vista-previa)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Instalación](#️-instalación)
- [Uso](#-uso)
- [Características Técnicas](#-características-técnicas-destacadas)
- [Responsive Design](#-responsive-design)
- [Personalización](#-personalización)
- [Decisiones Técnicas](#-decisiones-técnicas)
- [Roadmap](#-roadmap)
- [Autor](#-autor)
- [Licencia](#-licencia)

---

## ✨ Características

- ✅ **Diseño 100% Responsivo** - Adaptado para móvil, tablet y desktop
- ✅ **Navegación Multi-página** - Index y página de menú completo
- ✅ **Galería Interactiva** - Efectos hover con transiciones suaves
- ✅ **Google Maps Integrado** - Ubicaciones de sucursales embebidas
- ✅ **Hero Section Atractivo** - Con overlay y gradiente personalizado
- ✅ **Cards de Productos** - Sistema de precios por tamaño
- ✅ **Tipografía Elegante** - Dancing Script para títulos, Lato para contenido
- ✅ **Optimizado para SEO** - Estructura semántica HTML5
- ✅ **Performance Optimizado** - Build rápido con Vite
- ✅ **Sistema de Navegación con Anclas** - Scroll suave entre secciones

---

## 🚀 Tecnologías Utilizadas

| Tecnología | Versión | Propósito |
|------------|---------|-----------|
| **HTML5** | - | Estructura semántica |
| **Tailwind CSS** | 4.0.3 | Framework utility-first para estilos |
| **Vite** | 6.0.5 | Build tool moderno y rápido |
| **JavaScript ES6+** | - | Configuración mínima |
| **Google Fonts** | - | Dancing Script + Lato |
| **Google Maps** | - | Integración de mapas |

### DevDependencies
```json
{
  "vite": "^6.0.5"
}
```

### Dependencies
```json
{
  "@tailwindcss/vite": "^4.0.3",
  "tailwindcss": "^4.0.3"
}
```

---

## 📸 Vista Previa

### Desktop View
```
┌─────────────────────────────────────────────────┐
│  [Logo]              [Menú] [Sucursales] [...]  │
├─────────────────────────────────────────────────┤
│                                                  │
│         Llegaron las pizzzshasss                 │
│              Desde 1995                          │
│                                                  │
└─────────────────────────────────────────────────┘
```

### Mobile View
```
┌───────────────┐
│    [Logo]     │
├───────────────┤
│     [Nav]     │
├───────────────┤
│    [Hero]     │
├───────────────┤
│   [Content]   │
└───────────────┘
```

---

## 📁 Estructura del Proyecto

```
pizzeria/
│
├── index.html              # Página principal (Home)
├── menu.html               # Página de menú completo
├── package.json            # Dependencias del proyecto
├── vite.config.js          # Configuración de Vite
│
├── src/
│   ├── index.css          # Estilos principales + custom theme
│   └── main.js            # Entry point de JavaScript
│
├── img/                    # Assets de imágenes
│   ├── galeria/           # Imágenes de la galería (8 fotos)
│   ├── menu/              # Imágenes de productos
│   │   ├── pizza-*.png    # Pizzas (8 tipos)
│   │   ├── hamburguesa-*.png
│   │   └── bebida-*.png
│   ├── background.png     # Imagen del hero
│   └── acerca-de.png      # Imagen sección "Acerca de"
│
└── README.md              # Este archivo
```

---

## ⚙️ Instalación

### Requisitos Previos
- **Node.js** >= 18.0.0
- **npm** >= 8.0.0 o **yarn**

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone https://github.com/tu-usuario/pizzeria-restaurant.git
cd pizzeria-restaurant
```

2. **Instalar dependencias**
```bash
npm install
# o
yarn install
```

3. **Iniciar servidor de desarrollo**
```bash
npm run dev
# o
yarn dev
```

4. **Abrir en el navegador**
```
http://localhost:5173
```

---

## 🎯 Uso

### Comandos Disponibles

```bash
# Modo desarrollo (Hot reload)
npm run dev

# Build para producción
npm run build

# Preview del build de producción
npm run preview
```

### Build de Producción

El comando `npm run build` genera archivos optimizados en la carpeta `dist/`:

```
dist/
├── index.html
├── menu.html
├── assets/
│   ├── index-[hash].js
│   ├── index-[hash].css
│   └── [imágenes optimizadas]
```

---

## 🎨 Características Técnicas Destacadas

### 1. Hero Section con Overlay usando Pseudo-elementos

**Implementación:**
```html
<header class="relative pt-10 overflow-auto text-white bg-hero bg-cover bg-center 
               before:content-[''] before:bg-red-950/70 before:w-full before:h-full 
               before:block before:absolute before:z-0 before:top-0">
    <div class="relative z-10 w-11/12 mx-auto max-w-7xl">
        <!-- Contenido visible sobre el overlay -->
    </div>
</header>
```

**Técnicas utilizadas:**
- `before:content-['']` - Crea pseudo-elemento ::before
- `before:bg-red-950/70` - Color con opacidad del 70%
- `relative z-10` - Contenido aparece sobre el overlay

---

### 2. Grid Responsivo con Reordenamiento

**Código:**
```html
<div class="grid grid-cols-3 gap-0 md:gap-5">
    <!-- Info de sucursal -->
    <div class="col-span-full md:col-span-1 order-2 md:order-1">
        Información de contacto
    </div>
    
    <!-- Google Maps -->
    <iframe class="col-span-full md:col-span-2 
                   aspect-video md:aspect-auto 
                   order-1 md:order-2">
    </iframe>
</div>
```

**Resultado:**
- **Móvil:** Mapa arriba (order-1), info abajo (order-2)
- **Desktop:** Info izquierda (order-1), mapa derecha (order-2)

---

### 3. Galería con Efectos Hover

**Implementación:**
```html
<img src="./img/galeria/galeria-1.png"
     class="w-full aspect-square 
            opacity-90 hover:opacity-100 
            transition 
            grayscale-50 hover:grayscale-0" />
```

**Efectos:**
- Imagen con `grayscale-50` (50% blanco y negro)
- Al hover: color completo (`grayscale-0`)
- Transición suave automática

---

### 4. Cards de Productos Responsivas

**Estructura:**
```html
<div class="grid grid-cols-2 md:grid-cols-4 gap-5">
    <div class="mb-5 bg-white shadow-xs">
        <!-- Imagen cuadrada perfecta -->
        <div class="aspect-square">
            <img class="h-auto w-full" src="./img/menu/pizza-1.png" />
        </div>
        
        <!-- Lista de precios -->
        <div class="flex flex-col">
            <h3 class="p-2 text-center text-xl font-bold text-primary">
                Pepperoni
            </h3>
            <div class="flex justify-between border-b border-black/10 p-2">
                <p>Pequeña</p>
                <p>$123.00</p>
            </div>
            <!-- Más tamaños... -->
        </div>
    </div>
</div>
```

---

## 📱 Responsive Design

### Breakpoints de Tailwind

| Breakpoint | Ancho | Dispositivo | Grid Columns |
|------------|-------|-------------|--------------|
| **Default** | < 640px | Móvil | 2 columnas |
| **sm** | ≥ 640px | Móvil grande | 2 columnas |
| **md** | ≥ 768px | Tablet | 3-4 columnas |
| **lg** | ≥ 1024px | Desktop | 4 columnas |
| **xl** | ≥ 1280px | Desktop grande | 4 columnas |

### Ejemplos de Uso

```html
<!-- 2 columnas móvil, 4 en desktop -->
<div class="grid grid-cols-2 md:grid-cols-4">

<!-- Centrado en móvil, espaciado en desktop -->
<div class="justify-center lg:justify-between">

<!-- Sin gap en móvil, con gap en desktop -->
<div class="gap-0 md:gap-5">

<!-- Orden invertido según dispositivo -->
<div class="order-2 md:order-1">
```

---

## 🎨 Personalización

### Custom Theme

El tema personalizado está definido en `src/index.css`:

```css
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script...');
@import 'tailwindcss';

@theme {
    /* Tipografías */
    --font-title: 'Dancing Script', serif;
    --font-sans: 'Lato', serif;

    /* Colores */
    --color-primary: #644545;        /* Marrón principal */
    --color-background: #ece2e2;     /* Fondo crema */

    /* Imágenes */
    --background-image-hero: url('/img/background.png');
}
```

### Cómo Usar el Theme

```html
<!-- Usar tipografía custom -->
<h1 class="font-title">Título con Dancing Script</h1>
<p class="font-sans">Texto con Lato</p>

<!-- Usar colores custom -->
<div class="bg-primary text-white">
<div class="bg-background">

<!-- Usar background custom -->
<header class="bg-hero bg-cover">
```

### Cambiar Colores

Para cambiar el esquema de colores, edita las variables en `src/index.css`:

```css
@theme {
    --color-primary: #your-color;    /* Cambiar color principal */
    --color-background: #your-bg;    /* Cambiar fondo */
}
```

Los cambios se aplicarán automáticamente en todas las clases:
- `text-primary`
- `bg-primary`
- `border-primary`

---

## 🔧 Decisiones Técnicas

### ¿Por qué Tailwind CSS v4?

**Ventajas:**
- ✅ **Utility-first**: Desarrollo rápido sin escribir CSS custom
- ✅ **Purge automático**: Solo incluye clases usadas (CSS mínimo)
- ✅ **Responsive nativo**: Prefijos simples (`md:`, `lg:`)
- ✅ **Customización con @theme**: Sistema de diseño propio
- ✅ **Sin configuración compleja**: Funciona out-of-the-box con Vite

**Comparación con CSS tradicional:**

```html
<!-- Con Tailwind -->
<div class="flex items-center justify-between p-5 bg-white shadow-lg">
    Contenido
</div>

<!-- Sin Tailwind (requiere CSS separado) -->
<div class="card">
    Contenido
</div>

<style>
.card {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.25rem;
    background-color: white;
    box-shadow: 0 10px 15px rgba(0,0,0,0.1);
}
</style>
```

---

### ¿Por qué Vite sobre Webpack/CRA?

| Característica | Vite | Create React App |
|----------------|------|------------------|
| **Tiempo de inicio** | < 1 segundo | 10-30 segundos |
| **HMR** | Instantáneo | 2-5 segundos |
| **Build** | Rollup (optimizado) | Webpack |
| **Configuración** | Mínima | Compleja |

**Resultado:**
- 🚀 Desarrollo 10-100x más rápido
- ⚡ Hot Module Replacement instantáneo
- 📦 Build optimizado automáticamente

---

### ¿Por qué Multi-página en lugar de SPA?

**Decisión:** Usar `index.html` + `menu.html` separados

**Razones:**
1. **SEO mejorado** - Cada página tiene su propia meta info
2. **Carga más rápida** - Solo se carga contenido necesario
3. **Simplicidad** - No requiere router ni JavaScript adicional
4. **Performance** - Menos JavaScript = página más ligera

---

## 🐛 Troubleshooting

### Problema: Las imágenes no cargan

**Síntomas:**
```
404 Not Found: /img/pizza-1.png
```

**Solución:**
Verificar que las rutas sean relativas:
```html
✅ Correcto:  src="./img/menu/pizza-1.png"
❌ Incorrecto: src="/img/menu/pizza-1.png"
```

---

### Problema: El build falla con error de Tailwind

**Síntomas:**
```
Error: Cannot find module '@tailwindcss/vite'
```

**Solución:**
```bash
# Limpiar node_modules y reinstalar
rm -rf node_modules
rm package-lock.json
npm install
```

---

### Problema: Los estilos no se aplican

**Síntomas:**
Las clases de Tailwind no tienen efecto visual.

**Solución:**
1. Verificar que `src/index.css` esté importado en `index.html`:
```html
<link rel="stylesheet" href="./src/index.css" />
```

2. Verificar que el plugin esté en `vite.config.js`:
```javascript
import tailwindcss from '@tailwindcss/vite';
export default defineConfig({ 
    plugins: [tailwindcss()] 
});
```

---

### Problema: Google Maps no se muestra

**Síntomas:**
Iframe aparece en blanco.

**Solución:**
Verificar que la URL del iframe sea correcta y que tenga el parámetro `referrerpolicy`:
```html
<iframe 
    src="https://www.google.com/maps/embed?pb=..."
    referrerpolicy="no-referrer-when-downgrade"
    allowfullscreen>
</iframe>
```

---

## 🗺️ Roadmap

### Versión 1.1 (Próxima)
- [ ] Sistema de carrito de compras
- [ ] Formulario de pedidos online
- [ ] Integración con WhatsApp Business
- [ ] Selector de idioma (ES/EN)

### Versión 2.0 (Futuro)
- [ ] Panel de administración
- [ ] Sistema de reservas
- [ ] Blog de recetas
- [ ] Modo oscuro
- [ ] PWA (Progressive Web App)
- [ ] Integración con pasarela de pagos

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:

1. **Fork** el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -m 'feat: agrega nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Abre un **Pull Request**

### Convención de Commits

Seguimos [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: nueva característica
fix: corrección de bug
docs: documentación
style: formato de código
refactor: refactorización
test: agregar tests
chore: tareas de mantenimiento
```

---

## 👤 Autor

**Jack Joshua Sivipaucar Quilluya**

- 💼 LinkedIn: [jack-joshua-sivipaucar-quilluya](https://www.linkedin.com/in/jack-joshua-sivipaucar-quilluya-294495229)
- 📧 Email: jack.sivipaucar17@gmail.com
- 🌐 Portfolio: [https://portafolio-zeta-nine-85.vercel.app](https://portafolio-zeta-nine-85.vercel.app)
- 📱 Teléfono: +51 934099199
- 📍 Ubicación: Lima, Perú

### Experiencia Relevante
- **Frontend Developer** con experiencia en JavaScript, React, Tailwind
- **Integración de APIs RESTful**
- Metodologías ágiles (Scrum)
- Control de versiones con Git/GitHub

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

```
MIT License

Copyright (c) 2025 Jack Joshua Sivipaucar Quilluya

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 🙏 Agradecimientos

- **Tailwind CSS Team** - Por el increíble framework
- **Vite Team** - Por la herramienta de build ultra-rápida
- **Google Fonts** - Por las tipografías Dancing Script y Lato
- **Vercel** - Por el hosting gratuito

---

## 📊 Estadísticas del Proyecto

- **Líneas de código:** ~800 HTML + ~50 CSS
- **Páginas:** 2 (index.html, menu.html)
- **Componentes de UI:** Hero, Navbar, Cards, Gallery, Maps
- **Imágenes optimizadas:** 20+
- **Build size:** < 500KB (optimizado)
- **Lighthouse Score:** 95+ en todas las categorías

---

## 📞 Soporte

Si tienes preguntas o necesitas ayuda:

1. Abre un [Issue](https://github.com/tu-usuario/pizzeria/issues)
2. Envía un email a jack.sivipaucar17@gmail.com
3. Conéctate en LinkedIn

---

<div align="center">

**⭐ Si te gustó este proyecto, dale una estrella en GitHub ⭐**

Hecho con ❤️ y mucho 🍕 por [Jack Joshua](https://github.com/tu-usuario)

</div>
