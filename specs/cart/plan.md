# Plan de implementación: página del carrito

## Estado

Borrador pendiente de aprobación. Basado en la especificación aprobada en `specs/cart/spec.md`.

## Objetivo

Implementar una página estática `cart.html` que represente el carrito de MAISON ÉTOILE con tres productos ficticios, respetando el diseño compartido, permitiendo Tailwind CSS CDN y sin JavaScript propio de funcionalidad transaccional.

## Archivos previstos

- **Crear `cart.html`:** página del carrito con metadatos, navbar, contenido, resumen y footer.
- **No modificar `Design.md`, `Context.md` ni componentes compartidos:** la página reutilizará visualmente las decisiones y el marcado de referencia existentes.
- **No crear CSS ni JavaScript adicionales** salvo que durante la implementación se detecte una necesidad imprescindible y se solicite aprobación antes de ampliar el alcance.

## Enfoque de implementación

1. Construir el documento HTML5 en español, con metadatos de viewport y SEO, y enlazar Tailwind CSS según el patrón de `docs/reference.html`.
2. Replicar en `cart.html` la navbar y el footer de referencia, adaptando las rutas relativas al directorio raíz y sin incluir el script del menú móvil. Mantener la navegación disponible sin controles dependientes de JavaScript.
3. Crear el contenido principal con un encabezado «Tu carrito» y una nota breve que identifique los datos como ejemplos estáticos.
4. Maquetar tres productos ficticios mediante una lista semántica: placeholder accesible, nombre, variante o talla, precio unitario, cantidad fija e importe por línea.
5. Maquetar un resumen con subtotal, IVA, envío y total ficticios. Comprobar que subtotal equivale a la suma de las líneas y que el total equivale a subtotal más IVA y envío.
6. Añadir enlaces de navegación a `catalog.html` y `checkout.html`, presentados como continuación del prototipo y no como acciones de compra reales.
7. Aplicar clases responsive mobile-first, paleta y tipografías de `Design.md`, con estados de foco visibles y sin elementos de interacción simulada para cambiar o borrar productos.

## Verificación prevista

- Revisar que `cart.html` no contenga JavaScript propio de la tienda ni referencias a scripts propios. Se permiten el CDN/configuración Tailwind y JSON-LD.
- Validar que todos los enlaces internos apuntan a las rutas previstas y que la página se sirve desde la raíz del proyecto.
- Comprobar visualmente en móvil, tablet y escritorio: jerarquía, disposición de productos/resumen y ausencia de desbordamiento horizontal.
- Revisar semántica HTML, encabezados, etiquetas accesibles de placeholders y navegación por teclado/foco.
- Verificar manualmente la consistencia aritmética de los importes estáticos.
- No introducir tests automatizados ni modificar páginas ajenas como parte de este alcance.

## Fuera de alcance

- Checkout, pagos, almacenamiento o sincronización con el catálogo.
- Interacción para editar cantidades o eliminar productos.
- Cambios en navbar/footer compartidos de las demás páginas.
- Cambios en documentación fuera de `specs/cart/`.
