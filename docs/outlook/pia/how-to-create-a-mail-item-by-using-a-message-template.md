---
title: 使用邮件模板创建邮件项
TOCTitle: Create a mail item by using a message template
ms:assetid: 7d1ffc3b-d1a7-46d1-adb9-ac41e67f626a
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623026(v=office.15)
ms:contentKeyID: 55119862
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cdd9654187685ceab1062fb4ae1882b2d48c68d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349537"
---
# <a name="create-a-mail-item-by-using-a-message-template"></a>使用邮件模板创建邮件项

此示例使用 [CreateItemFromTemplate](https://msdn.microsoft.com/library/bb611329\(v=office.15\)) 方法创建邮件项。

## <a name="example"></a>示例

该代码示例打开 Ivy.oft 模板文件，分配一个主题，然后将邮件存入"草稿"文件夹。

如果您在磁盘上存储了一个希望用作邮件模板的 Outlook 窗体模板文件 (.oft)，则 **CreateItemFromTemplate** 方法很有用。此模板文件可以包含您希望包括在邮件中的具有预设格式的文本、信纸或图像。但是，如果模板文件包含的代码位于窗体之后，则窗体代码将不运行。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub CreateItemFromTemplate()
    Dim folder As Outlook.Folder = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderDrafts), Outlook.Folder)
    Dim mail As Outlook.MailItem = _
        CType(Application.CreateItemFromTemplate( _
        "c:\ivy.oft", folder), Outlook.MailItem)
    mail.Subject = "Congratulations"
    mail.Save()
End Sub
```


```csharp
private void CreateItemFromTemplate()
{
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderDrafts) as Outlook.Folder;
    Outlook.MailItem mail =
        Application.CreateItemFromTemplate(
        @"c:\ivy.oft", folder) as Outlook.MailItem;
    mail.Subject = "Congratulations";
    mail.Save();
}
```

## <a name="see-also"></a>另请参阅

- [邮件](mail.md)

