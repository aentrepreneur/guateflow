# Tender Proposal Template — Guatecompras

> Basado en el caso real `licitation-gt` (Nextcloud 32 / PostgreSQL 16 en DigitalOcean).
> Template reutilizable para futuras licitaciones de infraestructura cloud.

## Estructura de Propuesta

```
1. Resumen Ejecutivo
2. Antecedentes y Justificacion
3. Descripcion Tecnica de la Solucion
4. Arquitectura del Sistema
5. Plan de Implementacion
6. Presupuesto Detallado
7. Mantenimiento y Soporte
8. Seguridad y Cumplimiento
9. Capacitacion y Transferencia
10. Garantias y SLA
11. Cronograma
12. Anexos (Curriculum, Referencias, Certificaciones)
```

## Plantilla de Costos

| Rubro | Ejemplo | Formula |
|-------|---------|---------|
| Infraestructura mensual | $497.40/mo | (Costo Droplet + DB + storage) x 1.1 (buffer) |
| Setup | $1,200 | Horas de ingeneria x tarifa |
| Soporte mensual | $600/mo | 20h/mo x $30/h |
| Cambios (Change Order) | $50-75/hr | Precio por hora extra |
| Total proyecto | $6,687 | Setup + (infra + soporte) x meses |

## SLA Template

| Metrica | Objetivo |
|---------|----------|
| Disponibilidad | 99.5% |
| Respuesta critica | <1 hora |
| Respuesta normal | <4 horas |
| RTO (Recovery Time) | <4 horas |
| RPO (Recovery Point) | <24 horas |

## Documentos Requeridos

- `contract/` — Contrato de servicios
- `docs/` — Memoria tecnica
- `internal/` — Costos internos y margenes
- `templates/` — Formatos reutilizables

## Ver Contenido Original

El caso completo esta en `/opt/licitation-gt/` con los siguientes entregables:
- Propuesta tecnica-economica completa (1,026 lineas en 12 secciones)
- Anexo A: Curriculum del equipo
- Anexo B: Referencias de proyectos anteriores
- Anexo C: Certificaciones
- Contrato listo para firma
- Guia de licitacion para futuras convocatorias
