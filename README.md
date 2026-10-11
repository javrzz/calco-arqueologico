# Calco Arqueológico

Herramienta web para convertir fotos de paramentos, fachadas, paneles con grabados y piezas arqueológicas en **dibujo vectorial a escala**, lista para CAD o para imprimir en lámina.

Funciona entera en el navegador: las fotos no se suben a ningún servidor.

## Qué hace

1. **Foto**: cargar una imagen (JPG, PNG, WebP), pegarla o sacarla con la cámara.
2. **Rectificar**: enderezar la perspectiva marcando 4 puntos de un rectángulo de medidas conocidas. La imagen queda a escala.
3. **Escala**: o bien fijar la escala con dos puntos de medida conocida (jalón, regla, escala IFRAO).
4. **Líneas**: modo *Bordes* (muros, fachadas, grabados) o *Silueta* (piezas sobre fondo liso), con controles de detalle, continuidad, suavizado y simplificación.
5. **Editar**: goma que recorta trazos, borrar líneas, marcar contorno (trazo grueso), dibujar a mano, deshacer/rehacer.
6. **Lámina**: A4, A3 o A2, escala normalizada (1:1 a 1:1000), rótulo con sitio, unidad, elemento, dibujante, fecha y número de lámina, norte y escala gráfica.
7. **Exportar**: DXF a tamaño real en mm (capas CONTORNO, DETALLE, A_MANO), PDF vectorial de la lámina, SVG, PNG a 200 ppp y proyecto `.json` para seguir otro día.

## Uso

Abrir `index.html` en el navegador, o publicarlo en cualquier hosting estático. No necesita instalación ni base de datos.

## Publicación en el servidor

El repositorio incluye una automatización (`.github/workflows/deploy.yml`) que sube la app por FTP cada vez que se guarda un cambio en la rama `main`. Para activarla, cargar en *Settings → Secrets and variables → Actions*:

| Secreto | Ejemplo |
|---|---|
| `FTP_SERVER` | `ftp.midominio.com.ar` |
| `FTP_USERNAME` | usuario FTP del hosting |
| `FTP_PASSWORD` | contraseña FTP |
| `FTP_DIR` | `public_html/calco/` |

Sin esos secretos, la automatización se saltea sin dar error.

## Limitaciones

- Las líneas salen de detección de bordes, no de IA generativa: en fotos complejas conviene limpiar con la goma.
- No exporta DWG. El DXF abre en AutoCAD, BricsCAD, QGIS, LibreCAD y Rhino.
- Las fotos HEIC del iPhone hay que pasarlas antes a JPG.

## Licencia

© 2026 Javier Diaz · [MIT](LICENSE) · [github.com/javrzz](https://github.com/javrzz)
