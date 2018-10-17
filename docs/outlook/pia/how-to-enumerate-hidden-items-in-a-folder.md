---
title: 枚举文件夹中的隐藏项
TOCTitle: Enumerate hidden items in a folder
ms:assetid: dafad1fb-94ce-4584-b5d1-2de5fad2f72a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184645(v=office.15)
ms:contentKeyID: 55119888
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: b048ec7fb47a8cbf6b8b49115c59079754fd4ba6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406020"
---
# <a name="enumerate-hidden-items-in-a-folder"></a>枚举文件夹中的隐藏项

此代码示例展示了如何查找并枚举文件夹中的隐藏项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示文件夹中的一组项，它的特征之一是其中可能包含隐藏项。 若要返回文件夹中的隐藏项，请将 [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) 对象的 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法中的 *TableContents* 参数设置为 [olHiddenItems](https://msdn.microsoft.com/library/bb622801\(v=office.15\))。 在下面的代码示例中，TableForInboxHiddenItems 获取收件箱文件夹的隐藏项，并将每个隐藏项的 [Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)) 和 [MessageClass](https://msdn.microsoft.com/library/bb645845\(v=office.15\)) 属性的值写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void TableForInboxHiddenItems()
{
    // Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // Call GetTable with OlTableContents.olHiddenItems
    Outlook.Table table =
        folder.GetTable("",
        Outlook.OlTableContents.olHiddenItems);
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        // Test for null subject
        if (nextRow["Subject"] == null)
        {
            Debug.WriteLine(nextRow["MessageClass"]);
        }
        else
        {
            Debug.WriteLine(nextRow["Subject"] + " "
                + nextRow["MessageClass"]);
        }
    }
}
```

## <a name="see-also"></a>另请参阅

-[搜索和筛选](search-and-filter.md)

