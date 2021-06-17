# k3d-demo

## Pré requisitos
- docker
- kubctl

## Instalação
```
$ curl -s https://raw.githubusercontent.com/rancher/k3d/main/install.sh | bash
```
## Exemplo
```
$ k3d cluster create demo --servers 3 --agents 3
$ k3d cluster delete demo
```

#### Referência: https://k3d.io/#install-current-latest-release