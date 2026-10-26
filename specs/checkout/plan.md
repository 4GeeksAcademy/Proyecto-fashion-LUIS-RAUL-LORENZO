# Plan de implementación: página de checkout

## Estado

Borrador pendiente de aprobación. Basado en `specs/checkout/spec.md` aprobada.

## Objetivo

Implementar `checkout.html` como página estática en español que muestre los tres pasos de checkout, un resumen ficticio y un enlace de regreso al carrito, sin transmisión de información ni procesamiento de pagos.

## Archivos previstos

- **Crear `checkout.html` en la raíz:** página completa con metadatos, componentes compartidos, formulario visual, resumen y pie de página.
- **No modificar `cart.html` ni páginas compartidas:** se respetará el ejemplo actual del carrito y se mantendrá el trabajo limitado a checkout.
- **No crear CSS o JavaScript adicionales:** reutilizar Tailwind CDN y el patrón visual existente.

## Enfoque de implementación

1. Crear el esqueleto HTML5 con `lang="es"`, viewport, título, descripción SEO y datos estructurados Organization.
2. Añadir Tailwind CSS CDN, configuración de colores/tipografías y fuentes según el patrón de `cart.html` y `docs/reference.html`.
3. Copiar visualmente navbar y footer al HTML de checkout, adaptando rutas a la raíz y sin controles que dependan de JavaScript.
4. Presentar un encabezado «Finalizar compra» y un indicador estático y numerado de los pasos: «1. Datos personales», «2. Dirección de entrega» y «3. Pago con tarjeta». Los tres estarán visibles simultáneamente y el indicador no cambiará de estado.
5. Añadir un aviso destacado de demostración: no introducir datos reales; los campos no se envían ni almacenan y no se procesan pagos.
6. Maquetar los tres grupos de campos semánticamente como secciones dentro de un formulario visual. Asociar cada control con su `label`, utilizar tipos y atributos apropiados (`email`, `tel`, `text`, `number` o `month`, según aplique) y marcar claramente los campos opcionales. Evitar nombres/valores precargados que parezcan datos reales.
7. Mantener campos vacíos para que solo sean una demostración de interfaz. No añadir acción `submit` ni validación/envío real; incluir un botón final deshabilitado con texto explícito de demostración, sin posibilidad de iniciar un pedido.
8. Incluir un resumen estático con los tres productos ficticios y los mismos importes que el carrito: subtotal 725,00 €, IVA ilustrativo 145,00 €, envío gratis y total 870,00 €. Añadir un enlace a `cart.html`.
9. Aplicar diseño mobile-first, con campos de ancho adecuado, resumen y formulario apilados en móvil y una composición de dos columnas en escritorio; comprobar que no aparezca desplazamiento horizontal.

## Verificación prevista

- Analizar la estructura del HTML y comprobar que hay un solo `h1` y los tres pasos aparecen en el orden aprobado.
- Confirmar que las etiquetas `label` están asociadas a cada campo y que el aviso sobre datos/pagos ficticios es visible.
- Comprobar que no hay JavaScript propio, envío real del formulario ni almacenamiento; los únicos scripts permitidos serán Tailwind/configuración y JSON-LD.
- Verificar la consistencia de importes con los de `cart.html` y el destino del enlace a carrito.
- Revisar visualmente, si el entorno lo permite, los tamaños móvil, tablet y escritorio; de lo contrario, dejar constancia de que la comprobación se limitó a revisión estática.

## Fuera de alcance

- Convertir los pasos en navegación interactiva o desplegables.
- Validar, transmitir o almacenar información personal o de tarjeta.
- Enviar el formulario, crear pedidos o procesar pagos.
- Sincronizar automáticamente el resumen con el carrito.
- Modificar el carrito, la navegación compartida u otras páginas del proyecto.
