# Guia Completa de Nombres, Roadmap y Marketing para GuateFlow
# =================================================================

---

## Sección 10: Nombres de Publicación

| Contexto | Nombre | Notas |
|----------|--------|-------|
| VS Code Marketplace ID | `guateflow` | Unico, corto, 9 caracteres |
| VS Code Display Name | `GuateFlow` | Asi lo ve el usuario en la lista de extensiones |
| Publisher ID | `guateflow` | Creado via vsce, asociado a cuenta Microsoft |
| Lemon Squeezy Store | `GuateFlow` | Store name en dashboard |
| Repositorio GitHub | `guateflow` | github.com/aentrepreneur/guateflow |
| Dominio Landing | `guateflow.dev` | ~$12/year en Namecheap o similar |
| Cloudflare Worker | `guateflow-license` | Subdomain en workers.dev (gratis) |
| Email Soporte | `guateflow@aentrepreneur.dev` | Correo dedicado |
| Twitter/X | `@guateflow` | Handle para updates y comunidad |
| Nombre Legal Producto | `GuateFlow` | Marca no registrada (fase 1) |
| Licencia Código Base | MIT | Open source del scaffolding |
| Licencia Features Pro | Propietaria | License key via Lemon Squeezy |

### Reglas de Consistencia

- **Siempre** `GuateFlow` con G mayuscula y F mayuscula en textos formales
- **Siempre** `guateflow` en minusculas para IDs tecnicos (npm, GitHub, etc.)
- **Nunca** variar a Guate-Flow, Guate_Flow, o guate_flow
- El icono de la extension debe incluir el nombre completo "GuateFlow"

---

## Sección 11: Roadmap Completo

### FASE 1 (Semanas 1-4) — MVP Funcional

#### Semana 1: FREE Features

| Tarea | Archivo | Descripción |
|-------|---------|-------------|
| Scaffolding proyecto | `package.json`, `tsconfig.json`, `esbuild.config.js` | Yo generator VS Code + esbuild |
| DPI/NIT Validator | `src/free/dpi-validator.ts` | Abre browser integrado a portal SAT con CAPTCHA manual |
| Calculadora Laboral | `src/free/labor-calculator.ts` | Bono 14, Aguinaldo, Indemnizacion, Preaviso, Vacaciones |
| Formateador GT | `src/free/formatters.ts` | NIT, fechas dd/mm/aaaa, montos Q1,234.56 |
| Status Bar Licitaciones | `src/free/status-bar.ts` | Muestra conteo de licitaciones vigentes via OCDS API |
| Tests unitarios | `tests/test-labor-calculator.ts` | Validar formulas contra casos reales |
| Package VSIX | `vsce package` | Primer .vsix instalable localmente |

#### Semana 2: PRO Features (Guatecompras)

| Tarea | Archivo | Descripción |
|-------|---------|-------------|
| Cliente OCDS API | `src/pro/guatecompras-api.ts` | HTTP GET a ocds.guatecompras.gt, parse JSON |
| TreeView Panel | `src/pro/guatecompras-panel.ts` | TreeDataProvider para sidebar de VS Code |
| WebView Detalles | `src/pro/guatecompras-webview.ts` | HTML con info completa de licitacion |
| Filtros | `src/pro/filters.ts` | Keyword, monto minimo/maximo, entidad compradora |
| Ocultar Adjudicadas | `src/pro/filters.ts` | Filtra procesos con oferente asignado |
| Alertas Polling | `src/pro/alerts.ts` | setInterval c/6h, notificación VS Code al encontrar match |
| Perfiles Multi-filtro | `src/pro/filters.ts` | Hasta 5 perfiles guardados en globalState |

#### Semana 3: Licensing + Lemon Squeezy

| Tarea | Archivo | Descripción |
|-------|---------|-------------|
| License Checker | `src/licensing/license-check.ts` | Valida key via Cloudflare Worker |
| Trial Manager | `src/licensing/trial-manager.ts` | 14 dias en extension globalState |
| Upgrade Command | `src/licensing/upgrade-command.ts` | Abre checkout de Lemon Squeezy |
| Cloudflare Worker | `license-server/cloudflare-worker/index.ts` | Proxy de validación (oculta API key) |
| Setup Lemon Squeezy | `---` | Crear store, product, variants, trials |
| Activation Limit | `src/licensing/activation-limit.ts` | Max 3 dispositivos por key |

#### Semana 4: Publicación + Marketing

| Tarea | Descripción |
|-------|-------------|
| `vsce publish` | Extension en VS Code Marketplace |
| GitHub repo | README bilingue, capturas, instrucciones |
| Landing page | GitHub Pages o Vercel con link a checkout |
| Post dev.to/es | "Monitorea Guatecompras desde tu editor de código" |
| Post Facebook | Grupo Desarrolladores Guatemala |
| Reply to feedback | Primeros usuarios, bugs, sugerencias |

### FASE 2 (Meses 2-3) — Pulir y Retener

| Objetivo | Accion | Métrica |
|----------|--------|---------|
| Performance | Cache layer en Cloudflare Worker para OCDS API | <500ms response |
| Estabilidad | Manejo de errores: sin internet, API caida, timeout | 99% uptime perceived |
| UX | Feedback de primeros 10 usuarios | NPS > 40 |
| SEO Marketplace | Descripciones en espanol, keywords, tags | Impressions > 500/mes |
| Churn reduction | Email reminder antes de expirar trial | Churn < 4% |

### FASE 3 (Meses 4-6) — Expandir Features

| Feature | Indice | Complejidad | Impacto |
|---------|--------|-------------|---------|
| SAT DTE Validator | Pro | Media | Verificar facturas electronicas |
| Guatecompras Historial | Pro | Media | Tendencias de precios por producto |
| Team Sharing | Pro+ $10/mo | Alta | Compartir filtros en equipo |
| Exportar CSV/JSON mejorado | Pro | Baja | Integración con Excel/Sheets |

### FASE 4 (Meses 7-12) — Multi-Producto

| Producto | Público | Precio | Sinergia |
|----------|---------|--------|----------|
| MCP Server Guatecompras | AI Agents (Claude Code, Cursor) | $9/mo o $99 one-time | Reuso del código OCDS |
| MCP Server SAT | AI Agents | $9/mo | Reuso del validador |
| CLI `gt` | Devs GT en terminal | Gratis + Pro $5/mo | Misma base de datos OCDS |
| GuateFlow PRO Team | Equipos de 5+ | $10/user/mo | Panel compartido |

---

## Sección 12: Plan de Marketing (Ampliado)

### Estrategia General

**Costo total de marketing: $0.00**

No se invierte en anuncios. Todo es organic y community-driven. El mercado es pequeno y específico (devs GT + empresas que licitan), asi que el boca-a-boca en circulos locales es mas efectivo que ads globales.

### Canales Detallados

#### 1. VS Code Marketplace SEO (Alta prioridad)

| Elemento | Texto |
|----------|-------|
| Display Name | `GuateFlow - Guatecompras Monitor + Herramientas GT` |
| Description (corta) | `Monitorea licitaciones de Guatecompras, valida DPI/NIT, y calcula prestaciones laborales directamente en VS Code.` |
| Tags | `guatemala, guatecompras, sat, dpi, nit, licitaciones, guatemala-dev, chapin` |
| Category | `Other` |
| Icon | Logo cuadrado 256x256px con texto "GuateFlow" |
| README | Bilingue (es/en) con GIFs de uso, pricing, FAQ |
| License | `SEE LICENSE IN LICENSE.txt` |

**Keywords objetivo para SEO:**
- guatemala vscode extension
- guatecompras monitor
- licitaciones guatemala
- dpi validator
- nit validator
- calculadora laboral gt
- bono 14 aguinaldo
- herramientas chapinas vscode
- sat factura electronica

#### 2. dev.to/es (Alta prioridad)

**Titulo del post:** "Como monitorear licitaciones del gobierno de Guatemala desde tu editor de código"

**Estructura del post:**
1. El problema: revisar Guatecompras manualmente es tedioso
2. La solucion: GuateFlow como panel en VS Code
3. Demo: GIF de la extension funcionando
4. Datos abiertos: Que es OCDS y por que Guatecompras lo pública (CC BY 4.0)
5. Como empezar: Instalar gratis desde Marketplace
6. Pro features: Que ganas con la subscription
7. Call to Action: Link a Marketplace + Lemon Squeezy
8. Código abierto: Link a GitHub

**Frecuencia:** 1 post al mes (actualizaciones, nuevas features)

#### 3. Grupos Facebook (Alta prioridad)

| Grupo | Miembros | Estrategia |
|-------|----------|------------|
| Desarrolladores Guatemala | ~15,000 | Post de lanzamiento + updates mensuales |
| Programadores Guatemala | ~8,000 | Tutorial "Guatecompras desde VS Code" |
| Emprendedores Tecnologicos GT | ~5,000 | Caso de uso: encontrar licitaciones |
| Freelancers Guatemala | ~10,000 | "Ahorra 5h/semana revisando licitaciones" |

**Formato de post:** Screenshot + 3 bullet points + call to action

#### 4. LinkedIn (Media prioridad)

| Tipo de contenido | Frecuencia | Target |
|-------------------|------------|--------|
| Post de lanzamiento | Unico | Conexiones tech GT |
| Tutorial corto | Quincenal | Devs GT, CTOs, founders |
| Caso de uso: datos abiertos | Mensual | Sector público, ONGs |
| Métricas del proyecto | Trimestral | Comunidad tech |

**Hashtags:** #Guatemala #Desarrollo #OpenData #Guatecompras #VSCode #DevTools

#### 5. GitHub (Media prioridad)

| Elemento | Accion |
|----------|--------|
| README.md | Bilingue, con capturas, GIF de demo, link a Marketplace |
| LICENSE | MIT para código base |
| CONTRIBUTING.md | Guia para contribuir |
| Issues | Template para bugs y feature requests |
| GitHub Pages | Landing minimal (opcional, reemplazar por dominio propio) |
| GitHub Sponsors | Boton de赞助 (para quienes no quieren subscription) |

#### 6. Twitter/X (Media prioridad)

| Tipo | Frecuencia | Contenido |
|------|------------|-----------|
| Launch thread | Unico | Hilo contando la historia del proyecto |
| Tips de licitaciones | Semanal | "Licitacion de la semana" |
| Updates | Por release | Nueva feature, bug fix |
| Open source | Mensual | Estadisticas de crecimiento |

**Handle:** @guateflow

#### 7. Medium / Blog Propio (Baja prioridad)

Si el tiempo lo permite, replicar contenido de dev.to en Medium para SEO dual.

### Estrategia de Pricing Psicologico

| Tactica | Detalle |
|---------|---------|
| Trial 14 dias | Suficiente para que el usuario se enganche al ver licitaciones relevantes |
| $5/mo | Precio de cafe al dia — decision de compra sin pensar |
| $49/year | Sensacion de ahorro 18%, compromiso anual |
| Sin free tier PRO | No hay version gratuita del monitor (solo trial) — FREE tiene DPI/calculadora |
| Upgrade desde status bar | "Licitaciones: 23 — Ver detalles (Pro)" siempre visible |
| Email recordatorio trial | Lemon Squeezy lo maneja automaticamente |

### Métricas de Marketing

| Métrica | Semana 1 | Mes 1 | Mes 3 | Mes 6 |
|---------|----------|-------|-------|-------|
| Descargas Marketplace | primeras 50 | 200 | 1,000 | 5,000 |
| Trials iniciados | 5 | 20 | 100 | 500 |
| Conversion trial->pago | 2 (40%) | 5 (25%) | 25 (25%) | 125 (25%) |
| MRR | $10 | $25 | $125 | $625 |
| Churn mensual | -- | <5% | <4% | <4% |
| Estrellas Marketplace | 3.5 | 4.0 | 4.3 | 4.5 |
| Issues GitHub | 5 | 15 | 30 | 50 |

---

## Resumen Ejecutivo

```
PRODUCTO:     GuateFlow — VS Code Extension
PRECIO:       $5/mo · $49/year · Trial 14 dias
MERCADO:      Desarrolladores Guatemaltecos + empresas que licitan en GT
COSTO FIJO:   $0/mes (sin servidores, sin DB, sin hosting)
COSTO VARIABLE: 5% + $0.50 por venta (Lemon Squeezy merchant fee)
STACK:        TypeScript + esbuild + VS Code Extension API + Cloudflare Workers + Lemon Squeezy
DIFERENCIAL:  Unica extension que conecta Guatecompras al IDE
COMPETENCIA:  0 competidores directos en VS Code Marketplace
RIESGO:       Bajo (datos publicos via OCDS API, sin API keys externas, sin servidor)
PROYECCION:   $125-$750/mo MRR en 6 meses (escenario realista)
PROPIETARIO:  Angel Esquivel — CyberSecurity · OpenAngel
LICENCIA:     MIT (código base) + Propietaria (features Pro via license key)
REPO:         github.com/aentrepreneur/guateflow
STORE:        guateflow.lemonsqueezy.com
```

---

#End Development By Angel Esquivel (CyberSecurity) [gt-devtools 2026]
