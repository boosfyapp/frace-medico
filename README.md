# Frace Médico — Landing Page

Landing page para el vertical médico de Frace Solutions.

## Deploy en EasyPanel (Docker + Nginx)

### 1. Sube los archivos al servidor

```bash
# Opción A: clonar repo (si lo subes a GitHub)
git clone <repo-url> /srv/frace-medico

# Opción B: subir manualmente por SFTP
# Sube index.html a /srv/frace-medico/
```

### 2. Crea el Dockerfile

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

### 3. En EasyPanel

1. **Nueva app** → tipo "Dockerfile"
2. Apunta al directorio con el `Dockerfile` e `index.html`
3. Puerto interno: `80`
4. Dominio: `medicos.fracesolutions.com` (o el subdominio que elijas)
5. EasyPanel gestiona el SSL automáticamente con Let's Encrypt

### 4. Variables de entorno

No requiere ninguna — es 100% estático.

---

## Estructura

```
medicos/
└── index.html   ← Landing completa (todo en un archivo)
└── README.md    ← Este archivo
```

## Dependencias (CDN, sin instalación)

- Tailwind CSS v3
- GSAP 3.12 + ScrollTrigger
- Lenis 1.0.42 (smooth scroll)
- Lucide Icons

## Personalización rápida

| Qué cambiar | Dónde buscarlo en index.html |
|---|---|
| Logo / nombre | Buscar `Frace Médico` en navbar y footer |
| Colores | Bloque `:root { }` al inicio del `<style>` |
| Tipografía | Cambiar el `@import` de Google Fonts + variables Tailwind |
| Precios | Sección `id="precios"` |
| Video demo | Buscar `<!-- Video demo placeholder -->` (agregar cuando tengas la URL) |
| Facebook Pixel | Agregar el snippet antes de `</head>` |
