---
title: 选择文件夹并显示文件夹信息
TOCTitle: Select a folder and display folder information
ms:assetid: 737b19bc-1efd-4ddb-86d0-72b3ab8eaf8c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184616(v=office.15)
ms:contentKeyID: 55119859
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 41dc96f26e7e0040467096731cb16ae7c0c08f74
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721933"
---
# <a name="select-a-folder-and-display-folder-information"></a>选择文件夹并显示文件夹信息

此代码示例展示了如何以编程方式显示用户从指定文件夹列表中选择的文件夹的相关信息。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

在下面的代码示例中，ShowFolderInfo 使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [PickFolder()](https://msdn.microsoft.com/library/bb623484\(v=office.15\)) 方法，向用户显示“选择文件夹”**** 对话框，并等待用户选择文件夹。 在用户选择文件夹后，此代码示例便会显示文件夹的 [EntryID](https://msdn.microsoft.com/library/bb646192\(v=office.15\))、[StoreID](https://msdn.microsoft.com/library/bb612609\(v=office.15\))、[UnReadItemCount](https://msdn.microsoft.com/library/bb610138\(v=office.15\))、[DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\))、[CurrentView](https://msdn.microsoft.com/library/bb612411\(v=office.15\))、[Name](https://msdn.microsoft.com/library/bb623727\(v=office.15\)) 和 [FolderPath](https://msdn.microsoft.com/library/bb647409\(v=office.15\)) 属性。 然后，此代码示例调用 [GetFolderFromID](https://msdn.microsoft.com/library/bb647784\(v=office.15\)) 方法，以新建 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象并显示文件夹。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void ShowFolderInfo()
{
    Outlook.Folder folder =
        Application.Session.PickFolder()
        as Outlook.Folder;
    if (folder != null)
    {
        StringBuilder sb = new StringBuilder();
        sb.AppendLine("Folder EntryID:");
        sb.AppendLine(folder.EntryID);
        sb.AppendLine();
        sb.AppendLine("Folder StoreID:");
        sb.AppendLine(folder.StoreID);
        sb.AppendLine();
        sb.AppendLine("Unread Item Count: "
            + folder.UnReadItemCount);
        sb.AppendLine("Default MessageClass: "
            + folder.DefaultMessageClass);
        sb.AppendLine("Current View: "
            + folder.CurrentView.Name);
        sb.AppendLine("Folder Path: "
            + folder.FolderPath);
        MessageBox.Show(sb.ToString(),
            "Folder Information",
            MessageBoxButtons.OK,
            MessageBoxIcon.Information);
        Outlook.Folder folderFromID =
            Application.Session.GetFolderFromID(
            folder.EntryID, folder.StoreID)
            as Outlook.Folder;
        folderFromID.Display();
    }
}
```

## <a name="see-also"></a>另请参阅

- [文件夹](folders.md)

