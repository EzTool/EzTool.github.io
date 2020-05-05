## npm 是什麼？
npm 是 Node.js 的
## 常用指令
### 查看 npm 版本  
        npm -v

### 顯示已安裝套件列表
        npm list


### 初始化指令
此命令會在當前目錄下新增 package.json 檔案，用於記錄套件安裝情形。 

        npm init

### 初始化指令-全部載入預設值，不用輸入資料
        npm init -y

### 安裝
安裝依影響範圍區分為「全域安裝」及「專案安裝」兩種，其中專案安裝旨在安裝在專案的目錄下，只有在該專案目錄下該指定才能作用，而全域安裝則是在電腦的各個目錄都能執行命令。  

專案安裝必須先就該目錄初始化，亦即執行前述的 **npm init** 命令，則在執行專案安裝時會將套件相關資訊寫入到 **package.json** 檔案的 **dependencies** 欄位。  

進一步就專案安裝可區分出「專案開發環境安裝」狀態，前述安裝套件資訊會寫到 **package.json** 檔案的 **devDependencies** 欄位。

* 全域安裝：  

        npm install [套件名稱] -g

* 專案安裝

        npm install [套件名稱] -save

* 專案開發環境安裝

        npm install [套件名稱] -save-dev 

### 移除套件 
* 專案移除  

        npm uninstall [套件名稱]

* 全域移除  

        npm uninstall [套件名稱] -g
