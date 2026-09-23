# Fase 0 — Descubrimiento y estrategia

Fecha: 23/09/2026. Estado: propuesta para revisión de Diego. Ningún nombre, dominio o identidad visual se considera aprobado todavía.

## Alcance y prioridades

| Prioridad | Entregable de esta fase |
| --- | --- |
| Must | Tres nombres, propuesta de dominio, público y tono, propuesta de valor, mapa del sitio, seis wireframes textuales, sistema visual inicial, KPI, riesgos y logotipo SVG. |
| Should | Foco editorial y criterios de publicación, navegación móvil y estados esenciales de los formularios. |
| Could | Variante del logotipo para fondos oscuros tras elegir marca y validar la versión principal. |
| Won't | Compra de dominio, configuración de PostgreSQL, instalación del stack, desarrollo de páginas o despliegue. Corresponden a fases posteriores. |

## Identidad y dominio

| Nombre propuesto | Idea | Dominio candidato | Observación |
| --- | --- | --- | --- |
| **Materia y Código** (recomendado) | Une ciencia física y cultura digital sin encerrar la publicación en una sola disciplina. | `materiaycodigo.com`; alternativa `materiaycodigo.es` | Es largo, pero fácil de pronunciar y escribir sin tildes en el dominio. |
| Órbita Abierta | Curiosidad y exploración; permite una voz de divulgación accesible. | `orbitaabierta.com`; alternativa `.es` | Puede sugerir una especialización espacial que el proyecto no tiene. |
| Umbral Ciencia | Explica el paso de un hallazgo científico a su impacto cotidiano. | `umbralciencia.com`; alternativa `.es` | Más académico y menos explícito sobre tecnología. |

**Decisión pendiente:** elegir nombre y comprobar disponibilidad real del dominio, redes y posibles marcas antes de registrar o publicar. La búsqueda web preliminar no constituye una comprobación registral; la herramienta de disponibilidad de dominios de Vercel no devolvió resultado en esta sesión. Para marcas con efecto en España, consultar el [buscador de la OEPM](https://www.oepm.es/es/herramientas/buscador-base-de-datos/buscador-marcas-y-nombres-comerciales/). El SVG incluido representa solamente la opción recomendada y cambiará si se elige otra.

## Público, posición y voz

**Hipótesis de público, pendientes de validar con lectores:**

1. Profesionales de 25 a 45 años que necesitan entender una novedad sin invertir una hora en leer el estudio original.
2. Estudiantes que quieren conceptos claros, fuentes primarias y contexto para seguir aprendiendo.
3. Aficionados con curiosidad que buscan separar un avance comprobado de una promesa comercial.

**Propuesta de valor:** «Ciencia y tecnología explicadas con contexto, fuentes y consecuencias reales». Cada artículo responderá qué sabemos, cómo lo sabemos, qué sigue siendo incierto y por qué le importa al lector.

**Tono:** español de España, cercano, claro y preciso; titulares informativos, cifras contextualizadas y dudas expresadas sin exagerar certezas. No se publicarán afirmaciones científicas sin fuente identificable ni textos de relleno. El editor verificará fuentes y fecha de revisión. La etiqueta «Análisis» distinguirá interpretación de noticia; las correcciones quedarán visibles en el artículo.

**Secciones editoriales iniciales:** Física y espacio; Vida y salud; Planeta y energía; Tecnología; Inteligencia artificial. Son una propuesta de cinco categorías mutuamente comprensibles; las etiquetas cruzarán categorías y los formatos (noticia, explicación, análisis) serán atributos editoriales, no categorías extra.

## Arquitectura de información

| Nivel | Ruta prevista | Función y camino principal |
| --- | --- | --- |
| Inicio | `/` | Portada editorial, destacados, últimos artículos, curiosidades, acceso a categorías y suscripción. |
| Lectura | `/articulo/[slug]` | Texto, autor, fecha, fuentes, TOC, relacionados, compartir y correcciones. |
| Exploración | `/categoria/[slug]`, `/etiqueta/[slug]`, `/autor/[slug]` | Listados paginados y contexto de categoría, etiqueta o autor. |
| Histórico | `/archivo/[yyyy]/[mm]` | Artículos publicados en un mes. |
| Búsqueda | `/busqueda` | Consulta, filtros, resultados, estado vacío y paginación. |
| Institucional | `/sobre-nosotros`, `/contacto` | Equipo, metodología, política editorial, contacto y derechos de datos. |
| Legal | `/aviso-legal`, `/politica-privacidad`, `/politica-cookies`, `/terminos-condiciones`, `/declaracion-accesibilidad` | Información editable y accesible antes de abrir el sitio. |
| Sistema | `/404`, `/rss.xml`, `/sitemap.xml`, `/robots.txt`, `/manifest.json`, favicon | Recuperación, distribución e indexación. La implementación exacta de `/404` se definirá al configurar Next.js. |
| Administración | `/admin` (provisional) | Área privada de Payload. Su URL y permisos se definirán al instalar el CMS. |

**Navegación principal:** logo → inicio; Ciencia (subcategorías física, vida y planeta); Tecnología; Inteligencia artificial; Buscar; selector de tema. En móvil, menú con las mismas rutas y botón de búsqueda visible. En el pie: información, archivo, política editorial y todas las páginas legales. Las fichas de contenido enlazarán a autor, categoría y etiquetas para facilitar recorridos naturales.

**Flujos prioritarios:** portada → artículo → artículo relacionado; búsqueda → filtro → artículo; artículo → perfil de autor → otros textos; cualquier página → newsletter → confirmación doble; contacto → consentimiento y envío → confirmación. Suscripciones y mensajes se enviarán solo cuando exista una integración real y una política de tratamiento revisada.

## Wireframes textuales

Los bloques aparecen en orden de lectura y de tabulación. «Escritorio» indica distribución; en móvil se apilan en el mismo orden semántico. Los contenidos citados son ejemplos de estructura, no artículos ya publicados.

### Inicio `/`

| Orden | Bloque | Escritorio / móvil |
| --- | --- | --- |
| 1 | Enlace «Saltar al contenido», cabecera con logo, navegación, búsqueda y tema. | Menú completo / menú desplegable accesible con búsqueda visible. |
| 2 | Hero editorial: una historia principal con categoría, titular, resumen, fecha, autor e imagen acreditada. | Dos columnas asimétricas / texto sobre imagen o imagen debajo sin tapar el titular. |
| 3 | Dos destacados secundarios. | A un lado del hero / tarjetas consecutivas. |
| 4 | Cinco accesos a categorías y bloque «Lo último» con tarjetas y paginación. | Rejilla adaptable / una columna. |
| 5 | «Una idea en dos minutos» y suscripción con expectativa de frecuencia y enlace a privacidad. | Bento editorial / bloques apilados. |
| 6 | Pie con archivo, sobre nosotros, contacto, política editorial, legal y redes. | Cuatro grupos / acordeones solo si mantienen enlaces accesibles. |

### Artículo `/articulo/[slug]`

| Orden | Bloque | Escritorio / móvil |
| --- | --- | --- |
| 1 | Migas, categoría, H1, entradilla, autor, fecha de publicación y actualización, tiempo estimado. | Columna de lectura de ~70 caracteres / ancho con márgenes de 16 px. |
| 2 | Imagen principal con pie, autoría y licencia. | Ancho de lectura o destacado / ancho adaptable. |
| 3 | Índice de contenidos, cuerpo con encabezados, citas, fórmulas, código y notas al pie. | Índice lateral / índice plegable antes del texto. |
| 4 | Fuentes consultadas, nota de metodología/incertidumbre, historial de correcciones. | Después del cuerpo en ambas vistas. |
| 5 | Compartir, ficha del autor, etiquetas, relacionados y comentarios externos si se habilitan. | Dos columnas / una columna; no cargar Giscus sin configurar sus implicaciones de privacidad. |

### Categoría `/categoria/[slug]`

| Orden | Bloque | Escritorio / móvil |
| --- | --- | --- |
| 1 | Migas, H1 y descripción de qué entra en la categoría. | Igual estructura semántica. |
| 2 | Artículo destacado de la categoría. | Tarjeta grande / tarjeta vertical. |
| 3 | Listado por fecha con formato, autor y resumen; paginación con URL navegable. | Rejilla / lista de una columna. |
| 4 | Categorías vecinas y pie. | Navegación lateral / sección posterior. |

### Autor `/autor/[slug]`

| Orden | Bloque | Escritorio / móvil |
| --- | --- | --- |
| 1 | Migas, nombre, avatar con texto alternativo, biografía, especialidad y enlaces verificados. | Ficha horizontal / vertical. |
| 2 | Transparencia editorial: credenciales relevantes, conflictos declarados y política de correcciones. | Columna auxiliar / bajo la biografía. |
| 3 | Artículos firmados, orden por fecha y paginación. | Rejilla / lista. |

### Búsqueda `/busqueda`

| Orden | Bloque | Escritorio / móvil |
| --- | --- | --- |
| 1 | H1, campo de búsqueda con etiqueta visible y botón. | Ancho moderado / ancho completo. |
| 2 | Filtros por categoría y formato; contador de resultados y control de orden. | Barra lateral / controles desplegables etiquetados. |
| 3 | Resultados con título, extracto, fecha y categoría; paginación. | Lista / lista. |
| 4 | Estados: inicio sin consulta, cargando, sin resultados con sugerencias y error recuperable. | Mensajes anunciados de forma accesible. |

### Contacto `/contacto`

| Orden | Bloque | Escritorio / móvil |
| --- | --- | --- |
| 1 | H1, motivos de contacto y tiempo de respuesta cuando exista una capacidad real de atención. | Dos columnas / una columna. |
| 2 | Nombre, correo, motivo, mensaje, aceptación informada de privacidad, validación y protección anti-spam. | Etiquetas persistentes y errores junto al campo. |
| 3 | Envío, confirmación, error recuperable y vía alternativa de contacto. | Misma secuencia. |
| 4 | Enlace claro al mecanismo para ejercer derechos de protección de datos. | Debajo del formulario. |

## Sistema visual inicial

Concepto: publicación editorial contemporánea. Las fotografías y los gráficos explican el tema; las formas geométricas sirven a la lectura. El hero puede usar un tratamiento translúcido discreto donde el contraste del texto siga siendo suficiente. El bento de portada organiza jerarquía y variedad, sin convertir todas las tarjetas en formatos distintos.

| Token orientativo | Claro | Oscuro | Uso |
| --- | --- | --- | --- |
| `color.brand` | `#1A2A6C` | `#AFC3FF` | Navegación, enlaces y titulares destacados. |
| `color.accent` | `#F39C12` | `#F6B94C` | Pequeños acentos e indicadores; no usar texto blanco sobre naranja sin comprobar contraste. |
| `color.background` | `#F8F9FA` | `#101827` | Fondo de página. |
| `color.surface` | `#FFFFFF` | `#182337` | Tarjetas y paneles. |
| `color.text` | `#212529` | `#F1F4F9` | Texto principal. |
| `color.muted` | `#4C596A` | `#BAC5D3` | Metadatos y texto secundario. |
| `color.border` | `#D7DDE5` | `#3A4A60` | Separadores y contornos. |

- Tipografía: Merriweather en titulares, Inter en cuerpo y controles, con fuentes de sistema como reserva; tamaños fluidos y `font-display: swap`.
- Escala de espacio inicial: 4, 8, 12, 16, 24, 32, 48, 64 px. Radio: 8 px en controles y 16 px en tarjetas. Sombra suave solo donde aporta separación.
- Contenedor máximo aproximado: 1200 px; lectura: 68–72 caracteres por línea. Cortes de diseño: 480, 768, 1024 y 1280 px; comprobar también 1440 px.
- Estados: hover visible, foco de alto contraste con contorno de 3 px, activo, deshabilitado, carga, error y vacío. Objetivos de interacción y teclado se comprobarán en la fase de implementación.
- Movimiento: 150–250 ms para cambios de estado; sin autoplay agresivo y con respeto a `prefers-reduced-motion`.
- El usuario podrá escoger claro/oscuro, con persistencia local y valor inicial basado en su sistema. La variante de marca sobre fondo oscuro se resolverá al implementar el selector.
- Identidad provisional: un monograma M formado por dos trazos que confluyen en un punto naranja; wordmark en dos líneas. El SVG tiene fondo transparente y un icono separado para favicon. La validación en contexto y tamaños pequeños queda para la fase visual.

## Indicadores, medición y decisiones

| KPI | Definición propuesta | Decisión que ayuda a tomar |
| --- | --- | --- |
| Lectura comprometida | Tiempo activo y profundidad de lectura, definidos en el plan de analítica; excluir rebotes accidentales. | Mejorar estructura de los artículos. |
| Suscripciones confirmadas | Altas verificadas con doble confirmación / visitas a la página de suscripción. | Ajustar propuesta y ubicación del formulario. |
| Páginas por sesión | Páginas vistas / sesiones, respetando el consentimiento cuando proceda. | Mejorar enlaces internos y relacionados. |
| Compartidos | Uso del botón de compartir; no equiparar clics con publicaciones reales. | Evaluar utilidad percibida. |
| Core Web Vitals | LCP, INP y CLS de visitas reales, por dispositivo. | Corregir problemas de carga e interacción. |

No hay línea base ni metas numéricas observadas. Tras el lanzamiento se establecerán objetivos con 30 días de datos válidos, considerando consentimiento y volumen de muestra. La elección de herramienta de analítica se pospone a la fase 5.

## Riesgos y mitigación

| Riesgo | Impacto | Mitigación prevista |
| --- | --- | --- |
| Publicar una explicación inexacta o exagerada | Alto | Enlaces a fuentes primarias, revisión editorial, fecha de actualización y registro visible de correcciones. |
| Sobrecarga editorial de 12 artículos iniciales | Alto | Planificar autores, revisión de fuentes y calendario antes del seed; evitar publicar textos de relleno. |
| Dependencias externas: newsletter, comentarios, CAPTCHA, imágenes y analítica | Medio/alto | Inventario de proveedores, consentimiento cuando corresponda, alternativas y carga condicionada a configuración real. |
| Legales incompletos o identidad del titular desconocida | Alto | Mantener datos del titular como campos pendientes y revisar con asesoría antes de publicación pública. |
| Costes y límites de hosting, base de datos y media | Medio | Elegir proveedor y presupuesto en fase 1/6; dimensionar imágenes y copias de seguridad. |
| Nombre, dominio o marca no disponibles | Medio | Validar registrador, redes y OEPM antes de cerrar identidad; conservar dos alternativas. |
| Alcance demasiado amplio para una primera versión | Alto | Priorización por fases y aceptación explícita antes de avanzar. |

## Decisiones pendientes de Diego

1. Nombre definitivo de las tres propuestas (o uno nuevo) y dominio preferido.
2. Si la primera portada tendrá mayor peso de actualidad o de artículos explicativos de larga vida útil. Se propone una mezcla con prioridad a explicaciones verificables.
3. Identidad legal/editorial del titular y responsable de contenido, cuando llegue la fase legal.
4. Validación del concepto del logotipo antes de cerrar sus variantes finales.

**Siguiente fase, solo tras aprobación:** Fase 1, configuración de Next.js 15, TypeScript estricto, Tailwind, Payload 3/PostgreSQL, controles de calidad y CI según el plan original. Las versiones concretas de paquetes se comprobarán al instalarlos.
