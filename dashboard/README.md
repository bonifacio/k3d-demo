# Dashboard

## Deploy do dashboard
```
$ export GITHUB_URL=https://github.com/kubernetes/dashboard/releases
$ export VERSION_KUBE_DASHBOARD=$(curl -w '%{url_effective}' -I -L -s -S ${GITHUB_URL}/latest -o /dev/null | sed -e 's|.*/||')
$ kubectl create -f https://raw.githubusercontent.com/kubernetes/dashboard/$VERSION_KUBE_DASHBOARD/aio/deploy/recommended.yaml

```
## Deploy da configuração do admin-user
```
$ kubectl create -f dashboard-admin-user.yml -f dashboard-admin-user-role.yml
``` 

## Obtendo o token de acesso
```
$ kubectl -n kubernetes-dashboard describe secret admin-user-token | grep '^token'
```

## Acessando o dashboard
```
$ kubectl proxy
```
Endereço do dashboard: http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

#### Referência: https://rancher.com/docs/k3s/latest/en/installation/kube-dashboard/