# 💀 QR Prank - Sistema de "Robo" Simulado

Una broma interactiva diseñada para aparentar ser un sistema de hackeo que "extrae datos" del dispositivo del usuario, culminando con una alarma dramática y la revelación de que es solo una broma educativa.

## 🌐 Demo en Vivo
**[https://miguelin04.github.io/Qr_/](https://miguelin04.github.io/Qr_/)**

## 📱 ¿Cómo funciona?

1. **El usuario escanea un código QR** que lo dirige a la página
2. **Ve una interfaz tipo terminal** que simula estar "hackeando" su dispositivo
3. **Mensajes de extracción de archivos** aparecen progresivamente
4. **Culmina con una alarma terrorífica** con efectos visuales y sonoros
5. **Se revela que es una broma** con mensaje educativo

---

## 🎨 Características Principales

### 🖥️ **Interfaz Terminal Realista**
- **Diseño tipo CRT**: Efectos de scanlines y viñeta
- **Lluvia de bits**: Animación de matrix con caracteres binarios
- **Colores terminales**: Paleta verde apagada tipo hacker
- **Tipografía monospace**: IBM Plex Mono para autenticidad

### 🔊 **Sistema de Audio Interactivo**
- **Activación automática**: Se activa al primer toque/scroll
- **Sonidos de typing**: Cada carácter genera un click realista
- **Audio dinámico al scroll**: Frecuencia varía según velocidad
- **Alarma súper fuerte**: Sirena de emergencia + beeps intensos
- **Vibración en móviles**: Feedback háptico durante el susto

### 📱 **Optimizado para Móviles**
- **Scroll "trabado"**: Se siente pegajoso pero funcional
- **Resistencia táctil**: Efectos visuales al deslizar
- **Responsive design**: Se adapta a cualquier pantalla
- **Touch feedback**: Sonidos específicos para interacciones táctiles

### 💥 **Efecto de Susto Final**
- **Flash blanco intenso**: Pantalla completa por 1.2 segundos
- **Texto rojo parpadeante**: "💀 SISTEMA COMPROMETIDO 💀"
- **Shake de pantalla**: Animación de temblor dramática
- **Múltiples alarmas**: Thump grave + sirenas + beeps agudos
- **Vibración intensa**: Patrón de vibración extendido

---

## 🛠️ Tecnologías Utilizadas

### **Frontend**
- **HTML5**: Estructura semántica con ARIA
- **CSS3**: Animaciones, gradientes y efectos visuales
- **JavaScript ES6+**: Lógica interactiva y control de audio

### **Audio**
- **Web Audio API**: Generación de sonidos sintéticos
- **AudioContext**: Control completo del audio
- **Oscillators**: Creación de frecuencias específicas

### **Animaciones**
- **Canvas API**: Lluvia de bits animada
- **CSS Animations**: Efectos de shake y parpadeo  
- **Web Animations API**: Control programático de movimientos

---

## 📁 Estructura del Código

### **🎨 Estilos CSS**
```css
/* Variables de colores tipo terminal */
:root {
  --bg1: #030305;      /* Fondo oscuro principal */
  --bg2: #071018;      /* Fondo degradado */
  --text: #d6dde2;     /* Texto principal */
  --accent: #8fa68f;   /* Acentos verdes apagados */
}

/* Efectos CRT realistas */
.scanlines { /* Líneas de barrido */ }
.vignette { /* Oscurecimiento en bordes */ }
```

### **🎵 Sistema de Audio**
```javascript
// Activación automática ultra agresiva
function unlockAudio() {
  if (AudioCtx.state === 'suspended') {
    AudioCtx.resume();
  }
  // Reproduce sonido ultra silencioso para despertar audio
}

// Sonidos dinámicos al scroll
window.addEventListener('scroll', () => {
  const freq = 300 + Math.min(scrollDistance * 10, 800);
  const vol = Math.min(0.03 + (scrollDistance * 0.001), 0.08);
  // Crea oscilador con parámetros dinámicos
});
```

### **💻 Simulación de Terminal**
```javascript
// Mensajes progresivos de "hackeo"
const messages = [
  "Escaneando dispositivo...",
  "Obteniendo identificadores (ID)...",
  "Analizando configuraciones de red...",
  "Extrayendo archivos (lista)...",
  "Conectando a endpoint remoto...",
  "Finalizando transferencia..."
];

// Efecto de typing realista
function typeMessage(msg, callback) {
  // Simula escribir carácter por carácter con delays aleatorios
  // Reproduce sonido de tecla en cada carácter
}
```

### **🚨 Alarma Final**
```javascript
function playAlarmSiren() {
  // Sirena tipo emergencia con frequency sweep
  createSirenTone(now, 0.4, 300, 1200, 0.3);    // Subida
  createSirenTone(now + 0.4, 0.4, 1200, 300, 0.3); // Bajada
  
  // Beeps de alarma adicionales a 2000Hz
  // Volumen máximo (0.35) para máximo impacto
}
```

---

## 🎯 Flujo de Usuario

### **1. Carga Inicial (0-2s)**
- Se inicializa el canvas con lluvia de bits
- Se muestran efectos CRT (scanlines/vignette)  
- Comienza la secuencia de "hackeo"

### **2. Fase de Extracción (2-15s)**
- Mensajes progressivos de scanning
- Sonidos de typing realistas
- Archivos falsos "extraídos"
- Barra de progreso aumentando

### **3. Alarma Final (15-17s)**
- Flash blanco intenso
- Texto rojo parpadeante con calaveras
- Sirenas y alarmas múltiples
- Shake de pantalla dramático
- Vibración en dispositivos móviles

### **4. Revelación (17s+)**
- Se muestra el mensaje: "🎉 Era broma"
- Texto educativo sobre seguridad
- Controles para reiniciar

---

## 🎮 Controles Disponibles

- **Reiniciar**: Vuelve a ejecutar toda la secuencia
- **Revelar rápido**: Salta directamente al final
- **ESC**: Atajo de teclado para reiniciar
- **Espacio**: Atajo para revelar resultado

---

## 🔧 Características Técnicas

### **🎵 Audio**
- **Activación automática**: Múltiples estrategias para superar restricciones del navegador
- **12 eventos de activación**: touchstart, scroll, click, mousemove, etc.
- **Botón invisible**: Auto-click para forzar interacción
- **Sonidos sintéticos**: Generados con Web Audio API
- **Control de frecuencia**: Evita saturación de sonidos

### **📱 Móviles**
- **Scroll trabado**: `-webkit-overflow-scrolling: auto`
- **Resistencia visual**: Transform basado en velocidad de toque
- **Vibración contextual**: navigator.vibrate() con patrones
- **Audio optimizado**: Volúmenes aumentados para móviles

### **🎨 Efectos Visuales**
- **Canvas animado**: 60fps con requestAnimationFrame
- **Ruido generativo**: ImageData con pixeles aleatorios
- **Responsive**: Breakpoints en 900px
- **Transiciones suaves**: cubic-bezier easing

---

## 📖 Propósito Educativo

### **🎯 Objetivo**
Enseñar sobre seguridad digital de manera memorable:
- **No escanear QR desconocidos**
- **Desconfiar de sitios que piden permisos**
- **Entender técnicas de social engineering**

### **⚠️ Advertencia**
- **No recopila datos reales**
- **Es completamente inofensivo**
- **Solo efectos visuales y sonoros**
- **Código abierto y auditable**

---

## 🚀 Instalación y Uso

### **Método 1: GitHub Pages (Recomendado)**
```
https://miguelin04.github.io/Qr_/
```

### **Método 2: Local**
```bash
git clone https://github.com/miguelin04/Qr_.git
cd Qr_
# Abrir index.html en navegador
```

### **Método 3: Servidor Local**
```bash
python -m http.server 8000
# Navegar a http://localhost:8000
```

---

## 🎨 Personalización

### **Colores**
Modificar variables CSS en `:root`:
```css
--bg1: #030305;      /* Fondo principal */
--text: #d6dde2;     /* Color de texto */
--accent: #8fa68f;   /* Acentos */
--danger: #7b2b2b;   /* Alertas */
```

### **Mensajes**
Editar array `messages` en JavaScript:
```javascript
const messages = [
  "Tu mensaje personalizado 1...",
  "Tu mensaje personalizado 2...",
  // ...
];
```

### **Archivos Falsos**
Modificar array `fakeFiles`:
```javascript
const fakeFiles = [
  "tu_archivo.pdf",
  "documentos/secretos.docx",
  // ...
];
```

---

## 🛡️ Consideraciones de Seguridad

### **✅ Seguro**
- No accede a archivos reales
- No envía datos a servidores
- No usa APIs peligrosas
- Código completamente local

### **⚠️ Responsabilidad**
- Usar solo con fines educativos
- Obtener consentimiento antes de usar
- No usar para asustar a personas sensibles
- Explicar que es una broma después

---

## 🤝 Contribuciones

### **Cómo Contribuir**
1. Fork del repositorio
2. Crear rama feature: `git checkout -b nueva-caracteristica`
3. Commit cambios: `git commit -m 'Añadir nueva característica'`
4. Push a la rama: `git push origin nueva-caracteristica`
5. Abrir Pull Request

### **Ideas para Contribuir**
- Más efectos visuales
- Sonidos adicionales
- Traducciones a otros idiomas
- Mejoras de accesibilidad
- Optimizaciones de rendimiento

---

## 📝 Licencia

Este proyecto está bajo la Licencia MIT. Ver `LICENSE` para más detalles.

---

## 👨‍💻 Autor

**Miguel Luna**
- GitHub: [@miguelin04](https://github.com/miguelin04)
- Email: miguel.a.luna@unl.edu.ec

---

## 🙏 Agradecimientos

- Inspirado en simuladores de hackeo de películas
- Efectos CRT basados en monitores vintage
- Web Audio API para sonidos realistas
- Canvas API para animaciones fluidas

---

## 📊 Estadísticas

- **Líneas de código**: ~650
- **Tamaño**: ~25KB minificado
- **Compatibilidad**: Chrome 60+, Firefox 55+, Safari 11+
- **Rendimiento**: 60fps en dispositivos modernos

---

*Creado para el primer ciclo universitario como demostración de tecnologías web y concienciación sobre seguridad digital.*
