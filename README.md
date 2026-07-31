# kargo-demo

App de demonstração usada na POC do [Kargo](https://kargo.io) em
[poc-kargo](https://github.com/mario-valente/poc-kargo) (clusters kind: hub, staging, prod).

- `base/`: manifests kustomize da aplicação (nginx).
- `environments/non-prod/`, `environments/prod/`: overlays por ambiente.

Modelo **mono-branch**: tudo vive na branch `main`, organizado por pastas
(`environments/<ambiente>/`). O Kargo promove atualizando o `kustomization.yaml`
do ambiente correspondente e commitando direto na `main` — sem branches por
estágio. O Argo CD sincroniza cada `Application` a partir de
`main:environments/<ambiente>`.
