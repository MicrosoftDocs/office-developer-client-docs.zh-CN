---
title: 显示发送给收件人的任务请求项
TOCTitle: Display the task request items sent to a recipient
ms:assetid: 167c3d52-67b5-467c-a7b6-e8cc96002b63
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184591(v=office.15)
ms:contentKeyID: 55119930
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: f26e8d1402b75272e79c6244b7bd2875d783c1f1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406636"
---
# <a name="display-the-task-request-items-sent-to-a-recipient"></a>显示发送给收件人的任务请求项

此代码示例展示了如何显示收件人收件箱中的所有任务请求项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

[TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\)) 对象表示将任务分配给另一个用户的请求。 **TaskRequestItem** 在收件人收件箱中收到项时创建。 在下面的代码示例中，ShowTaskRequests 对收件人收件箱进行筛选，创建 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象，并为 [MessageClass](https://msdn.microsoft.com/library/bb610592\(v=office.15\)) 属性值等于 **IPM.TaskRequest** 的所有项都插入一行。 然后，此代码示例将收件人“收件箱”文件夹中每个任务的主题写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void ShowTaskRequests()
{
    string filter = "[MessageClass] = 'IPM.TaskRequest'";
    Outlook.Table table =
        Application.Session.GetDefaultFolder
        (Outlook.OlDefaultFolders.olFolderInbox).GetTable
        (filter, Outlook.OlTableContents.olUserItems);
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        Debug.WriteLine(nextRow["Subject"]);
    }
}
```

## <a name="see-also"></a>另请参阅

- [任务](tasks.md)

