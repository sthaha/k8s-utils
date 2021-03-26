# OpenShift `tcpdump` Tool

A tool to capture network packets from multiple pods

## Installation

```
git clone https://github.com/sthaha/k8s-utils

## assuming ~/bin is in your PATH
ln -sf $PWD/k8s-utils/tools/oc-oc-tools-tcpdump ~/bin

## Verify by running
oc tools tcpdump -h
```

## Usage

```
# capture network traffic including the node traffic from all openshift dns pods
oc tools tcpdump -n openshift-dns


# capture network traffic from nginx (label app=nginx) pods only
# deployed to 'web' namespace

oc tools tcpdump --no-nodes -n web -l app=nginx
```


## Todo

- [ ] Allow flags to be passed to `tcpdump`
- [ ] Port the logic to ksniff to allow multiple pods / deployment / daemonset
      to be packet captured


## Credits

* Inspired by [ksniff](https://github.com/eldadru/ksniff) but took a slight different
  approach

