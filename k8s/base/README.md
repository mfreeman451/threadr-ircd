#

## oper passwords (secrets)

```yaml
# secret.yaml
apiVersion: v1
kind: Secret
metadata:
  name: ergo-secrets
  namespace: default
type: Opaque
stringData:
  admin-password: "changeme"  # Change this in production

```

or

```shell
kubectl create secret generic ergo-secrets \
  --from-literal=admin-password=$(openssl rand -base64 32) -n threadr-ircd
```