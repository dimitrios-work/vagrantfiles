use built in chaos monkeys by modifying: ```--chaos-chance=0``` (kubelet)

faster (or not) failovers (controller):
```
      --node-monitor-grace-period=40s: Amount of time which we allow running Node to be unresponsive before marking it unhealty. Must be N times more than kubelet's nodeStatusUpdateFrequency, where N means number of retries allowed for kubelet to post node status.
      --node-monitor-period=5s: The period for syncing NodeStatus in NodeController.
      --node-startup-grace-period=1m0s: Amount of time which we allow starting Node to be unresponsive before marking it unhealty.
      --node-sync-period=10s: The period for syncing nodes from cloudprovider. Longer periods will result in fewer calls to cloud provider, but may delay addition of new nodes to cluster.
      --pod-eviction-timeout=5m0s: The grace period for deleting pods on failed nodes.
```
