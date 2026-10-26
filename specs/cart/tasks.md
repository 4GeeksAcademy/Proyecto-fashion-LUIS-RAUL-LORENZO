# Tareas de implementación: carrito

## Estado

Borrador pendiente de aprobación. Derivado de `specs/cart/spec.md` y `specs/cart/plan.md`.

## Tareas

### 1. Preparar el documento
- [ ] Crear `cart.html` en la raíz del proyecto.
- [ ] Añadir estructura HTML5 semántica, idioma español, viewport, título y descripción SEO.
- [ ] Enlazar Tailwind CSS y las fuentes siguiendo el patrón de `docs/reference.html`.

### 2. Incorporar componentes compartidos
- [ ] Añadir la navbar basada en la referencia, con enlaces correctos desde la raíz.
- [ ] Omitir JavaScript propio de interacción y no mostrar un botón de menú móvil que no funcione; se permite el CDN/configuración de Tailwind.
- [ ] Añadir el footer basado en la referencia, con rutas internas correctas.

### 3. Construir el listado de productos
- [ ] Añadir el encabezado «Tu carrito» y una nota que indique que los datos son ficticios y estáticos.
- [ ] Maquetar tres productos de ejemplo como lista semántica.
- [ ] Incluir para cada producto placeholder accesible, nombre, variante o talla, precio unitario, cantidad fija e importe de línea.
- [ ] Evitar controles de edición o eliminación que aparenten ser funcionales.

### 4. Construir el resumen
- [ ] Mostrar subtotal, IVA, gastos de envío y total como importes ilustrativos.
- [ ] Verificar la suma de las líneas para el subtotal y la suma de subtotal, IVA y envío para el total.
- [ ] Añadir un enlace para continuar a `checkout.html` y otro para volver a `catalog.html`, sin simular una compra real.

### 5. Aplicar estilo y accesibilidad
- [ ] Aplicar paleta, tipografías y estilo premium de `Design.md`.
- [ ] Ajustar el diseño con enfoque mobile-first para móvil, tablet y escritorio.
- [ ] Revisar jerarquía de encabezados, semántica, texto alternativo/etiquetas accesibles y foco visible.
- [ ] Comprobar que no haya desbordamiento horizontal en pantalla pequeña.

### 6. Verificar el alcance
- [ ] Confirmar que la página no contiene JavaScript propio de funcionalidad de tienda ni referencias a scripts propios; se permiten el cargador/configuración Tailwind y JSON-LD.
- [ ] Comprobar las rutas de enlaces internos a catálogo, checkout y páginas compartidas.
- [ ] Revisar visualmente la página en móvil, tablet y escritorio.
- [ ] Confirmar que no se añadieron persistencia, lógica de servidor, controles funcionales ni pagos reales.
