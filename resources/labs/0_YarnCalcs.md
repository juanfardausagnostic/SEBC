```
1. Adjust OS reserver memory to 24 GB
>> OS need more reserve memory if server have high physical memory
```
```
2. Adjust Task Container Settings
>> Increase memory for reducer container (mapreduce.reduce.memory.mb, )
  mapreduce.reduce.memory.mb = 2*mapreduce.map.memory.mb = 2048
>> Increase java heap for reduce container
  mapreduce.reduce.java.opts.max.heap = 0.8*mapreduce.reduce.memory.mb
```
```
3. Adjust MapReduce AM Settings
>> Increase AM memory to be same as yarn.scheduler.minimum-allocation-mb
  yarn.app.mapreduce.am.resource.mb = 1024
>> Increase yarn.app.mapreduce.am.resource.command-opts (refer to AM memory adjust)
  yarn.app.mapreduce.am.resource.command-opts = 0.8*yarn.app.mapreduce.am.resource.mb

```
