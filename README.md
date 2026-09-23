# Cotizador Seguridad PRO

Cotizador de proyectos de seguridad electrónica (control de acceso, CCTV, alarma, portería virtual y monitoreo).
Calcula equipos, materiales por reglas técnicas, tubería y accesorios, mano de obra, mantenimiento, financiación,
P&L del servicio de monitoreo y genera la propuesta comercial en PDF.

Desarrollado por **Ing. Edisson Macías Quevedo**.

## Instalar en el escritorio

1. Abra la dirección de la app en **Chrome o Edge**.
2. Pulse **Instalar en el escritorio** (pantalla Proyectos) o el ícono de instalar en la barra de direcciones.
3. Queda como un programa más, con ícono propio, y funciona sin internet.

## Dónde quedan sus datos

La app guarda en dos lugares:

| Lugar | Qué pasa si borra el historial del navegador |
|---|---|
| Navegador (IndexedDB) | Se puede perder |
| **Carpeta de datos** que usted elige | **No se pierde nada** |

La primera vez, en **Proyectos → Elegir carpeta de datos**, seleccione una carpeta de su computador
(recomendado: dentro de OneDrive o Google Drive para tener copia en la nube). La app escribe:

```
Su carpeta/
├── configuracion.json          marca, textos, catálogo, materiales y reglas
├── proyectos/                  un archivo por cotización, con su historial de versiones
│   └── COT-2026-001__EDIFICIO_EL_MIRADOR__p8x2k1.json
├── respaldos/                  copia completa diaria (últimos 30 días)
└── papelera/                   proyectos eliminados
```

Si borra el historial o cambia de computador: abra la app, pulse **Elegir carpeta de datos**,
seleccione la misma carpeta y pulse **Cargar datos de la carpeta**.

## Publicar en GitHub Pages

1. Cree un repositorio en GitHub (por ejemplo `cotizador-pro`).
2. Suba estos archivos: `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `.nojekyll`, `README.md`.
3. En el repositorio: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save**.
4. En uno o dos minutos la app queda en `https://SU-USUARIO.github.io/cotizador-pro/`.

Para actualizar la app, reemplace `index.html` en el repositorio. Si cambia `sw.js`, suba también el número de `CACHE`.

> **Importante:** en una cuenta gratuita, GitHub Pages solo publica repositorios **públicos**.
> El `index.html` incluye el catálogo con **costos de compra** y la portada de la empresa.
> Cualquiera con el enlace podría verlos. Si eso es un problema, use un repositorio privado con GitHub Pro,
> o publique una versión sin costos y cargue sus precios desde su carpeta de datos.

## Atajos

- **Ctrl + S**: guarda una versión de la cotización en el historial.
- Exportar el PDF o cambiar el estado comercial guarda una versión automática.
