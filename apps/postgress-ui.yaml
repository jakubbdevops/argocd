apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: postgres-ui
  namespace: argocd
spec:
  project: default
  source:
    repoURL: "https://github.com/zalando/postgres-operator.git"
    path: ui/manifests
    targetRevision: HEAD
  destination:
    server: https://kubernetes.default.svc
    namespace: postgres
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
    syncOptions:
      - CreateNamespace=true