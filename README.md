# Adivina la Micronación 🏴

Juego web progresivo (PWA) para adivinar micronaciones (entidades que se autoproclaman naciones o estados soberanos sin reconocimiento internacional) a partir de su bandera. Funciona sin conexión una vez instalada.

Incluye 15 micronaciones conocidas: Sealand, Molossia, Ladonia, Talossa, Liberland, Seborga, Freetown Christiania, Atlantium, Westarctica, Hutt River, Zaqistán, Redonda, Užupis, Elgaland-Vargaland y Kugelmugel.

## Sobre las banderas

Las micronaciones no tienen código ISO 3166-1, por lo que no existe un emoji de bandera para ellas. Cada bandera se dibuja en SVG siguiendo su diseño real (colores y elementos principales), a partir de la documentación disponible en fuentes como Wikipedia y la Vexillology Wiki. Son representaciones simplificadas con fines de juego, no reproducciones heráldicas exactas.

## Estructura del proyecto

```
.
├── index.html          # Aplicación principal
├── manifest.json        # Manifiesto de la PWA
├── service-worker.js    # Caché offline
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

## Publicar en GitHub Pages

1. En GitHub, entra al repositorio → **Settings** → **Pages**.
2. En **Build and deployment**, selecciona **GitHub Actions** (el workflow en `.github/workflows/deploy.yml` ya está listo) o **Deploy from a branch** con la rama `main` y la carpeta `/ (root)`.
3. Espera uno o dos minutos. La app quedará disponible en:

   ```
   https://TU_USUARIO.github.io/TU_REPOSITORIO/
   ```

## Verificar que funciona como PWA

- Abre la URL publicada desde un navegador compatible (Chrome, Edge, Safari en iOS/Android).
- Debería aparecer la opción "Instalar aplicación" o "Agregar a pantalla de inicio".
- Una vez instalada, la app se abre en modo standalone (sin barra de navegador) y funciona sin conexión gracias al `service-worker.js`.

## Notas

- Todas las rutas (`manifest.json`, `service-worker.js`, íconos) usan rutas relativas (`./`) para funcionar correctamente en la subruta que asigna GitHub Pages (`usuario.github.io/repositorio/`).
- Si actualizas `index.html` en el futuro, cambia el nombre de `CACHE_NAME` en `service-worker.js` (por ejemplo, a `v2`) para forzar que los usuarios reciban la versión nueva en lugar de la cacheada.
- Proyecto hermano: [Adivina la Bandera](https://github.com/IvanAraya/adivina-la-bandera), el mismo juego pero con banderas de países reales.
