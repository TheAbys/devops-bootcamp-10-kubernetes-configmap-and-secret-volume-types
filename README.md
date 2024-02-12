# 12 - ConfigMap & Secret Volume Types

Create the deployment

    kubectl apply -f mosquitto-without-volumes.yaml

Exec into the container

    kubectl exec -it mosquitto-6564db7cb5-lrlql -- /bin/sh

Update the configuration for the mosquitto deployment, add volumes and mounts

Execute all configuration files

    kubectl apply -f config-file.yaml
    kubectl apply -f secret-file.yaml
    kubectl apply -f mosquitto.yaml


The config file and secret file get mounted into the pod.
This are local volume types.