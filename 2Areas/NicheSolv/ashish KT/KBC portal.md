- only for KBC
- view only mode
- salma and saradhi - only 2 people responsible for portal

#### files to not touch
webpack.config.js
	do not touch. the max we can do is only touch the appUniqueName. will only be required when we need to create a new application
	we can also do the same when we need to run locally
metadata.js
jest files

##### how to package the application
```bash
npm run package:dev
```

### files
- createDevPackages
	- script that will create the .zip file for the different applications
### running locally
- change the name and the URL - `webpack.config.js`, `app.js`, `app-routing.js`
	- change the routing to `react-local` in the `baseHref` 
```javascript
const baseHref = `/${process.env.REACT_APP_BASE_PATH}/portal/dashboard`;
const baseHref = `/${process.env.REACT_APP_BASE_PATH}/portal/react-local`;
```
- once we do that, run the command
	- `npm run start`
- create a new application in the Acuity and point it to local (follow `Readme.me`)
- the local should now be running 