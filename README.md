# Gratia Labs & Academy — MVP

Sitio público y responsive en React + TypeScript + Tailwind CSS, con catálogo filtrable de siete servicios y recomendador determinístico de dos preguntas. No requiere backend ni API de IA.

## Ejecutar localmente

Requisitos: Node.js 20.19+ o 22+ y npm.

```bash
npm install
cp .env.example .env
npm run dev
```

Abrir la URL local que muestre Vite.

## Configurar WhatsApp

En `.env` establecer `VITE_WHATSAPP_NUMBER` con el número oficial en formato internacional, solo dígitos (sin +, espacios o guiones). Si se deja vacío, la web muestra “WhatsApp próximamente” y **no inventa un número**.

En Netlify configurar la misma variable en **Site configuration → Environment variables** y volver a desplegar. IMPORTANTE: variables `VITE_` son públicas en el código cliente. Usar únicamente un número comercial destinado a difusión pública; nunca secretos o credenciales.

## Desplegar en Netlify (sin dominio propio)

1. Subir el contenido de este proyecto a un repositorio de GitHub propio.
2. En Netlify elegir **Add new project → Import an existing project** y conectar el repositorio.
3. Build command: `npm run build`. Publish directory: `dist` (también declarados en `netlify.toml`).
4. Configurar la variable opcional de WhatsApp y desplegar.
5. Netlify asigna una URL `*.netlify.app`; elegir nombre de sitio si está disponible.

También se puede ejecutar `npm run build` y desplegar manualmente el contenido de `dist` en Netlify Drop. Para actualizaciones frecuentes se recomienda Git.

## Antes de publicar

- Confirmar precios, condiciones y disponibilidad de cada servicio.
- Configurar un número **comercial** de WhatsApp.
- Incorporar aviso de privacidad si se añaden formularios o analítica.
- Revisar ortografía y textos legales/comerciales.
- Probar versión móvil y los enlaces de contacto.

## Seguridad y privacidad

El recomendador usa reglas locales y no envía respuestas a ningún servidor. No hay base de datos ni captura de datos personales. El botón de WhatsApp abrirá la app externa cuando el número esté configurado. Los precios son indicativos; no se procesan pagos en esta versión.
