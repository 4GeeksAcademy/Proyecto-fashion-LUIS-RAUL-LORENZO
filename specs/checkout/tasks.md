# Tareas de implementación: checkout

## Estado

Borrador pendiente de aprobación. Derivado de `specs/checkout/spec.md` y `specs/checkout/plan.md`.

## Tareas

### 1. Preparar el documento
- [ ] Crear `checkout.html` en la raíz del proyecto.
- [ ] Añadir estructura HTML5, idioma español, viewport, título y descripción SEO.
- [ ] Añadir datos estructurados Organization.
- [ ] Enlazar Tailwind CSS CDN, configurar la paleta y tipografías del proyecto y cargar las fuentes de referencia.

### 2. Añadir navegación compartida
- [ ] Replicar visualmente la navbar de referencia con enlaces adaptados a la raíz.
- [ ] No incluir botón de menú móvil dependiente de JavaScript ni lógica JavaScript propia.
- [ ] Replicar visualmente el footer y sus enlaces según los patrones de las páginas existentes.

### 3. Presentar el flujo de checkout
- [ ] Añadir un título principal en español para finalizar la compra.
- [ ] Crear un indicador visual estático con los tres pasos numerados y en orden: datos personales, dirección de entrega y pago con tarjeta.
- [ ] Añadir un aviso destacado: checkout de demostración, no introducir datos reales y no se enviarán ni procesarán datos o pagos.

### 4. Maquetar datos personales
- [ ] Añadir campos vacíos etiquetados para nombre, apellidos y correo electrónico.
- [ ] Añadir teléfono opcional y marcarlo claramente como opcional.
- [ ] Utilizar tipos de entrada y atributos semánticos adecuados.

### 5. Maquetar dirección de entrega
- [ ] Añadir campos etiquetados para dirección, código postal, ciudad y país.
- [ ] Añadir complemento de dirección opcional y marcarlo claramente como opcional.
- [ ] Mostrar Francia como valor de ejemplo para el país, sin incluir datos personales reales.

### 6. Maquetar pago con tarjeta
- [ ] Añadir campos etiquetados vacíos para titular, número de tarjeta, caducidad y CVV.
- [ ] Usar tipos de entrada y atributos apropiados para cada campo.
- [ ] Aclarar junto a los campos que son únicamente demostrativos y no deben completarse con datos reales.
- [ ] Añadir un botón final deshabilitado con texto explícito de demostración, sin envío de formulario.

### 7. Añadir resumen estático
- [ ] Mostrar los tres productos ficticios y los importes coherentes con `cart.html`.
- [ ] Mostrar subtotal 725,00 €, IVA ilustrativo 145,00 €, envío gratis y total 870,00 €.
- [ ] Añadir un enlace de retorno a `cart.html`.

### 8. Aplicar estilo y accesibilidad
- [ ] Seguir la identidad visual de `Design.md` y los patrones de `cart.html` y `docs/reference.html`.
- [ ] Disponer formulario y resumen en una columna en móvil y una composición adaptable a escritorio.
- [ ] Comprobar que no exista desbordamiento horizontal en tamaños pequeños.
- [ ] Mantener encabezados jerárquicos, `label` asociado a cada control, orden de teclado lógico y foco visible.

### 9. Verificar alcance y resultado
- [ ] Confirmar que los tres pasos están visibles y en el orden definido.
- [ ] Revisar que no hay JavaScript propio, envío real ni persistencia de datos.
- [ ] Verificar resumen y aritmética contra los importes del carrito.
- [ ] Comprobar la ruta a `cart.html` y revisar el marcado HTML.
- [ ] Revisar visualmente móvil, tablet y escritorio cuando el entorno permita abrir la página; anotar si la comprobación es solo estática.
