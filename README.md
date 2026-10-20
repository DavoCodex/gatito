# 🐱 Gatito Runner

Juego endless runner para navegador, inspirado en el dinosaurio de Chrome pero protagonizado por un gatito. Todo el juego —HTML, CSS y JavaScript— vive en **un único archivo `index.html`**, sin dependencias ni proceso de compilación.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Single File](https://img.shields.io/badge/Single%20File-index.html-a6fe3c)
![License](https://img.shields.io/badge/License-MIT-green)

<!--
  Si agregas una captura o GIF, guárdalo en el repositorio y descomenta:
  ![Vista previa de Gatito Runner](preview.gif)
-->

## 📖 Descripción

**Gatito Runner** es un juego arcade infinito en el que controlas a un gato que debe esquivar plantas y aves mientras la velocidad aumenta. La partida termina al chocar contra un obstáculo, pero el récord se guarda automáticamente para la próxima vez.

El juego incluye ciclo de día y noche, efectos de sonido generados con Web Audio y controles táctiles para móviles.

## ✨ Características

- **Un solo archivo**: todo el juego está en `index.html`; no requiere instalación ni build.
- **Dificultad progresiva**: la velocidad aumenta a medida que avanzas.
- **Obstáculos variados**: plantas desde el inicio y aves a partir de los 200 puntos.
- **Ciclo día/noche**: el escenario cambia cada 300 puntos.
- **Récord persistente**: se guarda en `localStorage` con la clave `gatitoRunnerHighScore`.
- **Sonido sin archivos**: efectos generados con la Web Audio API; se puede silenciar y la preferencia se guarda.
- **Controles táctiles**: botones de saltar y agacharse en dispositivos móviles.
- **Diseño responsive**: el canvas se adapta al tamaño de la ventana.
- **Estilo pixel art**: dibujado por completo con Canvas 2D, sin imágenes externas.

## 🎮 Controles

| Acción | Teclado | Táctil |
| --- | --- | --- |
| Saltar | `Espacio`, `↑`, `W` | Botón **SALTAR** o toque en el escenario |
| Agacharse | `↓`, `S` | Botón **AGACHARSE** |
| Empezar / reintentar | `Espacio`, `Enter` o clic | Botón **Empezar / Reintentar** |
| Silenciar | Botón 🔊 del HUD | Botón 🔊 del HUD |

> Agacharse en el aire provoca una caída rápida.

## 🛠️ Tecnologías

- **HTML5** y **Canvas 2D** para el renderizado del juego.
- **CSS3** para la interfaz, el HUD y los overlays.
- **JavaScript (vanilla)** para la lógica, la física y las colisiones.
- **Web Audio API** para los efectos de sonido.
- **localStorage** para el récord y la preferencia de silencio.

Sin frameworks, sin dependencias y sin herramientas de compilación.

## 📂 Estructura del proyecto

```text
gatito-runner/
├── index.html      # Juego completo (HTML + CSS + JS)
├── inter.ttf       # Opcional: fuente Inter para el aspecto original
├── README.md
└── LICENSE
```

> La fuente `inter.ttf` es opcional. Si no está, el juego usa `Segoe UI` o la fuente del sistema.

## 🚀 Cómo ejecutarlo

### Opción 1: abrir directamente

Descarga o clona el repositorio y abre `index.html` en tu navegador:

```bash
git clone https://github.com/DavoCodex/gatito-runner.git
```

### Opción 2: servidor local (recomendado)

```bash
# Con Python 3
python -m http.server 8000

# Con Node.js
npx serve .
```

Luego visita <http://localhost:8000>.

## 🕹️ Cómo jugar

1. Pulsa **Empezar** o `Espacio` para comenzar.
2. Salta las plantas y esquiva las aves.
3. Usa `↓` para agacharte cuando un ave pase alta.
4. La velocidad sube con la distancia: anticipa los obstáculos.
5. Al chocar, pulsa `Espacio` o **Reintentar** para volver a jugar.
6. Supera tu récord: se guarda automáticamente en el navegador.

## ⚙️ Personalización

Todo se edita dentro de `index.html`.

### Colores

Los colores principales están en las variables CSS `:root`:

```css
:root {
  --bg: #141414;
  --accent: #a6fe3c;  /* color del gatito y los detalles */
  --text: #e8e8e8;
}
```

El color del gato también se define en JavaScript:

```js
const CAT = "#a6fe3c";
const CAT_SHADE = "#86d627";
const CAT_LINE = "#4f8b0e";
```

### Dificultad y física

| Constante / valor | Descripción |
| --- | --- |
| `GRAVITY` | Gravedad aplicada al salto (`0.62`). |
| `JUMP_VELOCITY` | Impulso del salto (`-12.6`). |
| `speed` | Velocidad inicial `5.2`, máximo `13.5`. |
| `distance / 4200` | Ritmo al que aumenta la velocidad. |
| `score > 200` | Puntos a partir de los cuales aparecen aves. |
| `score / 300` | Intervalo del ciclo día/noche. |
| `spawnTimer` | Frecuencia de aparición de obstáculos. |

### Sonido

Los efectos se generan en la función `beep(frecuencia, duración, tipo, volumen, frecuenciaFinal)`. Puedes ajustar los sonidos de salto, punto y choque en el objeto `sfx`.

## 🌐 Compatibilidad

Funciona en versiones modernas de Chrome, Edge, Firefox y Safari. Requiere soporte de Canvas 2D, Web Audio API y `localStorage`.

## 🤝 Contribuciones

1. Haz un fork del repositorio.
2. Crea una rama:
   ```bash
   git checkout -b feature/mi-mejora
   ```
3. Haz tus cambios y confirma:
   ```bash
   git commit -m "feat: agrega mi mejora"
   ```
4. Sube la rama:
   ```bash
   git push origin feature/mi-mejora
   ```
5. Abre un Pull Request.

Si encuentras un bug, abre un issue indicando qué ocurrió y cómo reproducirlo.

## 🗺️ Ideas para ampliar

- Más obstáculos y patrones.
- Power-ups (escudo, imán de puntos, cámara lenta).
- Tabla de récords con nombre.
- Modo contrarreloj.
- Música de fondo.

## 📄 Licencia

Distribuido bajo la licencia **MIT**. Si el repositorio aún no incluye un archivo `LICENSE`, puedes añadir el texto estándar de MIT con tu nombre y el año.

## 👤 Autor

**Tu Nombre**

- GitHub: [@DavoCodex](https://github.com/DavoCodex)

---

Hecho con ❤️, Canvas y JavaScript. ¡Que empiece la carrera! 🐾
