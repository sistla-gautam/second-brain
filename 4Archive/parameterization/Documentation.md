# URL parameterization
This is an additional feature that is working on top of webscript calling

## Initial config
- setup a dashboard
- configure the data mapping with variables that will call the required webscripts
- ![[Pasted image 20250403132313.png]]
- ![[Pasted image 20250403132331.png]]

The following Data IDs are set
- `something` - `var4`
- `abcd` - `Map` (`Map` is the name of the webscript)

The following variables are set
- `variable1` - `100`
- `var1` - `tank1`
- `var3` - `tank3`
- `var4` - `test-map` (`test-map` is the name of the webscript)

---
## Initial behavior
- When the data ID `abcd` is called, the webscript `Map` gets triggered
	- `abcd` -> `Map`
- When the data ID `something` is called, the variable `var4` is invoked. This in turn contains the `test-map` webscript
	- `something` -> `var4` -> `test-map`

---
## URL parameter behavior
- the dashboard will now allow us to pass additional parameters in the URL
- the variables will take these values from the URL parameters and use them in the variables

###### Lets assume the following query parameters are sent in the URL
- `var4` is `Map`
	- the URL will contain the following query parameters `...?var4=Map`
	- ![[Pasted image 20250403134524.png]]
- this will change the `var4` to the value `Map`
- now, the data ID `something` will return a call to the webscript `Map`

###### Lets assume a different scenario
- Add the following data ID to the data ID part
	- `test` - `var5`
	- ![[Pasted image 20250403160051.png]]
- Now calling `test` will not give us any webscript calls, as no value is assigned to `var5`

###### Additional case to look out for
- When passing the previous scenario, we also pass the value of `var5` in the URL parameter
- Lets set `var5` value to `Map`
- Upon calling `test`, it will not take the value of `var5`. This will in turn take the value of `Map` and a call to the Webscript `Map` will be made


**NOTE**: Only variables and `var` values will be replaced. Trying to replace the DataID or any other value will not replace the value from the URL

