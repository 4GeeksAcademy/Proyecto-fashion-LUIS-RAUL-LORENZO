# Plan de implementación del catálogo — MAISON ÉTOILE

## 1. Propósito

Establecer el enfoque y la secuencia de implementación de la página de catálogo definida en [specs.md](specs.md). Este plan describe fases, dependencias y criterios de cierre; el desglose de tareas corresponderá a otro documento.

El resultado previsto es `catalog.html`, situado en la raíz del proyecto: una página en español, responsive y accesible, con filtros visuales de categoría y talla, al menos 20 productos con placeholders y los componentes compartidos de MAISON ÉTOILE.

## 2. Marco de trabajo

La implementación seguirá [Agents.md](../Agents.md), [Context.md](../Context.md), [Design.md](../Design.md) y la especificación del catálogo. Se utilizarán HTML5 semántico, Tailwind CSS, CSS adicional solo si resulta necesario y Schema.org mediante JSON-LD.

El catálogo será un prototipo estático. Los selectores permitirán cambiar la opción seleccionada, pero no filtrarán el listado. No se incorporarán frameworks adicionales, backend, bases de datos, pagos ni funcionalidades fuera del alcance aprobado.

La responsabilidad corresponde al desarrollador 2. El trabajo se realizará en una rama independiente de `main`; los cambios en componentes compartidos y las operaciones de publicación o integración requerirán la autorización correspondiente.

## 3. Dependencias y límites

La única referencia del navbar y el footer será [docs/reference.html](../docs/reference.html). Ambos bloques conservarán estructura, textos, clases, estilos y atributos de accesibilidad; únicamente se ajustarán las rutas relativas necesarias para su ubicación en la raíz. También deberán mantenerse los recursos visuales que permiten reproducir su apariencia.

El catálogo dependerá de las rutas compartidas `index.html`, `product.html` y `cart.html` para su navegación. Si alguna página de destino todavía no existe, se registrará como dependencia pendiente, sin crearla ni modificar archivos de otros participantes.

La identidad visual y los puntos de ruptura procederán del diseño aprobado. Cualquier incompatibilidad que obligue a cambiar la referencia compartida o ampliar el alcance deberá resolverse con el equipo antes de continuar con esa parte.

## 4. Enfoque de implementación

La página se construirá de fuera hacia dentro: primero la estructura compartida y semántica, después el contenido del catálogo y finalmente su adaptación y verificación. Se favorecerá una composición sencilla, sin abstracciones ni dependencias innecesarias.

El listado utilizará 20 productos de referencia con nombre y precio en euros. Las tarjetas compartirán un mismo patrón visual y un placeholder generado con HTML y estilos, sin fotografías ni servicios externos de imágenes. Los enlaces de producto apuntarán a `product.html`, conforme a la especificación.

La adaptación será mobile-first: una columna por debajo de 640 px, dos desde 640 px y cuatro desde 1024 px. Con 20 productos, la presentación de escritorio tendrá cuatro columnas y cinco filas; no se pretende mostrar todas las filas dentro de una sola pantalla.

## 5. Fases y criterios de cierre

### Fase 1. Base de la página e integración compartida

**Objetivo:** establecer la estructura semántica de `catalog.html` e integrar el navbar y el footer sin alterar sus componentes originales. El contenido principal tendrá un destino válido para el enlace de salto y una jerarquía encabezada por «Catálogo».

**Dependencia:** referencia compartida y diseño aprobados.

**Criterio de cierre:** la página dispone de una estructura coherente, los componentes compartidos conservan su aspecto y las rutas relativas corresponden a la ubicación del catálogo.

### Fase 2. Composición del catálogo

**Objetivo:** definir la zona de contenido con la barra de filtros antes de la rejilla, sin barra lateral. Los selectores de categoría y talla tendrán etiquetas visibles, opciones y valores iniciales conforme a la especificación. Su alcance será exclusivamente visual, sin un botón que prometa aplicar resultados.

El listado presentará al menos 20 tarjetas uniformes con placeholder, nombre, precio y enlace de producto, sin paginación ni carga adicional para acceder a ese conjunto inicial.

**Dependencia:** base semántica e integración compartida resueltas.

**Criterio de cierre:** el contenido requerido está representado y los controles permiten seleccionar opciones sin modificar el listado ni sugerir una funcionalidad inexistente.

### Fase 3. Adaptación visual y responsive

**Objetivo:** consolidar la identidad minimalista del catálogo con la paleta y tipografías aprobadas, manteniendo independientes los estilos de los componentes compartidos. La rejilla y la barra de filtros se adaptarán a móvil, tablet y escritorio.

Los placeholders conservarán una proporción estable, preferiblemente 3:4. Los nombres largos y los precios seguirán siendo legibles, sin solapamientos ni desplazamiento horizontal.

**Dependencia:** contenido de referencia completo y patrón de tarjeta definido.

**Criterio de cierre:** la página mantiene una composición consistente en los tres tamaños de pantalla y muestra la distribución 4 × 5 del conjunto de referencia en escritorio.

### Fase 4. Accesibilidad y SEO

**Objetivo:** completar la navegación por teclado, el foco visible, el contraste y la asociación de etiquetas con controles. Los placeholders decorativos no añadirán información redundante a las tecnologías de asistencia.

La página contará con idioma español, título, metadescripción y datos estructurados `ItemList` con entradas `ListItem` correspondientes al listado. No se declararán imágenes, valoraciones ni otros datos comerciales inexistentes.

**Dependencia:** estructura y contenido suficientemente estables para que los metadatos describan el resultado real.

**Criterio de cierre:** los elementos interactivos son accesibles y la información semántica y estructurada es coherente con el contenido visible.

### Fase 5. Verificación y entrega para revisión

**Objetivo:** contrastar la página con los criterios de aceptación de la especificación mediante una revisión acotada del catálogo. La comprobación abarcará móvil, tablet y escritorio, navegación por teclado, enlaces, cantidad de productos y fidelidad de los componentes compartidos.

No se crearán pruebas automatizadas nuevas sin solicitud expresa ni se ejecutarán verificaciones ajenas al cambio. Las dependencias no disponibles y las comprobaciones pendientes quedarán indicadas, sin ampliar el alcance para resolverlas.

**Dependencia:** fases de implementación finalizadas.

**Criterio de cierre:** los requisitos del catálogo están verificados, las limitaciones quedan documentadas y el cambio está preparado para revisión del equipo, sin implicar un commit, push o merge automático.

## 6. Riesgos y decisiones de control

| Riesgo | Enfoque previsto |
|---|---|
| Diferencias con el navbar o footer compartidos | Mantener la referencia como fuente única y limitar las modificaciones a rutas relativas. |
| Confusión sobre el funcionamiento de los filtros | Conservar el alcance visual aprobado, sin acciones de aplicación ni promesas de actualización. |
| Interpretar 20 productos visibles como una sola pantalla | Mostrar el conjunto completo en el documento, permitiendo desplazamiento vertical. |
| Desbordamientos por controles o nombres largos | Usar distribución mobile-first, controles adaptables y texto multilínea. |
| Enlaces a páginas aún no disponibles | Registrar la dependencia para coordinación, sin intervenir en responsabilidades ajenas. |
| Dependencia accidental de fotografías externas | Generar los placeholders con HTML y estilos locales a la página. |

## 7. Resultado y continuidad

La entrega de implementación será la página de catálogo y su verificación frente a [specs.md](specs.md). Este plan no contempla cambios en otras páginas ni funcionalidades adicionales.

Un documento posterior traducirá estas fases en tareas concretas. Cualquier ampliación del comportamiento de los filtros, del listado o de la navegación deberá aprobarse y reflejarse primero en la especificación.