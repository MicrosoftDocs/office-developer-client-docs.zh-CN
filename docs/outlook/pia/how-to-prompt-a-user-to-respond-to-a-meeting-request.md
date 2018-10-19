---
title: 提示用户响应会议请求
TOCTitle: Prompt a user to respond to a meeting request
ms:assetid: a0d69f82-8659-457d-9418-1a897a10882f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184630(v=office.15)
ms:contentKeyID: 55119877
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: b309252685363774d45ff6f74e581b9be86b042f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407588"
---
# <a name="prompt-a-user-to-respond-to-a-meeting-request"></a>提示用户响应会议请求

本示例演示如何提示用户响应会议请求，以及如何使用户能够在发送响应之前编辑响应。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

[AppointmentItem](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) 对象的 [Respond](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 方法用于通知会议组织者，会议已获接受、遭拒绝，还是暂时添加到收件人的日历中。 通过使用 **Respond** 方法，可以指示是否要自动发送通知或者是否要允许用户在发送响应之前编辑响应。 **Respond** 方法接受三个参数。 *Response* 参数指明响应是接受、拒绝还是暂定。 *fNoUI* 和 *fAdditionalTextDialog* 参数是 **bool** 值，分别指明是否将响应发送给组织者，以及用户能否先编辑响应的正文再发送。 

在下面的代码示例中，PromptUserMeetingRequest 枚举所有 [MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) 对象，以获取关联的 **AppointmentItem** 对象，再调用 *fNoUI* 参数设置为 **false**、*fAdditionalTextDialog* 参数设置为 **true** 的 **Respond** 方法。 这样用户便可以选择是否发送响应，以及是否先编辑响应的正文再发送。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [会议请求](meeting-requests.md)

