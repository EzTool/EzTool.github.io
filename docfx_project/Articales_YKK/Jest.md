# Jest

[Jest][JestHost] 是一個由 Facebook 開發的測試器，至力于提供一個 bettery-included 單元測試解決方案，可以在 [官方文件][JestDoc] 學習到更多 Jest 的知識。

* [讀 Jest Doc - 建置測試環境][ref1]
* [讀 Jest Doc - 測試替身][ref2]
* [Jest | JOJO是你？我的替身能力是 Mock ！][ref3]

## 加法器的單元測試練習

轉錄 [Chris 技術筆記][refChris] 的範例，可以快速體會到 JavaScript 的單元測試。

### 建立環境

* 建立測試目錄  
建立練習目錄 *c:\\\\Jest\Test\Demo\\*

* 建立 npm 專案  
在 CMD 下移到練習目錄，並執行 npm 的初始專案命令

        npm init -y

* 取得 Jest  

        npm install --save-dev jest

### 待測程式
* **ADD.js**
    ```javascript
    function ADD(a, b){
        return a + b;
    }
    module.exports = ADD;
    ```
* **App.js**
    ```javascript
    const Add = require('./ADD');
    console.log(Add(1,2));    
    ```

* 運行  
透過 node.js 執行 App.js 會顯示其相加的值。

        node App.js

### 測試程式
* **ADD.test.js**
    ```javascript
    const ADD = require('./ADD');
    test('Execute 1 + 2 = 3', ()=>{
        expect(ADD(1, 2)).toBe(3);
    });
    ```


[JestHost]:https://jestjs.io/
[JestDoc]:https://jestjs.io/docs/en/getting-started.html
[ref1]:https://dwatow.github.io/2020/04-17-jest/jest-doc-1/
[ref2]:https://dwatow.github.io/2020/04-24-jest/jest-doc-5/
[ref3]:https://medium.com/enjoy-life-enjoy-coding/jest-jojo%E6%98%AF%E4%BD%A0-%E6%88%91%E7%9A%84%E6%9B%BF%E8%BA%AB%E8%83%BD%E5%8A%9B%E6%98%AF-mock-4de73596ea6e