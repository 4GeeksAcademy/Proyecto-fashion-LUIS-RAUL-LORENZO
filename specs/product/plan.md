# Plan de implementación de la hoja de producto — MAISON ÉTOILE

## 1. Propósito

Organizar la futura implementación de `product.html` conforme a [specs.md](specs.md). Este documento establece enfoque, dependencias, fases y criterios de cierre. El desglose de acciones concretas pertenece al documento de tareas, no a este plan.

El resultado previsto es una página estática en español para los mocasines de piel del catálogo, con placeholder, información del producto, controles visuales y navegación a catálogo y carrito.

## 2. Marco y responsabilidades

Se seguirán [Agents.md](../Agents.md), [Context.md](../Context.md) y [Design.md](../Design.md), utilizando HTML5, Tailwind CSS, CSS adicional únicamente cuando sea necesario y Schema.org mediante JSON-LD.

La implementación corresponde al desarrollador 2 y permanecerá exclusivamente en `feature/catalogue-products`, sin cambiar de rama. Se respetarán los cambios existentes y los archivos de otros participantes. No habrá commits, push o merges sin autorización.

El alcance es visual: las selecciones no se persistirán y el botón «Añadir al carrito» estará deshabilitado. No se incorporarán backend, inventario, pagos ni lógica de compra.

## 3. Dependencias

La fuente única del navbar y footer será [docs/reference.html](../docs/reference.html), incluidos los recursos que definen su apariencia y el comportamiento del menú móvil. Solo podrán ajustarse las rutas relativas necesarias para ubicar la página en la raíz.

[El catálogo](../catalog.html) aporta el nombre y precio del producto de referencia: Mocasines de piel, 129,00 €. El carrito existente será únicamente un destino de navegación; su contenido y contador no cambiarán.

Las páginas compartidas que todavía no existan se registrarán como dependencias pendientes, sin crearlas como parte de este trabajo. Las incompatibilidades de la referencia que requieran alterar sus componentes deberán consultarse con el equipo.

## 4. Enfoque técnico

La implementación avanzará desde la estructura semántica y compartida hacia la presentación del producto, los controles nativos y la adaptación responsive. Se priorizará HTML sencillo y contenido estático, sin dependencias adicionales ni abstracciones innecesarias.

El producto se presentará sin fotografías, mediante un placeholder HTML de proporción estable. La información comercial de ejemplo será explícita en la documentación y coherente entre el contenido visible y los datos estructurados.

La interfaz tendrá una columna en móvil y tablet y dos desde 1024 px. La adaptación del contenido principal no modificará los estilos de cabecera y footer.

## 5. Fases y criterios de cierre

### Fase 1. Base e integración compartida

**Objetivo:** disponer de la estructura de `product.html` en la raíz, con idioma español, recursos visuales, cabecera y footer de referencia. El contenido tendrá un único `main`, destino del enlace de salto, y una jerarquía de encabezados coherente.

**Dependencia:** instrucciones y referencia compartida disponibles.

**Criterio de cierre:** la base semántica es válida y los componentes compartidos conservan su estructura, estilos y comportamiento, con rutas correctas para la raíz.

### Fase 2. Presentación del producto

**Objetivo:** consolidar el placeholder y la información de los mocasines de piel: nombre, referencia, precio, descripción y materiales. La composición incluirá los enlaces de vuelta al catálogo y acceso al carrito, sin galería ni contenido adicional no aprobado.

**Dependencia:** base de la página resuelta y datos de referencia definidos en la especificación.

**Criterio de cierre:** toda la información requerida está presente, coincide con el producto de referencia y no depende de imágenes externas ni modifica otras páginas.

### Fase 3. Controles visuales

**Objetivo:** ofrecer selección nativa de talla y cantidad con etiquetas visibles y valores iniciales coherentes. El botón de carrito permanecerá deshabilitado; la navegación al carrito se ofrecerá mediante un enlace independiente.

**Dependencia:** información del producto estable.

**Criterio de cierre:** las opciones de talla y la validez nativa de cantidad corresponden a la especificación. Ningún control envía información, altera el precio o modifica el carrito.

### Fase 4. Diseño responsive y accesibilidad

**Objetivo:** aplicar la identidad visual y la disposición mobile-first sin recortes ni solapamientos. Los controles habilitados y los enlaces tendrán navegación por teclado, contraste adecuado y foco visible; el placeholder decorativo no añadirá información redundante.

**Dependencia:** contenido y controles completos.

**Criterio de cierre:** la página se comprueba en móvil, tablet y escritorio, mantiene una columna hasta 1024 px y dos desde ese ancho, y permite utilizar sus elementos habilitados mediante teclado.

### Fase 5. SEO y datos estructurados

**Objetivo:** completar título, metadescripción y JSON-LD de tipo `Product`, con nombre, referencia, descripción y materiales correspondientes al contenido visible. No se anunciarán imágenes ni datos comerciales fuera del alcance aprobado.

**Dependencia:** contenido definitivo del producto.

**Criterio de cierre:** los metadatos describen la página y el JSON es válido, coherente con el producto presentado y libre de información no justificada.

### Fase 6. Verificación y preparación para revisión

**Objetivo:** contrastar el resultado con los criterios de aceptación, incluida la fidelidad de componentes compartidos, los enlaces, la interacción visual, la accesibilidad y el comportamiento responsive.

La verificación será acotada a esta página, sin crear pruebas automatizadas nuevas salvo solicitud expresa. Se emplearán las herramientas disponibles; cualquier bloqueo del entorno se documentará y las tareas no verificadas permanecerán abiertas.

**Dependencia:** implementación completa y entorno de revisión disponible.

**Criterio de cierre:** existen evidencias de los requisitos comprobados, las dependencias pendientes están identificadas y el cambio queda preparado para revisión sin realizar operaciones de Git no autorizadas.

## 6. Riesgos y controles

| Riesgo | Enfoque previsto |
|---|---|
| Alterar componentes compartidos | Comparar con la referencia y limitar diferencias a rutas relativas. |
| Esperar una ficha distinta desde cada tarjeta | Mantener el producto de ejemplo único y dejar fuera de alcance el enrutado por producto. |
| Simular compras o cambios de inventario | Mantener el botón deshabilitado y limitar el acceso al carrito a un enlace. |
| Confundir el precio unitario con un total | Mantener el precio fijo al cambiar la cantidad. |
| Desbordamientos o pérdida de foco | Revisar tamaños representativos, texto multilínea y uso por teclado. |
| No poder ejecutar el navegador de revisión | Registrar el bloqueo y no dar por completada la validación visual. |

## 7. Entrega y continuidad

La entrega de implementación comprenderá la página de producto y el registro de sus comprobaciones en el documento de tareas. La creación de esta documentación no ejecuta esa implementación.

Las ampliaciones de alcance deberán aprobarse primero y reflejarse en la especificación antes de modificar el plan o las tareas.