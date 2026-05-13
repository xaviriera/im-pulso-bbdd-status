# IM·PULSO · Dashboard estado BBDD

Snapshot visual de la base de datos inmobiliaria IM·PULSO. Regenerado automáticamente tras cada sync de Excel de Rafa.

**URL pública**: https://xaviriera.github.io/im-pulso-bbdd-status/

## Qué contiene

- KPIs globales (propiedades, histórico, cargas, municipios, notarial)
- Timeline cargas recientes con deltas
- Distribución por provincia + municipios top
- Frecuencia de sincronización por municipio (semáforo fresh/stale)
- Datos notariales (€/m², compraventas, importe medio)
- Salud del histórico (completo / parcial / vacío)

## Cómo se actualiza

`index.html` se sobrescribe cada vez que `regenerar_dashboard.py` corre (después de cada `sync_bbdd.py`). El script vive en el repo principal `IM-PULSO/scripts/dashboard/`.

```bash
python scripts/dashboard/regenerar_dashboard.py --output scripts/dashboard/repo/index.html
cd scripts/dashboard/repo && git add . && git commit -m "auto: $(date +%Y-%m-%d %H:%M)" && git push
```

## Tech

- HTML estático + Tailwind CSS (CDN) + Chart.js (CDN)
- Zero build · zero npm · zero CI
- Datos leídos directamente de Supabase

## Privacidad

Repo privado en GitHub. URL Pages también requiere autenticación (Pages privado disponible en plan Pro).
