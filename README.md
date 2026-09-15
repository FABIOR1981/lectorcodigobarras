# 📱 Lector de Códigos PWA

Una aplicación web progresiva (PWA) minimalista y rápida diseñada para escanear códigos QR y de barras utilizando la cámara del dispositivo móvil, con soporte para instalación en pantalla completa (modo *standalone*) y funcionamiento optimizado.

## 🚀 Características Principales

* **Modo PWA Nativa:** Se puede instalar directamente en la pantalla de inicio de tu smartphone (como Android/Samsung) abriéndose en una ventana limpia y sin barras de navegador.
* **Escaneo Eficiente:** Utiliza la robusta librería `html5-qrcode` para garantizar una alta compatibilidad de lectura en diferentes lentes y dispositivos móviles[cite: 8].
* **Gestión de Portapapeles:** Copia el contenido del código detectado al portapapeles de forma automática o mediante un botón dedicado[cite: 8].
* **Soporte Offline:** Incorpora un Service Worker (`sw.js`) para la gestión de caché y rendimiento en segundo plano[cite: 10].

## 📂 Estructura del Proyecto

El proyecto se compone de tres archivos principales ubicados en la raíz del servidor:

1. **`index.html`**: Contiene la interfaz de usuario, los estilos visuales adaptados para dispositivos móviles y la lógica del escáner[cite: 8].
2. **`manifest.json`**: El archivo de configuración de la PWA (nombre, íconos y propiedad `display: standalone`)[cite: 9].
3. **`sw.js`**: El Service Worker encargado del almacenamiento en caché y la estabilidad offline[cite: 10].

## 🛠️ Tecnologías Utilizadas

* **HTML5 & CSS3** (Diseño adaptable y moderno).
* **JavaScript (Vanilla)** para el control de la interfaz y eventos.
* **[html5-qrcode](https://github.com/mebjas/html5-qrcode)** vía CDN como motor de decodificación de cámara[cite: 8].
* **Service Workers & Web App Manifest** para las capacidades de Progressive Web App.

## 🌐 Despliegue

El proyecto está optimizado para ser alojado de manera estática en plataformas como **Netlify**[cite: 2]. Asegúrate de subir los tres archivos (`index.html`, `manifest.json` y `sw.js`) directamente en la carpeta raíz del proyecto para evitar errores de ruta (`404`)[cite: 2, 8, 9, 10].
