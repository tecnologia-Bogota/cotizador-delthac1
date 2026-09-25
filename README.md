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

- **Guardar** (arriba, siempre visible) o **Ctrl + S**: guarda la cotización y deja una versión en el historial. Si no hay cambios, no duplica versiones.
- Las versiones se pueden comparar, restaurar, copiar como proyecto nuevo o borrar.
- Exportar el PDF o cambiar el estado comercial guarda una versión automática.

## Seguimiento comercial y orden de trabajo (v6)

- **Agenda** en Proyectos: gestiones vencidas, de hoy y de los próximos 7 días, con botón de WhatsApp y reprogramar +3/+7 días.
- **Registrar gestión** en cada proyecto (queda en su bitácora) y **motivo de pérdida** para ver por qué se pierden las cotizaciones.
- **Orden de trabajo** (PDF y JSON) cuando la cotización pasa a *Aprobada*: equipos, materiales para compras, canalización, actividades, lista de verificación y firmas.
- **Monitoreo**: tarifas fijas por modalidad (virtual $150.000 / híbrido $120.000 por apartamento) editables en Empresa y marca.
- **Licencias Hipcam automáticas**: 1 licencia única por proyecto (incluye 1 terminal de 8") + 1 adicional por cada terminal de 8" extra.
- **Plan de pagos** en la propuesta: tabla de amortización de 24 meses y cuotas de 3 meses.

## Tipo de cotización (v11)

Al crear un proyecto la app pregunta:

- **Con servicio de monitoreo**: portería virtual o híbrido, tarifa mensual por apartamento, P&L del servicio, esquema de ahorro y financiación con IVA preferencial.
- **Venta directa (suministro e instalación)**: cotización más directa para su propia empresa. Oculta la pestaña Monitoreo y quita de la propuesta todo lo relacionado (tarifa mensual, ahorro, P&L). Usa textos propios (editables en Empresa y marca → Textos para venta directa) con condiciones de pago 50 % anticipo / 50 % contra entrega.

El tipo se puede cambiar en cualquier momento desde el proyecto; los equipos y cantidades se conservan.

## IVA según el tipo de cotización (v12)

| Tipo | IVA que ve el cliente | Financiación |
|---|---|---|
| Con monitoreo | 1,9 % preferencial (base gravable 10 % × 19 %) sobre la implementación, las cuotas y el servicio mensual | Sí (24 y 3 meses) |
| Venta directa | 19 % pleno sobre el total | No |

## Consecutivo y borrado de proyectos (v14)

- El consecutivo (por ejemplo `COT-2026-004`) **sigue a la cotización más alta que exista** en el año. Si tiene de la 001 a la 004 y borra la 004, la próxima vuelve a ser la 004. Si borra una intermedia (la 002), la próxima sigue siendo la siguiente a la más alta.
- En Empresa y marca se edita el prefijo y, si hace falta, un número desde el cual continuar (para seguir una numeración anterior).
- Se pueden borrar todos los proyectos. Si la carpeta de datos está vinculada, lo borrado queda en `papelera/`.
