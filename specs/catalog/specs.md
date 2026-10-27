# Especificación del catálogo — MAISON ÉTOILE

## 1. Objetivo y alcance

Definir la página `catalog.html` del prototipo académico de MAISON ÉTOILE: un catálogo de moda en español, accesible, responsive y coherente con las páginas compartidas.

Esta especificación se basa en [Agents.md](../Agents.md), [Context.md](../Context.md), [Design.md](../Design.md) y [las tareas generales](../specs/tasks.md). La única referencia para el navbar y el footer es [docs/reference.html](../docs/reference.html).

El alcance comprende filtros visuales de categoría y talla, y una rejilla de al menos 20 productos de referencia. No incluye backend, bases de datos, pagos reales ni filtrado dinámico. Este documento no autoriza cambios en páginas de otros participantes.

## 2. Tecnologías y organización

- Usar HTML5 semántico, Tailwind CSS y CSS adicional solo cuando sea necesario.
- Incorporar datos estructurados mediante Schema.org.
- No utilizar React, Vue, Next.js, Angular ni otros frameworks adicionales.
- La futura página se ubicará en `catalog.html`, en la raíz del proyecto.
- El responsable del catálogo y producto es el desarrollador 2. Se trabajará en una rama independiente de `main`, sin commits, push ni merges sin autorización.

## 3. Estructura de la página

El orden del contenido será:

1. Navbar compartido.
2. Contenido principal con un único encabezado de nivel uno: «Catálogo».
3. Barra de filtros por categoría y talla.
4. Listado de productos en rejilla.
5. Footer compartido.

La barra de filtros estará dentro del contenido principal, antes de la rejilla. No se sustituirá por una barra lateral.

## 4. Navbar y footer compartidos

- Copiar íntegramente el bloque de cabecera que contiene el navbar y el bloque de footer de [docs/reference.html](../docs/reference.html).
- Conservar estructura HTML, textos, clases, estilos, atributos de accesibilidad y comportamiento responsive de ambos componentes.
- Ajustar únicamente las rutas relativas de los enlaces para que funcionen desde la raíz del proyecto. Por ejemplo, `../cart.html` pasará a `cart.html`.
- No rediseñar, simplificar ni añadir elementos a estos componentes.
- Mantener los recursos de tipografía y configuración visual necesarios para reproducir su aspecto.
- Conservar el enlace «Saltar al contenido» y su destino `id="contenido"` en el contenido principal.
- Cualquier cambio que requiera alterar los componentes compartidos deberá consultarse con el equipo y quedar fuera de esta implementación.

## 5. Barra de filtros

### 5.1. Categoría

Incluir un selector nativo con etiqueta visible «Categoría», asociado mediante `for` e `id`, y estas opciones:

- Todas las categorías, seleccionada por defecto.
- Calzado.
- Camisas.
- Pantalones.
- Accesorios.

### 5.2. Talla

Incluir un selector nativo con etiqueta visible «Talla», asociado mediante `for` e `id`, y estas opciones de referencia:

- Todas las tallas, seleccionada por defecto.
- Ropa: XS, S, M, L y XL.
- Calzado: 36, 37, 38, 39, 40, 41 y 42.
- Talla única para los accesorios correspondientes.

Las opciones de ropa y calzado podrán agruparse con `optgroup`, sin mezclar sus sistemas de tallaje.

### 5.3. Alcance e interacción

- Los controles serán visuales y permitirán seleccionar opciones mediante teclado o puntero; la selección no cambiará los productos mostrados.
- No se requiere JavaScript, envío de formulario, búsqueda, ordenación ni actualización de resultados.
- No añadir un botón «Aplicar» que sugiera un filtrado funcional inexistente.
- En móvil, los controles se apilarán; desde tablet podrán distribuirse en una fila si hay espacio suficiente.
- Las etiquetas y opciones deben ser legibles, sin recortes ni desbordamiento horizontal, con estados de foco visibles.

## 6. Rejilla de productos

### 6.1. Cantidad y distribución

- Mostrar al menos 20 tarjetas en el estado inicial, sin filtros aplicados.
- Utilizar 20 productos como conjunto de referencia: en escritorio formarán cuatro columnas y cinco filas.
- Si se incorporan más de 20 productos, conservar las cuatro columnas y añadir las filas necesarias.
- Los 20 productos estarán disponibles en el listado sin requerir paginación ni un botón «Cargar más». Se permite desplazamiento vertical; no se exige que quepan en una sola pantalla.
- Como referencia de contenido, se pueden distribuir cinco productos por cada una de las cuatro categorías.

### 6.2. Tarjeta de producto

Cada tarjeta incluirá:

- Un placeholder visual con proporción estable, preferiblemente vertical de 3:4.
- Nombre del producto en español.
- Precio de referencia en euros, con formato español, por ejemplo, «59,90 €».
- Un enlace identificable hacia `product.html`, sin inventar rutas de detalle que no existan.

Las tarjetas mantendrán espaciado uniforme y una estética minimalista. Los nombres largos podrán ocupar varias líneas sin solaparse con el precio ni alterar la proporción del placeholder.

### 6.3. Placeholders

- No utilizar fotografías reales, imágenes de stock ni servicios externos de imágenes.
- Crear el placeholder mediante HTML y clases de Tailwind o CSS, usando los colores del diseño.
- El placeholder no incluirá una imagen rota ni dependerá de recursos remotos.
- Si es puramente decorativo y el producto ya tiene un nombre visible, ocultarlo a las tecnologías de asistencia mediante `aria-hidden="true"`.
- Si se utiliza una imagen local como placeholder en una implementación posterior, deberá tener un texto alternativo adecuado a su función.

## 7. Diseño visual y responsive

Respetar la identidad definida en [Design.md](../Design.md):

- Texto principal: negro carbón `#202020`.
- Fondo: blanco marfil `#FAF9F6`.
- Color secundario: beige arena `#EAE4DA`.
- Acento: burdeos `#783B46`.
- Texto secundario: gris `#666666`.
- Bordes: gris claro `#E5E5E5`.
- Títulos: Playfair Display. Texto, navegación y controles: Inter.

La maquetación será mobile-first, con esta distribución de referencia:

| Pantalla | Ancho | Columnas del catálogo |
|---|---|---|
| Móvil | Menos de 640 px | 1 |
| Tablet | Desde 640 px y menos de 1024 px | 2 |
| Escritorio | Desde 1024 px | 4 |

No debe existir desplazamiento horizontal. La adaptación del contenido del catálogo no modificará los estilos responsive del navbar ni del footer de referencia.

## 8. Accesibilidad y SEO

- Declarar el idioma español mediante `lang="es"`.
- Usar elementos semánticos, incluido un único `main`, y una jerarquía de encabezados coherente.
- Representar la colección mediante una lista semántica o una estructura equivalente accesible; no utilizar `role="grid"` solo por la distribución visual.
- Garantizar navegación por teclado, foco visible y etiquetas asociadas a los filtros.
- Mantener contraste suficiente y no comunicar información únicamente mediante color.
- Incluir un título de documento descriptivo y una metadescripción en español.
- Incorporar Schema.org mediante JSON-LD de tipo `ItemList`, con entradas `ListItem` ordenadas que correspondan a los productos visibles y no anuncien fotografías inexistentes.
- No incorporar valoraciones, disponibilidad comercial ni otros datos que el prototipo no pueda justificar.

## 9. Criterios de aceptación

- [ ] El navbar y el footer conservan la estructura y los estilos de la referencia; solo cambian las rutas relativas necesarias.
- [ ] El enlace de salto lleva al contenido principal.
- [ ] La barra de filtros aparece antes del listado, no en una barra lateral.
- [ ] Existe un selector «Categoría» con las cuatro categorías y una opción general.
- [ ] Existe un selector «Talla» con opciones de ropa, calzado y talla única, además de una opción general.
- [ ] Ambos selectores tienen etiquetas visibles y se pueden utilizar con teclado.
- [ ] Los filtros son visuales y no prometen actualizar resultados.
- [ ] El estado inicial muestra al menos 20 productos sin carga adicional.
- [ ] Con 20 productos, la rejilla presenta cuatro columnas y cinco filas desde 1024 px.
- [ ] La rejilla pasa a dos columnas en tablet y una en móvil, sin desbordamientos horizontales.
- [ ] Cada tarjeta presenta placeholder, nombre, precio en euros y enlace a la página de producto.
- [ ] No hay fotografías reales, imágenes de stock ni peticiones a servicios externos de imágenes.
- [ ] Se mantienen los colores, tipografías y patrones compartidos del proyecto.
- [ ] La página incluye HTML semántico, metadatos SEO y datos estructurados coherentes.
- [ ] Se comprueba visualmente en móvil, tablet y escritorio, y se revisan navegación por teclado y enlaces compartidos.

## 10. Fuera de alcance

No se incluyen filtrado dinámico, búsqueda funcional, ordenación, paginación, favoritos, gestión de inventario, incorporación al carrito desde el catálogo, autenticación ni modificaciones de otras páginas. Cualquier ampliación requiere aprobación previa.