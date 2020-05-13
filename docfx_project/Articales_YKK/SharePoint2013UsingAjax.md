# 在 SharePoint 中透過 JQuery 的 AJAX 操作清單項目

因緣際會看到 SharePoint 中透過 JS 與 API 互動的 [文章][ref001]，原始文章為英文寫作，就作個中文記錄。

## 簡述 Introduction

本文介紹如何透過 REST API 及 jQuery Ajax 提供 SharePoint 列表項基本的 CRUD 操作，在使用 SharePoint Apps 或創建涉及客戶端代碼的自定義表單時，使用 REST API 或 JQuery 非常方便。

This article describes how to work with SharePoint list items, basically performing CRUD operations, using the combination of REST API and jQuery Ajax. Working with REST API or JQuery comes handy while working with SharePoint Apps or creating Custom Forms which involves Client Side Code.

## 情境 Scenario

讓我們以一個基本方案為例，在該方案中，我們具有一個指定為「columns-Name」（Single Line of Text）的「項目」列表。「說明」（Multiple Lines of Text）和「開始日期」（Date and Time）。我們必須將新項目添加到列表中，更新一些項目並刪除特定項目。

Let's take a basic scenario, where we have a list "Projects" with columns - Name (Single Line of Text). Description (Multiple Lines of Text) and Start Date (Date and Time). We have to add new items to the list, update few items and delete the specific item.

## Get List Items

要取得列表的所有項目，可以使用以下代碼:

In order to get all items from the list, below code can be used-

```javascript
<script>
    $.ajax({
        var siteurl = _spPageContextInfo.webAbsoluteUrl;
        $.ajax({
                   url: siteurl + "/_api/web/lists/getbytitle('Projects')/items",
                   method: "GET",
                   headers: { "Accept": "application/json; odata=verbose" },
                   success: function (data) {
                        if (data.d.results.length > 0 ) {
                             //This section can be used to iterate through data and show it on screen
                        }       
                  },
                  error: function (data) {
                      alert("Error: "+ data);
                 }
          });
    });
</script>
```
接著說明程式碼作用：

1. 透過 ***_spPageContextInfo*** 取得頁面的 URL 字串。
2. 透過 HTTP 的 ***Get*** 方法發出檢查項目的請求。
3. 標頭 ( headers ): 定義標頭以 JSon 格式返回輸出，否則默認情況下返回 XML 格式數據。

Now lets see, whats happening in code -

1.) Setting up siteurl using _spPageContextInfo. This object provides many SharePoint page properties which are useful in client-side code model. A complete list of properties can be seen here Jump .

2.) HTTP 'GET' method is used to send a request for retrieving items

3.) headers - These are defined to return output in JSON format otherwise by default SharePoint returns XML data.

## Get Specific List Items

## Delete Specific List Item

## Add New List Item

## Update List Item

## 參考文章
* [原始文章][ref001]

[ref001]:https://social.technet.microsoft.com/wiki/contents/articles/31995.sharepoint-2013-working-with-rest-api-using-jquery-ajax.aspx