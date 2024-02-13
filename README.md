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

# 13 - StatefulSet - Deploying Stateful Applications

Only the master pod can read and write.
The replica pods can only read.
Everytime a new replica pod is created it copies the data from the previous pod.
This also means theoretically, if pods never die, the data will not get lost. But this means obviously if all pods crash at the same time data is lost.
Therefore it is still required to keep data peristant.

StatefulSet pods get fixed ordered names while a Deployment does not.
Deletion will start from the max number and then delete the number zero.

The created pods also get a fixed individual DNS name like mysql-0.svc2 which is podname + servicename.

Containerized environments are not perfect for Stateful applications.