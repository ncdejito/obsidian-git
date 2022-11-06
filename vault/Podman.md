[[DevOps]]

Pros
Easier networking - can talk over localhost!
Daemon-less - very secure
Same commands as docker
Can create k8s yaml files
Can install as a snap

Cons
doesnt have installable arm64 snap in Ubuntu Core

Enable device
```
podman run --device=/dev/sdc:/dev/xvdc:rwm
```