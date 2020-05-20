# Azure Pipeline

## 費用

* 公開專案
* 私有專案： 1,800 minutes( 30 hours )/month 免費。

## 概觀

![Key Concepts](../images/Azure/key-concepts-overview.svg)  
[圖片來源][pic001]

* **Trigger** 觸發 **Pipeline** 啟動。
* 個別 **Pipeline** 由一個或數個 **Stage** 組成。( 個別 **Pipeline** 可以佈置到一個或多個 **environments** )

### Trigger ( 觸發器 )

Trigger 是為了告訴 Pipeline 何時運行而設置的。例如可以配置 Pipeline 於有推送到 Repository 時，計劃的時間或另一個 Build 任務完成時運行。所有這些動作都稱為觸發器。

### Pipeline ( 管線 )

Pipeline 定義了應用程序的持續集成和部署過程。它由一個或多個 Stage 組成。可以將其視為定義如何運行測試，構建和部署步驟的工作流。

### Stage

Stage 是 Pipeline 中的邏輯邊界。它可用於標記關注點分離（例如，編譯，測試和生產）。每個階段包含一個或多個 Job 。

### Step

Step 是 Pipeline 的最小組成部分。
例如，Pipeline 可能包含 Build 和 Test 步驟。
步驟可以是腳本 ( Script ) 或任務 ( Task )。
而 Task 只是為了方便而預創建立的 Script 。

## 開始使用

可以支援持續整合( continuous integration, CI )及持續交付( continuous delivery, CD) 以持續不斷地測試和構建您的代碼並將其交付給任何目標。可以透過以下兩種不同方式進行設定：

* YAML 檔案
* 用戶介面

兩種不同的設定方式差異可參考 [Use Azure Pipelines][MSDN:UseAzurePipelines]

## 建立預設的 YML 檔案

經過系統的操作後，會提供預設的 YAML 設定檔案。

預設建立

* **trigger**:
* **pool**: 所使用的測試環境。
* **variables**: 宣告 task 內的所使用的變數。
* **steps**: 真正進行動作的地方，在 azure pipeline 內，將各個動作都視為 task 段落。

```yml
# ASP.NET Core (.NET Framework)
# Build and test ASP.NET Core projects targeting the full .NET Framework.
# Add steps that publish symbols, save build artifacts, and more:
# https://docs.microsoft.com/azure/devops/pipelines/languages/dotnet-core

trigger:
- master

pool:
  vmImage: 'windows-latest'

variables:
  solution: '**/*.sln'
  buildPlatform: 'Any CPU'
  buildConfiguration: 'Release'

steps:
- task: NuGetToolInstaller@1

- task: NuGetCommand@2
  inputs:
    restoreSolution: '$(solution)'

- task: VSBuild@1
  inputs:
    solution: '$(solution)'
    msbuildArgs: '/p:DeployOnBuild=true /p:WebPublishMethod=Package /p:PackageAsSingleFile=true /p:SkipInvalidConfigurations=true /p:DesktopBuildPackageLocation="$(build.artifactStagingDirectory)\WebApp.zip" /p:DeployIisAppPath="Default Web Site"'
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

- task: VSTest@2
  inputs:
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

```

## Jobs & stages

### Specify jobs in your pipeline

### Define container jobs

### Add stages, dependencies & conditions

### Deployment jobs

### Specify conditions

### Specify demands

## 參考文章

* [三十天.NET與Azure漸進式開發專案(29): 在Azure DevOps從無到有建立CI/CD專案][Ref003]
* [YouTube:【DevOps 線 02】那個Code不是我弄壞的!!持續整合與版本控制策略(示範 SonaQube)][Ref002]
* [Azure Pipelines][MSDN:Pipeline]
* [13. 持續整合 - Azure Pipelines of Azure DevOps][Ref001]
* [Creating NuGet packages in Azure DevOps with Azure Pipelines and YAML][Ref004]
* [Azure DevOpe —— Azure Pipeline][Ref005]
* [使用 Azure Pipelines 和 Compute Engine 创建 CI/CD 流水线][Ref006]
* [裝載您自己的 NuGet 摘要][Ref007]
* [使用 nuget.exe CLI 建立套件][Ref008]

[pic001]:https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/key-pipelines-concepts?view=azure-devops
[MSDN:Pipeline]:https://docs.microsoft.com/en-us/azure/devops/pipelines/?view=azure-devops
[MSDN:UseAzurePipelines]:https://docs.microsoft.com/zh-tw/azure/devops/pipelines/get-started/pipelines-get-started?view=azure-devops
[Ref001]:https://ithelp.ithome.com.tw/articles/10206169
[Ref002]:https://www.youtube.com/watch?v=GtHxhIYK_dg
[Ref003]:https://ithelp.ithome.com.tw/articles/10207833
[Ref004]:https://medium.com/@dan.cokely/creating-nuget-packages-in-azure-devops-with-azure-pipelines-and-yaml-d6fa30f0f15e
[Ref005]:https://blog.csdn.net/playermaker57/article/details/87901531
[Ref006]:https://cloud.google.com/solutions/creating-cicd-pipeline-vsts-compute-engine?hl=zh-cn
[Ref007]:https://docs.microsoft.com/zh-tw/nuget/hosting-packages/overview
[Ref008]:https://docs.microsoft.com/zh-tw/nuget/create-packages/creating-a-package