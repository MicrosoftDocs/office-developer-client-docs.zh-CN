---
title: 查找与会议请求关联的约会项
TOCTitle: Find the appointment item associated with a meeting request
ms:assetid: ff356fcf-0980-4567-8570-4bbcb14381e7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184658(v=office.15)
ms:contentKeyID: 55119875
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 5fa3822206d86b976bcfa2360cecf3ef22602e96
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407497"
---
# <a name="find-the-appointment-item-associated-with-a-meeting-request"></a><span data-ttu-id="4ae6e-102">查找与会议请求关联的约会项</span><span class="sxs-lookup"><span data-stu-id="4ae6e-102">Find the appointment item associated with a meeting request</span></span>

<span data-ttu-id="4ae6e-103">此代码示例展示了如何使用 [GetAssociatedAppointment(Boolean)](https://msdn.microsoft.com/library/bb652725\(v=office.15\)) 方法查找与会议请求相关联的约会。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-103">This example shows how to use the [GetAssociatedAppointment(Boolean)](https://msdn.microsoft.com/library/bb652725\(v=office.15\)) method to find the appointment that is associated with a meeting request.</span></span>

## <a name="example"></a><span data-ttu-id="4ae6e-104">示例</span><span class="sxs-lookup"><span data-stu-id="4ae6e-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="4ae6e-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="4ae6e-106">[MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) 对象并不表示约会，而是表示包含向收件人日历添加约会的请求的邮件。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-106">A [MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) object does not represent an appointment, but a message that contains a request to add an appointment to the recipient's calendar.</span></span> <span data-ttu-id="4ae6e-107">在下面的代码示例中，MeetingRequestExample 对从用户收件箱检索到的每个 **MeetingItem** 使用 **MeetingItem** 对象的 [GetAssociatedAppointment(Boolean)](https://msdn.microsoft.com/library/bb652725\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-107">In the following code example,   uses the GetAssociatedAppointment(Boolean) method of the MeetingItem object on each MeetingItem retrieved from the user's Inbox.</span></span> <span data-ttu-id="4ae6e-108">然后，此代码示例使用返回的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象，将约会的主题写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-108">The returned [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object is then used to write the subject of the appointment to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>


> [!NOTE]
> <span data-ttu-id="4ae6e-109">请注意，**GetAssociatedAppointment** 参数设置为 **false**，这样就不会将约会添加到用户日历中了。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-109">Note that **GetAssociatedAppointment** argument is set to **false** so that the appointment is not added to the user's calendar.</span></span>

<span data-ttu-id="4ae6e-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="4ae6e-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-111">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="4ae6e-112">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="4ae6e-112">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void MeetingRequestsExample()
{
    Outlook.Folder folder = Application.Session.
        GetDefaultFolder(Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    string filter = "[MessageClass] = " +
        "'IPM.Schedule.Meeting.Request'";
    Outlook.Items items = folder.Items.Restrict(filter);
    foreach (Outlook.MeetingItem request in items)
    {
        Outlook.AppointmentItem appt =
            request.GetAssociatedAppointment(false);
        if (appt != null)
        {
            Debug.WriteLine(appt.Subject);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="4ae6e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ae6e-113">See also</span></span>

- [<span data-ttu-id="4ae6e-114">会议请求</span><span class="sxs-lookup"><span data-stu-id="4ae6e-114">Meeting Requests</span></span>](meeting-requests.md)

