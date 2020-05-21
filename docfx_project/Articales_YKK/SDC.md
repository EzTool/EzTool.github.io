## 預期做法
* 按下 Save 按鍵時，取得當前附上的檔案清單，進行檢查。
* 檢查檔案:
    * 數量為三(超過也不對)
    * 具備 .html 副檔名的檔案
    * 具備 .xml 副檔名的檔案
    * 具備 .docx 副檔名的檔案\
* 若未通過則中止並顯示訊息：
    * 訊息：
        * 數量錯誤。
        * 缺少以下檔案檔案：
            * iXBRL 檔
            * ClineInfo 檔
            * 財報檔

```flow
st=>start: 使用者按下 Save 按鍵
e=>end: 進行儲存
b=>end: 中斷儲存
op=>operation: 取得檔案清單
msg=>operation: 錯誤訊息

cond1=>condition: 數量為三
cond2=>condition: 具備 .html 副檔名的檔案
cond3=>condition: 具備 .xml 副檔名的檔案
cond4=>condition: 具備 .docx 副檔名的檔案

st->op->cond1
cond1(no)->msg
cond1(yes)->cond2
cond2(no)->msg
cond2(yes)->cond3
cond3(no)->msg
cond3(yes)->cond4
cond4(no)->msg
cond4(yes)->e
msg->b
```


## 技術點
* Save 按鍵事件
* 取得檔案清單
* 中斷儲存