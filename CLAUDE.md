# CADEA App — Cámara Argentina de Destilados y Afines

## Objetivo
Crear una landing page de presentación para la aplicación oficial CADEA, que reúne a productores de destilados argentinos, sus marcas y geografía.

## Arquitectura
**Multi-archivo frontend estático:**
```
cadea/web/
├── index.html          ← HTML estructura + contenido
├── css/styles.css      ← Todo el CSS custom
└── js/app.js           ← Intersection Observer para scroll reveal
```

Librerías externas: cargadas desde CDN en el HTML
- Google Fonts: Fraunces, Manrope, JetBrains Mono
- Sin dependencias npm (proyecto estático puro)

## Stack
- **OS**: Windows 11, sin WSL
- **Frontend**: HTML + CSS + Vanilla JS
- **Hosting**: Vercel (conectado a GitHub)
- **Deploy**: Auto-deploy en cada push a `main`

## Cómo ejecutar localmente
```bash
# Previsualizar sin servidor (solo archivos locales — cuidado con CORS)
cd web && open index.html

# Mejor: servir localmente
python -m http.server 8000 --directory web
# Luego: http://localhost:8000
```

## Deploy
1. **Git**: Realizar cambios y hacer commit
2. **Push a GitHub**: `git push origin main`
3. **Vercel**: Auto-redeploy en ~30s

## Workflow estándar
```bash
# Editar archivos en web/
git add .
git commit -m "Descripción del cambio"
git push origin main
# Vercel redeploya automáticamente
```

## Notas técnicas
- **HTML monolítico**: No era escalable. Dividido en multi-archivo para ediciones rápidas.
- **CSS**: ~1000 líneas, variables CSS para colores (tema dorado/marrón).
- **Scroll reveal**: Intersection Observer nativa (sin librerías).
- **Map**: SVG con geometrías reales de provincias argentinas.
- **Responsive**: Mobile-first, media queries en 900px y 560px.
