# canvas-aws-prebuilt

-----

##Adapted version of [node-canvas](https://github.com/Automattic/node-canvas) to use with AWS and Serverless.

#### Important note: currently the module is using node-canvas v1.6.7. Support of v2 may be added later.

-----

## Installation
```
npm install --save canvas-aws-prebuilt
```

## Usage
This is a drop-in replacement of [node-canvas](https://github.com/Automattic/node-canvas) package.

### ES5
```javascript
const canvas = require('canvas-aws-prebuilt');
```
### ES6
```javascript
import canvas from 'canvas-aws-prebuilt';
```

## API
See node-canvas API.

## FAQ

### Why?
I spent some time (a week, actually) trying to deploy a Serverless application with node-canvas (and succeeded), so I decided to make life easier for those who try to do the same. The main problem I came across is that the project used serverless-webpack with externals enabled, which prevented me from simply copying the pre-built module into node_modules.

### Can it be used with serverless-webpack?
Yes. You'll probably need a [loader](https://github.com/webpack-contrib/node-loader) for `canvas.node`.

For those who is deploying the app via CI (like I did), you'll need to use [native-ext-loader](https://github.com/smt116/node-native-ext-loader) instead of node-loader. It have to be configured like this:
```javascript
module: {
  rules: [
    test: /\.node$/,
    loader: 'native-ext-loader',
    options: {
      name: '[name].[ext]', // <-- not necessary, just to make the file names readable
      rewritePath: '/var/task' // <-- is necessary to run on AWS Lambda
    }
  ]
}
```

### How did you make it?
Coming soon.

## License

MIT