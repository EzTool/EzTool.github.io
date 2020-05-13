# 如何判斷 Word 檔案有使用追蹤設定功能

## 透過 Automation
在 [Document][ref001] 物件有 [Revisions][ref002] 屬性。

## 透過 OpexXML  

以下兩項有一為真即該檔案有使用追蹤設定。

* **檢查 comments**  
取得文件中 Main Part 的 comments 的關連資訊，查看是否有 comments.xml 設定。

```csharp
objPackageRelCollection = objMainPackagePart.GetRelationshipsByType("http://schemas.openxmlformats.org/officeDocument/2006/relationships/comments")
For Each objExtLinkRel In objPackageRelCollection
    If objExtLinkRel.TargetUri.ToString().Equals("comments.xml") Then
        bResult = True
        Exit For
    End If
Next
```

* **檢查 settings.xml**  
檢查 settings.xml 裡面是否有 trackRevisions 設定。

```csharp
Dim sPartTargetURI As Uri = New Uri("/word/settings.xml", UriKind.Relative)

If objPackage.PartExists(sPartTargetURI) Then
    Dim objPartTarget As PackagePart = objPackage.GetPart(sPartTargetURI)

    Using objPartStream As Stream = objPartTarget.GetStream(FileMode.Open, FileAccess.Read)
        Using objReader As StreamReader = New StreamReader(objPartStream)
            Dim sResult As String = objReader.ReadToEnd()

            If sResult.Contains("trackRevisions") Then
                bResult = True
            End If
        End Using

        objPartStream.Close()
    End Using
End If
```

[ref001]:https://docs.microsoft.com/zh-tw/dotnet/api/microsoft.office.tools.word.document?view=vsto-2017  
[ref002]:https://docs.microsoft.com/zh-tw/dotnet/api/microsoft.office.tools.word.document.revisions?view=vsto-2017#Microsoft_Office_Tools_Word_Document_Revisions