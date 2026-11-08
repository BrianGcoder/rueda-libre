# Rueda Libre

Sitio modular de alquiler de bicicletas y recorridos en Medellín. El sitio principal conserva Bootstrap; la campaña **Rueda Nocturna** es una landing independiente construida con Tailwind CSS v4.

## Sitio publicado

La versión actualmente publicada del sitio está en [ruedalibre en GitHub Pages](https://briangcoder.github.io/rueda-libre/). La URL de la landing será [Rueda Nocturna](https://briangcoder.github.io/rueda-libre/nocturna.html) después de integrar estos cambios en la rama publicada; por ahora esa ruta aún no está desplegada.

## Requisitos

- Node.js 20 o posterior
- npm

## Desarrollo de Rueda Nocturna

`prototipo-nocturna.html` conserva el primer boceto del hero con Play CDN. Es una evidencia de aprendizaje, no la hoja de estilos de producción.

Instala las dependencias y compila el CSS de Tailwind:

```bash
npm install
npm run build:css
```

`nocturna.html` usa el CSS compilado `nocturna.css`, versionado para que la página estática pueda servirse desde GitHub Pages sin ejecutar Node en el servidor.

Para recompilar automáticamente durante el desarrollo:

```bash
npm run watch:css
```

Abre `nocturna.html` con una extensión de servidor estático de VS Code o sirve la raíz del repositorio con cualquier servidor local. Los enlaces del encabezado conectan la campaña con las páginas Bootstrap del sitio.

## Decisión de framework

Se conserva Bootstrap en las páginas modulares existentes porque ya proporciona su navegación, grillas y componentes con cambios acotados. Tailwind se usa solo en Rueda Nocturna para practicar el enfoque utility-first, construir un kit visual propio y encapsular el tema de campaña. Mantener ambos a nivel de página evita migrar innecesariamente el sitio completo; la landing no carga Bootstrap y el resto del sitio no depende del CSS compilado de Tailwind.

## Componentes de la campaña

El kit de Rueda Nocturna vive en `src/nocturna.css`:

- `.rn-btn`: botón con estados de interacción y foco
- `.rn-card`: tarjeta para rutas y planes
- `.rn-alert`: aviso informativo
- `.rn-label` y `.rn-input`: controles del formulario
- `@theme`: colores de marca y tipografía
- `dark:` y tema claro alternable desde el encabezado

El formulario valida nombre, correo, teléfono, plan y confirmación. Es una demostración de frontend: no envía ni almacena datos. Las rutas nocturnas y sus tarifas deben confirmarse con Rueda Libre antes de aceptar reservas.

## Publicar en GitHub Pages

1. Ejecuta `npm install` y `npm run build:css`.
2. Sube a GitHub los archivos de la landing, `nocturna.css`, `src/nocturna.css`, `package.json` y `package-lock.json`.
3. Integra los cambios a la rama `master` y, en **Settings → Pages**, configura la publicación desde esa rama y la carpeta raíz del repositorio.
4. Comprueba el enlace que GitHub Pages muestra en esa pantalla; la landing estará en `/nocturna.html`.

La publicación requiere subir los cambios y tener GitHub Pages habilitado en el repositorio. La disponibilidad del formulario no equivale a una reserva real.

## Guion para una demo de 3 minutos

1. **0:00–0:35:** presentar la campaña, el hero y el enlace con Rueda Libre.
2. **0:35–1:15:** recorrer las tarjetas y los planes en escritorio y móvil.
3. **1:15–1:45:** cambiar tema y mostrar el kit de componentes Tailwind.
4. **1:45–2:25:** probar la validación del formulario con datos incompletos y válidos.
5. **2:25–3:00:** explicar por qué Bootstrap se conserva para el sitio y Tailwind se aísla en la campaña; mostrar la publicación y este README.
