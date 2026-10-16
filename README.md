# Mis clientes — PWA

App sin dependencias, sin backend y con IndexedDB. Los recibos se abren en WhatsApp y se envían manualmente.

## Ejecutar en VS Code

1. Abre la carpeta `clientes-pwa` en VS Code.
2. Instala la extensión **Live Server** y elige **Open with Live Server** en `index.html` (no abrir directamente como archivo `file://`).
3. Prueba altas, ediciones, bajas, búsqueda, ajustes y pagos. En DevTools → Application puedes comprobar IndexedDB, manifest y service worker. Activa Offline y recarga después de la primera visita.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub y sube **el contenido de esta carpeta** a la rama `main` (en la raíz).
2. Ve a **Settings → Pages → Build and deployment**, selecciona **Deploy from a branch**, `main`, carpeta `/(root)` y guarda.
3. Abre la URL HTTPS que GitHub te indique y espera la primera carga completa antes de probar sin conexión.
4. En iPhone, abre la URL en Safari → Compartir → **Añadir a pantalla de inicio** → abre desde el icono instalado.

## Notas importantes

- El total mostrado es la suma de mensualidades de todos los clientes, **no** dinero cobrado.
- Registrar pago guarda la fecha de hoy antes de abrir WhatsApp. Si WhatsApp no se abre, el detalle ofrece un enlace para reintentar durante esa visita. La app **no puede saber** si enviaste el mensaje.
- El número configurado en Ajustes es el **destinatario** del recibo.
- Los datos se guardan solo en el navegador/app de ese dispositivo. Desinstalar, borrar datos o perder el teléfono puede eliminarlos permanentemente. La solicitud de almacenamiento persistente es una ayuda, no una garantía.
- El uso offline requiere una primera visita online exitosa. WhatsApp necesita conectividad para enviar.
- Para instalar y probar PWA en móvil usa HTTPS; `localhost` sirve para desarrollo local.
