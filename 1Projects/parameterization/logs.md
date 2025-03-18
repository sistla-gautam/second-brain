
---
### initial config
- configure `something` to hold some resource value
- pass `something={10}` as URL params

##### logs
```js
  logger.debug('updateMappingDataWithParams: mappingData', mappingData)
```
- contains the following logs
```json
{DataID: 'something', DataCategory: 'JSON', IsResourceVar: false, Resource: '460e4719-add3-4054-9e2e-c98ecce53dde', IsResourceType: false, …}
```

```js
      logger.debug(
        'updateMappingDataWithParams: replacementKey',
        replacementKey
      )
```
- contains the following logs
```json
{something: '{10}'}
```

- mappingData -> data mapping side
- replacementKey -> URL params

---
variables to keep a look at
- `resolvedDataMappingList` - contains something, what type of data it is and the webscript part
- `resolvedVaribaleItems` - contains the different variables that are part of the data mapping and their respective values
- `nonVarMap` - collection of variables used in data mapping


---
# notes (updated requirements)
- mapping with only webscript name
	- https://webscripts.dev.apps.yokogawa.build/api/v1/de9788ec-bf1d-4c33-b112-820996790f7b/<webscript-name>
- mapping with URL param (var4=abcd)
	- this is with the var4 = webscript-name
	- https://webscripts.dev.apps.yokogawa.build/api/v1/de9788ec-bf1d-4c33-b112-820996790f7b/abcd
- mapping with URL param with addition params for webscipt
`{var4}?param1={var1}&param2={var3}&param3=10`
	- https://webscripts.dev.apps.yokogawa.build/api/v1/de9788ec-bf1d-4c33-b112-820996790f7b/abcd?param1=tank1&param2=tank3&param3=10
- `http://127.0.0.1:5500/bieditor/dashboards/URL-test?var4=abcd&var1=xyz&param3=20`
	- https://webscripts.dev.apps.yokogawa.build/api/v1/de9788ec-bf1d-4c33-b112-820996790f7b/abcd?param1=xyz&param2=tank3&param3=10
> only value with the keyword `var` need to be considered as variable. param3 here will not be replaced

