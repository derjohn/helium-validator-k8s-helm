# helium-validator-k8s-helm
A Helm Chart to run a Helium Validator with helm

# Requirements
Obviously you'll need a running Kubernetes cluster and helm3.
Also you need an ingress controller that supports 'spec.externalIp' 

# Installation
```helm upgrade --install helium-validator ./helium-validator --namespace my-validator --create-namespace --set publicIp=127.0.1.2```

Likewise the removal is done with
```helm uninstall helium-validator --namespace my-validator``` 

# Access the Pod
```kubectl -n my-validator exec -it helium-validator -- sh```

Inside it you can run the validator cli like
```/opt/miner/bin/miner peer book -s```

# Versions
This Helm Chart supports image.tag, so you can override the container version with
```helm upgrade --install --set image.tag=validatorvariant47.11```

# Configuration
See values.yaml in this repo.

# Todo
This is version 0.1.1 of the chart. There is probably stuff to do :) ... PRs welcome.
 
# Managed Service
If this is too technical for for, or you want to evade legal and tax issues, you can book a validator as managed service here:
[https://validators.cloud](https://validators.cloud)
