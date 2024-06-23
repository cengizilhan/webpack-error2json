# webpack-error2json

A Webpack plugin to export errors and warnings to JSON files.

## Purpose

When there are too many errors, the console screen becomes hard to read and truncates some of the error messages. This plugin addresses this issue by generating separate JSON files for errors and warnings in the project's root directory.

## Installation

Install the plugin via npm:

```sh
npm install webpack-error2json
```

## Usage
To use the plugin in your Webpack configuration, follow these steps:

Integrate the Plugin with Webpack: In your webpack.config.js file, require the plugin and add it to the plugins array.

```
const path = require('path');
const ErrorToJsonPlugin = require('webpack-error2json');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  },
  plugins: [
    new ErrorToJsonPlugin()
  ],
  mode: 'development'
};
```

and and just build from webpack.

npx webpack --config webpack.config.js

### Generated Files
The plugin generates the following files in the root directory:

webpack-errors.json

webpack-warnings.json

### webpack-errors.json Example
```
[
  {
    "message": "Module not found: Error: Can't resolve '@/bower_components/jquery_legacy/dist/blabla' in 'C:\\Users\\cengiz.ilhan\\source\\repos\\Assets\\webpack-project\\Static\\src...'",
    "details": "resolve '@/bower_components/jquery_legacy/dist/blabla' in 'C:\\Users\\cengiz.ilhan\\source\\repos\\..."
  },
  {
    "message": "Module not found: Error: Can't resolve '@/bower_components/jquery_legacy/dist/blabla' in 'C:\\Users\\cengiz.ilhan\\source\\repos\\Assets\\webpack-project\\Static\\src...'",
    "details": "resolve '@/bower_components/jquery_legacy/dist/blabla' in 'C:\\Users\\cengiz.ilhan\\source\\repos\\..."
  }
]
```

https://github.com/cengizilhan

https://github.com/cengizilhan/webpack-error2json

