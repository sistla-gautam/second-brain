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
use the `{force:true}` flag only if we are connecting from another IP than the already initialized IP

---

## mongo rs.config()

```JSON
{
  _id: 'rs0',
  version: 5,
  term: 8,
  members: [
    {
      _id: 1,
      host: '10.202.64.14:27017',
      arbiterOnly: false,
      buildIndexes: true,
      hidden: false,
      priority: 1,
      tags: {},
      secondaryDelaySecs: Long('0'),
      votes: 1
    },
    {
      _id: 2,
      host: '10.202.64.16:27017',
      arbiterOnly: false,
      buildIndexes: true,
      hidden: false,
      priority: 1,
      tags: {},
      secondaryDelaySecs: Long('0'),
      votes: 1
    }
  ],
  protocolVersion: Long('1'),
  writeConcernMajorityJournalDefault: true,
  settings: {
    chainingAllowed: true,
    heartbeatIntervalMillis: 2000,
    heartbeatTimeoutSecs: 10,
    electionTimeoutMillis: 10000,
    catchUpTimeoutMillis: -1,
    catchUpTakeoverDelayMillis: 30000,
    getLastErrorModes: {},
    getLastErrorDefaults: { w: 1, wtimeout: 0 },
    replicaSetId: ObjectId('665596d6fb1fcbb1051291f4')
  }
}
```

```
{
  _id: 'rs0',
  version: 5,
  term: 8,
  members: [
    {
      _id: 1,
      host: '10.202.64.14:27017',
      arbiterOnly: false,
      buildIndexes: true,
      hidden: false,
      priority: 1,
      tags: {},
      secondaryDelaySecs: Long('0'),
      votes: 1
    },
    {
      _id: 2,
      host: '10.202.64.16:27017',
      arbiterOnly: false,
      buildIndexes: true,
      hidden: false,
      priority: 1,
      tags: {},
      secondaryDelaySecs: Long('0'),
      votes: 1
    }
  ],
  protocolVersion: Long('1'),
  writeConcernMajorityJournalDefault: true,
  settings: {
    chainingAllowed: true,
    heartbeatIntervalMillis: 2000,
    heartbeatTimeoutSecs: 10,
    electionTimeoutMillis: 10000,
    catchUpTimeoutMillis: -1,
    catchUpTakeoverDelayMillis: 30000,
    getLastErrorModes: {},
    getLastErrorDefaults: { w: 1, wtimeout: 0 },
    replicaSetId: ObjectId('665596d6fb1fcbb1051291f4')
  }
}
```