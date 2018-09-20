#HTML Webpack Plugin Cross Origin (Webpack 4)
This plugin adapt [html-webpack-inject-attributes-plugin](https://github.com/dyw934854565/html-webpack-inject-attributes-plugin)(v1.0.0) for webpack 4.
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
It will add the `crossorigin=anonymous` to script tag like:
```html
<script src="index.js" crossorigin=anonymous></script>
```

This plugin fixed the problem from the origin one:
> ERROR in   TypeError: callback is not a function
>  
>  - index.js:35 
>    [ex-child-webpack]/[html-webpack-inject-attributes-plugin]/index.js:35:13

