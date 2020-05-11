## GitFlow
### 內容
master 及 develop 會持績存在，其餘的 feature, release 及 hotfix 的分支則會在整合後就會被刪除。

* master:  
主要的分支。
* develop:

* feature:  
    從 develop 分支拉出來且只能被合併回 develop 分支，命名的原則為：  

        feature/[功能名稱]

    我们能看到feature branch最明显的两个好处是：  
    * 各个feature之间的代码是隔离的，可以独立地开发、构建、测试；
    * 当feature的开发周期长于release周期时，可以避免未完成的feature进入生产环境。
* release:  
新功能開發到差不多時，在 release 分支只會 Commit 修改 Bug 而不會是新功能。
合併回 develop 分支。
* hotfix:  

### merge
merge代码总是痛苦和易错的。在软件开发的世界里，如果一件事很痛苦，那就频繁地去做它。比如集成很痛苦，那我们就nightly build或continuous integration，比如部署很痛苦，那我们就频繁发布或continuous deployment。 merge也是一样。所有的git教程和git工作流都会建议你频繁地从master pull代码，早做merge。

### 問題
* **同一個 feature 多人開發時？**  
再依不同人員建立分支，例如 John 及 Tom 兩個人同時開發時，就可以從該 feature 分支建立個別的分支，同時也只能合併回 feature 的分支，如下：

        feature/[功能名稱]/[人名]

* **遠端的 feature 分支有新的 Commit 時，本地端分支的處理？**  
採用 rebase 操作會較 merge 操作來說不易出錯，因為 merge 會要求一次整合所有差異，而 rebase 則是會先比對遠端及本地的 Commit 的差異。

## 建立 Flow
* **master:**   
    穩定的發行版本。
* **hotfix:**  
    修正 master 的錯誤，從 master 分支出來，並 merge 回 master 分支。
* **refact:**  
    重構程式時，從 master 分支出來，測試完畢後 merge 回 master 分支。
* **feature:**  
    發展新功能，從 master 分支出來，不同功能之間平行開發，當 master 有 hotfix 或 refact 分支 merge 回去 master 時，要透過 rebase 將 hotfix 或 refact 分支的內容整合到 feature 分支。
* **release:**  
    下個發行版本，從 master 分支出來，在所有待發行的 feature 分支都 merge 並驗收完畢後 merge 回 master 分支。
### 多人同步開發一個功能

### 發行版本包含功能異動

### 正在開發的多個功能有共同需要的異動


## 參考文章
* [了解 Git Flow][Ref001]
* [git flow 實戰經驗談 part1 - 別再讓 gitflow 拖累團隊的開發速度][Ref002]
* [git flow 實戰經驗談 part2 - 可能更好的 gitflow][Ref003]
* [Gitflow 有害论][Ref004]



[Ref001]:https://blog.hellojcc.tw/understanding-git-flow/
[Ref002]:https://blog.hellojcc.tw/the-flaw-of-git-flow/
[Ref003]:https://blog.hellojcc.tw/a-better-git-flow/
[Ref004]:https://insights.thoughtworks.cn/gitflow-consider-harmful/