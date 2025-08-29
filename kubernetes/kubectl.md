# kubectl Notes

## 📝 Set default editor
Set `KUBE_EDITOR` to Visual Studio Code (assumes `code` is in PATH):

```
export KUBE_EDITOR='code --wait'
```

Now running:

```
kubectl edit ...
```
will open the YAML file in Visual Studio Code.

## 📂 Copy files from a pod
Copy a file or directory from pod to local path:

```kubectl cp [namespace/]pod-name:/path/to/file /local/path```

## 🗑 Delete pods by label
Delete pods in a namespace matching a label selector:

```kubectl delete pods -l <label> -n <ns>```

## 🗑 Force delete a namespace
Force deletion of a stuck namespace:

```kubectl delete namespace <namespace> --grace-period=0 --force```

## 🛠 Remove finalizers from a namespace
If namespace is stuck in Terminating state:

```kubectl patch namespace <ns> -p '{"metadata":{"finalizers":[]}}' --type=merge```