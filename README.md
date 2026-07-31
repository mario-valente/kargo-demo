# kargo-demo

App de demonstração usada na POC do [Kargo](https://kargo.io) em
[poc-kargo](https://github.com/mario-valente/poc-kargo) (clusters kind: hub, staging, prod).

- `base/`: manifests kustomize da aplicação (nginx).
- `stages/staging/`, `stages/prod/`: overlays por estágio.

O Kargo escreve nas branches `stage/staging` e `stage/prod` deste repositório durante as
promoções (padrão GitOps: Git é a fonte de verdade, Argo CD sincroniza a partir daqui).
