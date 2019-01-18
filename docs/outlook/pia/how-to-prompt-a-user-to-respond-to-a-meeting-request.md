---
title: 提示用户响应会议请求
TOCTitle: Prompt a user to respond to a meeting request
ms:assetid: a0d69f82-8659-457d-9418-1a897a10882f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184630(v=office.15)
ms:contentKeyID: 55119877
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 26e59cca7431e9f11f3fea5fa058548b9a5903a4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722611"
---
# <a name="prompt-a-user-to-respond-to-a-meeting-request"></a><span data-ttu-id="d33e2-102">提示用户响应会议请求</span><span class="sxs-lookup"><span data-stu-id="d33e2-102">Prompt a user to respond to a meeting request</span></span>

<span data-ttu-id="d33e2-103">本示例演示如何提示用户响应会议请求，以及如何使用户能够在发送响应之前编辑响应。</span><span class="sxs-lookup"><span data-stu-id="d33e2-103">This example shows how to prompt the user for a response to a meeting request, and to enable the user to edit the response before sending it.</span></span>

## <a name="example"></a><span data-ttu-id="d33e2-104">示例</span><span class="sxs-lookup"><span data-stu-id="d33e2-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="d33e2-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="d33e2-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="d33e2-106">[AppointmentItem](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) 对象的 [Respond](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 方法用于通知会议组织者，会议已获接受、遭拒绝，还是暂时添加到收件人的日历中。</span><span class="sxs-lookup"><span data-stu-id="d33e2-106">The [Respond](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) method of the [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object is used to notify the meeting organizer whether the meeting has been accepted, declined, or tentatively added to the recipient’s calendar.</span></span> <span data-ttu-id="d33e2-107">通过使用 **Respond** 方法，可以指示是否要自动发送通知或者是否要允许用户在发送响应之前编辑响应。</span><span class="sxs-lookup"><span data-stu-id="d33e2-107">By using the **Respond** method, you can indicate whether you want to send the notification automatically, or whether you want to allow the user to edit the response before sending it.</span></span> <span data-ttu-id="d33e2-108">**Respond** 方法接受三个参数。</span><span class="sxs-lookup"><span data-stu-id="d33e2-108">The **Respond** method accepts three parameters.</span></span> <span data-ttu-id="d33e2-109">*Response* 参数指明响应是接受、拒绝还是暂定。</span><span class="sxs-lookup"><span data-stu-id="d33e2-109">The *Response* parameter indicates whether the response is accept, decline, or tentative.</span></span> <span data-ttu-id="d33e2-110">*fNoUI* 和 *fAdditionalTextDialog* 参数是 **bool** 值，分别指明是否将响应发送给组织者，以及用户能否先编辑响应的正文再发送。</span><span class="sxs-lookup"><span data-stu-id="d33e2-110">The *fNoUI* and *fAdditionalTextDialog* parameters are **bool** values that indicate whether the response will be sent to the organizer, and whether the user can edit the body of the response before sending it, respectively.</span></span> 

<span data-ttu-id="d33e2-111">在下面的代码示例中，PromptUserMeetingRequest 枚举所有 [MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) 对象，以获取关联的 **AppointmentItem** 对象，再调用 *fNoUI* 参数设置为 **false**、*fAdditionalTextDialog* 参数设置为 **true** 的 **Respond** 方法。</span><span class="sxs-lookup"><span data-stu-id="d33e2-111">In the following code example, PromptUserMeetingRequest enumerates through the [MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) objects to get the associated **AppointmentItem** objects, and then calls the **Respond** method with the *fNoUI* parameter set to **false** and the *fAdditionalTextDialog* parameter set to **true**.</span></span> <span data-ttu-id="d33e2-112">这样用户便可以选择是否发送响应，以及是否先编辑响应的正文再发送。</span><span class="sxs-lookup"><span data-stu-id="d33e2-112">This allows the user to choose whether to send a response, and whether to edit the body of the response before sending it.</span></span>

<span data-ttu-id="d33e2-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d33e2-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="d33e2-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d33e2-114">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="d33e2-115">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d33e2-115">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void PromptUserMeetingRequest()
{
    Outlook.MeetingItem mtgResponse;
    Outlook.Folder folder = Application.Session.
        GetDefaultFolder(Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    string filter = "[MessageClass] = " +
        "'IPM.Schedule.Meeting.Request'";
    Outlook.Items items = folder.Items.Restrict(filter);
    foreach (Outlook.MeetingItem request in items)
    {
        Outlook.AppointmentItem appt =
            request.GetAssociatedAppointment(true);
        if (appt != null)
        {
            mtgResponse = appt.Respond(
                Outlook.OlMeetingResponse.olMeetingAccepted,
                false, true);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d33e2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d33e2-116">See also</span></span>

- [<span data-ttu-id="d33e2-117">会议请求</span><span class="sxs-lookup"><span data-stu-id="d33e2-117">Meeting requests</span></span>](meeting-requests.md)

