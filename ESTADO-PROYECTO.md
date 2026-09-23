# Estado del proyecto — Blog de ciencia, tecnología e IA

Actualizado: 23/09/2026. Fase actual: **0 entregada para revisión**. No empezar la fase 1 sin confirmación explícita de Diego.

## Fuente de verdad y alcance

- Encargo de referencia: archivo del usuario «Pegado text(2).txt», con fases 0–6 y stack Next.js 15 + Payload 3 + PostgreSQL.
- Repositorio: `DiegoMonje/blog-ciencia-y-tecnologia`, rama por defecto `main`. Estaba vacío al iniciar la fase 0.
- En la cuenta Vercel consultada solo figuraba el proyecto de módulos prefabricados; aún no se ha creado proyecto Vercel para este blog.
- Documento de fase: `docs/FASE-0.md`.
- Logotipo SVG provisional: `public/logo-materia-y-codigo.svg`.
- Icono SVG provisional: `public/favicon-materia-y-codigo.svg`.

## Decisiones y propuestas de la fase 0

- Nombre recomendado, pendiente de aprobar: **Materia y Código**. Alternativas: **Órbita Abierta** y **Umbral Ciencia**.
- Dominio candidato: `materiaycodigo.com`, con `.es` como alternativa. La disponibilidad real y el registro de marca no están verificados; no se ha comprado nada.
- Propuesta de valor: «Ciencia y tecnología explicadas con contexto, fuentes y consecuencias reales».
- Cinco categorías propuestas: Física y espacio, Vida y salud, Planeta y energía, Tecnología, Inteligencia artificial.
- Dirección visual provisional: editorial moderno, azul `#1A2A6C`, naranja `#F39C12`, fondos claros y oscuros; Merriweather + Inter; logo transparente con monograma M.
- Están definidos públicos hipotéticos, mapa del sitio, seis wireframes textuales, KPI sin metas inventadas y riesgos en `docs/FASE-0.md`.
- Must/Should/Could/Won't están documentados en el mismo archivo. No se ha iniciado la configuración del stack ni el despliegue.

## Rutas y nombres exactos propuestos

- Públicas: `/`, `/articulo/[slug]`, `/categoria/[slug]`, `/etiqueta/[slug]`, `/autor/[slug]`, `/archivo/[yyyy]/[mm]`, `/busqueda`, `/sobre-nosotros`, `/contacto`, `/404`, `/aviso-legal`, `/politica-privacidad`, `/politica-cookies`, `/terminos-condiciones`, `/declaracion-accesibilidad`.
- Generadas: `/rss.xml`, `/sitemap.xml`, `/robots.txt`, `/manifest.json`, favicon.
- Administración: `/admin` provisional, sujeto a la configuración de Payload.
- Componentes previstos, todavía no implementados: `SiteHeader`, `SiteFooter`, `FeaturedStory`, `ArticleCard`, `ArticleBody`, `TableOfContents`, `SearchForm`, `NewsletterForm`, `ThemeToggle`, `CookieConsent`.
- Campos previstos, todavía no implementados: Artículo con título, slug, extracto, cuerpo, imagen, categoría, etiquetas, autor, fecha, estado editorial, SEO, destacado, notas y relacionados; otros campos y permisos se especificarán en fase 2.
- Dependencias confirmadas a nivel de familia, no instaladas: Next.js 15, TypeScript, Payload CMS 3, PostgreSQL, Tailwind CSS; versiones concretas de paquetes y proveedores pendientes de fase 1.

## Pendientes y siguiente fase

1. Diego debe elegir nombre y aprobar o pedir cambios de la estrategia, wireframes y logo.
2. Comprobar disponibilidad de dominio y búsqueda de marca antes de fijar identidad; no confundir búsqueda web preliminar con certificación.
3. Definir prioridad editorial de noticias frente a artículos explicativos y, más adelante, los datos del titular del sitio.
4. Tras **confirmación explícita para la Fase 1**, revisar versiones y compatibilidad reales, crear estructura y scripts, validación de variables, configuración de Payload/PostgreSQL, Tailwind y CI base. Mantener este archivo actualizado al terminar esa fase.
