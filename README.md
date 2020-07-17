# Kubelet [![Docker Repository on Quay](https://quay.io/repository/poseidon/kubelet/status "Image Repository on Quay")](https://quay.io/repository/poseidon/kubelet) [![Dockerhub](https://img.shields.io/badge/container-dockerhub-blue)](https://hub.docker.com/r/psdn/kubelet)

`kubelet` provides a [container image](https://quay.io/repository/poseidon/kubelet) packaging the upstream Kubernetes `kubelet` and dependencies, for use on container-optimized OS distributions. `kubelet` is a component of the [Typhoon](https://github.com/poseidon/typhoon) Kubernetes distribution.

## Repositories

Typhoon publishes Kubelet container images to repositories ([detailed policy](https://typhoon.psdn.io/topics/security/#container-images)).

* [quay.io/poseidon/kubelet](https://quay.io/repository/poseidon/kubelet) (official)
* [docker.io/psdn/kubelet](https://hub.docker.com/repository/docker/psdn/kubelet) (fallback)

Two tag styles indicate the build strategy:

* Single and multi-arch images are published by Typhoon infrastructure (e.g. `v1.18.4`, `v1.18.4-amd64`, `v1.18.4-arm64`)
* Quay or Docker autobuilt images (e.g. `build-SHA` on Quay, `build-master` on Dockerhub))

## Packages

The [debian-iptables](https://github.com/kubernetes/kubernetes/tree/master/build/debian-iptables) base provides `conntrack`, `ebtables`, `ipset`, `kmod`, and `netbase`.

Kubelet also requires:

* `ca-certificates` - https://github.com/kubernetes/kubernetes/pull/7755
* `ceph-common` - https://github.com/kubernetes/kubernetes/pull/34416
* `cifs-utils` - https://github.com/kubernetes/kubernetes/pull/34416
* `e2fsprogs` (`mkfs.ext4`) - https://github.com/kubernetes/kubernetes/issues/52789
* `xfsprogs` - https://github.com/kubernetes/kubernetes/pull/56937
* `ethtool` - https://github.com/kubernetes/kubernetes/pull/18273
* `glusterfs-client` - https://github.com/kubernetes/kubernetes/pull/32686
* `jq` - https://github.com/coreos/bugs/issues/1706
* `kmod` (`modprobe`) - https://github.com/kubernetes/kubernetes/pull/53642
* `nfs-common` - https://github.com/kubernetes/kubernetes/pull/30320
* `udev` (`udevadm`)- https://github.com/kubernetes/kubernetes/pull/61357
* `iproute2` - https://github.com/kubernetes/kubernetes/pull/92581

### kubectl

`kubectl` (no dependencies) is also included for convenience (e.g. use pre-pulled Kubelet image to `kubectl delete node` on preemption)
