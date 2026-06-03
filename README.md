# docs-puente

Documentación pública de Puente OS lista para deploy en **Mintlify**.

Destino sugerido: `docs.puente.app`

## Estructura

```
docs-puente/
├── mint.json                   # Config de navegación, branding y theme
├── introduction.mdx            # Landing — qué es Puente OS + componentes
├── quickstart.mdx              # Guía de 5 minutos: tabla + app + workflow
├── essentials/
│   ├── conceptos.mdx           # Modelo mental: workspace, projects, builds
│   └── glosario.mdx            # Diccionario de todos los términos
├── componentes/
│   ├── menu.mdx                # Panel central de navegación
│   ├── app-builder.mdx         # Constructor de apps con IA
│   ├── databases.mdx           # Build type Database (UI: Tables)
│   ├── workflows.mdx           # Constructor de automatizaciones
│   └── agents.mdx              # Agents IA + widget embebible
├── studio/
│   ├── overview.mdx            # Qué es Puente Studio
│   ├── setup.mdx               # Setup local del CLI
│   ├── coding-agents.mdx       # Uso con Claude Code, Cursor, ChatGPT
│   └── api-reference.mdx       # Referencia completa de endpoints REST
├── integraciones.mdx           # 50+ plataformas LATAM por categoría
├── casos-de-uso.mdx            # Procesos reales por vertical (retail, eCom, logística)
├── seguridad.mdx               # Encriptación, hosting GCP, backups, privacidad
├── enterprise.mdx              # Roadmap público SSO/RBAC/SOC 2 con fechas
└── faq.mdx                     # Preguntas frecuentes (sincronizadas con sitio web)
```

17 páginas en total + config.

## Nomenclatura canónica (Puente OS Blueprint)

Toda la doc respeta el glosario del Blueprint:

- **Capa de gestión:** Workspace, Team, Project, **Task** (no "Issue"), Cycle, Initiative, View
- **Capa de construcción (Builds):** **App**, **Agent**, **Workflow**, **Database** (no "Table" como Build type)
- El módulo visual donde el operador edita una Database se llama "Tables" (`puente-table` en código) — convive con el Build type "Database" sin contradicción.

## Cómo deployar (Mintlify)

1. **Crear cuenta en Mintlify** — https://mintlify.com
2. **Conectar este folder a un repo de GitHub** (ej. `puenteos/docs`)
3. **Install Mintlify GitHub App** sobre ese repo
4. **Configurar custom domain** `docs.puente.app` en Mintlify dashboard
5. **Apuntar DNS** — CNAME `docs.puente.app` → `cname.vercel-dns.com` (Mintlify lo indica)

Cada push a `main` redespliega.

## Cómo editar localmente

```bash
npm i -g mintlify
cd docs-puente
mintlify dev
```

Levanta servidor en `localhost:3000` con hot reload.

## Pendientes antes de publicar

- [ ] Logo SVG light/dark en `/logo/`
- [ ] Favicon en `/favicon.svg`
- [ ] Imágenes hero light/dark en `/images/`
- [ ] Confirmar URLs externas:
  - `https://app.puente.app` (CTA topbar)
  - `https://status.puente.app` (estado del servicio)
  - `https://puente.app/pricing`, `/changelog`
  - LinkedIn + X handles en footer
- [ ] Confirmar email `octavio@puente.xyz`

## Fuente del contenido

Las páginas de `componentes/` se basan en las guías originales escritas por Octavio en https://github.com/octaviofv/puente_info, archivadas en `~/Puente-OS-Brain/Puente OS - Componentes/`.

Si Octavio actualiza el repo fuente:

```bash
cd /tmp && rm -rf puente_info && git clone https://github.com/octaviofv/puente_info.git
# Comparar con ~/Puente-OS-Brain/Puente OS - Componentes/
# Aplicar los deltas a las paginas .mdx correspondientes
```
