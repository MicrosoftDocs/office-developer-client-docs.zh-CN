---
title: 响应任务请求项
TOCTitle: Respond to a task request item
ms:assetid: 573c98ef-4d15-4fd1-bccd-25a22c9a63f0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184608(v=office.15)
ms:contentKeyID: 55119896
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: ca85ee701b26f5ae896f9f4d012f93fea42930ec
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406727"
---
# <a name="respond-to-a-task-request-item"></a><span data-ttu-id="326b8-102">响应任务请求项</span><span class="sxs-lookup"><span data-stu-id="326b8-102">Respond to a task request item</span></span>

<span data-ttu-id="326b8-103">此示例展示了如何获取并响应任务请求项。</span><span class="sxs-lookup"><span data-stu-id="326b8-103">This example shows how to get and respond to a task request item.</span></span>

## <a name="example"></a><span data-ttu-id="326b8-104">示例</span><span class="sxs-lookup"><span data-stu-id="326b8-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="326b8-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="326b8-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="326b8-106">在下面的代码示例中，AcceptTaskRequest 使用 [TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\)) 对象的 [GetAssociatedTask(Boolean)](https://msdn.microsoft.com/library/bb645779\(v=office.15\)) 方法来获取 [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="326b8-106">In the following code example,   uses the GetAssociatedTask(Boolean) method of the TaskRequestItem object to get the TaskItem object.</span></span> <span data-ttu-id="326b8-107">然后，此代码示例调用 [Respond(OlTaskResponse, Object, Object)](https://msdn.microsoft.com/library/bb644188\(v=office.15\)) 方法，其中参数设置为 [olTaskAccept](https://msdn.microsoft.com/library/bb624484\(v=office.15\)) 以接受任务请求。</span><span class="sxs-lookup"><span data-stu-id="326b8-107">The example then calls the [Respond(OlTaskResponse, Object, Object)](https://msdn.microsoft.com/library/bb644188\(v=office.15\)) method with the parameter set to [olTaskAccept](https://msdn.microsoft.com/library/bb624484\(v=office.15\)) to accept the task request.</span></span>

<span data-ttu-id="326b8-108">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="326b8-108">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="326b8-109">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="326b8-109">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="326b8-110">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="326b8-110">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void AcceptTaskRequest()
{
    string filter = "[MessageClass] = 'IPM.TaskRequest'";
    Outlook.Items items =
        Application.Session.GetDefaultFolder
        (Outlook.OlDefaultFolders.olFolderInbox).
        Items.Restrict(filter);
    if (items.Count > 0)
    {
        Outlook.TaskRequestItem taskRequest =
            (Outlook.TaskRequestItem)items[1];
        Outlook.TaskItem task =
            taskRequest.GetAssociatedTask(false);
        Outlook.TaskItem taskResponse = task.Respond(
            Outlook.OlTaskResponse.olTaskAccept, true, false);
        taskResponse.Send();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="326b8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="326b8-111">See also</span></span>

- [<span data-ttu-id="326b8-112">任务</span><span class="sxs-lookup"><span data-stu-id="326b8-112">Tasks</span></span>](tasks.md)

