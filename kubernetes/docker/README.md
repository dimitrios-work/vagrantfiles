Kubernetes using docker, 3 VMs for etcd, 1 for master, one for flannel master, two minions. Around 7-8GB RAM total, can be trimmed.

master:
```
vagrant@master:~$ /vagrant/hyperkube kubectl get cs
NAME                 STATUS    MESSAGE              ERROR
scheduler            Healthy   ok
controller-manager   Healthy   ok
etcd-1               Healthy   {"health": "true"}
etcd-0               Healthy   {"health": "true"}
etcd-2               Healthy   {"health": "true"}
vagrant@master:~$ /vagrant/hyperkube kubectl get no
NAME      STATUS    AGE
minion1   Ready     1h
vagrant@master:~$ /vagrant/hyperkube kubectl cluster-info
Kubernetes master is running at http://localhost:8080
vagrant@master:~$
```

etcd:
```
vagrant@etcd1:~$ /vagrant/etcd-v2.3.6-linux-amd64/etcdctl get /coreos.com/network/config
{ "Network": "172.16.0.0/16" }

vagrant@etcd1:~$
```
and
```
vagrant@etcd1:~$ /vagrant/etcd-v2.3.6-linux-amd64/etcdctl ls / --recursive
/coreos.com
/coreos.com/network
/coreos.com/network/config
/coreos.com/network/subnets
/coreos.com/network/subnets/172.16.6.0-24
/registry
/registry/ranges
/registry/ranges/serviceips
/registry/ranges/servicenodeports
/registry/namespaces
/registry/namespaces/default
/registry/services
/registry/services/endpoints
/registry/services/endpoints/default
/registry/services/endpoints/default/kubernetes
/registry/services/specs
/registry/services/specs/default
/registry/services/specs/default/kubernetes
/registry/serviceaccounts
/registry/serviceaccounts/default
/registry/serviceaccounts/default/default
/registry/events
/registry/events/default
/registry/events/default/minion1.1455489a1d2d0b79
/registry/events/default/minion1.1455489a2e500df7
/registry/events/default/minion1.1455489a31684f1f
/registry/events/default/minion1.1455489c87231358
/registry/minions
/registry/minions/minion1
vagrant@etcd1:~$
```

