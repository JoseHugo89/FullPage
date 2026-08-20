# 📸 FullPage Personal Capture

[English](#english) | [Español](#español)

A lightweight Chrome extension for capturing **full-page screenshots** directly from your browser.

FullPage Personal Capture automatically scrolls through the current webpage, captures each visible section, stitches the screenshots together, and generates a single high-resolution image.

🔒 **Everything is processed locally in your browser. No screenshots or browsing data are sent to external servers.**

---

# English

## 🚀 FullPage Personal Capture

FullPage Personal Capture is a lightweight Chrome extension designed to capture an entire webpage as a single image, including content outside the visible viewport.

The extension automatically:

1. Detects the full height of the webpage.
2. Saves your current scroll position.
3. Scrolls to the top.
4. Captures the visible sections of the page.
5. Scrolls through the entire document.
6. Stitches all captures together.
7. Generates a single full-page image.
8. Restores your original scroll position.
9. Opens a preview of the result.

Everything happens locally inside your browser.

---

## ✨ Features

* 📸 Full-page screenshots
* 🖼️ High-resolution capture
* 📜 Automatic scrolling
* 🧩 Automatic image stitching
* ✂️ Last-segment cropping to reduce duplicated content
* 📌 Handling of fixed and sticky elements
* 🔄 Original scroll position restoration
* 🖥️ Screenshot preview
* 📥 PNG download
* 📥 JPG download
* 📊 Capture progress indicator
* 🔒 Local processing
* 🚫 No external servers
* 🚫 No analytics
* 🚫 No telemetry
* 🚫 No user tracking
* 🚫 No account required
* 🚫 No API keys required

---

## 🔐 Privacy

FullPage Personal Capture was designed with a minimal-permission approach.

The extension does **not**:

* collect browsing history;
* collect personal information;
* read browser cookies;
* track websites you visit;
* send screenshots to external servers;
* use analytics services;
* use telemetry;
* require an account;
* require cloud services.

Screenshot processing is performed locally using browser APIs and HTML Canvas.

Your screenshots remain on your device unless **you choose to share them yourself**.

---

## 🛡️ Permissions

The extension uses a small set of Chrome permissions.

### `activeTab`

Provides temporary access to the tab where the user explicitly activates the extension.

The extension does not require permanent access to every website you visit.

Access is triggered by user interaction.

### `scripting`

Allows the extension to execute the capture logic inside the currently active webpage.

It is used for tasks such as:

* detecting page dimensions;
* reading the current scroll position;
* scrolling through the document;
* temporarily handling fixed/sticky elements;
* restoring the original page state.

### `downloads`

Allows the generated screenshot to be downloaded to your computer when requested by the user.

---

## 🚫 Permissions intentionally NOT requested

FullPage Personal Capture does not request permissions such as:

```text
<all_urls>
cookies
history
webRequest
browsingData
bookmarks
management
clipboardRead
```

The project follows the principle of requesting only the permissions required for its core functionality.

---

## 🔍 How it works

The basic capture process is:

```text
Current webpage
      ↓
Detect page dimensions
      ↓
Save original scroll position
      ↓
Scroll to top
      ↓
Capture visible viewport
      ↓
Scroll down
      ↓
Capture next viewport
      ↓
Repeat until bottom
      ↓
Stitch captures using Canvas
      ↓
Generate final image
      ↓
Restore original page state
      ↓
Preview / Download
```

The extension uses Chrome's screenshot capabilities together with programmatic scrolling.

The captured sections are combined locally using an HTML `<canvas>` element.

---

## 🔒 Local-first architecture

The extension does not require a backend.

```text
Chrome
   ↓
FullPage Personal Capture
   ↓
Chrome Capture API
   ↓
HTML Canvas
   ↓
PNG / JPG
   ↓
Your computer
```

There is no external server involved in the screenshot-generation process.

---

## 📦 Installation

This project can be installed manually as an unpacked Chrome extension.

### 1. Download the project

Download or clone this repository.

### 2. Open Chrome Extensions

Navigate to:

```text
chrome://extensions
```

### 3. Enable Developer Mode

Enable:

```text
Developer mode
```

### 4. Load the extension

Click:

```text
Load unpacked
```

Select the project folder.

The extension should now appear in Chrome.

---

## 📸 Usage

1. Open a normal webpage.
2. Click the FullPage Personal Capture icon.
3. Select:

```text
Capture full page
```

4. Wait while the extension automatically scrolls through the page.
5. A preview will open when the capture is complete.
6. Download the result as PNG or JPG.

---

## ⚠️ Chrome restrictions

Chrome prevents extensions from executing scripts on certain protected pages.

For example:

```text
chrome://
chrome-extension://
Chrome Web Store pages
other protected browser pages
```

Full-page capture may therefore not work on these pages.

This is a Chrome security restriction, not an extension error.

---

## ⚠️ Known limitations

Some websites can be difficult to capture perfectly due to:

* dynamically loaded content;
* infinite scrolling;
* animations;
* lazy-loaded images;
* embedded iframes;
* sticky headers;
* fixed navigation elements;
* dynamically resizing components;
* very large pages;
* browser Canvas size limitations.

The project attempts to handle common cases while keeping the implementation lightweight.

---

## 🧱 Technology

Built with:

* Chrome Extensions
* Manifest V3
* JavaScript
* HTML
* CSS
* HTML Canvas API
* Chrome Extension APIs

No frontend frameworks are required.

No build process is required.

---

## 📂 Project structure

```text
fullpage-personal-capture/
│
├── manifest.json
├── background.js
├── popup.html
├── popup.css
├── popup.js
├── capture.js
├── preview.html
├── preview.css
├── preview.js
│
└── icons/
    ├── icon16.png
    ├── icon32.png
    ├── icon48.png
    └── icon128.png
```

The exact structure may evolve as the project grows.

---

## 🔧 Development

No installation or build tools are required.

You do NOT need:

```text
npm
Node.js
React
Vue
Angular
API keys
external servers
```

Edit the source files and reload the extension from:

```text
chrome://extensions
```

---

## 🎯 Project philosophy

The project follows four main principles:

**Simple**

Do one thing and do it well.

**Local**

Screenshot processing should remain on the user's device.

**Minimal permissions**

Request only the Chrome permissions required for the feature being used.

**Transparent**

The complete source code is available for inspection.

---

## 📋 Current status

**Version:** V1

The current version focuses on:

* reliable full-page capture;
* image quality;
* automatic scrolling;
* image stitching;
* avoiding duplicated sections;
* handling fixed/sticky elements;
* restoring the original webpage state;
* PNG/JPG export.

Additional features may be introduced in future versions.

---

## 🗺️ Possible future features

Potential improvements include:

* selected-area screenshots;
* visible-area screenshots;
* copy screenshot to clipboard;
* annotation tools;
* automatic sensitive-data blur;
* element selection;
* custom screenshot quality;
* custom delays for dynamic websites;
* PDF export;
* improved infinite-scroll support;
* advanced handling of fixed/sticky elements.

Any new feature requiring additional Chrome permissions should be evaluated before adding those permissions.

---

## 🔐 Security

If you discover a security or privacy issue, please open a GitHub issue describing the problem.

Do not include sensitive screenshots, credentials, cookies, tokens, or personal information in public issues.

---

## 📄 License

A license has not yet been specified.

If this repository is intended to be open source, consider adding a license such as MIT before encouraging redistribution.

---

# Español

## 🚀 FullPage Personal Capture

FullPage Personal Capture es una extensión ligera para Google Chrome diseñada para capturar una **página web completa en una sola imagen**, incluyendo el contenido que se encuentra fuera del área visible de la pantalla.

La extensión automáticamente:

1. Detecta la altura completa de la página.
2. Guarda la posición actual del scroll.
3. Se desplaza hacia el inicio.
4. Captura la sección visible.
5. Avanza automáticamente por la página.
6. Captura los diferentes segmentos.
7. Une las capturas.
8. Genera una única imagen.
9. Restaura la posición original del usuario.
10. Abre una previsualización del resultado.

Todo el procesamiento se realiza localmente dentro del navegador.

---

## ✨ Características

* 📸 Captura de página completa
* 🖼️ Capturas en alta resolución
* 📜 Scroll automático
* 🧩 Unión automática de capturas
* ✂️ Corrección del último segmento
* 📌 Manejo de elementos fixed y sticky
* 🔄 Restauración de la posición original
* 🖥️ Previsualización
* 📥 Descarga PNG
* 📥 Descarga JPG
* 📊 Indicador de progreso
* 🔒 Procesamiento local
* 🚫 Sin servidores externos
* 🚫 Sin Analytics
* 🚫 Sin telemetría
* 🚫 Sin seguimiento del usuario
* 🚫 Sin cuentas
* 🚫 Sin API keys

---

## 🔐 Privacidad

FullPage Personal Capture está diseñada siguiendo un enfoque de **permisos mínimos**.

La extensión NO:

* recopila el historial de navegación;
* recopila información personal;
* lee cookies del navegador;
* rastrea las páginas que visitas;
* envía capturas a servidores externos;
* utiliza servicios de Analytics;
* utiliza telemetría;
* requiere crear una cuenta;
* necesita servicios en la nube.

Las capturas se procesan localmente utilizando las APIs del navegador y HTML Canvas.

Las imágenes permanecen en tu dispositivo salvo que **tú decidas compartirlas posteriormente**.

---

## 🛡️ Permisos utilizados

### `activeTab`

Proporciona acceso temporal a la pestaña donde el usuario activa explícitamente la extensión.

La extensión no necesita acceso permanente a todas las páginas visitadas.

El acceso se produce como consecuencia de una acción del usuario.

### `scripting`

Permite ejecutar la lógica necesaria dentro de la página activa.

Se utiliza para:

* detectar las dimensiones de la página;
* obtener la posición del scroll;
* realizar el desplazamiento automático;
* manejar temporalmente elementos fixed/sticky;
* restaurar el estado original de la página.

### `downloads`

Permite guardar la captura generada en la computadora cuando el usuario solicita descargarla.

---

## 🚫 Permisos que intencionalmente NO solicitamos

La extensión no solicita permisos como:

```text
<all_urls>
cookies
history
webRequest
browsingData
bookmarks
management
clipboardRead
```

La filosofía del proyecto es solicitar únicamente los permisos necesarios para realizar la captura.

---

## 🔍 ¿Cómo funciona?

```text
Página actual
      ↓
Detectar dimensiones
      ↓
Guardar posición del scroll
      ↓
Ir al inicio
      ↓
Capturar pantalla visible
      ↓
Bajar
      ↓
Capturar siguiente sección
      ↓
Repetir hasta llegar al final
      ↓
Unir capturas con Canvas
      ↓
Generar imagen
      ↓
Restaurar la página
      ↓
Previsualizar / Descargar
```

La extensión combina las capacidades de captura de Chrome con desplazamiento programático.

Posteriormente los segmentos son procesados localmente mediante `<canvas>`.

---

## 🔒 Arquitectura local

No existe un backend encargado de procesar las capturas.

```text
Chrome
   ↓
FullPage Personal Capture
   ↓
API de captura de Chrome
   ↓
HTML Canvas
   ↓
PNG / JPG
   ↓
Tu computadora
```

La captura no necesita enviarse a Internet para generar la imagen final.

---

## 📦 Instalación

### 1. Descargar el proyecto

Descarga o clona este repositorio.

### 2. Abrir extensiones

En Chrome abre:

```text
chrome://extensions
```

### 3. Activar modo desarrollador

Activa:

```text
Modo desarrollador
```

### 4. Cargar extensión

Selecciona:

```text
Cargar descomprimida
```

y elige la carpeta del proyecto.

---

## 📸 Uso

1. Abre una página web normal.
2. Presiona el icono de FullPage Personal Capture.
3. Selecciona:

```text
Capturar página completa
```

4. Espera mientras la extensión recorre automáticamente la página.
5. Cuando termine se abrirá una previsualización.
6. Descarga la captura como PNG o JPG.

---

## ⚠️ Restricciones de Chrome

Por razones de seguridad, Chrome no permite que las extensiones ejecuten código en determinadas páginas protegidas.

Por ejemplo:

```text
chrome://
chrome-extension://
Chrome Web Store
otras páginas internas protegidas
```

Por ello, la captura puede no funcionar en estas páginas.

No es un error de FullPage Personal Capture, sino una restricción de seguridad del navegador.

---

## ⚠️ Limitaciones conocidas

Algunas páginas pueden resultar más difíciles de capturar debido a:

* contenido dinámico;
* scroll infinito;
* animaciones;
* lazy loading;
* iframes;
* headers sticky;
* elementos fixed;
* componentes que cambian de tamaño;
* páginas extremadamente largas;
* límites de tamaño de Canvas del navegador.

El objetivo es mejorar progresivamente estos casos sin aumentar innecesariamente los permisos de la extensión.

---

## 🧱 Tecnologías

El proyecto utiliza:

* Chrome Extensions
* Manifest V3
* JavaScript
* HTML
* CSS
* HTML Canvas API
* Chrome Extension APIs

No utiliza frameworks externos.

---

## 🔧 Desarrollo

No necesitas instalar:

```text
npm
Node.js
React
Vue
Angular
API keys
servidores externos
```

Modifica los archivos y vuelve a cargar la extensión desde:

```text
chrome://extensions
```

---

## 🎯 Filosofía del proyecto

### Simple

Hacer una función concreta y hacerla correctamente.

### Local

Las capturas deben procesarse en el dispositivo del usuario.

### Permisos mínimos

Solicitar únicamente los permisos estrictamente necesarios.

### Transparente

Todo el código fuente puede ser inspeccionado.

---

## 📋 Estado actual

**Versión:** V1

Esta primera versión se centra principalmente en:

* captura completa;
* calidad de imagen;
* scroll automático;
* unión de capturas;
* evitar segmentos duplicados;
* manejo de elementos fixed/sticky;
* restauración del estado original;
* exportación PNG/JPG.

---

## 🗺️ Posibles mejoras

En futuras versiones se podrían incorporar:

* captura de una zona seleccionada;
* captura únicamente del área visible;
* copiar imagen al portapapeles;
* herramientas de anotación;
* desenfoque de información sensible;
* selección de elementos;
* configuración de calidad;
* configuración del tiempo entre capturas;
* exportación PDF;
* mejor soporte para scroll infinito;
* mejor detección de elementos fixed/sticky.

Antes de introducir una función que necesite permisos adicionales de Chrome, se deberá evaluar si dicho permiso es realmente necesario.

---

## 🔐 Seguridad

Si encuentras un problema relacionado con seguridad o privacidad, puedes reportarlo mediante GitHub Issues.

No publiques capturas privadas, credenciales, cookies, tokens ni información personal dentro de un Issue público.

---

## 📄 Licencia

Actualmente no se ha definido una licencia.

Si el proyecto se va a distribuir como software open source, se recomienda agregar una licencia antes de permitir su redistribución.
