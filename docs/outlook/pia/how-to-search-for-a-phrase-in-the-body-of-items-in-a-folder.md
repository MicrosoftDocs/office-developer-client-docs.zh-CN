---
title: 在文件夹中项的正文内搜索某短语
TOCTitle: Search for a phrase in the body of items in a folder
ms:assetid: 2c9f3b5f-ed91-4a07-b247-8f89f00cbc68
ms:mtpsurl: https://msdn.microsoft.com/library/Bb644806(v=office.15)
ms:contentKeyID: 55119924
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: dc8e0fb2b82ae9660e292a6ec1dea70e82fe36ef
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722142"
---
# <a name="search-for-a-phrase-in-the-body-of-items-in-a-folder"></a>在文件夹中项的正文内搜索某短语

此示例在收件箱中项的正文内搜索字符串“office”。

## <a name="example"></a>示例

此代码示例使用 DAV 搜索和定位 (DASL) 语法来指定查询。 为了构造筛选器，此代码示例先检查默认存储中是否已启用“即时搜索”，以确定是使用 **ci\_phrasematch** 关键字在项正文中完全匹配“office”短语，还是使用 **like** 关键字将项目正文中出现的任何“office”都匹配为确切字符串或子字符串。 然后，此代码示例将筛选器应用于收件箱的 [GetTable](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法，并获取 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象中的结果。 接下来，此代码示例显示 **Table** 中每个返回项的主题。

此代码示例使用命名空间表示法 urn:schemas:httpmail:textdescription 指定 **Body** 属性。

使用 **ci\_phrasematch** 关键字的语法为：

`<PropertySchemaName> ci_phrasematch <ComparisonString>`

使用 **like** 关键字进行前缀匹配的语法为：

`<PropertySchemaName> like <Token>%`

使用 **like** 关键字进行任何子字符串匹配的语法为：

`<PropertySchemaName> like %<Token>%`

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub DemoSearchBody()
    Dim filter As String
    If (Application.Session.DefaultStore.IsInstantSearchEnabled) Then
        filter = "@SQL=" & Chr(34) _
            & "urn:schemas:httpmail:textdescription" & Chr(34) _
            & " ci_phrasematch 'office'"
    Else
        filter = "@SQL=" & Chr(34) _
            & "urn:schemas:httpmail:textdescription" & Chr(34) _
            & " like '%office%'"
    End If
    Dim table As Outlook.Table = _
        Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderInbox).GetTable( _
        filter, Outlook.OlTableContents.olUserItems)
    While Not (table.EndOfTable)
        Dim row As Outlook.Row = table.GetNextRow()
        Debug.WriteLine(row("Subject"))
    End While
End Sub
```


```csharp
private void DemoSearchBody()
{
    string filter;
    if (Application.Session.DefaultStore.IsInstantSearchEnabled)
    {
        filter = "@SQL=" + "\""
            + "urn:schemas:httpmail:textdescription" + "\""
            + " ci_phrasematch 'office'";
    }
    else
    {
        filter = "@SQL=" + "\""
            + "urn:schemas:httpmail:textdescription" + "\""
            + " like '%office%'";
    }
    Outlook.Table table = Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).GetTable(
        filter, Outlook.OlTableContents.olUserItems);
    while (!table.EndOfTable)
    {
        Outlook.Row row = table.GetNextRow();
        Debug.WriteLine(row["Subject"]);
    }
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

