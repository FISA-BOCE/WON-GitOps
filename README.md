# WON-GitOps

WON 카드/증권 채널계 EKS 배포 선언을 관리하는 GitOps 레포입니다.

Terraform 레포는 AWS 인프라와 ArgoCD 설치를 담당하고, 이 레포는 ArgoCD가 동기화할 Kubernetes/Helm 배포 상태를 관리합니다.

## Directory Layout

```text
.
├── apps/
│   ├── card-channel-server/
│   │   └── templates/
│   └── invest-channel-server/
│       └── templates/
├── argocd/
│   ├── card/
│   └── securities/
└── environments/
    ├── card/
    │   ├── dev/
    │   └── prod/
    └── securities/
        ├── dev/
        └── prod/
```

## Responsibilities

- `apps/`: 앱별 공통 Helm chart를 관리합니다.
- `environments/`: 카드/증권 및 환경별 values 파일을 관리합니다.
- `argocd/`: 각 EKS 클러스터의 ArgoCD Application manifest를 관리합니다.
