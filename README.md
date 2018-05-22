#HTML Webpack Plugin Cross Origin
This plugin is a fork from [html-webpack-inject-attributes-plugin](https://github.com/dyw934854565/html-webpack-inject-attributes-plugin)(v1.0.0). Fix the problems for new version html-webpack-plugin (3.2.0).
```bash
npm i --save-dev html-webpack-plugin-crossorigin
```
##Usage
```javascript
const HtmlWebpackPlugin = require('html-webpack-plugin');
const HtmlWebpackPluginCrossorigin = require('html-webpack-plugin-crossorigin');

new HtmlWebpackPlugin({
    plugins: [
        new HtmlWebpackPlugin({
            filename: 'test.html',
            template: 'src/assets/test.html'
            // add script attributes here!
            attributes: {
                crossorigin: 'anonymous'
            }
        }),
        // this one should be placed after HtmlWebpackPlugin
        new HtmlWebpackPluginCrossorigin({
            inject: true
        })
    ]
});
```

This plugin fixed the problem from the origin one:
> ERROR in   TypeError: callback is not a function
>  
>  - index.js:35 
>    [ex-child-webpack]/[html-webpack-inject-attributes-plugin]/index.js:35:13

