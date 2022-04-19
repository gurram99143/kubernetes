```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-latest.x86_64.rpm
sudo rpm -Uvh minikube-latest.x86_64.rpm
```

```
minikube start
```

```
If you already have kubectl installed, you can now use it to access your shiny new cluster:

kubectl get po -A
Alternatively, minikube can download the appropriate version of kubectl and you should be able to use it like this:

minikube kubectl -- get po -A
You can also make your life easier by adding the following to your shell config:

alias kubectl="minikube kubectl --"

```

