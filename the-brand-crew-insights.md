# The Brand Crew — Informe de Insights y Ciegas

**Fecha**: 10 de Septiembre 2026

---

## 💡 Mejores Insights de las Sesiones

### 1. El delay importa más que la duración
El flickering del CTA hover no se resolvía con duraciones más largas (llegamos a 3.5s y seguía parpadeando). La solución fue un **delay de 0.3s** antes de que arranque la transición.

**Lección**: A veces el problema no es la velocidad sino el **cuándo** arranca.

### 2. GSAP para secuencias, CSS para estados
Usamos GSAP para el typewriter y el logo landing, pero las transiciones de hover son puro CSS.

**Regla**: GSAP cuando necesitás **secuencias coordinadas** (typewriter + logo + cascade). CSS cuando es **estado aislado** (hover, focus, active).

### 3. El hero cascade es un funnel visual
El orden no es aleatorio — es un funnel cognitivo:
1. **Logo** → Marca (qué empresa soy)
2. **Título** → Propuesta (qué hago)
3. **Sub** → Público (para quién)
4. **Precio** → Costo (cuánto)
5. **CTA** → Acción (hacé click)

### 4. Mobile ≠ copiar desktop
El menú mobile no es una copia del desktop — es una **experiencia diferente**. Los items deben ser los mismos (consistencia), pero el tamaño, el hover, el background todo es un contexto distinto.

### 5. Los drops de opacidad son experimentales
Probamos 0.10 → 0.18 → 0.28 → 0.40 y revertimos a 0.10. A veces **menos es más** y hay que aceptar que el original estaba bien.

---

## 🔍 Cosas que Quizás No Estás Viendo

### Ciegas Técnicas
1. **GSAP pesado en mobile** — El paquete completo son 6.4MB. En conexiones lentas el hero puede tardar en aparecer. Considerá lazy-load solo del core gsap.

2. **Hover en touch devices** — El sliding highlight del menú se activa con `:hover` que en touch devices se "pega" después del tap. Necesita `@media (hover: hover)`.

3. **Reduced motion incompleto** — El cascade del hero tiene reduced motion, pero el sliding highlight del menú mobile no.

4. **9 selectores CSS duplicados** — Algunos son intencionales (overrides), otros podrían limpiarse. No rompen nada pero ensucian el stylesheet.

### Ciegas de UX
5. **Typewriter sin loop** — Después de 30s la página se siente estática. Considerar un "replay" button.

6. **Precio en desktop** — El slogan domina en mobile, pero en desktop el precio puede necesitar más prominencia (los usuarios de desktop tienen más intención de compra).

### Ciegas de Accesibilidad
7. **Focus-visible en mobile menu** — Los links tienen `focus-visible` pero el hover effect puede confundir usuarios de teclado.

---

## 📊 Salud del Codebase

| Categoría | Estado |
|-----------|--------|
| Dead code | ✅ Limpio |
| console.log | ✅ Ninguno |
| TODO/FIXME | ✅ Ninguno |
| Unused imports | ✅ Ninguno |
| Unused files | ✅ Ninguno |
| i18n consistency | ✅ 243 keys en ambos idiomas |
| Accessibility | ✅ aria-labels, roles, skip link |
| TypeScript | ✅ Sin errores (después de @types/node) |
| Assets | ✅ Ninguno > 200KB |
