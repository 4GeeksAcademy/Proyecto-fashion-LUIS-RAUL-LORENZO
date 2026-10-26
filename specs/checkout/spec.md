# Especificación: página de checkout

## Estado

Borrador pendiente de aprobación.

## Objetivo

Definir una página de checkout estática para el prototipo académico de MAISON ÉTOILE. La página presenta visualmente un flujo de compra en tres pasos, sin enviar, almacenar ni procesar datos personales o de pago.

## Decisiones de alcance

- El archivo será `checkout.html`, enlazado desde `cart.html`.
- Los tres pasos estarán visibles, numerados y en orden en una sola página: **1. Datos personales**, **2. Dirección de entrega** y **3. Pago con tarjeta**.
- No habrá navegación interactiva entre pasos, validación dinámica, envío de formularios ni JavaScript propio.
- Se permite Tailwind CSS CDN y su configuración visual, siguiendo el patrón del proyecto.
- Todos los campos serán demostrativos. La página advertirá de forma visible que no se deben introducir datos reales y que no se procesa ningún pago.
- Se incluirá un resumen visual de pedido con importes ficticios coherentes con el ejemplo de `cart.html`, sujeto a confirmación del alcance final en el plan.

## Estructura y campos

### Encabezado y progreso

- Título principal «Finalizar compra» o «Checkout» (la implementación usará una única forma en español).
- Indicador visual de los tres pasos, no interactivo y comprensible sin depender solo del color.
- Nota visible de que el checkout es una demostración académica sin procesamiento de datos ni pagos.

### Paso 1: Datos personales

Campos etiquetados:
- Nombre.
- Apellidos.
- Correo electrónico.
- Teléfono (opcional).

### Paso 2: Dirección de entrega

Campos etiquetados:
- Dirección.
- Complemento de dirección (opcional).
- Código postal.
- Ciudad.
- País, con Francia como valor de ejemplo.

### Paso 3: Pago con tarjeta

Campos etiquetados:
- Titular de la tarjeta.
- Número de tarjeta.
- Fecha de caducidad.
- Código de seguridad (CVV).

Los campos no estarán asociados a un envío real. No se utilizarán credenciales reales ni se conectará con un proveedor de pagos.

### Resumen y navegación

- Mostrar un resumen del pedido con productos e importes ficticios coherentes con el carrito de demostración.
- Incluir un enlace para volver a `cart.html`.
- Puede presentarse un botón final claramente identificado como demostrativo y deshabilitado o no funcional, sin enviar el formulario ni simular una compra. La decisión concreta se fijará en el plan tras aprobar esta spec.

## Requisitos visuales, técnicos y accesibilidad

- Interfaz en español, estética minimalista, elegante y premium de MAISON ÉTOILE.
- Respetar paleta, tipografías y responsive de `Design.md`.
- HTML5 semántico y mobile-first, adaptable a móvil, tablet y escritorio sin desplazamiento horizontal.
- Formularios con `label` asociado a cada campo, tipos de entrada apropiados y orden lógico de teclado.
- Estados de foco visibles, contraste suficiente y encabezados jerárquicos.
- Metadatos SEO y datos estructurados Organization siguiendo la referencia del proyecto.
- No incluir datos personales reales, persistencia, backend, lógica de negocio, JavaScript propio ni pagos reales.
- Navbar y footer serán coherentes con `docs/reference.html`, sin controles que dependan de JavaScript. Se permite Tailwind CSS CDN.

## Criterios de aceptación

- [ ] Existe `checkout.html` como página de checkout estática del prototipo.
- [ ] Los tres pasos se muestran numerados, completos y en orden en la misma página.
- [ ] Cada campo tiene etiqueta asociada y los campos opcionales se identifican.
- [ ] Existe un aviso visible que indica que es una demostración y que no se deben introducir datos reales ni se procesará ningún pago.
- [ ] El resumen usa importes ficticios coherentes con los valores de demostración del carrito.
- [ ] Hay un enlace para volver a `cart.html`.
- [ ] El diseño sigue la identidad compartida y se adapta a móvil, tablet y escritorio.
- [ ] No se añade JavaScript propio, envío de formularios, persistencia ni integración de pago.

## Fuera de alcance

- Avance interactivo por pasos o pestañas.
- Validación dinámica o envío de formularios.
- Almacenamiento o transmisión de datos personales o tarjetas.
- Procesamiento de pagos, creación de pedidos, cuentas o gestión de stock.
