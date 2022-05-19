

```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo list
helm search repo drupal
helm search repo content
helm search repo drupal --versions
helm install mysite bitnami/drupal
helm install mysite bitnami/drupal --values values.yaml
helm install mysite bitnami/drupal --set drupalUsername=admin
helm list
helm list --all-namespaces
helm upgrade mysite bitnami/drupal 
helm repo update
helm uninstall mysite
helm uninstall mysite --namespace first
````
