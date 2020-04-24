# Webpack 

 * [webpack 新手教學之淺談模組化與 snowpack](https://blog.techbridge.cc/2020/01/22/webpack-%E6%96%B0%E6%89%8B%E6%95%99%E5%AD%B8%E4%B9%8B%E6%B7%BA%E8%AB%87%E6%A8%A1%E7%B5%84%E5%8C%96%E8%88%87-snowpack/)
* [什么是 Webpack](https://zhaoda.net/webpack-handbook/what-is-webpack.html)
* [Webpack 零設定，入門教學](https://ithelp.ithome.com.tw/articles/10192578)

Webpack 的功能是模組整合工具程式，透過指定單一檔案作為進入點，這個檔案會是樹狀結構的根節點，然後 Webpack 將所有的檔案都挷定為單一樹狀結構。

* 進行靜態分析，將模組之間的關係建立為一個樹狀結構，如此實現即時載入的機制，避免了一次載入所有模組(將所有模組打包在單一檔案)或是逐檔載入的載入耗時或載入次數過多的兩難問題。
### 要解決其他打包工具的問題
* 提供即時加載
* 初始化載入耗時較短
* 可加載圖檔，CSS 設定，不限定 JS 檔案
* 可加載第三方函式庫
* 自訂打包邏輯
* 單頁／多頁的大型專案適用

而且這些檔案可以不必是 JavaScript 檔案，透過 Webpack 的 loader 機制，可以將 .css, .png 及 .html 的檔案都透過 require 指定動作加進來。

此外，還可以透過 Plugins 機制，來增加額外的功能，例如 UglyfyJsPlugin 可以 minify 包含的 JavaScript 程式碼。


## 什麼是「模組整合工具」？
* [JavaScript Modules: A Beginner’s Guide](https://www.freecodecamp.org/news/javascript-modules-a-beginner-s-guide-783f7d7a5fcc/#.jw1txw6uh)
* [JavaScript Modules Part 2: Module Bundling](https://medium.com/free-code-camp/javascript-modules-part-2-module-bundling-5020383cf306#.lfnspler2)


# 為什麼你需要 Webpack ？
-> 模組化開發 -> 透過 CommonJS 方式 --> 透過 Node.js 運行  
Node.js 採用 CommonJS 的模組化規範  

        如何在瀏覽器上達到相同的模組化結果？

* 前處理工具 Preprocess tool 
* 專案檔案夾
    * src: 放置待打包的資源檔案 es6, png, sass, vue, jsx 等。
    * dist: 經過 Webpack 打包過的產出，拿這個產出去部署。
* 進入點：
    * js 檔案
    * 運行在 Nodejs 之上，所以要安裝 nodejs  
* 安裝
    * 建立專案目錄
    * 初始專案  
        
            npm init

    * 安裝 Webpack 工具  

            npm install webpack webpack-cli --save-dev
* Hello world
    * 新增打包設定檔 webpack.config.js

    ```js
    const path = require('path');
    module.exports = {
        entry: './index.js', 
        output: {
            filename: 'index.bundle.js', 
            path: path.resolve(__dirname, './'),
        }
    };
    ```       
    設定檔案參數：     
    entry- 這是 bundle 進入點，可以是一個陣列，提供多個進入點，同時會產出多個 bundle 檔案。  
    output- 宣告 Webpack 的輸出型式。  
        path: 存放輸出的 bundle 檔案的位置。  
        filename: bundle 檔案的名稱。
      
      


    * 新增 index.js 檔案
    ```js
    console.log("It's alive!!");
    ```
    * 調整 npm 專案檔 package.json
    
    ```json
    {
      "name": "webpack-test",
      "version": "1.0.0",
      "description": "",
      "main": "index.js",
      "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "build": "webpack"
      },
      "author": "",
      "license": "ISC",
      "devDependencies": {
        "webpack": "^4.6.0",
        "webpack-cli": "^2.0.15"
      }
    }
    ```
    * 透過 npm 執行打包  

            npm run build
# 安裝
* 全域安裝可以提供大部分的功能
    
        npm install -g webpack

* 本機安裝可以提供優化的 plugins 

        npm install --save-dev webpack

# 命令
* 執行 Webpack  

        webpack

* 儲存檔案即自動行建置

        webpack --watch

* 使用自訂設定檔

        webpack --config myconfig.js

# 設定檔案
Webpack 透過設定檔案決定運行程序，此設定檔的檔案名稱則預設為：

        webpack.config.js

如果要使用不同的檔名，在執行命令時需要透過 **--config** 來指定自訂的檔案。

# 模組化
兩個不同功能，透過定義進行互動，螢幕可以用來看電視，打電動，分別有不同的定義，螢幕定義了其如何運行的規範，透過接頭傳入指定的訊號就會依定義的給序反饋，所以不管是電腦、電玩還是電視盒，只要接頭對了就可以顯示，而這就是不同模組。

程式的模組化也就是如此，將所有的邏輯都放在同一個方法中，當然也可以運行，但若是發生異常，或是需要調整，因為只有一個方法

# 後記
工具只是工具。


[Webpack]:https://webpack.js.org/