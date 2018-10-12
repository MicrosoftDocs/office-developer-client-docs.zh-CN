---
title: 自动接受会议请求
TOCTitle: Automatically accept a meeting request
ms:assetid: 3c729bcf-4c85-4efa-af79-2c94d55c2042
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184604(v=office.15)
ms:contentKeyID: 55119874
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: d49044d87cd14c150527d518108f740b9eb319da
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405733"
---
# <a name="automatically-accept-a-meeting-request"></a><span data-ttu-id="178c8-102">自动接受会议请求</span><span class="sxs-lookup"><span data-stu-id="178c8-102">Automatically accept a meeting request</span></span>

<span data-ttu-id="178c8-103">此代码示例展示了如何使用 [Respond(OlMeetingResponse, Object, Object)](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) 方法自动接受会议请求。</span><span class="sxs-lookup"><span data-stu-id="178c8-103">This example shows how to use the [Respond(OlMeetingResponse, Object, Object)](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) method to automatically accept a meeting request.</span></span>

## <a name="example"></a><span data-ttu-id="178c8-104">示例</span><span class="sxs-lookup"><span data-stu-id="178c8-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="178c8-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="178c8-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>


<span data-ttu-id="178c8-106">[MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) 对象表示向收件人的日历添加约会（由 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象表示）的请求。</span><span class="sxs-lookup"><span data-stu-id="178c8-106">A [MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) object represents a request to add an appointment, represented by an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object, to a recipient's calendar.</span></span> <span data-ttu-id="178c8-107">若要响应会议请求，请使用 [GetAssociatedAppointment(Boolean)](https://msdn.microsoft.com/library/bb652725\(v=office.15\)) 方法，获取与会议请求关联的 **AppointmentItem**。</span><span class="sxs-lookup"><span data-stu-id="178c8-107">To respond to a meeting request, use the [GetAssociatedAppointment(Boolean)](https://msdn.microsoft.com/library/bb652725\(v=office.15\)) method to obtain the **AppointmentItem** associated with the meeting request.</span></span> <span data-ttu-id="178c8-108">然后，使用 **AppointmentItem** 的 [Respond(OlMeetingResponse, Object, Object)](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) 方法，通知会议组织者会议已获接受、遭拒绝，还是暂时添加到收件人的日历中。</span><span class="sxs-lookup"><span data-stu-id="178c8-108">Then use the [Respond(OlMeetingResponse, Object, Object)](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) method of the **AppointmentItem** to notify the meeting organizer whether the meeting has been accepted, declined, or tentatively added to the recipient's calendar.</span></span> <span data-ttu-id="178c8-109">**Respond** 方法接受三个参数。</span><span class="sxs-lookup"><span data-stu-id="178c8-109">The **Respond** method accepts three parameters.</span></span> 

<span data-ttu-id="178c8-110">*Response* 参数指明响应是接受、拒绝还是暂定。</span><span class="sxs-lookup"><span data-stu-id="178c8-110">The  *Response* parameter indicates whether the response is accept, decline, or tentative.</span></span> <span data-ttu-id="178c8-111">fNoUI 和 fAdditionalTextDialog 参数是 **bool** 值，分别用于决定是否发送响应，以及用户能否编辑响应。</span><span class="sxs-lookup"><span data-stu-id="178c8-111">The  fNoUI and  fAdditionalTextDialog parameters are **bool** values that determine whether a response will be sent, and whether the user may or may not edit the response, respectively.</span></span> <span data-ttu-id="178c8-112">在下面的代码示例中，AutoAcceptMeetingRequests 枚举每个 **MeetingItem** 对象，以获取关联的 **AppointmentItem**。</span><span class="sxs-lookup"><span data-stu-id="178c8-112">In the following code example,   enumerates through every MeetingItem object to get the associated AppointmentItem.</span></span> <span data-ttu-id="178c8-113">然后，AutoAcceptMeetingRequests 使用 **Respond** 方法，其中 *fNoUI* 参数设置为 **true**，以指明将通过自动发送响应来接受会议请求。</span><span class="sxs-lookup"><span data-stu-id="178c8-113"> then uses the Respond method with the  fNoUI parameter set to true to indicate that a response will be sent automatically to accept the meeting request.</span></span>

<span data-ttu-id="178c8-114">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="178c8-114">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="178c8-115">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="178c8-115">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="178c8-116">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="178c8-116">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void AutoAcceptMeetingRequests()
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
                true, Type.Missing);
            mtgResponse.Send();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="178c8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="178c8-117">See also</span></span>

- [<span data-ttu-id="178c8-118">会议请求</span><span class="sxs-lookup"><span data-stu-id="178c8-118">Meeting Requests</span></span>](meeting-requests.md)

