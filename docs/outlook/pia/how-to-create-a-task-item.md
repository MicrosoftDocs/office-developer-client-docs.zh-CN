---
title: 创建任务项
TOCTitle: Create a task item
ms:assetid: d458dd31-2771-4a3c-a713-13c7e4e02a74
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184644(v=office.15)
ms:contentKeyID: 55119894
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 467d715e0fca1adfd835b11c36889dff3dbf145d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406804"
---
# <a name="create-a-task-item"></a><span data-ttu-id="18d13-102">创建任务项</span><span class="sxs-lookup"><span data-stu-id="18d13-102">Create a task item</span></span>

<span data-ttu-id="18d13-103">此代码示例展示了如何使用 [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)) 方法创建任务项。</span><span class="sxs-lookup"><span data-stu-id="18d13-103">This example shows how to create a task item by using the [MarkAsTask(OlMarkInterval)](https://msdn.microsoft.com/library/bb609068\(v=office.15\)) method.</span></span>

## <a name="example"></a><span data-ttu-id="18d13-104">示例</span><span class="sxs-lookup"><span data-stu-id="18d13-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="18d13-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="18d13-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>


<span data-ttu-id="18d13-106">在下面的代码示例中，CreateToDoItemExample 创建待办事项，具体方法为对项调用 **MarkAsTask** 方法并保存项。</span><span class="sxs-lookup"><span data-stu-id="18d13-106">In the following code example, CreateToDoItemExample creates a to-do item by calling the **MarkAsTask** method on the item and then saving the item.</span></span> <span data-ttu-id="18d13-107">此示例标记项以供明天跟进，并设置明天上午 10:00 的提醒</span><span class="sxs-lookup"><span data-stu-id="18d13-107">The example marks the item for follow-up tomorrow and sets a reminder for tomorrow at 10:00 A.M.</span></span> <span data-ttu-id="18d13-108">（具体是使用 [ReminderSet](https://msdn.microsoft.com/library/bb622600\(v=office.15\)) 和 [ReminderTime](https://msdn.microsoft.com/library/bb622803\(v=office.15\)) 属性）。</span><span class="sxs-lookup"><span data-stu-id="18d13-108">by using the [ReminderSet](https://msdn.microsoft.com/library/bb622600\(v=office.15\)) and [ReminderTime](https://msdn.microsoft.com/library/bb622803\(v=office.15\)) properties.</span></span> <span data-ttu-id="18d13-109">然后，此代码示例使用 [Save()](https://msdn.microsoft.com/library/bb645518\(v=office.15\)) 方法保存项。</span><span class="sxs-lookup"><span data-stu-id="18d13-109">The example then uses the [Save()](https://msdn.microsoft.com/library/bb645518\(v=office.15\)) method to save the item.</span></span>

<span data-ttu-id="18d13-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="18d13-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="18d13-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="18d13-111">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="18d13-112">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="18d13-112">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateToDoItemExample()
{
    // Date operations
    DateTime today = DateTime.Parse("10:00 AM");
    TimeSpan duration = TimeSpan.FromDays(1);
    DateTime tomorrow = today.Add(duration);
    Outlook.MailItem mail = Application.Session.
        GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).Items.Find(
        "[MessageClass]='IPM.Note'") as Outlook.MailItem;
    mail.MarkAsTask(Outlook.OlMarkInterval.olMarkTomorrow);
    mail.TaskStartDate = today;
    mail.ReminderSet = true;
    mail.ReminderTime = tomorrow;
    mail.Save();
}
```

## <a name="see-also"></a><span data-ttu-id="18d13-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18d13-113">See also</span></span>

- [<span data-ttu-id="18d13-114">任务</span><span class="sxs-lookup"><span data-stu-id="18d13-114">Tasks</span></span>](tasks.md)

