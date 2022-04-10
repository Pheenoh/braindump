---
aliases: [informer, SharedInformer]
---
# SharedInformer
#k8s 


Multiple [[controller|controllers]] need to care about multiple [[resources]], so a SharedInformer functions as a sharded local cache between the controllers.