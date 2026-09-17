# SoundFest 2026 - Plataforma Web Oficial del Festival

## 👥 Información del Equipo

- **Integrantes:**
  - Antezana Villegas, Jhojan Manuel
  - Tocas Anglas, Angle

---

## 🛠️ Descripción del Proyecto

`SoundFest 2026` es una landing page interactiva desarrollada para la promoción y venta de entradas de un festival de música ficticio en Lima, Perú. El sistema combina una interfaz estética moderna, alta accesibilidad y un diseño totalmente responsivo adaptado para dispositivos móviles, tablets y computadoras de escritorio.

---

## 🚀 Desafíos Técnicos y Solución de Complicaciones

Durante la fase de integración visual y funcional de la aplicación, el equipo enfrentó un problema crítico de compatibilidad en la navegación móvil:

### ⚠️ El Problema: Rebote / Cierre Automático del Menú Hamburguesa

Al combinar la versión CDN de **Bootstrap 5.3.3** con el **Play CDN de Tailwind CSS**, el menú hamburguesa presentaba un comportamiento inestable en dispositivos móviles (se abría y se cerraba de forma inmediata al hacer clic).

- **Causa Raíz:**
  1. **Conflicto de Especificidad CSS:** La clase `.collapse` de Bootstrap define la visibilidad mediante `display: none`, mientras que las clases utilitarias de Tailwind aplican sus propias reglas globales sobre el DOM. Esto producía una colisión en el cálculo de estilos en tiempo de ejecución.
  2. **Duplicidad de Eventos JavaScript:** El atributo nativo `data-bs-toggle="collapse"` de Bootstrap detectaba múltiples llamadas de eventos (_click handlers_) debido a la alteración del DOM generada por Tailwind, provocando la apertura y el colapso en cuestión de milisegundos.

### 💡 La Solución Implementada

Para garantizar estabilidad absoluta y un control predictivo de la UI, se aplicó una refactorización basada en **control manual híbrido**:

1. Se removió el atributo dinámico `data-bs-toggle="collapse"` del HTML para aislar el script nativo de Bootstrap.
2. Se tomó el control de la visibilidad utilizando clases utilitarias nativas de Tailwind (`hidden` y `flex`).
3. Se añadió un _script_ ligero en JavaScript puro que alterna (_toggle_) las clases de Tailwind de forma segura y cierra el menú automáticamente al hacer clic en cualquier sección interna del navbar en móviles.

---

## 📋 Backlog del Proyecto

### Sprint 1: Fundamentos y Estructura

- [x] Configuración inicial del documento HTML5 con metaetiquetas SEO y Open Graph.
- [x] Vinculación de librerías mediante CDN (Bootstrap 5.3.3 CSS/JS y Tailwind CSS).
- [x] Definición de la estructura semántica de la página (`header`, `nav`, `section`, `article`, `footer`).

### Sprint 2: Componentes UI y Responsividad

- [x] Desarrollo del Header y Navbar Híbrido responsivo (`navbar-expand-lg`) con Dropdown de géneros.
- [x] Creación de la sección Hero con gradientes dinámicos y tipografía adaptativa.
- [x] Implementación del Grid de Tarjetas de Artistas usando el sistema de 12 columnas de Bootstrap (`col-12`, `col-md-6`, `col-lg-4`).
- [x] Diseño de Badge interactivo para la reserva de tickets.

### Sprint 3: Formulario, Accesibilidad y Corrección de Bugs

- [x] Construcción del formulario de reserva con validación en el cliente (`needs-validation` y `invalid-feedback`).
- [x] Implementación de estándares de Accesibilidad (A11y): atributos `aria-*`, roles semánticos y contrastes visuales.
- [x] **Resolución de Bug:** Solución al colapso/rebote del menú hamburguesa mediante script de control directo de clases.
- [x] Documentación final del proyecto (`README.md`).

---

## 🧰 Tecnologías Utilizadas

- **HTML5 Semántico**
- **CSS3 & JavaScript (ES6)**
- **Bootstrap v5.3.3** (Sistema de Rejilla, Componentes base y Validación de Formularios)
- **Tailwind CSS** (Utilidades de Estilizado, Gradientes, Spacing y Responsive design)
