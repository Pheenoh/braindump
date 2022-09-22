---
aliases: [controllers]
---
# Controller
#k8s 

A controller on a Kubernetes cluster implements a [[controller pattern]].

A controller is made up of a [[SharedInformer]] and a [[Workqueue]].

# Controller Psuedo-code
```go
controller.informer = cache.NewSharedInformer(...)
controller.queue = workqueue.NewRateLimitingQueue(workqueue.DefaultControllerRateLimiter())

controller.informer.Run(stopCh)

if !cache.WaitForCacheSync(stopCh, controller.HasSynched)
{
    log.Errorf("Timed out waiting for caches to sync"))
}

// Now start processing
controller.runWorker()
```