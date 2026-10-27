# DESIGN.md — MAISON ÉTOILE

## 1. Identidad visual

MAISON ÉTOILE es una marca francesa ficticia de moda contemporánea.

- Estilo: moderno, minimalista, elegante y premium.
- Idioma de la web: español.
- Enfoque: diseño editorial, limpio y mobile-first.

## 2. Paleta de colores

| Uso | Color | HEX |
|---|---|---|
| Principal y textos | Negro carbón | `#202020` |
| Fondo | Blanco marfil | `#FAF9F6` |
| Secundario | Beige arena | `#EAE4DA` |
| Acento | Burdeos | `#783B46` |
| Texto secundario | Gris | `#666666` |
| Bordes | Gris claro | `#E5E5E5` |

## 3. Tipografía

- Títulos: Playfair Display.
- Texto, navegación y botones: Inter.
- Mantener una jerarquía clara, buena legibilidad y espaciado consistente.

## 4. Diseño responsive

Utilizar Tailwind CSS con enfoque mobile-first.

- Móvil: menos de 640 px.
- Tablet: desde 640 px.
- Escritorio: desde 1024 px.

Evitar desplazamiento horizontal y adaptar imágenes, cuadrículas, navegación y formularios a cada pantalla.

## 5. Componentes compartidos

### Navbar
- Logotipo textual MAISON ÉTOILE.
- Buscador.
- Acceso a cuenta.
- Acceso al carrito.
- Navegación responsive.

### Footer
- Categorías: Calzado, Camisas, Pantalones, Accesorios.
- Información: Acerca de.
- Legal: Condiciones generales, Política de privacidad.
- Contacto.

### Botones
- Principal: fondo negro carbón y texto blanco.
- Secundario: transparente con borde oscuro.
- Estados hover y focus visibles.

### Tarjetas de producto
- Sin imágenes reales, aplicar un placeholder
- Nombre y precio visibles.
- Espaciado uniforme.
- Diseño minimalista.

## 6. Diseño de las páginas

### Home
Hero editorial, nuevos lanzamientos y productos más vendidos.

### Catálogo
Filtros por categoría y talla. Cuadrícula de referencia de 20 productos, cuatro columnas en escritorio.

### Producto
Dos columnas en escritorio: imagen e información. Diseño vertical en móvil.

### Carrito
Listado de productos, cantidades, precios y resumen de compra.

### Checkout
Formulario visual de tres pasos: datos personales, dirección de entrega y tarjeta.

## 7. Accesibilidad y SEO

- HTML semántico.
- Jerarquía correcta de encabezados.
- Contraste suficiente.
- Textos alternativos para imágenes.
- Formularios con etiquetas.
- Navegación mediante teclado.
- Metadatos SEO y Schema.org.

## 8. Consistencia

Los tres desarrolladores deben seguir esta guía.

Cualquier modificación importante en colores, tipografías o componentes compartidos debe acordarse con el equipo y reflejarse en este archivo.
