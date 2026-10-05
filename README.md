# 👕 Altimonar Factory | Production Webstore & Pro Graphics Studio

¡Bienvenido al repositorio oficial de la infraestructura web de **Altimonar Factory**! Este sistema es una plataforma híbrida de comercio electrónico avanzada diseñada específicamente para la maquetación, personalización y venta automatizada de indumentaria (hoodies, playeras, gorras) y artículos impresos troquelados de alta fidelidad.

El software está construido bajo un enfoque de desarrollo **Workspace-First (no invasivo)** y se ejecuta como una SPA (Single Page Application) estática de alto rendimiento optimizada para ser desplegada en **Netlify** con control de versiones automatizado en **GitHub**.

---

## 🛠️ Arquitectura y Capacidades Técnicas

El núcleo del sistema integra módulos profesionales de edición vectorial y automatización comercial que operan de manera nativa en el navegador del cliente:

*   **Motor de Lienzo Interactivo (Canvas Engine):** Controlado a través de `Fabric.js` para la manipulación avanzada de capas, textos tipográficos pesados, dibujo libre suavizado y transformaciones matriciales de objetos.
*   **Aislamiento de Canales Alfa (Filtro Chroma):** Algoritmo real basado en tolerancia Euclidiana de color para la remoción instantánea de fondos uniformes en mapas de bits subidos por el usuario.
*   **Illustrator Masking (Máscaras de Recorte):** Motor matemático que encapsula imágenes dentro de vectores geométricos para previsualizar stickers circulares, pines o troqueles exactos.
*   **Líneas de Troquel Automáticas (Cutline / Sangrado):** Generador expansivo perimetral (`offset stroke`) que calcula el borde de corte exacto requerido por la maquinaria física y plotters de Altimonar Factory.
*   **Compilación Multiformato de Impresión:** Salidas optimizadas para producción masiva con exportación en `PNG Pro` con duplicación de densidad de píxeles (equivalente a 300 DPI) y `SVG Vectorial Puro` con coordenadas de curvas infinitas.
*   **Checkout de Ingeniería Comercial por WhatsApp:** Automatización que serializa el estado del carrito de compras, desglosa tallas y precios, y despacha un mensaje estructurado codificado mediante el protocolo HTTP directo al canal de atención de la empresa (`+52 55 2414 6182`).

---

## 📁 Estructura del Repositorio

Para el correcto despliegue de las Serverless Functions y los módulos estáticos en Netlify, el proyecto mantiene la siguiente jerarquía de archivos:

```text
altimonar-factory-studio/
├── index.html          # Interfaz de usuario (UI), estilos CSS y lógica del motor gráfico
├── netlify.toml        # Directivas de configuración de Netlify, redirecciones y políticas de caché
└── README.md           # Documentación técnica del sistema (Este archivo)
```

---

## 🚀 Guía de Instalación y Despliegue Local

Sigue estos pasos para clonar el repositorio, realizar pruebas en tu entorno de desarrollo local y empujar a producción:

### 1. Clonar el repositorio y preparación
```bash
# Clonar tu repositorio de GitHub
git clone https://github.com

# Acceder a la carpeta del proyecto
cd altimonarfactory-store
```

### 2. Ejecución en entorno local
Al estar construido en HTML5, CSS3 y JavaScript vanilla, no requiere instaladores de paquetes complejos. Puedes levantar un servidor local rápido utilizando extensiones como *Live Server* en VS Code o mediante Python en tu terminal:
```bash
# Levantar servidor local en el puerto 8000
python -m http.server 8000
```
Abre tu navegador web e ingresa a `http://localhost:8000`.

### 3. Despliegue continuo hacia Netlify
Cada vez que realices modificaciones en la interfaz o los precios del catálogo, sincroniza tu producción ejecutando los siguientes comandos en tu consola:
```bash
# Agregar los cambios al área de preparación
git add .

# Crear un punto de control en el historial
git commit -m "build: optimize graphics rendering engine and update catalog pricing"

# Empujar el código a la rama principal
git push origin main
```
*Nota: Netlify detectará el cambio en tu repositorio de GitHub y actualizará de manera automática la Webstore en vivo en menos de 5 segundos.*

---

## 🔒 Variables de Entorno y Seguridad

El sistema cuenta con ganchos asíncronos preparados para conectarse con funciones en la nube. Si decides reactivar el soporte de Inteligencia Artificial Generativa (DALL-E 3) mediante Serverless Functions, asegúrate de registrar la siguiente variable segura en el panel de Netlify (*Site configuration > Environment variables*):

*   `OPENAI_API_KEY`: Tu clave secreta oficial de OpenAI (`sk-...`) para que las peticiones se procesen de forma oculta en el backend, protegiendo tus credenciales de accesos no autorizados en el navegador.

---

## 📄 Licencia y Propiedad

Este software es propiedad exclusiva de **Altimonar Factory**. Todos los derechos sobre los algoritmos de corte, diseño de la interfaz y flujos de comercio electrónico están reservados para la marca.

---
Hecho con ⚡ para Altimonar Factory. Desarrollado y optimizado para la automatización industrial de artículos personalizados.
