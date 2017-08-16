# Sysdig Monitor Agent deployment for Kubernetes 1.7+

1. create service account for Sysdig Agent:
   `kubectl create -f sysdig-account.yaml`
2. create secrets for Agent key and tags (fill in valid data first):
   `kubectl create -f sysdig-secret.yaml`
3. if you want to expose a configuration file using a Kubernetes ConfigMap run first:
   `kubectl create configmap sysdig-agent-config --from-file=dragent.yaml`
   and then:
    `kubectl create -f sysdig-daemonset-config.yaml`
   
   otherwise, if you want to configure using environment variables:
    `kubectl create -f sysdig-daemonset.yaml`.
