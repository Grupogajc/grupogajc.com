# Grupo GAJC — Sitio web

## Estructura de archivos
```
index.html                        (incluye CSS y JS embebidos, igual que el portafolio)
politica-tratamiento-datos.html
politica-privacidad.html
terminos-condiciones.html
php/enviar-formulario.php
```

## Diseño
Esta versión usa el mismo lenguaje visual de tu portafolio de empresa: fondo negro (#111111), naranja (#E86200 / #FF7A1A), ámbar (#F5C842), crema (#FFF8EE) en las secciones de respiro, tipografía Playfair Display para titulares y DM Sans para el cuerpo, badges con punto pulsante, tarjetas numeradas y animación fade-in al hacer scroll.

## Publicar en cPanel
1. Comprima esta carpeta o súbala completa (manteniendo la estructura de subcarpetas) a `public_html` mediante el Administrador de archivos o FTP.
2. Confirme que el dominio apunte a la carpeta donde quedó `index.html`.
3. El hosting debe tener PHP 7.4 o superior habilitado para que funcione `php/enviar-formulario.php`.

## Formulario de contacto
- El formulario envía los datos a `php/enviar-formulario.php`, que los reenvía por correo a `asistente.gerencia@grupogajc.co` usando la función `mail()` de PHP.
- Muchos hostings de cPanel exigen que el dominio del correo remitente coincida con el dominio del sitio, o piden usar SMTP en lugar de `mail()`. Si los correos no llegan, lo más común es reemplazar la función `mail()` por un envío SMTP (por ejemplo con PHPMailer) usando las credenciales de correo de su propio hosting.
- Antes de publicar, se recomienda agregar un captcha (por ejemplo Google reCAPTCHA) para evitar spam, ya que el script actual no incluye esa protección.
- Si el envío por correo falla, el formulario ofrece automáticamente al usuario un enlace para enviar los mismos datos por WhatsApp, así nunca se pierde el contacto.

## Chatbot "Sofía"
Es un asistente con menús predefinidos (no una IA con conexión a una base de datos real). Las respuestas sobre saldos, acuerdos o información de cuenta son orientativas y siempre dirigen al usuario a un asesor humano por WhatsApp para confirmar datos específicos de su caso.

## Documentos legales
Las tres páginas de política de datos, privacidad y términos incluyen un texto modelo general, marcado con una nota visible de "necesita revisión legal". Antes de publicar el sitio, un abogado debe revisar y ajustar estos textos conforme a la Ley 1581 de 2012 y demás normativa colombiana aplicable, especialmente porque el sitio recolecta cédulas y datos de obligaciones financieras.

## Mapa de ubicación
El mapa embebido en el footer busca la dirección en Bogotá ("Cra 4 No. 18-50, Bogotá, Colombia"). Si la oficina está en otra ciudad, edite la URL del `<iframe>` en `index.html` (sección `.map-embed`) para corregir la ciudad.

## Redes sociales
No se incluyeron iconos de redes sociales porque no se proporcionaron las cuentas oficiales. Pueden agregarse fácilmente en el footer cuando se tengan los enlaces.

## Personalización rápida
- Colores y tipografías: variables al inicio de `css/styles.css` (sección `:root`).
- Textos: directamente en `index.html`.
- WhatsApp y correo: buscar y reemplazar en `index.html` y `js/script.js` si los números cambian.
