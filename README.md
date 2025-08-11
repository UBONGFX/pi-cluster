# 🏗️ Pi Cluster - Talos Kubernetes Homelab 

## 🚧 Work in progress 🚧

A complete Kubernetes homelab setup running on 4 Raspberry Pi 5 devices with Talos Linux, featuring GitOps deployment with ArgoCD.

## Architecture Overview

- **4x Raspberry Pi 5 8GB** running Talos Linux
- **Kubernetes cluster** with 1 control plane + 3 worker nodes
- **GitOps deployment** using ArgoCD
- **Applications**: Keycloak, Home Assistant, and custom applications

## Repository Structure

```
├── talos/                    # Talos Linux configuration
│   ├── configs/             # Node configurations
│   ├── patches/             # Configuration patches
│   └── scripts/             # Bootstrap and management scripts
├── kubernetes/              # Kubernetes manifests
│   ├── infrastructure/      # Core infrastructure components
│   │   ├── argocd/         # ArgoCD setup
│   │   ├── cert-manager/   # Certificate management
│   │   ├── ingress-nginx/  # Ingress controller
│   │   ├── metallb/        # Load balancer
│   │   └── longhorn/       # Storage solution
│   ├── applications/        # Application deployments
│   │   ├── keycloak/       # Identity and access management
│   │   ├── home-assistant/ # Home automation
│   │   └── monitoring/     # Prometheus, Grafana stack
│   └── argocd-apps/        # ArgoCD Application definitions
├── custom-apps/             # Custom application source code
│   └── .gitkeep            # Placeholder for your apps
├── hardware/                # Hardware designs and documentation
│   └── case/               # Custom 3D printed case/rack
│       ├── stl/           # 3D printable files
│       ├── docs/          # Assembly and print guides
│       └── images/        # Assembly photos
├── docs/                    # Documentation
└── scripts/                 # Utility scripts
```

## Quick Start

1. [Hardware Setup](docs/hardware-setup.md)
2. [Talos Installation](docs/talos-installation.md)
3. [Kubernetes Bootstrap](docs/kubernetes-bootstrap.md)
4. [ArgoCD Setup](docs/argocd-setup.md)
5. [Application Deployment](docs/application-deployment.md)

## Components

### Infrastructure
- **Talos Linux**: Immutable OS for Kubernetes
- **ArgoCD**: GitOps continuous delivery
- **MetalLB**: Load balancer for bare metal
- **Ingress-NGINX**: Ingress controller
- **Cert-Manager**: Automatic TLS certificates
- **Longhorn**: Distributed storage

### Applications
- **Keycloak**: Identity and access management
- **Home Assistant**: Home automation platform
- **Monitoring Stack**: Prometheus, Grafana, AlertManager

## Network Configuration

- **Cluster Network**: 10.244.0.0/16 (Pods)
- **Service Network**: 10.96.0.0/16 (Services)
- **MetalLB Pool**: 192.168.1.100-192.168.1.110 (adjust for your network)

## Prerequisites

- 4x Raspberry Pi 5 (8GB RAM)
- 4x GeeekPi P31 M.2 NVMe M-Key PoE+ HAT with Active Cooler
- 4x M.2 NVMe SSD (2230/2242, 128GB+)
- NETGEAR GS305P PoE+ Switch (63W)
- Cat8 Ethernet cables (0.15m)
- SD Cards (32GB+ each, for initial setup)
- kubectl
- talosctl

## Hardware Features

- **PoE+ Power**: Single power source, no individual adapters needed
- **NVMe Storage**: 10-50x faster than SD cards
- **Active Cooling**: Better thermal management under load
- **Gigabit Networking**: Full bandwidth per node with Cat8 cables
- **Future-Proof**: 40 Gbit/s rated cables for potential upgrades

## Why This Setup?

**Cost vs. Learning**: While cloud providers or used enterprise hardware might be more cost-effective for pure compute, this project prioritizes:

- 🎯 **Hands-on Learning**: Building Kubernetes expertise with real hardware
- 🔧 **Custom Engineering**: Designing and 3D printing a purpose-built case
- ⚡ **Modern Tech Stack**: PoE+, NVMe, Talos Linux, GitOps workflows
- 🏠 **Home Integration**: Perfect for home automation and personal services
- 🌱 **Scalable Foundation**: Skills transfer directly to production environments
- 😊 **Pure Enjoyment**: There's something magical about running your own infrastructure

This isn't just a cluster—it's a learning laboratory, conversation starter, and a beautifully engineered piece of functional art that happens to run your applications. Sometimes the journey and knowledge gained are worth more than raw cost efficiency.

**Perfect for**: Kubernetes enthusiasts, homelab hobbyists, learning-focused engineers, and anyone who gets excited by well-engineered hardware solutions.