# Especificación: página del carrito

## Estado

Borrador pendiente de aprobación.

## Objetivo

Definir una página de carrito estática para el prototipo académico de MAISON ÉTOILE. Debe mostrar una representación visual clara de un carrito de compra, sin implementar almacenamiento, cálculos dinámicos, pagos ni otras funciones de comercio real.

## Decisiones de alcance

- El archivo de la página será `cart.html`, para mantener la coherencia con `Context.md`, `specs/tasks.md` y los enlaces existentes en `docs/reference.html`.
- El contenido del carrito será fijo y ficticio: tres líneas de producto de ejemplo.
- Se permite el JavaScript necesario para cargar y configurar Tailwind CSS mediante CDN, conforme al patrón existente. No se añadirá JavaScript propio para la funcionalidad del carrito. La página no tendrá controles que aparenten modificar el carrito de forma funcional.
- La página seguirá las tecnologías y convenciones definidas en `Agents.md`, `Context.md` y `Design.md`.
- La navbar y el footer seguirán visualmente los componentes compartidos de `docs/reference.html`.

## Contenido y estructura

1. **Encabezado de página**
   - Título principal «Tu carrito».
   - Indicación de que contiene tres productos de ejemplo, sin sugerir que los datos sean persistentes.

2. **Listado del carrito**
   - Tres productos ficticios, cada uno con nombre, variante o talla cuando corresponda, precio unitario y cantidad fija.
   - Imagen sustituida por un placeholder accesible, coherente con la guía visual.
   - Importe de cada línea presentado de forma comprensible.
   - Las cantidades se mostrarán como contenido estático; no habrá selectores ni botones interactivos para modificarlas o eliminar productos.

3. **Resumen de compra**
   - Subtotal, IVA, gastos de envío y total, con importes ficticios y consistentes entre sí.
   - Los valores se identificarán como ilustrativos. No representan una cotización real ni se recalcularán.
   - Enlace o botón visual para continuar hacia `checkout.html`, sin procesar un pedido o un pago.

4. **Continuación de compra**
   - Enlace para volver al catálogo (`catalog.html`).

5. **Componentes compartidos**
   - Navbar y footer coherentes con la referencia compartida.
   - El enlace de carrito de la navbar podrá indicar tres productos de ejemplo.

## Requisitos visuales y técnicos

- Interfaz en español y estética minimalista, elegante y premium de MAISON ÉTOILE.
- Paleta, tipografías y patrones responsive definidos en `Design.md`.
- HTML5 semántico y diseño mobile-first, usable en móvil, tablet y escritorio.
- No debe producir desplazamiento horizontal en pantallas pequeñas.
- No se añadirá JavaScript propio inline ni mediante archivos externos para lógica de tienda. Se permite el cargador y la configuración de Tailwind CSS CDN, además del bloque JSON-LD de datos estructurados.
- No se implementarán backend, persistencia, edición de cantidades, eliminación de productos, cupones, autenticación ni pagos reales.
- Los enlaces deben apuntar a los nombres de página definidos en el proyecto: `catalog.html` y `checkout.html`.
- Incluir título y descripción SEO, jerarquía correcta de encabezados, navegación por teclado, foco visible y etiquetas accesibles para placeholders e importes.

## Criterios de aceptación

- [ ] Existe una especificación aprobable para una página estática `cart.html`.
- [ ] La página presenta tres líneas de productos ficticios con cantidades y precios visibles.
- [ ] El resumen muestra subtotal, IVA, envío y total; las cifras son consistentes e identificadas como ilustrativas.
- [ ] La página ofrece un enlace a `checkout.html` y otro a `catalog.html`.
- [ ] La navbar y el footer mantienen coherencia visual con la referencia compartida.
- [ ] La disposición se adapta a móvil, tablet y escritorio sin desbordamiento horizontal.
- [ ] El HTML es semántico y contempla accesibilidad básica y metadatos SEO.
- [ ] No se añade JavaScript propio de funcionalidad de tienda ni se presentan controles de carrito como si fueran funcionales; el CDN y la configuración de Tailwind quedan permitidos.
- [ ] No se implementan pagos, persistencia ni lógica de servidor.

## Fuera de alcance

- Actualizar el carrito desde el catálogo o la página de producto.
- Recalcular importes al cambiar cantidades.
- Eliminar productos o guardar el estado del carrito.
- Validar stock, aplicar descuentos o gestionar cuentas.
- Completar el proceso de checkout o efectuar pagos.
