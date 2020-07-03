
```
mkdir acm-demo
cd acm-demo
nomos init
```

```
cat > acm-demo/namespaces/production>prod-ns.yaml <<EOF
apiVersion: v1
kind: Namespace
metadata:
  name: production
EOF
```

```
cat > acm-demo/system/repo.yaml <<EOF
apiVersion: configmanagement.gke.io/v1
kind: Repo
metadata:
  creationTimestamp: null
  name: repo
spec:
  version: 1.0.0
status:
  import:
    lastUpdate: null
  source: {}
  sync:
    lastUpdate: null
EOF
```

### Watch namespace, Delete namespace, See namespace come back to life
```
# Run these commands in separate terminals
kubectl get ns --watch
kubectl delete ns production
```
