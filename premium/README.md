# Finger Frame Studio — Premium V1

Finger Frame Studio convierte el gesto de formar un rectángulo con ambas manos en una pantalla viva y móvil.

## Concepto

La herramienta separa dos cosas que antes estaban acopladas:

1. **Gesture source** — la persona que hace el gesto con las manos.
2. **Frame content** — el contenido que aparece dentro del rectángulo detectado.

Esto permite usar el finger frame como una superficie creativa general, no solo como una ventana hacia una versión AI del mismo vídeo.

## Modos de entrada

- Live Camera
- Uploaded Gesture Video

## Contenido dentro del frame

- Uploaded Video
- Uploaded Image
- Screen Share
- Direct media URL (requiere CORS compatible para exportación)

## Tracking

- MediaPipe Hand Landmarker
- 2 manos
- tracking local en navegador
- ordenación geométrica de cuatro puntos
- smoothing temporal
- hold de frames cortos cuando se pierde detección
- fade de presencia

## Look

- frame outline animado
- color editable
- border width
- corner dots
- corner size
- glow
- content opacity
- cover / contain / stretch

## Playback

Tanto el vídeo de gesto como el vídeo proyectado tienen controles básicos de reproducción.

## Output

- Preview Clean
- Record 30 FPS / 60 FPS
- WebM download
- PNG screenshot
- Save / Restore settings

La grabación usa `canvas.captureStream()` y por tanto captura el resultado compuesto, no el panel del editor.

## Privacidad

MediaPipe se ejecuta localmente. Los medios locales permanecen en el navegador salvo que el usuario elija explícitamente un backend remoto en futuras fases.

## Roadmap

### V1 — Media Window
- live camera
- uploaded gesture video
- uploaded video/image
- screen share
- direct media URL
- record/export

### V2 — Stream adapters
- HLS/DASH adapter
- WebRTC remote streams
- second camera/device

### V3 — Live AI adapters
- Decart Lucy
- fal Lucy
- fal FLUX realtime

### V4 — Premium authoring
- trigger rules
- gesture open/close transitions
- content playlists
- cue points
- timeline
- frame presets
- branded overlays
- final standalone viewer/embed

## Product principle

The AI layer is optional. The core product must remain useful with no API key, no generation cost, and no waiting time.
