# Tenants Repo (enterprise-platform-tenants)

Repositorio de configuración dinámica de tenants del Enterprise Platform (ADR-0005).

## Estructura

```
tenants/
├── README.md
└── tenants/
    └── <slug>/            # Un directorio por tenant
        ├── values.yaml    # Generado por el TPS (secrets sellados con kubeseal)
        └── metadata.yaml  # tenant_id, created_at, plan, domain
```

## Notas

- Solo el **Tenant Provisioning Service** escribe en este repositorio.
- ArgoCD (ApplicationSet `tenant-apps`) vigila `tenants/*` y despliega una
  instancia aislada de IUMBIT por cada tenant.
- El repo de la plataforma (código estático) vive en
  `https://github.com/JFranOFigueroa/enterprise-platform.git`.
