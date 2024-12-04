##### Overall flow
- initiate mongo on docker
- initiate the replica set, but change the address from localhost to 0.0.0.0 to bind to any port
- find the IP of the host machine by using `HOSTNAME -I` option
- connect to the mongo using the required IP and the port number

### changes to be once replicaset is initialized
- get the current config into a variable called the `cfg` using this
```
cfg=rs.conf();
```
- this is a JSON object. find the required name in the members array and edit it to the required IP
```
cfg.members[0].host='xxx.xxx.xx.xx:27017'
```
- reapply this config to the replicaset
```
rs.reconfig(cfg, {force:true})
```
use the `{force:true` flag only if we are connecting from another IP than the already initialized IP