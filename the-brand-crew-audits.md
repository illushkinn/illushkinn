# The Brand Crruite — Reporte de Audits

**Fecha**: 10 de Septiembre 2026

---

## Audit #1: Performance y Dead Code (Primera Sesión)

### Crítico (Resuelto)
- **GSAP no estaba en `package.json`** — Dependencia fantasma que rompía en install limpio
- **`--font-heading` undefined** — Referenciado pero nunca definido, usaba fallback del browser

### Medio (Resuelto)
- **~60 líneas de CSS muerto** — `.btn-full-width`, `.footer-brand`, `.footer-illya`, `.mobile-lang-switcher`
- **3 exports nunca importados** — `languages`, `t()`, `getLangFromUrl()`
- **13 keys de i18n sin usar** — `hero.headline1`, `hero.priceFrom`, `footer.brand`, etc.
- **`siteURL` sin usar** — Variable asignada pero nunca referenciada
- **`data-theme="terracotta"` sin usar** — Atributo HTML muerto
- **`cssCodeSplit: false`** — Forzaba todo el CSS en cada página

### Bajo (Resuelto)
- 4 CSS custom properties sin usar (`--bg-elevated`, `--oklch-verde-hover`, `--black`)
- `.text-italic` sin usar

**Resultado**: 98 líneas eliminadas, build limpio

---

## Audit #2: Limpieza Profunda (Segunda Sesión)

### Encontrado
| Item | Severidad | Estado |
|------|-----------|--------|
| Zone.Identifier files (3) | Baja | ✅ Eliminados |
| `.footer-brand` CSS duplicado | Baja | ✅ Eliminado |
| `@types/node` faltante | Media | ✅ Instalado |
| 9 selectores CSS duplicados | Info | Pendiente revisión |
| `offsetParent` type error | Media | Pendiente fix en test |

### Salud General
- **Dead code**: Limpio
- **console.log**: Ninguno
- **TODO/FIXME**: Ninguno
- **Unused imports**: Ninguno
- **Unused files**: Ninguno
- **i18n consistency**: 243 keys en ambos idiomas
- **Accessibility**: Completa (aria-labels, roles, skip link)
- **Assets**: Ninguno > 200KB

---

## Resumen de Línea de Código

| Archivo | Líneas | Notas |
|---------|--------|-------|
| components.css | ~1,279 | El más grande, contiene hover states |
| responsive.css | ~551 | Breakpoints mobile/tablet/desktop |
| ui.ts | ~650 | Diccionarios ES/EN |
| Hero.astro | ~130 | GSAP cascade + typewriter |
| BaseLayout.astro | ~140 | Layout principal |

**Total CSS**: ~2,100 líneas (concatenado vía global.css)
**Total páginas**: 12 (static build)
**Build time**: ~4.5s
