# Tareas de la hoja de producto — MAISON ÉTOILE

## Uso del documento

Estas tareas desarrollan [specs.md](specs.md) siguiendo las fases de [plan.md](plan.md). Se realizarán en orden y únicamente tras autorizar la implementación de la página.

Marcar una casilla con `[x]` solo cuando se cumpla su criterio de comprobación. Si una tarea está implementada pero falta verificarla, debe permanecer pendiente con el motivo registrado. La creación de estos documentos no completa ninguna tarea de implementación.

Todos los cambios permanecerán en `feature/catalogue-products`. No se cambiará de rama ni se crearán otras. No se realizarán commits, push o merges sin autorización.

## Estado de la implementación

Se ha creado [product.html](../product.html) en la raíz y en la rama exigida. La comprobación estructural confirma la igualdad de cabecera y footer con la referencia salvo rutas, un único `main` y `h1`, identificadores únicos, controles etiquetados, tallas 36–42, atributos de cantidad, botón deshabilitado, placeholder sin imágenes y JSON-LD válido y coherente con el contenido visible.

El código de las tareas visuales y de interacción está implementado, pero sus casillas permanecerán pendientes hasta comprobar sus criterios en navegador. Chromium no puede ejecutarse en el contenedor: la comprobación de dependencias confirma la ausencia de `libatk-1.0.so.0`, `libatk-bridge-2.0.so.0`, `libXcomposite.so.1`, `libXdamage.so.1`, `libXfixes.so.3`, `libXrandr.so.2`, `libgbm.so.1`, `libxkbcommon.so.0`, `libasound.so.2` y `libatspi.so.0`. No se han verificado carga de recursos, foco, contraste visual, menú móvil, validez nativa en ejecución ni distribución o desbordamientos en pantalla.

Los destinos `catalog.html`, `cart.html` y `product.html` existen. `index.html` continúa como dependencia pendiente del equipo; no se ha creado ni modificado. Tampoco se han modificado catálogo o carrito ni realizado operaciones de publicación o integración.

## 1. Preparación

- [x] **T001 — Confirmar el alcance aprobado.** Revisar [Agents.md](../Agents.md), [Context.md](../Context.md), [Design.md](../Design.md), la especificación y el plan de producto. **Comprobación:** se conoce el alcance de producto único, controles visuales, placeholder y carrito sin cambios.
- [x] **T002 — Verificar la rama y los cambios existentes.** Comprobar el estado de trabajo sin sobrescribir cambios del usuario. **Comprobación:** la rama activa es `feature/catalogue-products` y es posible continuar sin cambiarla ni afectar trabajo ajeno.
- [x] **T003 — Identificar las dependencias.** Localizar [docs/reference.html](../docs/reference.html), el catálogo y el carrito; comprobar las rutas de navegación compartidas. **Comprobación:** se dispone de la referencia y quedan registrados los destinos aún no disponibles, sin crear páginas de otros participantes.

## 2. Estructura y componentes compartidos

- [ ] **T004 — Preparar la base HTML.** Crear `product.html` en la raíz con HTML5, idioma español, UTF-8 y viewport. **Comprobación:** la página abre correctamente y no incorpora frameworks ni tecnologías fuera del alcance.
- [ ] **T005 — Incorporar los recursos visuales.** Reutilizar la configuración de Tailwind, paleta y tipografías de la referencia, con CSS adicional solo si es necesario. **Comprobación:** los recursos cargan y están disponibles Playfair Display, Inter y los colores aprobados.
- [x] **T006 — Integrar cabecera y navbar.** Copiar íntegramente el bloque compartido, ajustando únicamente las rutas relativas necesarias para la raíz y conservando el comportamiento del menú móvil. **Comprobación:** estructura, textos, clases, estilos y atributos de accesibilidad coinciden con la referencia.
- [x] **T007 — Integrar el footer.** Copiar íntegramente el footer compartido con los ajustes de rutas permitidos. **Comprobación:** todos sus apartados, textos, estilos y atributos permanecen iguales a la referencia.
- [ ] **T008 — Establecer la estructura principal.** Incorporar un único `main` con `id="contenido"`, el enlace de salto compartido y una jerarquía coherente con un solo `h1`. **Comprobación:** los identificadores son únicos y «Saltar al contenido» lleva al destino correcto.

## 3. Contenido y placeholder

- [x] **T009 — Incorporar los datos del producto.** Mostrar Mocasines de piel, referencia ME-CAL-001 y precio unitario 129,00 €. **Comprobación:** el nombre y precio coinciden con la primera tarjeta del catálogo y el nombre es el único `h1`.
- [x] **T010 — Construir el placeholder.** Utilizar HTML y estilos con proporción estable de referencia 3:4 y `aria-hidden="true"` cuando sea decorativo. **Comprobación:** no existen fotografías, imágenes rotas ni solicitudes a servicios externos de imágenes.
- [x] **T011 — Añadir descripción y materiales.** Incluir texto breve en español y apartados con encabezados subordinados; utilizar exterior de piel y suela de goma como materiales de ejemplo. **Comprobación:** el contenido no añade certificaciones, disponibilidad, garantías ni promesas comerciales no aprobadas.
- [ ] **T012 — Incorporar los enlaces de navegación.** Añadir «Volver al catálogo» hacia `catalog.html` y «Ver carrito» hacia `cart.html`. **Comprobación:** ambos destinos se abren sin modificar el contenido de las páginas enlazadas.

## 4. Controles visuales

- [ ] **T013 — Incorporar el selector de talla.** Usar un `select` nativo etiquetado «Talla», con asociación `for`/`id`, opción inicial vacía «Selecciona una talla» y tallas 36–42. **Comprobación:** empieza sin talla elegida y permite seleccionar cada talla mediante teclado o puntero.
- [x] **T014 — Incorporar el control de cantidad.** Usar un `input` numérico etiquetado «Cantidad», asociado mediante `for`/`id`, con valor inicial 1, mínimo 1 y paso 1, sin máximo de inventario. **Comprobación:** los atributos y el estado inicial coinciden con la especificación.
- [ ] **T015 — Incorporar el botón visual de carrito.** Mostrar «Añadir al carrito» con `type="button"` y `disabled`, con estado deshabilitado perceptible y sin control de compra asociado. **Comprobación:** no puede activarse, no recibe foco como control habilitado ni presenta confirmaciones simuladas.
- [x] **T016 — Mantener los límites de interacción.** Evitar envíos de formulario, persistencia, cálculos y modificaciones del carrito. **Comprobación:** talla y cantidad no tienen lógica de compra asociada y no existe almacenamiento local ni recálculo del precio.

## 5. Presentación responsive

- [ ] **T017 — Ajustar la composición móvil.** Por debajo de 640 px, disponer placeholder e información en una sola columna. **Comprobación:** los controles y textos caben en pantalla sin desbordamientos, recortes ni solapamientos.
- [ ] **T018 — Ajustar la composición de tablet.** Entre 640 px y menos de 1024 px, mantener una columna con anchos y espaciados adaptados. **Comprobación:** se conserva la legibilidad y no se altera el navbar ni el footer para conseguirla.
- [ ] **T019 — Ajustar la composición de escritorio.** Desde 1024 px, colocar placeholder a la izquierda e información a la derecha. **Comprobación:** existen dos columnas estables, con proporción de placeholder correcta y sin encerrar la información en una tarjeta decorativa adicional.
- [ ] **T020 — Consolidar la identidad visual.** Aplicar la paleta y tipografías aprobadas, espaciado consistente y texto multilínea cuando sea necesario. **Comprobación:** nombre, precio, controles y descripción son legibles y los estilos específicos no modifican componentes compartidos.

## 6. Accesibilidad y SEO

- [ ] **T021 — Verificar accesibilidad de la interacción.** Comprobar etiquetas, contraste, foco visible y navegación por teclado en enlaces y controles habilitados. **Comprobación:** no hay trampas de foco, identificadores duplicados ni información que dependa únicamente del color, y el placeholder no genera lectura redundante.
- [x] **T022 — Incorporar metadatos específicos.** Definir título y metadescripción del producto en español. **Comprobación:** describen los mocasines de piel de MAISON ÉTOILE y no conservan contenido de plantilla.
- [x] **T023 — Incorporar JSON-LD de producto.** Añadir Schema.org de tipo `Product` con nombre, `sku`, descripción y materiales. **Comprobación:** el JSON es válido, coincide con el contenido visible y no declara imágenes, valoraciones, existencias u ofertas fuera del alcance.

## 7. Verificación y preparación de la entrega

- [ ] **T024 — Contrastar los componentes compartidos.** Comparar cabecera y footer con la referencia, y comprobar menú móvil, enlaces y salto al contenido. **Comprobación:** solo cambian las rutas relativas permitidas; las dependencias no disponibles están documentadas y no se modifican páginas ajenas.
- [ ] **T025 — Revisar los tamaños de pantalla.** Comprobar móvil, tablet y escritorio, por ejemplo en 360, 640, 768, 1024 y 1440 px. **Comprobación:** hay una columna por debajo de 1024 px y dos desde ese ancho, sin desplazamiento horizontal ni solapamientos; los recursos visuales cargan correctamente.
- [ ] **T026 — Comprobar los controles en navegador.** Cambiar talla y cantidad y comprobar la validez nativa de cantidad vacía, 0, valores negativos y decimales no enteros, frente a enteros positivos. **Comprobación:** la validación identifica valores no válidos sin envío automático, y las selecciones no alteran precio, contador del navbar ni productos del carrito; el botón sigue deshabilitado.
- [ ] **T027 — Revisar los criterios de aceptación.** Contrastar el resultado con la especificación y registrar las verificaciones realmente realizadas, sin crear pruebas automatizadas nuevas salvo solicitud expresa. **Comprobación:** cada requisito está verificado o tiene una limitación identificada; las tareas bloqueadas permanecen sin marcar, indicando el motivo.
- [ ] **T028 — Preparar la revisión del equipo.** Resumir archivos modificados, alcance, verificaciones y dependencias pendientes. **Comprobación:** la página queda preparada para revisión en la rama exigida, sin funcionalidades adicionales, modificaciones ajenas ni commits, push o merges no autorizados.