# lab-cfg-dm-argo-cd

Repo **GitOps** del dominio demo (`dm`).
Argo CD lee de aquí los valores de cada app. **Un push a `main` despliega.**

```
global.yaml                              # todas las apps, todos los ambientes
<app>/shared.yaml                        # una app, todos los ambientes
<app>/shared-envvars.yaml                # variables de entorno comunes
<app>/<env>/app.yaml                     # tag de imagen (lo escribe el CD), réplicas
<app>/<env>/infrastructure.yaml          # recursos, nombre del secreto y de la tabla DynamoDB
```

Orden de aplicación (el último gana): global → shared → shared-envvars → app → infrastructure.
