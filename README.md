# Rueda Libre v2.0

Sitio de alquiler de bicicletas y recorridos en Medellín. El sitio principal usa Bootstrap 5; *Rueda Nocturna* es una landing independiente hecha con Tailwind CSS.

## Páginas

- `index.html`: presentación, carrusel y catálogo de bicicletas con enlaces de reserva.
- `recorridos.html`: recorridos guiados y tarifas de referencia.
- `formulario.html`: formulario con validación visual y modal de políticas.
- `nocturna.html`: campaña con planes, tema claro/oscuro y formulario de demostración.

El formulario no envía ni guarda datos. .

## Desarrollo de Rueda Nocturna

Se necesita Node.js 20 o posterior y npm. Para compilar los estilos:

```bash
npm install
npm run build:css
```
## Comparación: CSS propio y Bootstrap

Bootstrap añade la grilla, las utilidades y componentes como la navbar, el carrusel y el modal. El CSS propio se mantiene para la identidad visual y algunos detalles de la marca. Las cifras cuentan solo `styles.css`; no incluyen el CSS descargado desde el CDN ni representan tiempos de carga.

## Framework elegido

Bootstrap se mantiene en las páginas principales porque ya resuelve la grilla y los componentes que pide el proyecto, con poco CSS adicional. Tailwind se limita a Rueda Nocturna para practicar `utility-first` sin mezclar sus estilos con Bootstrap.

## Guía sencilla de Tailwind en Rueda Nocturna

Tailwind CSS permite dar estilo escribiendo clases directamente en el HTML. Cada clase suele resolver una tarea pequeña: por ejemplo, `p-6` agrega espacio interior y `text-white` cambia el color del texto. Al combinar varias clases se construye el diseño sin tener que escribir una regla CSS nueva para cada elemento.

En esta página las clases se usan para organizar el contenido, adaptarlo a distintos tamaños de pantalla y mantener una apariencia coherente. El archivo HTML usa Tailwind; los estilos que se repiten y algunos detalles del tema están definidos en `src/nocturna.css`.

### Cómo leer las clases
| Diseño y alineación | `flex`, `grid`, `items-center`, `justify-between`, `mx-auto` | Ordenan los elementos en filas o columnas, los alinean y centran el contenido. |
| Columnas y espacios | `grid-cols-1`, `md:grid-cols-2`, `xl:grid-cols-3`, `gap-6`, `mt-5`, `px-4`, `py-16` | Definen cuántas columnas hay y cuánto espacio queda entre elementos o alrededor de ellos. |
| Tamaños | `w-full`, `max-w-7xl`, `h-52`, `min-h-screen` | Controlan el ancho y la altura de secciones, imágenes y elementos. |
| Texto | `text-xl`, `font-black`, `leading-7`, `tracking-wide`, `uppercase` | Cambian tamaño, grosor, separación y presentación del texto. |
| Colores y fondos | `bg-night-950`, `bg-neon`, `text-slate-300`, `border-white/10` | Aplican los colores del tema a fondos, textos y bordes. |
| Bordes y formas | `rounded-xl`, `rounded-full`, `border`, `shadow-xl` | Redondean esquinas, dibujan bordes y agregan sombras. |
| Imágenes | `object-cover`, `overflow-hidden` | Hacen que las imágenes llenen su espacio y recortan lo que queda fuera. |
| Movimiento | `transition`, `duration-500`, `hover:scale-105`, `hover:text-neon` | Suavizan cambios y agregan efectos al pasar el cursor. |

### Diseño adaptable a móvil y escritorio

Tailwind aplica algunos estilos solo a partir de ciertos tamaños de pantalla. El prefijo indica cuándo se activa la clase:

- Sin prefijo, como `flex-col`: se aplica desde pantallas pequeñas.
- `sm:`, como `sm:flex-row`: se aplica desde el tamaño pequeño definido por Tailwind.
- `md:`, como `md:grid-cols-2`: se aplica desde el tamaño mediano.
- `lg:` y `xl:`, como `lg:grid-cols-2` y `xl:grid-cols-3`: se aplican en pantallas grandes y extra grandes.

Por ejemplo, `grid-cols-1 md:grid-cols-2 xl:grid-cols-3` muestra una columna en móvil, dos en pantallas medianas y tres en pantallas grandes. Así las rutas se acomodan al espacio disponible sin duplicar la página.

### Estados e interacciones

Una clase con prefijo describe cuándo debe activarse:

- `hover:text-neon`: cambia el color al pasar el cursor.
- `focus-visible:outline-2`: muestra un contorno visible cuando se navega con teclado.
- `group-hover:scale-105`: permite que la imagen crezca cuando el cursor está sobre la tarjeta que tiene `group`.
- `dark:bg-night-950`: aplica un fondo oscuro cuando está activo el modo oscuro.

El botón de tema añade o quita la clase `dark` del documento con JavaScript. Tailwind usa esa clase para aplicar los estilos oscuros; `src/nocturna.css` define el comportamiento de la variante oscura y también algunos ajustes del tema claro.

### Colores propios y clases especiales

`src/nocturna.css` declara el tema de la página con `@theme`. De allí salen los colores `night-950`, `night-900` y `neon`, además de la tipografía `display`. Por eso se pueden usar en el HTML como clases, por ejemplo `bg-night-950`, `text-neon` y `font-display`.

Algunas clases tienen valores escritos directamente entre corchetes, como `bg-[radial-gradient(...)]` o `tracking-[0.18em]`. Se usan cuando el diseño necesita un valor muy específico que no corresponde a una medida estándar.

Clases como `rn-card`, `rn-btn`, `rn-btn-primary`, `rn-btn-secondary`, `rn-alert`, `rn-label` y `rn-input` . Son clases propias del proyecto definidas en `src/nocturna.css`; varias agrupan utilidades de Tailwind con `@apply` para reutilizar el aspecto de tarjetas, botones, avisos y campos del formulario.

### Dónde se generan los estilos

Después de cambiar las clases del HTML o el archivo fuente de estilos, ejecuta `npm run build:css` para generar de nuevo `nocturna.css`. Durante el desarrollo puedes usar `npm run watch:css` para recompilarlo automáticamente cuando haya cambios.
