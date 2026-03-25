# IMAGINARIA ✦
### Experiencias narrativas colaborativas con Inteligencia Artificial

Imaginaria es una aplicación web de una sola página (HTML autocontenido, sin dependencias externas) que convierte a una IA en director de juego para partidas de rol, murder mystery, escape room, obra de teatro y fiestas temáticas. No requiere instalación: basta con abrir el archivo en un navegador.

---

## ✨ Funcionalidades

| Función | Descripción |
|---|---|
| 🎭 **6 modos de juego** | Rol, Teatro, Fiesta temática, Murder mystery, Escape room y Personalizado |
| 🤖 **Narración con IA** | Google Gemini actúa como DM/narrador con memoria de contexto |
| 🎨 **Imágenes generadas** | Portada, escenas y retrato del grupo vía Pollinations.AI |
| 🗺️ **Mapa del mundo** | Mapa ilustrado generado al inicio de la partida |
| 🎙️ **Reconocimiento de voz** | Dicta tu respuesta con el micrófono (Chrome/Edge) |
| 🎵 **Sonido ambiental** | ElevenLabs genera efectos de sonido en cada escena |
| 📜 **Historial** | Las sesiones terminadas se guardan en el navegador |
| 🧙 **Personajes guardados** | Biblioteca de personajes reutilizables entre partidas |
| 🔞 **Filtros de contenido** | Control de violencia, romance, terror y humor negro por edades |
| 📦 **Sin instalación** | Todo en un único `.html`, funciona offline (salvo las APIs) |

---

## 🚀 Inicio rápido

### Opción A — Abrir directamente
Descarga `imaginaria_voice.html` y ábrelo en **Chrome** o **Edge**.

### Opción B — GitHub Pages (recomendado)
1. Crea un repositorio público en GitHub
2. Sube el archivo renombrado como `index.html`
3. Ve a **Settings → Pages → Deploy from branch → main**
4. Tu app estará en `https://TU_USUARIO.github.io/REPO/`

### Opción C — Servidor local con FastAPI
```bash
pip install -r requirements.txt
cp imaginaria_voice.html static/imaginaria.html
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
# → http://localhost:8000
```

---

## 🔑 Claves de API

Todas las claves se introducen en la pantalla de configuración y se guardan únicamente en el navegador (`localStorage`). No se envían a ningún servidor propio.

| Servicio | Clave | Obtener |
|---|---|---|
| **Google Gemini** | `AIzaSy...` | [aistudio.google.com](https://aistudio.google.com/app/apikey) — **obligatorio** |
| **Pollinations.AI** | `pk_...` | [enter.pollinations.ai](https://enter.pollinations.ai) — gratuito, muy recomendado |
| **ElevenLabs** | `sk_...` | [elevenlabs.io](https://elevenlabs.io) — opcional, para sonido ambiental |

> **Pollinations sin clave** funciona pero tiene un límite de 1 petición cada 15 s, lo que puede provocar que las imágenes tarden o fallen. La cuenta gratuita elimina este límite y las marcas de agua.

---

## 🎮 Cómo jugar

1. **Configura** el tipo de experiencia, número de jugadores y ambientación
2. **Introduce** los nombres de los participantes (o usa personajes guardados)
3. **Ajusta** los filtros de contenido según el público
4. Pulsa **✦ Comenzar experiencia** — la IA genera la intro y la portada
5. Cada jugador por turnos describe qué hace su personaje (texto o voz 🎙)
6. La IA narra las consecuencias y avanza la historia
7. Al terminar, se genera un epílogo y puedes guardar la sesión

---

## 🎙️ Reconocimiento de voz

Disponible en **Chrome y Edge** (requiere HTTPS en producción, por eso GitHub Pages es ideal).

- Pulsa el botón **🎙 Hablar** junto al campo de respuesta
- Habla con normalidad en español — la transcripción aparece en tiempo real
- Pulsa **⏹ Parar** cuando termines; revisa el texto y pulsa Enviar

En Firefox el botón aparece desactivado con un aviso informativo.

---

## 🛠️ Tecnologías

- **Frontend:** HTML5 + CSS3 + JavaScript vanilla (sin frameworks)
- **IA narrativa:** Google Gemini 2.5 Flash (`gemini-2.5-flash`)
- **Imágenes:** [Pollinations.AI](https://pollinations.ai) — modelo Flux, sin coste
- **Voz:** Web Speech API nativa del navegador
- **Sonido:** ElevenLabs Sound Generation API
- **Persistencia:** `localStorage` del navegador
- **Servidor opcional:** Python + FastAPI + Uvicorn

---

## ⚙️ Modos de juego en detalle

| Modo | Mecánica principal | Recompensas |
|---|---|---|
| ⚔️ Partida de rol | Narrativa profunda con consecuencias | Objetos mágicos / armas |
| 🎭 Obra de teatro | Improvisación por actos | Accesorios de atrezzo |
| 🎉 Fiesta temática | Minijuegos y retos físicos reales | Puntos / premios |
| 🔍 Murder mystery | Investigación colaborativa | Pistas y evidencias |
| 🚪 Escape room | Puzzles colaborativos | Herramientas / códigos |
| ✨ Personalizado | Tú defines las reglas | Recompensas temáticas |

---

## 📋 Requisitos del navegador

| Función | Chrome | Edge | Firefox | Safari |
|---|---|---|---|---|
| App completa | ✅ | ✅ | ✅ | ✅ |
| Reconocimiento de voz | ✅ | ✅ | ❌ | ⚠️ parcial |
| HTTPS para voz | GitHub Pages / servidor con SSL | | | |

---

## 📄 Licencia

Proyecto personal de uso libre. Las APIs de terceros están sujetas a sus propios términos de servicio.
