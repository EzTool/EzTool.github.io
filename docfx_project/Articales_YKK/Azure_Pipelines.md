# Pipelines

## 費用

* 公開專案
* 私有專案： 1,800 minutes( 30 hours )/month 免費。

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

## 參考文章

* [Azure Pipelines][MSDN:Pipeline]
* [13. 持續整合 - Azure Pipelines of Azure DevOps][Ref001]

[MSDN:Pipeline]:https://docs.microsoft.com/en-us/azure/devops/pipelines/?view=azure-devops
[MSDN:UseAzurePipelines]:https://docs.microsoft.com/zh-tw/azure/devops/pipelines/get-started/pipelines-get-started?view=azure-devops
[Ref001]:https://ithelp.ithome.com.tw/articles/10206169