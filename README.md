# MAISON ÉTOILE

Prototipo académico de una tienda online de moda contemporánea francesa. La experiencia está en español y adapta su diseño a móviles, tablets y escritorio.

## Sitio web

[https://maison-etoile-ten.vercel.app/](https://maison-etoile-ten.vercel.app/)

## Elementos compartidos

### Barra de navegación

Las páginas presentan la identidad MAISON ÉTOILE y enlaces a Inicio, Catálogo, Producto y Carrito, además de accesos visuales a búsqueda y cuenta. La navegación se adapta a los distintos tamaños de pantalla.

### Pie de página

El pie de página reúne enlaces a las categorías de productos, información de la marca, apartados legales y datos de contacto.

### Paleta de colores

- Negro carbón: `#202020`
- Blanco marfil: `#FAF9F6`
- Beige arena: `#EAE4DA`
- Burdeos: `#783B46`
- Gris: `#666666`
- Bordes: `#E5E5E5`

### Tipografía

Se utiliza **Playfair Display** en títulos y **Inter** en textos, navegación y controles, de acuerdo con la identidad editorial y minimalista del proyecto.

## Páginas

- **Inicio (`index.html`):** página prevista con una portada editorial, imagen principal y accesos a la colección, seguida de secciones de novedades y productos más vendidos.
- **Catálogo (`catalog.html`):** reúne 20 productos en una cuadrícula con nombre, precio y placeholder visual. Incluye selectores de categoría y talla; son visuales y no filtran dinámicamente los resultados.
- **Producto (`product.html`):** muestra una ficha de ejemplo en dos columnas en pantallas grandes. Presenta fotografía e información de unos mocasines de piel, con referencia, precio, tallas, cantidad, descripción y materiales. La descripción menciona su calce versátil como orientación de uso. El botón para añadir al carrito está deshabilitado.
- **Carrito (`cart.html`):** muestra tres productos ficticios con variantes, cantidades, precios unitarios e importes por línea. Incluye un resumen con subtotal, IVA, envío y total, además de enlaces para volver al catálogo o continuar al checkout.
- **Checkout (`checkout.html`):** presenta en una página los tres pasos de demostración: datos personales, dirección de entrega y pago con tarjeta. Incluye campos etiquetados, un resumen del pedido y un aviso de que no deben introducirse datos reales. No envía ni almacena información y no procesa pagos.

## Tecnologías

- HTML5 semántico.
- Tailwind CSS mediante CDN.
- CSS adicional cuando es necesario.
- Schema.org para datos estructurados.
- Metadatos SEO y recursos tipográficos.

El proyecto no utiliza frameworks de JavaScript ni requiere backend, base de datos o instalación de dependencias. Tailwind CSS y algunos recursos externos requieren conexión a Internet.

## Integrantes

- **Luis:** página de inicio y componentes de navegación y pie de página.
- **Lorenzo:** catálogo y página de producto.
- **Raúl:** carrito y checkout.

## Ejecutar localmente

Se necesita Python 3. Desde la carpeta del proyecto, ejecuta:

```bash
python3 -m http.server 8000
```

En esta rama, abre una página disponible, por ejemplo [http://localhost:8000/catalog.html](http://localhost:8000/catalog.html). La URL raíz abrirá la página de inicio cuando `index.html` esté integrado. Para detener el servidor, pulsa `Ctrl+C` en la terminal.

## Organización del proyecto

- `docs/`: documentación y página de referencia compartida.
- `specs/`: especificaciones, planes y tareas de las páginas.
- `Agents.md`: instrucciones y convenciones para asistentes.
- `Context.md`: contexto, páginas requeridas y objetivos.
- `Design.md`: identidad visual y criterios de diseño.
- `catalog.html`, `product.html`, `cart.html` y `checkout.html`: páginas presentes en esta rama.

## Trabajo colaborativo

Cada integrante trabaja en una rama propia y propone sus cambios mediante pull requests. Antes de empezar, consulta `Agents.md`, `Context.md`, `Design.md` y la especificación correspondiente en `specs/`. Los cambios deben revisarse antes de integrarse en `main`.

## Alcance

Este repositorio contiene un prototipo visual académico. No incluye backend, persistencia del carrito, inventario, cuentas ni pagos reales. Los productos, cantidades e importes son ilustrativos.
