# Webpack For TypeScript Environment
## Environment Setup

### Init NPM
Execute `npm init` command to create `package.json`.
```
$ npm init -y
```

### Install
```
$ npm i -D webpack webpack-cli typescript ts-loader
```

### Ignore File
`npm install` automatically generate blow.
```
node_modules
package-lock.json
```

Then, you ignore this blow.
.gitignore
```
node_modules
```


### Create TS Config
tsconfig.json
```json
{
  "compilerOptions": {
    "sourceMap": true,
    "target": "es5",
    "module": "es2015"
  }
}
```

### Create Webpack Config
webpack.config.js
```js
module.exports = {
  mode: 'development',
  entry: './src/index.ts',

  module: {
    rules: [
      {
        test: /\.ts$/,
        use: 'ts-loader',
      },
    ],
  },
  resolve: {
    extensions: [
      '.ts', '.js',
    ],
  },
};
```

### Add Command
package.json
```json
  "scripts": {
    "build": "webpack",
    "watch": "webpack -w"
  },
```

### Create HTML and TS File
index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

    <script src="./src/index.ts"></script>
</body>
</html>
```

src/index.ts
```ts
console.log('Hello TypeScript !');
```

### Access
Open `index.html` with Browser.
Then, you can see `Hello TypeScript !` in development console.
