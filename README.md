# Adivina la Micronación 🏴

Juego web progresivo (PWA) para adivinar micronaciones (entidades que se autoproclaman naciones o estados soberanos sin reconocimiento internacional) a partir de su bandera. Funciona sin conexión una vez instalada.

Incluye 25 micronaciones conocidas: Sealand, Molossia, Ladonia, Talossa, Liberland, Seborga, Freetown Christiania, Atlantium, Westarctica, Hutt River, Zaqistán, Redonda, Užupis, Elgaland-Vargaland, Kugelmugel, Araucanía y Patagonia, Isla de las Rosas, Conch (Cayo Hueso), Minerva, Saugeais, Flandrensis, Outer Baldonia, Austenasia, Imperio Aericano y los Estados Libres Ambulantes de Obsidia.

## Sobre las banderas

Las micronaciones no tienen código ISO 3166-1, por lo que no existe un emoji de bandera para ellas. Cada bandera se carga directamente desde el archivo real publicado en **Wikimedia Commons** (mediante `Special:FilePath`, que siempre apunta al archivo vigente), salvo la de Obsidia, que se toma de **MicroWiki** (micronations.wiki) porque no está publicada en Commons. Al revelar la respuesta, la app muestra un enlace hacia la página del archivo de esa bandera, donde figuran el autor y la licencia correspondiente (la mayoría son CC BY-SA).

Créditos por bandera (página del archivo de origen):

| Micronación | Archivo |
|---|---|
| Sealand | [Flag_of_Sealand.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Sealand.svg) |
| Molossia | [Flag_of_the_Republic_of_Molossia.svg](https://commons.wikimedia.org/wiki/File:Flag_of_the_Republic_of_Molossia.svg) |
| Ladonia | [Flag_of_Ladonia.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Ladonia.svg) |
| Talossa | [Flag_of_the_Kingdom_of_Talossa.svg](https://commons.wikimedia.org/wiki/File:Flag_of_the_Kingdom_of_Talossa.svg) |
| Liberland | [Flag_of_Liberland.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Liberland.svg) |
| Seborga | [Flag_of_the_Principality_of_Seborga_(current).svg](https://commons.wikimedia.org/wiki/File:Flag_of_the_Principality_of_Seborga_(current).svg) |
| Freetown Christiania | [Flag_of_Christiania.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Christiania.svg) |
| Atlantium | [Bandera_d'Atlantium.svg](https://commons.wikimedia.org/wiki/File:Bandera_d'Atlantium.svg) |
| Westarctica | [Flag_of_Westarctica.png](https://commons.wikimedia.org/wiki/File:Flag_of_Westarctica.png) |
| Hutt River | [Hutt_River_Flag.svg](https://commons.wikimedia.org/wiki/File:Hutt_River_Flag.svg) |
| Zaqistán | [Zaqistan_flag.png](https://commons.wikimedia.org/wiki/File:Zaqistan_flag.png) |
| Redonda | [Flag_of_the_Kingdom_of_Redonda.svg](https://commons.wikimedia.org/wiki/File:Flag_of_the_Kingdom_of_Redonda.svg) |
| Užupis | [Flag_of_the_Republic_of_Uzupis.gif](https://commons.wikimedia.org/wiki/File:Flag_of_the_Republic_of_Uzupis.gif) |
| Elgaland-Vargaland | [Elgaland-Vargaland_flag.png](https://commons.wikimedia.org/wiki/File:Elgaland-Vargaland_flag.png) |
| Kugelmugel | [Flag_of_Kugelmugel_in_Austria.png](https://commons.wikimedia.org/wiki/File:Flag_of_Kugelmugel_in_Austria.png) |
| Araucanía y Patagonia | [Flag_of_the_Kingdom_of_Araucanía_and_Patagonia.svg](https://commons.wikimedia.org/wiki/File:Flag_of_the_Kingdom_of_Araucan%C3%ADa_and_Patagonia.svg) |
| Isla de las Rosas | [Rose_Island_Flag.svg](https://commons.wikimedia.org/wiki/File:Rose_Island_Flag.svg) |
| Conch (Cayo Hueso) | [Flag_of_Key_West,_Florida.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Key_West,_Florida.svg) |
| Minerva | [Flag_Minerva.svg](https://commons.wikimedia.org/wiki/File:Flag_Minerva.svg) |
| Saugeais | [Flag_of_Saugeais.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Saugeais.svg) |
| Flandrensis | [Flag_of_Flandrensis.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Flandrensis.svg) |
| Outer Baldonia | [Flag_of_Outer_Baldonia.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Outer_Baldonia.svg) |
| Austenasia | [Flag_of_Austenasia.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Austenasia.svg) |
| Imperio Aericano | [Flag_of_Aerica.svg](https://commons.wikimedia.org/wiki/File:Flag_of_Aerica.svg) |
| Estados Libres Ambulantes de Obsidia | [Flag_of_the_Ambulatory_Free_States_of_Obsidia.svg (MicroWiki)](https://micronations.wiki/wiki/File:Flag_of_the_Ambulatory_Free_States_of_Obsidia.svg) |

Como las imágenes se enlazan directamente desde Wikimedia (no se guardan copias en este repositorio), la primera vez que se ve cada bandera requiere conexión a internet; después queda disponible sin conexión gracias al `service-worker.js`, que la cachea automáticamente.

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
- El documento HTML se pide siempre a la red primero (con la caché como respaldo si no hay conexión), así que los cambios en `index.html` se ven de inmediato en la próxima recarga. Si en el futuro cambias `manifest.json` o los íconos, cambia el nombre de `CACHE_NAME` en `service-worker.js` (por ejemplo, a `v3`) para forzar que esos archivos se renueven en la caché.
- Proyecto hermano: [Adivina la Bandera](https://github.com/IvanAraya/adivina-la-bandera), el mismo juego pero con banderas de países reales.
