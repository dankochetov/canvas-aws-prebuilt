# canvas-aws-prebuilt

-----

##Adapted version of [node-canvas](https://github.com/Automattic/node-canvas) to use with AWS and Serverless.

#### Important note: currently this module is using `node-canvas v1.6.7`. Support of `v2` may be added later.

-----

## Installation
Download the package:
```
npm install --save canvas-aws-prebuilt
```

Next you'll need to copy the shared libraries from the package directory into the root of your Lambda package.

### Serverless

You'll need these: 

- [serverless-webpack](https://github.com/serverless-heaven/serverless-webpack)
- [node-loader](https://github.com/webpack-contrib/node-loader) for `canvas.node`
- [copy-webpack-plugin](https://github.com/webpack-contrib/copy-webpack-plugin) with following configuration:
  ```js
  module: {
      plugins: [
          new CopyWebpackPlugin([
              {
                  from: 'node_modules/canvas-aws-prebuilt/lib',
                  to: ''
              }
          ])
      ],
  }
  ```
  
### AWS CLI / AWS Console
Copy all of the `node_modules/canvas-aws-prebuilt/lib` libs into the root folder of your Lambda package.


## Usage
Replace `require('canvas')` with `require('canvas-aws-prebuilt')`.
## API
See [node-canvas API](https://github.com/Automattic/node-canvas#non-standard-api).

## FAQ
  
### Can I use this in other environments (Windows, MacOS etc.)?
No, you're probably looking for [node-canvas-prebuilt](https://github.com/node-gfx/node-canvas-prebuilt).
  
### The Reason
  I spent some time (a week, actually) trying to deploy a Serverless application with node-canvas (and succeeded), so I decided to make life easier for those who try to do the same. The main problem I came across is that the project used serverless-webpack with externals enabled, which prevented me from simply copying the pre-built module into node_modules.

## Thanks
- [Automattic](https://github.com/Automattic) for making such a wonderful [library](https://github.com/Automattic/node-canvas);
- [WebSeed](https://github.com/WebSeed) for his [node-canvas-aws-lambda-example](https://github.com/WebSeed/node-canvas-aws-lambda-example) which gave me the inspiration;
- [anandanand84](https://github.com/anandanand84) for his [how-dependencies-were-created](https://github.com/anandanand84/aws-lambda-node-canvas/blob/master/how-dependencies-were-created) (I slightly modified it and used to build the libs);
- [mankins](https://github.com/mankins) for his [guide](https://github.com/Automattic/node-canvas/issues/680#issuecomment-179968875) (really helped me to find the solution).
## License

MIT