# Bitácora de estructura y estilos

## Alcance

Esta bitácora explica la página de inicio (`index.html`), recorridos y tarifas (`recorridos.html`), reservas (`formulario.html`) y los estilos compartidos de `styles.css`. Describe las clases de Bootstrap y las clases propias del proyecto; no cubre la página nocturna, que tiene su propia explicación.

## Pasos y decisiones

1. Se organizó el contenido con HTML semántico. `header` contiene la navegación, `main` el contenido principal, `section` separa temas, `article` agrupa información que puede entenderse por separado y `footer` reúne la información final.
2. Se añadió una navegación común. El mismo menú permite pasar entre inicio, recorridos y reservas. La marca y el botón de menú móvil quedan en el encabezado; Bootstrap contrae los enlaces en pantallas pequeñas.
3. Se separó el contenido por propósito.Inicio presenta el servicio, promociones, planes y bicicletas; recorridos explica las rutas y tarifas; el formulario reúne los datos de reserva
4. **Se usaron tarjetas para elementos comparables.** Cada tarjeta presenta un elemento con título, descripción y cuando corresponde, una acción Las alturas y la distribución se mantienen uniformes en las cuadrículas.
5. **Se centralizaron los ajustes visuales compartidos en `styles.css`.** Allí están los colores, la tipografía, el foco visible, las imágenes y los componentes propios del sitio.

## De dónde vienen las clases

- *Bootstrap 5: las clases de cuadrícula, espaciado, botones, navegación, tarjetas, carrusel, formularios, tablas y modal. Se cargan desde Bootstrap en cada página; se usan para mantener componentes consistentes y adaptables a distintos tamaños.
- `styles.css`: las clases propias `navbar-pastel`, `navbar-logo`, `introduccion`, `introduccion-contenido`, `bike-card-image`, `formulario`, `site-footer`, `promo-slide` y `promo-carousel-image`. Se crearon para aplicar el aspecto y las medidas particulares de Rueda Libre.
- Clases identificadoras `presentacion` y `boton` nombran zonas específicas del HTML. No tienen una regla propia en `styles.css`; la presentación se completa con las clases de Bootstrap que las acompañan.

 Navegación y estructura compartida

En las tres páginas, `container` limita el ancho del contenido y lo centra. En el menú:

- `navbar`, `navbar-expand-lg` y `navbar-light` forman la barra y permiten que los enlaces se expandan desde pantallas grandes; `navbar-pastel` aplica el fondo y los colores propios.
- `navbar-brand` identifica el enlace de marca; `navbar-logo` ajusta el tamaño y el recorte del logotipo.
- `d-flex`, `align-items-center` y `gap-2` alinean la marca y separan sus elementos.
- `navbar-toggler` y `navbar-toggler-icon` presentan el control del menú en pantallas pequeñas. `collapse` y `navbar-collapse` permiten ocultar y desplegar los enlaces.
- `navbar-nav`, `nav-item` y `nav-link` estructuran la lista de navegación. `active` marca la página actual y `aria-current="page"` la identifica para tecnologías de asistencia.
- `me-auto`, `mb-2` y `mb-lg-0` distribuyen el menú y ajustan sus márgenes según el tamaño de pantalla.
- `btn`, `btn-primary` y `btn-lg` forman el botón destacado de reserva.

En el pie, `site-footer` define el color y el espaciado propios. `d-flex`, `flex-column`, `flex-sm-row`, `justify-content-between`, `align-items-center` y `gap-2` apilan los elementos en móviles y los distribuyen horizontalmente en pantallas mayores.

Inicio: tarjetas y contenedores

- `container my-4` centra el contenido principal y le da margen vertical.
- `row g-4 mb-4` inicia una fila, separa sus columnas y deja espacio antes de la siguiente sección.
- `introduccion col-12 col-md-6 col-lg-4` crea el bloque de bienvenida: ocupa todo el ancho en móvil y se ajusta en pantallas medianas y grandes. `introduccion-contenido` limita el ancho del texto para facilitar la lectura.
- `presentacion col-12 col-md-6 d-flex` reserva el bloque vecino y permite que su tarjeta se estire. `card shadow-sm border-0 mb-4 p-4 w-100` crea una tarjeta de presentación con sombra discreta, sin borde, relleno y ancho completo.
- `btn-light` da contraste al enlace sobre el bloque de bienvenida; `btn-outline-primary` ofrece acciones secundarias con borde en lugar de relleno.
- La sección de promociones usa `mb-4` y el título `mb-3` para separar el carrusel del contenido cercano. `carousel slide`, `carousel-indicators`, `carousel-inner` y `carousel-item` son las piezas del carrusel; `active` marca la diapositiva inicial. `carousel-control-prev` y `carousel-control-next` son los botones para cambiar de diapositiva; sus clases `carousel-control-prev-icon` y `carousel-control-next-icon` dibujan las flechas.
- Cada promoción usa `card promo-slide shadow-sm border-0`. `promo-slide` recorta el contenido en los bordes redondeados. Dentro, `row g-0 align-items-center` alinea imagen y texto sin separación entre columnas; `col-md-5` y `col-md-7` reparten el ancho entre ambos. `promo-carousel-image` mantiene una altura adaptable y recorta la imagen sin deformarla. `card-body p-4` da espacio al texto. `text-uppercase`, `fw-bold`, `text-primary` y `mb-2` distinguen la etiqueta de la promoción.
- La cuadrícula de planes usa `row row-cols-1 row-cols-md-3 g-3`: una tarjeta por fila en móvil y tres por fila en pantallas medianas. `col` contiene cada tarjeta. `card h-100 shadow-sm border-0 p-4` iguala alturas y conserva un estilo sencillo. `h5` da a los títulos el tamaño visual previsto sin alterar su nivel semántico. `align-self-start` mantiene el botón alineado al inicio y `mt-auto` lo desplaza al final de la tarjeta.
- La cuadrícula de bicicletas usa `row row-cols-1 row-cols-sm-2 row-cols-lg-3 g-4`: una, dos o tres columnas según el ancho disponible. `card h-100 shadow-sm` iguala las tarjetas; `card-img-top` coloca la imagen arriba. `bike-card-image` fija una altura común y usa recorte proporcional. `card-body d-flex flex-column` organiza el contenido en vertical y `mt-auto` alinea los botones de reserva en la base.
- La sección final usa `mb-5` para separarse del pie. Su contenedor `p-4 bg-white rounded shadow-sm` crea un panel blanco con espacio interior, esquinas redondeadas y sombra ligera.
- `mb-0` elimina el margen inferior de párrafos donde el siguiente elemento ya controla la separación.

 Recorridos: tarjetas y tablas

- `container py-4` centra el contenido y añade espacio vertical. El encabezado usa `mb-4`; `lead` destaca el texto introductorio.
- Cada sección usa `mb-5` para separar bloques principales y `mb-3` para acercar cada título a su contenido.
- `row row-cols-1 row-cols-md-3 g-4` presenta una tarjeta por fila en móvil y tres en pantallas medianas. `col` contiene cada una.
- `card h-100 shadow-sm` mantiene altura uniforme y una sombra discreta. `card-body d-flex flex-column` organiza el contenido en columna; `h5` establece el tamaño del título y `mt-auto` mantiene alineado el párrafo de inclusiones hacia la parte inferior.
- `table-responsive` permite desplazarse horizontalmente si una tabla no cabe en pantallas pequeñas. `table` aplica el formato de Bootstrap; `table-striped` alterna el fondo de las filas, `table-hover` resalta la fila bajo el cursor y `align-middle` centra verticalmente su contenido. `caption-top` coloca la explicación de la tabla antes de sus encabezados.
- `alert alert-info` presenta una nota destacada sobre la confirmación de las condiciones.

Formulario: campos, avisos y modal

- `container flex-grow-1` centra el contenido y permite que el área principal use el espacio libre de la página.
- `formulario` aplica el ancho máximo, el margen, el relleno, el fondo y la sombra definidos en `styles.css`.
- `alert alert-info alert-dismissible fade show` crea un aviso informativo que puede cerrarse. `bi bi-info-circle` muestra el icono y `btn-close` el control para cerrar.
- `row g-3` organiza los campos con separación uniforme; `needs-validation` identifica el formulario cuya validación se presenta con Bootstrap. `fieldset row g-3 border-0 p-0` agrupa los campos relacionados sin añadir un borde o relleno extra.
- `col-md-6` pone dos campos en una fila desde el tamaño mediano; `col-12` reserva el ancho completo para los campos largos. `form-label`, `form-control` y `form-select` dan formato consistente a etiquetas, entradas y listas desplegables. `invalid-feedback` contiene el mensaje que aparece cuando falta un dato válido.
- `boton` identifica el bloque del botón de envío; `btn btn-primary btn-lg` le da el estilo destacado y un tamaño mayor. `needs-validation` y `was-validated` se usan junto con el código del formulario para mostrar el resultado de la validación.
- `alert alert-success d-none mt-3` reserva el área del mensaje final: comienza oculta, se muestra tras la interacción y conserva separación superior.
- `modal fade` define la ventana emergente; `modal-dialog` y `modal-content` establecen su estructura. `modal-header`, `modal-body` y `modal-footer` separan título, condiciones y acciones. `modal-title fs-5` da formato al título; `btn-close` permite cerrar y `btn-secondary` distingue la acción de cancelar frente a la principal.

 Clases propias de `styles.css`

- `navbar-pastel`: aplica el fondo celeste del menú y define el color de marca y enlaces.
- `navbar-logo`: establece el tamaño y el ajuste del logotipo; en móvil reduce sus dimensiones.
- `introduccion`: construye el bloque de bienvenida con altura mínima, texto legible sobre la imagen y espaciado adaptable. La capa degradada ayuda a mantener el contraste.
- `introduccion-contenido`: limita el ancho del texto para que las líneas no sean demasiado largas.
- `.card.shadow-sm`: redondea las tarjetas que usan la sombra discreta de Bootstrap.
- `.btn-primary` y `.btn-outline-primary`: ajustan los botones de Bootstrap a los colores y estados interactivos definidos para el sitio.
- `bike-card-image`: unifica la altura de las fotos de bicicletas y las recorta para mantener una presentación consistente.
- `formulario`: centra y limita el ancho del formulario, con fondo blanco, relleno y sombra.
- `.formulario fieldset`: permite que el grupo de campos se reduzca correctamente dentro de su contenedor.
- `site-footer`: define el espacio, el color y el fondo del pie de página; la regla de sus párrafos elimina márgenes sobrantes.
- `promo-slide`: recorta los elementos del carrusel dentro de los bordes redondeados.
- `promo-carousel-image`: ajusta las imágenes promocionales a un alto adaptable sin distorsionarlas.
- Las reglas para `:focus-visible` dibujan un contorno visible al navegar con teclado. Las variables de `:root` centralizan colores, tipografía y radios para mantener un estilo común.

Las clases propias se combinan con Bootstrap en el HTML: Bootstrap aporta la estructura y los componentes generales; `styles.css` adapta su apariencia a la identidad del sitio.
