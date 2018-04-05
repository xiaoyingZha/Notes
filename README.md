# Vue项目兼容IE浏览器
###    问题：
      Vue项目部署到服务器后，除IE浏览器外其他都正常，而IE浏览器会报这么个问题：
> SCRIPT5022: [vuex] vuex requires a Promise polyfill in this browser.
    
###   原因：

    因为Vue使用了ES6 Promise，而IE浏览器不支持，解决方法是: 
    使用babel-polyfill转换 
>  $ npm install --save-dev babel-polyfill
     
    如果使用vue-cli项目，在webpack.config.js中添加：
> require('babel-polyfill');
>
> entry: {
>   app: ['babel-polyfill','./src/main.js']
> },
