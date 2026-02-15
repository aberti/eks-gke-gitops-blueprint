# echo app (local-first)

## Apply
```bash
kubectl apply -k app/echo/k8s
kubectl -n echo get all
```

## Access (local)
Port-forward:
```bash
kubectl -n echo port-forward svc/echo 8080:80
curl -i http://127.0.0.1:8080/
```

Ingress: this repo provides an `Ingress` for `echo.local`, but you must have an ingress controller installed in your cluster for it to work.

## Teardown
```bash
kubectl delete -k app/echo/k8s
kubectl delete ns echo --ignore-not-found
```
