# Tenants Repo (clone local)

Working copy local del repositorio de tenants del Enterprise Platform.

> El repo aún no existe en GitHub (Fase 0 pendiente). Cuando se cree:

```bash
git clone https://github.com/JFranOFigueroa/enterprise-platform-tenants.git .
```

## Estructura esperada

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
- Este clone es para desarrollo/pruebas locales; Argo CD y el TPS en el cluster
  usan el remoto de GitHub.
