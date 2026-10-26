# Especificación de la hoja de producto — MAISON ÉTOILE

## 1. Objetivo y fuentes

Definir la futura página `product.html`, situada en la raíz del proyecto, para presentar un producto de referencia del catálogo en español. Será un prototipo visual, responsive, accesible y optimizado para SEO.

Se aplican [Agents.md](../Agents.md), [Context.md](../Context.md), [Design.md](../Design.md) y [las tareas generales](../specs/tasks.md). La única referencia de navbar y footer será [docs/reference.html](../docs/reference.html). Se mantendrá la coherencia con [el catálogo](../catalog.html) y [su especificación](../proyecto%20catalogo%20de%20producto/specs.md).

La elaboración de esta documentación no implica implementar la página ni ejecutar sus tareas.

## 2. Tecnologías y límites

- HTML5 semántico, Tailwind CSS y CSS adicional únicamente cuando sea necesario.
- Schema.org mediante JSON-LD.
- Sin React, Vue, Next.js, Angular ni frameworks adicionales.
- Sin backend, bases de datos, inventario, autenticación ni pagos reales.
- Sin gestión dinámica del carrito ni persistencia de selecciones.
- Desarrollo a cargo del desarrollador 2, exclusivamente en la rama actual `feature/catalogue-products`, sin crear otra rama ni trabajar sobre `main`.
- No ejecutar commits, push o merges sin autorización ni modificar archivos de otros participantes.

## 3. Estructura y componentes compartidos

La página presentará, en este orden:

1. Cabecera con navbar compartido.
2. Contenido principal con enlace de vuelta al catálogo.
3. Presentación del producto: placeholder e información.
4. Descripción y materiales, dentro de la información del producto.
5. Footer compartido.

Copiar íntegramente la cabecera que contiene el navbar y el footer de la referencia. Conservar estructura, textos, clases, estilos, atributos de accesibilidad y comportamiento responsive, incluidos los recursos visuales y el comportamiento del menú móvil. Ajustar únicamente las rutas relativas necesarias para su ubicación en la raíz, por ejemplo, `../catalog.html` por `catalog.html`.

Conservar el enlace «Saltar al contenido» con destino a un único `main` con `id="contenido"`. Las necesidades de modificación de los componentes compartidos se consultarán antes de intervenir en ellos.

## 4. Producto de referencia

Todos los enlaces de las tarjetas actuales apuntan a una misma página. Esta entrega mostrará un único producto de ejemplo, sin resolver productos mediante parámetros ni modificar el catálogo.

| Campo | Valor de referencia |
|---|---|
| Nombre | Mocasines de piel |
| Referencia | ME-CAL-001 |
| Categoría | Calzado |
| Precio unitario | 129,00 € |
| Tallas | 36, 37, 38, 39, 40, 41 y 42 |
| Cantidad inicial | 1 |

El nombre y el precio coincidirán con la primera tarjeta del catálogo. La referencia y el contenido descriptivo son datos ficticios para el proyecto académico, no información comercial verificada.

La descripción explicará el diseño del producto con texto breve en español. Los materiales de referencia serán exterior de piel y suela de goma, sin añadir certificaciones, garantías, disponibilidad o promesas de entrega no justificadas.

## 5. Presentación visual

### Placeholder

- No utilizar imágenes reales, fotografías de stock ni servicios externos de imágenes.
- Generar un placeholder con HTML y Tailwind o CSS, con proporción estable de referencia 3:4 y colores del diseño.
- No mostrar imágenes rotas ni depender de recursos externos de imágenes.
- Si es decorativo y el nombre visible identifica el producto, utilizar `aria-hidden="true"`.
- No incorporar galería, zoom, carrusel ni vistas adicionales.

### Información del producto

- Un único `h1` con el nombre del producto.
- Referencia y precio unitario visibles y legibles.
- Selector de talla, control de cantidad y botón de carrito.
- Encabezados subordinados para «Descripción» y «Materiales».
- Enlace «Volver al catálogo» dirigido a `catalog.html` y enlace «Ver carrito» dirigido a `cart.html`.

## 6. Controles y alcance de la interacción

### Talla

Utilizar un `select` nativo con etiqueta visible «Talla», asociado mediante `for` e `id`. La opción inicial «Selecciona una talla» tendrá valor vacío; las opciones disponibles serán del 36 al 42. No usar tallas de ropa para este producto de calzado.

### Cantidad

Utilizar un `input` de tipo `number` con etiqueta visible «Cantidad», asociación `for`/`id`, valor inicial 1, mínimo 1 y paso 1. No establecer un máximo que sugiera existencias conocidas. La validación nativa identificará valores vacíos, inferiores al mínimo o no enteros; no se corregirán ni enviarán automáticamente.

### Carrito

El botón «Añadir al carrito» estará presente como elemento visual, con `type="button"` y `disabled`, sin eventos de compra ni confirmaciones simuladas. Su estado deshabilitado debe ser perceptible y no depender únicamente del color. El enlace «Ver carrito» permitirá navegar al carrito existente, sin alterar sus tres productos de ejemplo.

Cambiar talla o cantidad no modificará el precio unitario, el contador del navbar ni el contenido del carrito. No habrá envío de formularios, almacenamiento local ni cálculo de totales. No se añadirán instrucciones de uso o explicaciones del prototipo al contenido público de la página.

## 7. Diseño responsive e identidad

Aplicar el diseño mobile-first aprobado:

| Pantalla | Distribución del producto |
|---|---|
| Menos de 640 px | Una columna: placeholder y después información |
| Desde 640 px y menos de 1024 px | Una columna, con anchos y espaciados adaptados |
| Desde 1024 px | Dos columnas: placeholder a la izquierda e información a la derecha |

Mantener proporciones estables, controles adaptados al ancho y texto multilínea cuando sea necesario. No debe existir desplazamiento horizontal ni solapamiento entre nombre, precio, controles y descripción. La información no se encerrará en una tarjeta decorativa adicional.

Usar Playfair Display para títulos e Inter para texto y controles. Respetar negro carbón `#202020`, blanco marfil `#FAF9F6`, beige arena `#EAE4DA`, burdeos `#783B46`, gris `#666666` y borde `#E5E5E5`. Los estilos específicos del producto no alterarán el navbar ni el footer.

## 8. Accesibilidad y SEO

- Declarar `lang="es"`, UTF-8 y viewport responsive.
- Mantener HTML semántico, un único `main` y una jerarquía coherente de encabezados.
- Asociar etiquetas visibles a los controles y evitar identificadores duplicados con los componentes compartidos.
- Permitir usar enlaces y controles habilitados mediante teclado, con foco visible y contraste suficiente. El botón deshabilitado no deberá recibir foco como si pudiera activarse.
- Incluir título y metadescripción específicos del producto en español.
- Incorporar JSON-LD Schema.org de tipo `Product` con nombre, `sku`, descripción y materiales coherentes con el contenido visible.
- No declarar fotografías, valoraciones, existencias, ofertas o información comercial que no forme parte del alcance documentado.

## 9. Criterios de aceptación

- [ ] La página utiliza únicamente las tecnologías autorizadas y mantiene el contenido en español.
- [ ] Navbar y footer son idénticos a la referencia salvo los ajustes de rutas relativos a la raíz.
- [ ] El menú móvil y el enlace de salto conservan su comportamiento.
- [ ] El nombre y precio coinciden con los mocasines de piel del catálogo.
- [ ] Se muestran referencia, descripción y materiales del producto de ejemplo.
- [ ] Existe un placeholder estable sin fotografías ni solicitudes a servicios externos de imágenes.
- [ ] El selector de talla ofrece del 36 al 42 y comienza sin talla elegida.
- [ ] La cantidad comienza en 1, con mínimo 1 y paso 1, y su validez nativa puede comprobarse.
- [ ] El botón de carrito permanece deshabilitado y no modifica datos ni presenta confirmaciones de compra.
- [ ] Los enlaces al catálogo y al carrito apuntan a los destinos correctos.
- [ ] Cambiar los controles no modifica el precio, el contador ni los productos del carrito.
- [ ] El producto presenta una columna en móvil y tablet, y dos en escritorio desde 1024 px.
- [ ] No hay desbordamientos horizontales, recortes o solapamientos en los tamaños revisados.
- [ ] Los controles habilitados tienen etiquetas y pueden utilizarse con teclado, con foco visible.
- [ ] Los metadatos y el JSON-LD válido describen el producto visible sin datos inventados fuera del ejemplo aprobado.
- [ ] Se documentan las verificaciones realizadas y cualquier dependencia o limitación pendiente.

## 10. Fuera de alcance

No se incluyen selección dinámica de productos, modificaciones del catálogo, carrito funcional, cálculo de importes, variantes de color, favoritos, reseñas, productos relacionados, guía de tallas, galería, zoom ni otras ampliaciones. Cualquier cambio requiere aprobación previa.