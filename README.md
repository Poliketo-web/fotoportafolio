# Portafolio Fotográfico

Sitio estático listo para Cloudflare Pages.

## Estructura

```
fotoportafolio/
├── index.html     ← la app completa
├── data.json      ← tus sesiones (edita esto)
├── fotos/         ← crea esta carpeta y sube tus imágenes aquí
└── README.md
```

## Cómo agregar una sesión nueva

Abre `data.json` y agrega un bloque nuevo dentro del array `sessions`:

```json
{
  "id": "006",
  "date": "2025-03-10",
  "type": "concierto",
  "title": "Nombre del artista o festival",
  "description": "Breve descripción de la sesión.",
  "credits": [
    { "rol": "Artista", "nombre": "Nombre del artista" },
    { "rol": "Venue", "nombre": "Nombre del lugar" }
  ],
  "photos": [
    "./fotos/sesion-006/foto1.jpg",
    "./fotos/sesion-006/foto2.jpg",
    "./fotos/sesion-006/foto3.jpg"
  ]
}
```

Las sesiones se ordenan automáticamente por fecha, las más recientes primero.

## Cómo subir las fotos

1. Crea una subcarpeta dentro de `fotos/` por sesión, ej: `fotos/sesion-006/`
2. Sube tus imágenes en JPG o WEBP (recomendado: 1200-1800px ancho máximo)
3. Referencia las rutas en `data.json` como `"./fotos/sesion-006/foto.jpg"`

## Deploy en Cloudflare Pages

1. Sube esta carpeta a un repositorio de GitHub
2. En Cloudflare Pages → Create a project → Connect to Git
3. Selecciona tu repo → Framework preset: **None** → Build command: vacío → Output directory: `/`
4. Deploy → listo! Cada `git push` actualiza el sitio automáticamente.
