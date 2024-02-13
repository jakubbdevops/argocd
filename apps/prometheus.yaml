apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: prometheus-stack
  namespace: argocd
  finalizers:
  - resources-finalizer.argocd.argoproj.io
spec:
  project: default
  source:
    repoURL: https://prometheus-community.github.io/helm-charts
    chart: kube-prometheus-stack
    targetRevision: '56.6.2'
    helm:
      values: |-
        grafana:
          enabled: true
          ingress:
            enabled: false
  destination:
    namespace: monitoring
    name: in-cluster
  syncPolicy:
      automated:
      prune: true
      selfHeal: true
    syncOptions:
      - CreateNamespace=true