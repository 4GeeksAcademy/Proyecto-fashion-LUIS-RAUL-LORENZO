# Tareas del catálogo — MAISON ÉTOILE

## Uso del documento

Este documento desglosa la implementación definida en [specs.md](specs.md) y organizada en [plan.md](plan.md). Las tareas se realizarán en el orden indicado, respetando sus dependencias.

Marcar una casilla con `[x]` únicamente cuando se cumpla su criterio de comprobación. La creación de este documento no significa que las tareas estén ejecutadas ni autoriza commits, push, merges o cambios fuera del catálogo.

## Estado de la implementación

El catálogo está creado en [catalog.html](../catalog.html), en la rama `feature/catalogue-products`. Se han comprobado mediante análisis del HTML los 20 productos y placeholders, la estructura principal, los identificadores únicos, los filtros etiquetados, el JSON-LD y la igualdad del navbar y footer con la referencia salvo las rutas relativas. El editor no detecta errores en la página.

Las casillas pendientes incluyen comprobaciones que todavía necesitan navegador, aunque su código ya esté implementado. Se intentó la revisión con Playwright, pero Chromium no pudo arrancar por la ausencia de `libatk-1.0.so.0` en el contenedor. No se ha confirmado la carga de recursos externos, la apariencia, los desbordamientos, la navegación por teclado ni el funcionamiento del menú en navegador. La comprobación responsive deberá incluir los anchos de 360, 640, 768, 1024 y 1440 px.

Los destinos `index.html` y `product.html` todavía no existen; sus rutas se conservan como dependencias del equipo. Los destinos `catalog.html` y `cart.html` sí existen. No se han creado páginas ajenas, cambiado de rama ni realizado commits, push o merges.

## 1. Preparación

- [x] **T001 — Confirmar los requisitos aprobados.** Revisar [Agents.md](../Agents.md), [Context.md](../Context.md), [Design.md](../Design.md), la especificación y el plan del catálogo. **Comprobación:** el alcance está claro: catálogo estático en español, filtros visuales, al menos 20 productos y placeholders, sin funcionalidades adicionales.
- [x] **T002 — Comprobar la rama y el estado de trabajo.** Verificar que la rama activa es independiente de `main` e identificar los cambios existentes sin sobrescribirlos. **Comprobación:** la implementación puede continuar en una rama adecuada sin alterar trabajo ajeno; cualquier cambio de rama necesario se coordina antes de editar.
- [x] **T003 — Identificar las dependencias compartidas.** Localizar la cabecera, el navbar, el footer y sus recursos visuales en [docs/reference.html](../docs/reference.html), junto con las rutas previstas a las otras páginas. **Comprobación:** se conocen los bloques que se copiarán y se registran los destinos todavía no disponibles, sin crear páginas ajenas.

## 2. Estructura y componentes compartidos

- [ ] **T004 — Crear la base de la página.** Preparar `catalog.html` en la raíz con HTML5, `lang="es"`, codificación UTF-8 y metadato viewport. **Comprobación:** el documento abre correctamente y utiliza únicamente las tecnologías aprobadas.
- [ ] **T005 — Incorporar los recursos de diseño.** Reutilizar la configuración de Tailwind y los recursos de tipografía necesarios para reproducir la referencia, con CSS adicional solo si es necesario. **Comprobación:** están disponibles Playfair Display, Inter y la paleta aprobada, sin frameworks adicionales.
- [x] **T006 — Integrar la cabecera y el navbar.** Copiar íntegramente el bloque correspondiente de la referencia, ajustando solo las rutas relativas necesarias para la raíz. **Comprobación:** estructura, textos, clases, atributos de accesibilidad, estilos y comportamiento responsive permanecen intactos.
- [x] **T007 — Integrar el footer.** Copiar el bloque completo de la referencia y ajustar únicamente sus rutas relativas cuando corresponda. **Comprobación:** se conservan todos los apartados, textos, clases, estilos y atributos originales.
- [ ] **T008 — Definir el contenido principal.** Incorporar un único `main` con `id="contenido"` y un único encabezado de nivel uno «Catálogo». Mantener el enlace de salto de la referencia. **Comprobación:** el enlace «Saltar al contenido» conduce al contenido principal y la jerarquía de encabezados es coherente.

## 3. Barra de filtros visuales

- [x] **T009 — Situar la barra de filtros.** Reservar su espacio dentro del contenido principal, después del título y antes del listado, sin barra lateral. **Comprobación:** tanto el orden del documento como el visual sitúan los filtros antes de los productos.
- [ ] **T010 — Incorporar el selector de categoría.** Usar un `select` nativo con etiqueta visible «Categoría», asociación `for`/`id` y las opciones Todas las categorías, Calzado, Camisas, Pantalones y Accesorios. **Comprobación:** la opción general está seleccionada inicialmente y todas las opciones se pueden elegir con teclado.
- [ ] **T011 — Incorporar el selector de talla.** Usar un `select` nativo con etiqueta visible «Talla» y asociación `for`/`id`. Incluir Todas las tallas, XS–XL, tallas de calzado 36–42 y Talla única; los sistemas de tallaje pueden organizarse con `optgroup`. **Comprobación:** la opción general está seleccionada inicialmente y las opciones de ropa y calzado son distinguibles.
- [x] **T012 — Mantener el alcance visual de los controles.** Permitir seleccionar opciones sin filtrar productos, enviar formularios ni añadir un botón «Aplicar». **Comprobación:** cambiar categoría o talla no modifica el listado ni provoca navegación o recarga, y la interfaz no promete actualizar resultados.

## 4. Productos y tarjetas

- [x] **T013 — Preparar el contenido de referencia.** Definir al menos 20 productos con nombre en español y precio en euros; se recomienda representar las cuatro categorías. **Comprobación:** existen 20 o más entradas completas y los precios siguen el formato español, por ejemplo, «59,90 €».
- [ ] **T014 — Establecer el patrón de tarjeta.** Definir una composición uniforme con placeholder, nombre, precio y enlace identificable a `product.html`. **Comprobación:** todos los datos se leen sin solapamientos y no se inventan rutas de detalle individuales.
- [x] **T015 — Construir el placeholder.** Utilizar HTML y estilos con colores del diseño y proporción estable, preferiblemente 3:4, sin fotografías ni servicios externos de imágenes. **Comprobación:** no hay imágenes rotas ni solicitudes a servicios de imágenes; el placeholder decorativo lleva `aria-hidden="true"` cuando el nombre visible ya identifica el producto.
- [x] **T016 — Completar el listado de productos.** Aplicar el patrón de tarjeta a todas las entradas en una lista semántica o estructura accesible equivalente. No añadir `role="grid"` por motivos exclusivamente visuales. **Comprobación:** los 20 productos iniciales están presentes sin paginación ni botón de carga adicional, admitiendo desplazamiento vertical.

## 5. Diseño responsive

- [ ] **T017 — Ajustar la presentación móvil.** Por debajo de 640 px, presentar una columna de productos y filtros apilados. **Comprobación:** textos, selectores y tarjetas caben en el ancho disponible sin desplazamiento horizontal ni recortes.
- [ ] **T018 — Ajustar la presentación de tablet.** Desde 640 px y por debajo de 1024 px, presentar dos columnas y permitir filtros en fila si hay espacio suficiente. **Comprobación:** la rejilla conserva una separación uniforme y los controles siguen siendo legibles.
- [ ] **T019 — Ajustar la presentación de escritorio.** Desde 1024 px, presentar cuatro columnas. **Comprobación:** el conjunto de 20 productos ocupa cuatro columnas y cinco filas, sin exigir que todas quepan en una sola pantalla.
- [ ] **T020 — Consolidar la identidad visual.** Aplicar la paleta, las tipografías y los espaciados aprobados al catálogo sin modificar los componentes compartidos. **Comprobación:** las tarjetas mantienen proporciones estables y los nombres largos pueden ocupar varias líneas sin invadir el precio ni otros elementos.

## 6. Accesibilidad y SEO

- [ ] **T021 — Revisar la navegación accesible.** Comprobar etiquetas, orden de tabulación, foco visible, contraste y enlaces de producto identificables. **Comprobación:** los controles y enlaces se pueden utilizar con teclado y ninguna información depende únicamente del color.
- [x] **T022 — Completar los metadatos SEO.** Incorporar un título descriptivo y una metadescripción en español. **Comprobación:** los metadatos describen el catálogo de MAISON ÉTOILE y no conservan textos genéricos de plantilla.
- [x] **T023 — Incorporar datos estructurados.** Añadir JSON-LD Schema.org de tipo `ItemList`, con entradas `ListItem`, posiciones consecutivas y contenido correspondiente al listado. **Comprobación:** el JSON es válido y no declara fotografías, valoraciones ni otros datos comerciales inexistentes.

## 7. Verificación y preparación para revisión

- [x] **T024 — Comparar los componentes compartidos.** Contrastar cabecera, navbar y footer con la referencia. **Comprobación:** solo difieren las rutas relativas necesarias y se conservan estructura, contenido, estilos y comportamiento responsive.
- [ ] **T025 — Comprobar el catálogo en los tres tamaños.** Revisar móvil, tablet y escritorio, incluidos los cambios de distribución en 640 y 1024 px. **Comprobación:** se cumplen las distribuciones de una, dos y cuatro columnas; no existen solapamientos ni desbordamiento horizontal y todos los productos son accesibles mediante desplazamiento vertical.
- [x] **T026 — Verificar enlaces y dependencias.** Comprobar la navegación compartida, el enlace de salto y los enlaces de las tarjetas. **Comprobación:** las rutas son correctas y cualquier destino aún no disponible se registra como dependencia pendiente, sin modificar páginas ajenas.
- [ ] **T027 — Contrastar los criterios de aceptación.** Revisar el resultado frente a [specs.md](specs.md), incluidos filtros visuales, cantidad de productos, placeholders, accesibilidad y SEO. **Comprobación:** cada requisito está verificado o tiene una limitación pendiente claramente identificada; no se crean pruebas automatizadas nuevas sin solicitud expresa.
- [ ] **T028 — Preparar la entrega para revisión del equipo.** Resumir el alcance implementado, las verificaciones realizadas y las dependencias o limitaciones pendientes. **Comprobación:** el cambio queda listo para revisión sin incluir modificaciones ajenas, funcionalidades adicionales ni operaciones de Git no autorizadas.