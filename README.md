# Bleads Design System

> **Efficiency Growth** — Design System oficial de Bleads SpA v2025

Sistema de diseño oficial de [Bleads](https://bleads.cl), la agencia B2B especialista en crecimiento, marketing, prospección y ventas para industrias complejas.

---

## ¿Qué incluye?

```
bleads-design-system/
├── tokens/
│   ├── bleads-tokens.css      # CSS custom properties (plug-and-play)
│   └── bleads-tokens.json     # Design tokens (Figma Tokens / Style Dictionary)
├── components/
│   └── bleads-components.css  # Clases de componentes reutilizables
├── figma-export/
│   └── bleads-figma-tokens.json  # Import directo en Figma (Tokens Studio)
└── README.md
```

---

## Instalación rápida

### Via CDN (recomendado para proyectos web)
```html
<!-- En tu <head> -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/bleads/design-system@latest/tokens/bleads-tokens.css">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
```

### Via npm
```bash
npm install @bleads/design-system
```

```js
import '@bleads/design-system/tokens/bleads-tokens.css'
```

### Clonar el repo
```bash
git clone https://github.com/bleads/design-system.git
cd design-system
```

---

## Colores de marca

| Token | Hex | Uso |
|-------|-----|-----|
| `--bleads-blue`   | `#084BB9` | Color principal · CTA · Encabezados |
| `--bleads-red`    | `#EF2D2D` | Acento principal · Urgencia · Noticias |
| `--bleads-orange` | `#FF7F00` | Secundario · Minería |
| `--bleads-green`  | `#9CF95B` | Secundario · Forestal / Agrícola |
| `--bleads-teal`   | `#00FFD4` | Secundario · Energía |
| `--bleads-gray`   | `#545454` | Texto sobre blanco |

---

## Tipografía

La fuente oficial es **Poppins** (Google Fonts). Usar siempre en estos pesos:

| Uso | Peso | Token |
|-----|------|-------|
| Títulos H1 / Display | SemiBold 600 | `--font-semibold` |
| Títulos H2 / H3 / CTA | SemiBold 600 | `--font-semibold` |
| Párrafos y cuerpo | Regular 400 | `--font-regular` |
| Notas al pie / captions | Light 300 / Regular 400 | `--font-light` |

---

## Elementos visuales clave

De acuerdo al Manual de Marca Bleads:

- **Círculos** — aluden a la luna del logo del lobo. Presentes en fondos, separadores y overlays.
- **Rectángulos con esquinas redondeadas** — estructura de cards y contenedores.
- **Líneas rectas** — para dar movimiento, subrayar y "desordenar" levemente la composición.
- **Formas del logo** — el semicírculo del ojo o las puntas del pelo del lobo pueden extraerse en casos especiales.

---

## Uso de CSS tokens

```css
/* Usar tokens en tu CSS */
.mi-boton {
  background-color: var(--bleads-blue);
  color: var(--bleads-white);
  border-radius: var(--radius-pill);
  padding: var(--space-3) var(--space-6);
  font-family: var(--font-primary);
  font-weight: var(--font-semibold);
  font-size: var(--text-sm);
  transition: background-color var(--duration-base) var(--ease-in-out);
}

.mi-boton:hover {
  background-color: var(--blue-500);
}

.mi-titulo {
  font-family: var(--font-primary);
  font-weight: var(--font-semibold);
  font-size: var(--text-4xl);
  color: var(--bleads-blue);
  line-height: var(--leading-tight);
  letter-spacing: var(--tracking-tight);
}
```

---

## Uso en Figma (Tokens Studio)

1. Instalar el plugin [Tokens Studio for Figma](https://tokens.studio/)
2. En el plugin → **Load from file** → seleccionar `figma-export/bleads-figma-tokens.json`
3. Aplicar los tokens a tus componentes
4. Para sincronizar cambios: el plugin soporta sync con este repositorio vía GitHub

---

## Uso con Style Dictionary

```bash
npm install -g style-dictionary
```

```js
// config.js
module.exports = {
  source: ['tokens/bleads-tokens.json'],
  platforms: {
    css: {
      transformGroup: 'css',
      buildPath: 'dist/',
      files: [{ destination: 'bleads-variables.css', format: 'css/variables' }]
    },
    js: {
      transformGroup: 'js',
      buildPath: 'dist/',
      files: [{ destination: 'bleads-tokens.js', format: 'javascript/es6' }]
    }
  }
}
```

```bash
style-dictionary build
```

---

## Voz de marca (resumen)

Bleads es un **Héroe Rebelde**: audaz, seguro, directo, disruptivo e inspirador.

- ✅ **Sí**: Mensajes directos, motivadores, desafiantes. Lenguaje de negocios: ventas, márgenes, rentabilidad.
- ❌ **No**: Ambigüedad, eufemismos, lenguaje corporativo vacío, conformismo.

---

## Reglas de logo

| Fondo | Versión permitida |
|-------|------------------|
| Blanco | Todas las variantes |
| Azul `#084BB9` | Logotipo blanco o isotipo simple blanco |
| Rojo `#EF2D2D` | Logotipo blanco o isotipo simple blanco |
| Fotografía / color no-corporativo | Usar lockup con recuadro blanco, o logotipo sin lobo |

---

## Contribuir

1. Crea un branch: `git checkout -b feat/nombre-del-cambio`
2. Edita los tokens en `tokens/bleads-tokens.json`
3. Regenera el CSS ejecutando: `npm run build`
4. Abre un Pull Request con descripción del cambio

---

## Licencia

Uso interno Bleads SpA — © 2025 Bleads SpA. Todos los derechos reservados.

Para consultas: francisca@bleads.cl · [bleads.cl](https://bleads.cl)
