# docs-puente

Documentacion publica de Puente OS lista para deploy en **Mintlify**.

Destino sugerido: `docs.puente.app`

## Estructura

```
docs-puente/
├── mint.json                   # Config de navegacion, branding y theme
├── introduction.mdx            # Landing — que es Puente OS + componentes
├── quickstart.mdx              # Guia de 5 minutos: tabla + app + workflow
├── essentials/
│   ├── conceptos.mdx           # Modelo mental: workspace, projects, builds
│   └── glosario.mdx            # Diccionario de todos los terminos
├── componentes/
│   ├── menu.mdx                # Panel central de navegacion
│   ├── app-builder.mdx         # Constructor de apps con IA
│   ├── tables.mdx              # Editor de tablas dinamicas
│   ├── workflows.mdx           # Constructor de automatizaciones
│   └── agents.mdx              # Agentes IA + widget embebible
└── recursos/
    ├── atajos.mdx              # Atajos de teclado por componente
    └── faq.mdx                 # Preguntas frecuentes
```

11 paginas en total + config.

## Como deployar (Mintlify)

1. **Crear cuenta en Mintlify** — https://mintlify.com
2. **Conectar este folder a un repo de GitHub** (ej. `puenteos/docs`)
3. **Install Mintlify GitHub App** sobre ese repo
4. **Configurar custom domain** `docs.puente.app` en Mintlify dashboard
5. **Apuntar DNS** — CNAME `docs.puente.app` → `cname.vercel-dns.com` (Mintlify lo indica)

Cada push a `main` redespliega.

## Como editar localmente

```bash
npm i -g mintlify
cd docs-puente
mintlify dev
```

Levanta servidor en `localhost:3000` con hot reload.

## Pendientes antes de publicar

- [ ] Logo SVG light/dark en `/logo/`
- [ ] Favicon en `/favicon.svg`
- [ ] Imagenes hero light/dark en `/images/`
- [ ] Confirmar URLs externas:
  - `https://app.puente.app` (CTA topbar)
  - `https://status.puente.app` (estado del servicio)
  - `https://puente.app/pricing`, `/changelog`
  - LinkedIn + X handles en footer
- [ ] Confirmar email `soporte@puente.app`

## Fuente del contenido

Las paginas de `componentes/` se basan en las guias originales escritas por Octavio en https://github.com/octaviofv/puente_info, archivadas en `~/Puente-OS-Brain/Puente OS - Componentes/`.

Si Octavio actualiza el repo fuente:

```bash
cd /tmp && rm -rf puente_info && git clone https://github.com/octaviofv/puente_info.git
# Comparar con ~/Puente-OS-Brain/Puente OS - Componentes/
# Aplicar los deltas a las paginas .mdx correspondientes
```
