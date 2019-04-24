---
title: 自动接受会议请求
TOCTitle: Automatically accept a meeting request
ms:assetid: 3c729bcf-4c85-4efa-af79-2c94d55c2042
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184604(v=office.15)
ms:contentKeyID: 55119874
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f546b4e2de2a77034fdfeca4d685d7b7f909f40a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359701"
---
# <a name="automatically-accept-a-meeting-request"></a>自动接受会议请求

此代码示例展示了如何使用 [Respond(OlMeetingResponse, Object, Object)](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) 方法自动接受会议请求。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


[MeetingItem](https://msdn.microsoft.com/library/bb645703\(v=office.15\)) 对象表示向收件人的日历添加约会（由 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象表示）的请求。 若要响应会议请求，请使用 [GetAssociatedAppointment(Boolean)](https://msdn.microsoft.com/library/bb652725\(v=office.15\)) 方法，获取与会议请求关联的 **AppointmentItem**。 然后，使用 **AppointmentItem** 的 [Respond(OlMeetingResponse, Object, Object)](https://msdn.microsoft.com/library/bb647086\(v=office.15\)) 方法，通知会议组织者会议已获接受、遭拒绝，还是暂时添加到收件人的日历中。 **Respond** 方法接受三个参数。 

*Response* 参数指明响应是接受、拒绝还是暂定。 fNoUI 和 fAdditionalTextDialog 参数是 **bool** 值，分别用于决定是否发送响应，以及用户能否编辑响应。 在下面的代码示例中，AutoAcceptMeetingRequests 枚举每个 **MeetingItem** 对象，以获取关联的 **AppointmentItem**。 然后，AutoAcceptMeetingRequests 使用 **Respond** 方法，其中 *fNoUI* 参数设置为 **true**，以指明将通过自动发送响应来接受会议请求。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [会议请求](meeting-requests.md)

