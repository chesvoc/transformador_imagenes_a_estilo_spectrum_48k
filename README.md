# ZX Spectrum 48K — Image Transformer · Transformador de Imágenes

Single-file web app that converts photos to the **ZX Spectrum 48K** look (internal **256×192** px, ZX palette, optional dithering, attribute 8×8 clash, AI outline and B/W hatching).  
Aplicación web de **un solo archivo** que convierte fotos al estilo **ZX Spectrum 48K** (lienzo interno **256×192** px, paleta ZX, dithering opcional, atributos 8×8, contorno IA y tramas B/N).

---

## Table of Contents · Tabla de contenidos
- [English](#english)
  - [Live Demo](#live-demo)
  - [Features](#features)
  - [How to Use](#how-to-use)
  - [Deploy on GitHub Pages](#deploy-on-github-pages)
  - [Tech Notes](#tech-notes)
  - [License](#license)
  - [Credits](#credits)
- [Español](#español)
  - [Demo](#demo)
  - [Funcionalidades](#funcionalidades)
  - [Uso](#uso)
  - [Publicación en GitHub Pages](#publicación-en-github-pages)
  - [Notas técnicas](#notas-técnicas)
  - [Licencia](#licencia)
  - [Créditos](#créditos)

---

## English

### Live Demo
👉 https://chesvoc.github.io/transformador_imagenes_a_estilo_spectrum_48k/  
Repository: https://github.com/chesvoc/transformador_imagenes_a_estilo_spectrum_48k

### Features
- **True ZX resolution:** internal canvas **256×192**, scaled with `image-rendering: pixelated`.
- **Palettes:**
  - **Base 8** (Black, Blue, Red, Magenta, Green, Cyan, Yellow, White).
  - **Base 8 + Bright** (15 effective colors; “bright black” is still black).
- **Dithering:** optional **Floyd–Steinberg** for smoother gradients with a limited palette.
- **Attribute 8×8 (Clash):** constrain each **8×8** cell to **two colors** (the two most frequent in that block). Controls for cell size and ink/paper bias.
- **Adjustments:** **Brightness / Contrast / Saturation** with **Live Preview**.
- **AI Outline + Brush:** light saliency + edges to draw a brush-like outline; **re-quantize** to the ZX palette afterwards.
- **B/W Hatching:** monochrome shading (dots / lines / cross-hatch) with density/angle/width controls; edge reinforcement.
- **Auto-fit:** uploaded photo is letterboxed and centered to **256×192** preserving aspect ratio.
- **Download:** always available (PNG named `zx48_image_<mode>_<timestamp>.png`).
- **No dependencies:** a single HTML file; runs entirely in the browser.

### How to Use
1. Open the **demo** (or double-click `index.html` locally).
2. **Select file** (JPG/PNG). The image becomes the working **256×192** base.
3. Pick a **processing mode**: Classic ZX (Base 8 / Base 8 + Bright), **AI Outline + Brush**, **B/W Hatching**.  
   (Optional) enable **Attribute 8×8** for clash behavior.
4. Tweak **Brightness / Contrast / Saturation**.  
   Use **Apply** to bake the current output as the new base; **Reset** to revert.
5. Click **Download** to save the current canvas as PNG.  
   *(If you trigger an action with no image loaded, the file picker opens automatically.)*

### Deploy on GitHub Pages
1. Repo → **Settings → Pages** → **Source:** *Deploy from a branch* → **Branch:** `main` / **Folder:** `/ (root)` → **Save**.
2. Make sure the entry file is **`index.html`** at the repo root.
3. Wait about a minute and open:  
   `https://chesvoc.github.io/transformador_imagenes_a_estilo_spectrum_48k/`

### Tech Notes
- Implemented as a small module (`ZXImageLab`) using Canvas 2D.
- Palette quantization by Euclidean RGB; **Floyd–Steinberg** dithering.
- Attribute-clash mode selects the two most frequent palette indices per 8×8 block and remaps the rest.

## License

- **Code:** [MIT](./LICENSE)  
MIT License

Copyright (c) 2025 David Llobet Sarria

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

- **Non-code content** (README, screenshots, sample images): **CC BY 4.0** — attribution to **David Llobet Sarria (chesvoc)**.

### Credits
Built by **David Llobet Sarria (chesvoc)**.  
Mixing **retro ZX aesthetics** with modern browser canvas — single-file, no dependencies.

---

## Español

### Demo
👉 https://chesvoc.github.io/transformador_imagenes_a_estilo_spectrum_48k/  
Repositorio: https://github.com/chesvoc/transformador_imagenes_a_estilo_spectrum_48k

### Funcionalidades
- **Resolución ZX real:** lienzo interno **256×192**, escalado con `image-rendering: pixelated`.
- **Paletas:**
- **Base 8** (Negro, Azul, Rojo, Magenta, Verde, Cian, Amarillo, Blanco).
- **Base 8 + Bright** (15 colores efectivos; el “bright black” sigue siendo negro).
- **Dithering:** **Floyd–Steinberg** opcional para suavizar degradados con paleta limitada.
- **Atributos 8×8 (Clash):** cada celda **8×8** queda restringida a **dos colores** (los dos más frecuentes del bloque). Controles de tamaño de celda y sesgo ink/paper.
- **Ajustes:** **Brillo / Contraste / Saturación** con **Live Preview**.
- **Contorno IA + Pincel:** saliencia + bordes para trazar contorno con efecto pincel; luego **re-cuantiza** a la paleta ZX.
- **Tramas B/N:** sombreado monocromo (puntos / líneas / cross-hatch) con densidad/ángulo/grosor; refuerzo de bordes.
- **Auto-encaje:** al subir la foto, se centra con letterbox a **256×192** manteniendo proporciones.
- **Descarga:** siempre disponible (PNG `zx48_image_<mode>_<timestamp>.png`).
- **Sin dependencias:** un único HTML que corre íntegramente en el navegador.

### Uso
1. Abre la **demo** (o `index.html` local).  
2. Pulsa **Seleccionar archivo** (JPG/PNG). La imagen pasa a ser la base a **256×192**.
3. Elige **modo de procesado**: ZX clásico (Base 8 / Base 8 + Bright), **Contorno IA + Pincel**, **Tramas B/N**.  
 (Opcional) activa **Atributos 8×8** para simular el “clash”.
4. Ajusta **Brillo / Contraste / Saturación**.  
 Con **Apply** “horneas” el resultado como nueva base; **Reset** revierte.
5. Pulsa **Download** para guardar el lienzo como PNG.  
 *(Si pulsas una acción sin imagen, se abrirá el selector automáticamente.)*

### Publicación en GitHub Pages
1. Repo → **Settings → Pages** → **Source:** *Deploy from a branch* → **Branch:** `main` / **Folder:** `/ (root)` → **Save**.
2. Asegúrate de que el archivo de entrada es **`index.html`** en la raíz.
3. Espera ~1 minuto y abre:  
 `https://chesvoc.github.io/transformador_imagenes_a_estilo_spectrum_48k/`

### Notas técnicas
- Implementación en un pequeño módulo (`ZXImageLab`) con Canvas 2D.
- Cuantización por paleta (distancia Euclídea RGB); dithering **Floyd–Steinberg**.
- En “attribute clash” cada bloque 8×8 elige los dos índices más frecuentes y remapea el resto.

### Licencia
- **Código:** MIT  
MIT License
Copyright (c) 2025 David Llobet Sarria

- **Contenido no-código** (README, capturas, imágenes de ejemplo): **CC BY 4.0** — atribución a **David Llobet Sarria (chesvoc)**.

### Créditos
Creado por **David Llobet Sarria (chesvoc)**.  
Mezclando **estética ZX retro** con canvas moderno en el navegador — un solo archivo, sin dependencias.

