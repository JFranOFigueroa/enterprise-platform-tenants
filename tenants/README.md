# Tenants

Directorio de configuración por tenant. Un directorio por `tenants/<slug>/`:

```
tenants/
├── <slug>/
│   ├── values.yaml    # Generado por el TPS (secrets sellados con kubeseal)
│   └── metadata.yaml  # tenant_id, created_at, plan, domain
└── README.md
```

Solo el **Tenant Provisioning Service** escribe aquí. El ApplicationSet `tenant-apps`
(ArgoCD) genera una Application por directorio (`tenant-<slug>`).