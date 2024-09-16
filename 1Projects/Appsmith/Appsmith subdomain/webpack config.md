## standard webpack config
- contains a `module.exports` JSON object that contains the required config data
- we need to focus on the `output` object
- the `output` object will contain the following keys
	- path
	- publicPath
	- pathinfo

##### path
the output directory as an absolute path
```javascript
const path = require('path');

module.exports = {
  //...
  output: {
    path: path.resolve(__dirname, 'dist/assets'),
  },
};
```
##### publicPath
```javascript
const path = require('path');

module.exports = {
  //...
  output: {
    path: path.resolve(__dirname, 'public/assets'),
    publicPath: 'https://cdn.example.com/assets/',
  },
};
```
##### pathInfo
tells webpack to include comments in bundles with information about the contained modules
```javascript
module.exports = {
  //...
  output: {
    pathinfo: true,
  },
};
```
---
## webpack config in craco
- slightly different configuration style of webpack in craco
- craco contains a `configure` object that will hold the required object values
```javascript
module.exports = {
    configure: {
      output: {
        publicPath: '/<path>'
      }
    }
  }
}
```
- the `<path>` will contain the required values of the `publicPath`