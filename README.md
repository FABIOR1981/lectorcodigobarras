# 📱 Lector de Códigos PWA

Una aplicación web progresiva (PWA) minimalista y rápida diseñada para escanear códigos QR y de barras utilizando la cámara del dispositivo móvil, con soporte para instalación en pantalla completa (modo *standalone*) y funcionamiento optimizado.

## 🚀 Características Principales

* **Modo PWA Nativa:** Se puede instalar directamente en la pantalla de inicio de tu smartphone (como Android/Samsung) abriéndose en una ventana limpia y sin barras de navegador.
* **Escaneo Eficiente:** Utiliza la robusta librería `html5-qrcode` (versión fijada vía CDN) para garantizar una alta compatibilidad de lectura en diferentes lentes y dispositivos móviles.
* **Gestión de Portapapeles:** Copia el contenido del código detectado al portapapeles de forma automática o mediante un botón dedicado.
* **Soporte Offline:** Incorpora un Service Worker (`sw.js`) que cachea la app, los íconos y la librería de escaneo para funcionar sin conexión.
* **Versión visible en pantalla:** El pie de la app muestra la versión leída directamente desde `sw.js` (`CACHE_NAME`), sin duplicar el dato.

## 📂 Estructura del Proyecto

1. **`index.html`**: Interfaz de usuario, estilos y lógica del escáner.
2. **`manifest.json`**: Configuración de la PWA (nombre, íconos y `display: standalone`).
3. **`sw.js`**: Service Worker para caché y funcionamiento offline. Contiene `CACHE_NAME`, que define la versión mostrada en la app.
4. **`icons/icon-192.png` y `icons/icon-512.png`**: Íconos de la app alojados en el propio repo (no dependen de un CDN externo).
5. **`test.html`**: Panel auxiliar para generar códigos QR/de barras de prueba (estáticos y dinámicos con fecha/hora), útil para probar el lector sin códigos físicos a mano.

## 🛠️ Tecnologías Utilizadas

* **HTML5 & CSS3** (Diseño adaptable y moderno).
* **JavaScript (Vanilla)** para el control de la interfaz y eventos.
* **[html5-qrcode](https://github.com/mebjas/html5-qrcode)** vía CDN (versión fijada) como motor de decodificación de cámara.
* **Service Workers & Web App Manifest** para las capacidades de Progressive Web App.

## 🔢 Versionado

Para publicar una nueva versión, alcanza con cambiar `CACHE_NAME` en `sw.js` (por ejemplo, de `lector-cache-v1.1.0` a `lector-cache-v1.1.1`). El número se refleja automáticamente en el pie de `index.html` y fuerza la invalidación del caché anterior.

## 🌐 Despliegue

El proyecto está optimizado para ser alojado de manera estática en plataformas como **Netlify**. Subí todos los archivos y carpetas (`index.html`, `manifest.json`, `sw.js`, `icons/`) directamente en la carpeta raíz del proyecto para evitar errores de ruta (`404`).
