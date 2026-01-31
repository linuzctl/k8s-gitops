# k8s-gitops

High-availability Kubernetes cluster setup using kubeadm, managed declaratively via GitOps.

This repository serves as the source of truth for my private Kubernetes cluster.

## Cluster Management

Cluster provisioning and lifecycle management are handled using a custom Ansible playbook [kubernetes-ansible](https://github.com/linuzctl/kubernetes-ansible).

## Repository Structure

A high-level overview of the repository layout:

```sh
📁 k8s-gitops
├── 📁 apps                  # applications
├── 📁 cluster               # Flux configuration
│   ├── 📁 kustomizations    # Flux Kustomization objects for applications 
│   ├── 📁 flux-system       # Flux bootstrap components (GitOps controllers)
│   ├── 📁 helmrepositories  # Helm repositories definitions for applications
│   └── 📁 notifications     # Notification configurations
└── 📁 crds                  # crds
```

- **.github** directory contains GitHub related files

#### Details
- Each application lives in its own directory under `apps/` and is managed by a Flux Kustomization object located in `cluster/kustomizations`.
- This setup allows each application to be reconciled independently, so deleting or updating one app does not affect the others.
- Exceptions occur when an application depends on another; in such cases, dependencies are explicitly specified in the Kustomization configuration.

## Secrets Management

Secrets are encrypted using [SOPS](https://github.com/getsops/sops) with [age](https://github.com/FiloSottile/age) keys, allowing safe storage directly in Git and secure collaboration.

## Hardware

| Device               | Num | OS Disk Size               | Data Disk Size              | Ram  | OS  | Role                            |
|----------------------|-----|----------------------------|-----------------------------|------|-----|---------------------------------|
| HP EliteDesk 800 G4  | 3   | 256GB Samsung NVMe         | —                           | 16GB | -   | Kubernetes Control Plane        |
| Minisforum MS-01     | 3   | 1TB Samsung NVMe 990 Pro   | 4TB Samsung NVMe 990 Pro    | 64GB | -   | Kubernetes Worker Nodes         |
| Minisforum N5 Pro    | 1   | 1TB Samsung NVMe 990 Pro   | 5x22TB Seagate Exos X22     | 64GB | -   | NAS                             |

> Note: Hardware was purchased before the AI-driven price explosion

## Disclaimer

This cluster is built and operated by a single person and is tailored to my personal needs and learning goals.

The primary objective of this project is learning and experimentation. While the configuration works for my environment, it may not be suitable for yours.

If you plan to build something similar:
- Do not blindly copy & paste
- Take time to understand what each component does
- Adapt ideas to your own requirements and constraints

Getting inspired by how others design and operate their infrastructure is always valid — just make sure you understand why things are done a certain way before adopting them.
