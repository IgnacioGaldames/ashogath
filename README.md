# Logia Ashogath

Sitio editorial en español para el círculo de escritura Logia Ashogath. La portada conecta el fanzine, cada una de sus obras y autores, el blog, el podcast y la convocatoria.

## Desarrollo

| Herramienta | Versión |
|---|---|
| Jekyll | 4.3 |
| jekyll-seo-tag | Sí |
| jekyll-sitemap | Sí |
| jekyll-feed | Sí |

```powershell
bundle install
bundle exec jekyll serve
$env:JEKYLL_ENV="production"; bundle exec jekyll build --strict_front_matter
```

## Editar el contenido

El contenido editorial vive en colecciones Markdown con front matter:

| Contenido | Carpeta | Ruta pública |
|---|---|---|
| Autores | `_authors/` | `/autores/` |
| Cuentos, poemas y ensayos | `_works/` | `/obras/` |
| Ediciones del fanzine | `_issues/` | `/fanzines/` |
| Temas y géneros | `_topics/` | `/temas/` |
| Episodios | `_podcast/` | `/podcast/` |
| Entradas del blog | `_posts/` | `/blog/` |

Pages CMS lee la configuración de [`.pages.yml`](.pages.yml). Para editar desde el navegador, abre [pagescms.org](https://pagescms.org), inicia sesión con GitHub y autoriza el acceso al repositorio `IgnacioGaldames/ashogath`. El CMS guarda los cambios como commits en Git; no necesita credenciales OAuth propias ni un backend adicional. La autorización de GitHub y el acceso al repositorio son requisitos de la cuenta que lo active.

La convocatoria se controla en [`_data/convocatoria.yml`](_data/convocatoria.yml). Usa `status: open` solo cuando estén confirmadas las bases y el canal de envío; completa tema, plazo y correo/formulario únicamente con datos oficiales. El Instagram de la Logia es un canal de consultas, no un medio de envío. La página puede editarse desde Pages CMS.

Para publicar una obra:

1. Crea un perfil en `_authors/` y copia su `slug` en el campo `author` de cada obra.
2. Crea o elige un tema en `_topics/`; usa su `slug` en `tags`.
3. Añade el texto y sus metadatos a `_works/`, con `issue`, `issue_name`, tipo, resumen y páginas impresas.
4. Añade la edición a `_issues/` y guarda su PDF en `assets/downloads/`; usa la ruta pública `/assets/downloads/nombre.pdf`.
5. Si se conocen, completa enlaces personales o redes y un retrato autorizado. No inventes biografías, fechas, bases ni enlaces.

Cada obra enlaza a su autor y edición; cada perfil reúne las obras publicadas. El cuerpo de las obras se conserva en Markdown, con párrafos y diálogos legibles en el sitio.

## Estructura

```text
ashogath/
├── _authors/            # Perfiles
├── _data/               # Navegación y convocatoria
├── _issues/             # Ediciones
├── _podcast/            # Episodios
├── _posts/              # Blog (YYYY-MM-DD-titulo.md)
├── _topics/             # Temas y géneros
├── _works/              # Cuentos, poemas y ensayos
├── assets/
│   ├── downloads/        # PDFs descargables
│   ├── images/          # Marca y retratos autorizados
│   └── css/style.scss   # Sistema visual
├── _includes/            # Metadatos y datos estructurados
├── _layouts/             # Plantillas de páginas
├── .pages.yml            # Editor visual conectado a GitHub
└── index.md              # Página de inicio
```

El sitio usa `baseurl: /ashogath` y `url: https://ignaciogaldames.com`. Mantén `relative_url` en enlaces internos. Los metadatos sociales, canonical, feed y sitemap se generan con los plugins Jekyll existentes.

## Publicación

GitHub Pages publica desde `master` en la raíz del repositorio. El workflow del repositorio compila el sitio en los pull requests y en los pushes a `master`. Para validar localmente, usa `bundle exec jekyll build --strict_front_matter`.
