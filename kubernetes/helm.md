# Helm Notes

## 📥 Add and update repos
Add a repo (example: Argo) and update repositories:
```
helm repo add bitnami https://charts.bitnami.com/bitnami

helm repo update
```

## 🚀 Install a chart
Install a release from a chart:
```
helm install <release-name> <chart>
```

Example:
```
helm install my-argo bitnami/argo-cd
```

## Show chart values
Display available values for customization:
```
helm show values <chart> > values.yaml
```

Example:
```
helm show values bitnami/argo-cd > values.yaml
```

## ⚙️ Install with custom values
Install a chart with your own configuration:
```
helm install <release-name> <chart> -f values.yaml
```

Example:
```
helm install argo-cd bitnami/argo-cd -f values.yaml
```

## ⬆️ Upgrade a release

Update an existing release with new values:
```
helm upgrade <release-name> bitnami/argo-cd -f values.yaml
```

Example:
```
helm upgrade argo-cd bitnami/argo-cd -f values.yaml
```

## 📊 List releases
List installed releases in a namespace:

```
helm list -n <namespace>
```

## 🗑 Uninstall a release
Remove a release from a namespace:
```
helm uninstall <release-name> -n <namespace>
```

## 📦 Download (pull) a chart
Download a specific chart version (example: argo-cd 10.0.4):
```
helm pull bitnami/argo-cd --version 10.0.4
```

Unpack the chart:
```
tar -xvzf argo-cd-10.0.4.tgz
```

```
ls argo-cd/
Chart.lock	Chart.yaml	README.md	charts		crds		templates	values.yaml
```