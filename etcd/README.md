```
vagrant@etcd1:~$ tail -f /tmp/etcd-run.log
2016-06-04 22:39:05.153321 W | etcdserver: failed to reach the peerURL(http://etcd3-pub:2380) of member 2b5ddd20d38d2693 (Get http://etcd3-pub:2380/version: dial tcp 192.168.1.124:2380: i/o timeout)
2016-06-04 22:39:05.153360 W | etcdserver: cannot get the version of member 2b5ddd20d38d2693 (Get http://etcd3-pub:2380/version: dial tcp 192.168.1.124:2380: i/o timeout)
2016-06-04 22:39:09.748674 W | etcdserver: failed to reach the peerURL(http://etcd3-pub:2380) of member 2b5ddd20d38d2693 (Get http://etcd3-pub:2380/version: dial tcp 192.168.1.124:2380: getsockopt: no route to host)
2016-06-04 22:39:09.748716 W | etcdserver: cannot get the version of member 2b5ddd20d38d2693 (Get http://etcd3-pub:2380/version: dial tcp 192.168.1.124:2380: getsockopt: no route to host)
2016-06-04 22:39:12.479071 W | rafthttp: the connection to peer 2b5ddd20d38d2693 is unhealthy
2016-06-04 22:39:13.752346 W | etcdserver: failed to reach the peerURL(http://etcd3-pub:2380) of member 2b5ddd20d38d2693 (Get http://etcd3-pub:2380/version: dial tcp 192.168.1.124:2380: getsockopt: connection refused)
2016-06-04 22:39:13.752434 W | etcdserver: cannot get the version of member 2b5ddd20d38d2693 (Get http://etcd3-pub:2380/version: dial tcp 192.168.1.124:2380: getsockopt: connection refused)
2016-06-04 22:39:16.263587 I | rafthttp: the connection with 2b5ddd20d38d2693 became active
2016-06-04 22:39:17.754655 I | etcdserver: updating the cluster version from 2.2 to 2.3
2016-06-04 22:39:17.756652 N | etcdserver: updated the cluster version from 2.2 to 2.3


----------


vagrant@etcd1:~/etcd-v2.3.6-linux-amd64$ ./etcdctl cluster-health
member 2a710adb0b21a748 is healthy: got healthy result from http://etcd2-pub:2379
member 2b5ddd20d38d2693 is healthy: got healthy result from http://etcd3-pub:2379
member 8ab62b3125370c1f is healthy: got healthy result from http://etcd1-pub:2379
cluster is healthy
vagrant@etcd1:~/etcd-v2.3.6-linux-amd64$
```
