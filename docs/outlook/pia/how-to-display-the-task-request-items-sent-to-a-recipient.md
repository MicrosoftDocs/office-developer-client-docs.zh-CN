---
title: 显示发送给收件人的任务请求项
TOCTitle: Display the task request items sent to a recipient
ms:assetid: 167c3d52-67b5-467c-a7b6-e8cc96002b63
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184591(v=office.15)
ms:contentKeyID: 55119930
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9ab5e830003fbfb64b44fc9e0d813c7a7c5163bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357419"
---
# <a name="display-the-task-request-items-sent-to-a-recipient"></a><span data-ttu-id="3036b-102">显示发送给收件人的任务请求项</span><span class="sxs-lookup"><span data-stu-id="3036b-102">Display the task request items sent to a recipient</span></span>

<span data-ttu-id="3036b-103">此代码示例展示了如何显示收件人收件箱中的所有任务请求项。</span><span class="sxs-lookup"><span data-stu-id="3036b-103">This example shows how to display all of the task request items that are in a recipient's Inbox.</span></span>

## <a name="example"></a><span data-ttu-id="3036b-104">示例</span><span class="sxs-lookup"><span data-stu-id="3036b-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="3036b-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="3036b-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="3036b-106">[TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\)) 对象表示将任务分配给另一个用户的请求。</span><span class="sxs-lookup"><span data-stu-id="3036b-106">A [TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\)) object represents a request to assign a task to another user.</span></span> <span data-ttu-id="3036b-107">**TaskRequestItem** 在收件人收件箱中收到项时创建。</span><span class="sxs-lookup"><span data-stu-id="3036b-107">The **TaskRequestItem** is created when the item is received in the recipient's Inbox.</span></span> <span data-ttu-id="3036b-108">在下面的代码示例中，ShowTaskRequests 对收件人收件箱进行筛选，创建 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象，并为 [MessageClass](https://msdn.microsoft.com/library/bb610592\(v=office.15\)) 属性值等于 **IPM.TaskRequest** 的所有项都插入一行。</span><span class="sxs-lookup"><span data-stu-id="3036b-108">In the following code example, ShowTaskRequests filters through a recipient’s Inbox, creates a [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object, and inserts a row for each item for which the value of the [MessageClass](https://msdn.microsoft.com/library/bb610592\(v=office.15\)) property equals **IPM.TaskRequest**.</span></span> <span data-ttu-id="3036b-109">然后，此代码示例将收件人“收件箱”文件夹中每个任务的主题写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="3036b-109">The subject of each task in the recipient’s Inbox folder is then written to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="3036b-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="3036b-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="3036b-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="3036b-111">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="3036b-112">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="3036b-112">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3036b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3036b-113">See also</span></span>

- [<span data-ttu-id="3036b-114">任务</span><span class="sxs-lookup"><span data-stu-id="3036b-114">Tasks</span></span>](tasks.md)

