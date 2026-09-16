# pacientitos.tortugapower.com

Sitio web de Pacientitos, la app de registro fotográfico clínico (iOS/iPadOS).
Se publica con GitHub Pages desde la rama `main`.

Repositorio de la app: [PatientJournal-iOS](https://github.com/TortugaPower/PatientJournal-iOS).

## Estructura

| Ruta | Descripción |
|---|---|
| `index.html` | Landing page — también es la **Support URL** de App Store Connect |
| `privacidad.md` | Política de Privacidad → `/privacidad/` |
| `privacy.md` | Privacy Policy (inglés) → `/privacy/` |
| `_layouts/legal.html` | Plantilla de las páginas legales |

Se publican las dos versiones del aviso de privacidad porque el idioma principal
de la ficha en App Store Connect todavía no está decidido. La URL que se declare
en App Store Connect debe coincidir con ese idioma.

## App Store Connect

Ambos campos son **obligatorios** para poder enviar la app a revisión
(directriz 5.1.1(i) de las App Review Guidelines):

| Campo | Valor |
|---|---|
| Privacy Policy URL | `https://pacientitos.tortugapower.com/privacidad/` (o `/privacy/`) |
| Support URL | `https://pacientitos.tortugapower.com/` |

La misma directriz exige además un enlace a la política **dentro de la app**, en
un lugar accesible. En Pacientitos vive en la pantalla de diagnóstico
(`StorageDiagnosticsView`, el engranaje de la barra de navegación).

## DNS

`pacientitos.tortugapower.com` es un registro `CNAME` que apunta a
`tortugapower.github.io.`, en la zona de **Route 53** de `tortugapower.com`
(`Z07949021XLLEGLU7HW6H`, perfil `bookplayer` del AWS CLI) — igual que
`facturita.tortugapower.com`.

> Nota: el README de `facturita.github.io` dice que la zona está en Google Cloud
> DNS. Es incorrecto; `tortugapower.com` se gestiona en Route 53.

## Sin `.well-known`

A diferencia de `facturita.github.io`, este sitio no necesita archivos de
asociación de dominio: la app no usa passkeys, Associated Domains ni universal
links. Por eso `_config.yml` no lleva el `include` de `.well-known`.
