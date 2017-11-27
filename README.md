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

### Serverless

If you're using [serverless-webpack](https://github.com/serverless-heaven/serverless-webpack), you'll need [node-loader](https://github.com/webpack-contrib/node-loader) to load `canvas.node`. (Isn't needed if you're also using [webpack-node-externals](https://github.com/liady/webpack-node-externals)).

## Usage
Replace `require('canvas')` with `require('canvas-aws-prebuilt')`.

## API
See [node-canvas API](https://github.com/Automattic/node-canvas#non-standard-api).

## FAQ
  
### Can I use this in other environments (Windows, MacOS etc.)?
No, you're probably looking for [node-canvas-prebuilt](https://github.com/node-gfx/node-canvas-prebuilt).
  
### The Reason
  I spent some time (a week, actually) trying to deploy a Serverless application with node-canvas, so I decided to make life easier for those who try to do the same.

## Thanks
- [Automattic](https://github.com/Automattic) for making such a wonderful [library](https://github.com/Automattic/node-canvas);
- [WebSeed](https://github.com/WebSeed) for his [node-canvas-aws-lambda-example](https://github.com/WebSeed/node-canvas-aws-lambda-example) which gave me the inspiration;
- [anandanand84](https://github.com/anandanand84) for his [how-dependencies-were-created](https://github.com/anandanand84/aws-lambda-node-canvas/blob/master/how-dependencies-were-created) (I slightly modified it and used to build the libs);
- [mankins](https://github.com/mankins) for his [guide](https://github.com/Automattic/node-canvas/issues/680#issuecomment-179968875) (really helped me to find the solution);
- [eonarheim](https://github.com/eonarheim) for [this comment](https://github.com/Automattic/node-canvas/issues/641#issuecomment-148270114) from which I learned how to make the executable to search for libs in its current folder.

## License

MIT