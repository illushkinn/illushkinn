# The Brand Crew — Bitácora de Sesiones

**Proyecto**: Sitio web institucional para agencia de diseño web
**Stack**: Astro 5.1.5, Vercel (static), GSAP, OKLCH colors
**Última sesión**: 10 de Septiembre 2026

---

## Progreso Completado ✅

### Hero & Animaciones
| Feature | Estado | Detalle |
|---------|--------|---------|
| Typewriter effect | ✅ | GSAP, 0.07s stagger por char, cursor parpadeante |
| Headline split | ✅ | "Páginas web" / "que funcionan" (ES), "Web pages" / "that work" (EN) |
| Logo landing | ✅ | GSAP back.out(1.4), 0.7s, aterriza PRIMERO que el typewriter |
| Hero cascade GSAP | ✅ | Logo→Title→Sub→Price→CTA→Tags con stagger suave |
| SVG depth | ✅ | Dual drop-shadow en .hero-isotype |
| Slogan hierarchy | ✅ | Slogan 1.8rem domina precio 1.3em |
| Price text thin | ✅ | font-weight 300 |

### Mobile
| Feature | Estado | Detalle |
|---------|--------|---------|
| Menu sincronizado | ✅ | 1:1 con desktop (Servicios, Cómo funciona, Casos, FAQ, Pricing, Contacto) |
| Font size | ✅ | 1.8rem (balance entre 2.8rem excesivo y 1.4rem apretado) |
| Hover effect | ✅ | Verde glow + sliding highlight (::before translateX) |
| Background oscuro | ✅ | 0.92 opacidad |

### CTA & Botones
| Feature | Estado | Detalle |
|---------|--------|---------|
| Hover sin flicker | ✅ | Delay 0.3s + transition 0.6s |
| Corner-shape squircle | ✅ | Progressive enhancement con @supports |
| Text contrast | ✅ | text-shadow para WCAG en botones blancos |

### Navbar
| Feature | Estado | Detalle |
|---------|--------|---------|
| Transparency | ✅ | 0.72 opacidad + backdrop-filter blur(16px) |
| Border | ✅ | 1px solid verde 0.3 opacity |

### Pricing
| Feature | Estado | Detalle |
|---------|--------|---------|
| Split pages | ✅ | Kit 1 (/pricing) + Kit 2 (/pricing/growth-partner) |
| Growth Partner | ✅ | Retainer en italics |
| CTA link | ✅ | Desde Kit 1 linking a Growth Partner |

### Performance & Limpieza
| Feature | Estado | Detalle |
|---------|--------|---------|
| GSAP dependency | ✅ | Agregado a package.json |
| --font-heading fix | ✅ | → --font-display (variable existente) |
| Dead code | ✅ | 98+ líneas eliminadas |
| cssCodeSplit | ✅ | Habilitado (era false) |
| Zone.Identifier | ✅ | 3 archivos eliminados |
| @types/node | ✅ | Instalado para TypeScript |

---

## Pendiente 🔲

### Alta Prioridad
- [ ] .cdr file del diseñador para rotating textPath
- [ ] Testear hero cascade en dispositivos reales
- [ ] Deploy a Vercel (necesita `vercel login`)

### Media Prioridad
- [ ] Revisar 9 selectores CSS duplicados
- [ ] Lighthouse audit en mobile real
- [ ] Optimizar imágenes PNG

### Baja Prioridad
- [ ] `@media (hover: hover)` para touch devices
- [ ] Reduced motion para sliding highlight
- [ ] Página 404 personalizada
- [ ] Blog posts

---

## Commits Recientes (Sesión 10 Sept)

```
f34a02c chore: deep cleanup — Zone.Identifier files, dead CSS, @types/node
4e3c723 feat: mobile menu hover — verde glow + sliding highlight
4055ca7 revert: mobile bg back to original (verde 0.10, terracota 0.08/0.15)
ba2021b fix: mobile menu font 1.8rem (was 1.4rem too small, 2.8rem too big)
4c8fc36 feat: hero GSAP landing cascade + mobile menu sync + slogan hierarchy
790082d chore: audit cleanup — dead code, undefined vars, performance
6d11185 fix: CTA hover delay 0.3s + transition 0.6s (fixes flickering)
f5647d0 style: price text thin (font-weight 300, was 600)
```
