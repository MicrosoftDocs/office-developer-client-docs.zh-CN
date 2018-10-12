---
title: 打开并显示 iCalendar 文件内容
TOCTitle: Open and display the contents of an iCalendar file
ms:assetid: 2066e404-7aaf-4fd2-bf5c-9604e3fc2681
ms:mtpsurl: https://msdn.microsoft.com/library/Bb644609(v=office.15)
ms:contentKeyID: 55119818
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: dcebc65c651804148969c6260ecac72060bf9ef0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406776"
---
# <a name="open-and-display-the-contents-of-an-icalendar-file"></a>打开并显示 iCalendar 文件内容

该示例演示如何根据文件包含单个或重复性约会还是包含一组约会来打开和显示 iCalendar 文件的内容。

## <a name="example"></a>示例

该代码示例先尝试使用 [NameSpace](https://msdn.microsoft.com/library/bb645399\(v=office.15\)) 对象的 [OpenSharedItem](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法将 iCalendar 文件作为包含单个约会的 iCalendar 文件打开。如果操作成功，将在检查器窗口中显示约会项目的详细信息，但不会将该项目复制到默认存储区中。如果示例无法将该文件作为包含单个约会的 iCalendar 文件打开，则会使用 [NameSpace](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) 对象的 **OpenSharedFolder** 方法尝试将内容作为新日历导入默认存储区。如果导入成功，则会在资源管理器窗口中显示该日历。

此代码示例利用[创建用于访问常见 Outlook 项成员的帮助程序类员](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)中定义的 OutlookItem 帮助程序类，便捷地调用 **OutlookItem.Display** 方法来显示约会项，无需先强制转换项。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub OpenICalendarFile(ByVal fileName As String)
    If String.IsNullOrEmpty(fileName) Then
        Throw New ArgumentException(_
        "Parameter must contain a value.", "exportFileName")
    End If
    If Not File.Exists(fileName) Then
        Throw New FileNotFoundException(fileName)
    End If

    '' First try to open the icalendar file as an appointment 
    '' (not a calendar folder).
    Dim item As Object = Nothing
    Try
         item = Application.Session.OpenSharedItem(fileName)
    Catch
    End Try

    If Not item Is Nothing Then
        '' Display the item
        Dim olItem As OutlookItem = New OutlookItem(item)
        olItem.Display()
        Return
    End If

    '' If unsucessful in opening it as an item, 
    '' try opening it as a folder
    Dim importedFolder As Outlook.Folder = Nothing
    Try
        importedFolder = TryCast( _
            Application.Session.OpenSharedFolder(fileName), _
            Outlook.Folder)
    Catch
    End Try

    '' If sucessful, open the folder in a new explorer window
    If Not importedFolder Is Nothing Then
        Dim explorer As Outlook.Explorer = _
            Application.Explorers.Add( _
            importedFolder, _
            Outlook.OlFolderDisplayMode.olFolderDisplayNormal)
        explorer.Display()
    End If
End Sub
```


```csharp
private void OpenICalendarFile(string fileName)
{
    if (string.IsNullOrEmpty(fileName))
        throw new ArgumentException("exportFileName", 
        "Parameter must contain a value.");
    if (!File.Exists(fileName))
        throw new FileNotFoundException(fileName);

    // First try to open the icalendar file as an appointment 
    // (not a calendar folder).
    object item = null;
    try
    {
        item = Application.Session.OpenSharedItem(fileName);
    }
    catch
    { }

    if (item != null)
    {
         // Display the item
         OutlookItem olItem = new OutlookItem(item);
         olItem.Display();
         return;
    }

    // If unsucessful in opening it as an item, 
    // try opening it as a folder
    Outlook.Folder importedFolder = null;
    try
    {
        importedFolder = Application.Session.OpenSharedFolder(
            fileName, Type.Missing, Type.Missing, Type.Missing) 
            as Outlook.Folder;
    }
    catch
    { }

    // If sucessful, open the folder in a new explorer window
    if (importedFolder != null)
    {
        Outlook.Explorer explorer =
            Application.Explorers.Add(importedFolder, 
            Outlook.OlFolderDisplayMode.olFolderDisplayNormal);
        explorer.Display();
    }
}
```

## <a name="see-also"></a>另请参阅

- [日历](calendar.md)

