##### accessing the general settings
- this is done with the help of `options` object
```javascript
var user = options.globalSettings.<settings_name>
```

##### accessing the encrypted settings
- this is done with the `waylay` object
```javascript
let SMS_APIToken = await waylay.vault.get("<settings_name");
```