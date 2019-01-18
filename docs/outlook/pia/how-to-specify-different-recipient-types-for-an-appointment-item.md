---
title: 为约会项指定不同的收件人类型
TOCTitle: Specify different recipient types for an appointment item
ms:assetid: 83aedc8f-adc0-453d-8e71-1bb9aacc7993
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184622(v=office.15)
ms:contentKeyID: 55119807
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: beb29c46d590938d1650dac0c862dd5f898333fc
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709178"
---
# <a name="specify-different-recipient-types-for-an-appointment-item"></a>为约会项指定不同的收件人类型

此代码示例展示了如何通过使用 [OlMeetingRecipientType](https://msdn.microsoft.com/library/bb623431\(v=office.15\)) 枚举，为约会项指定不同的收件人类型。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

若要在表示会议请求的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象中添加收件人，可使用 OlMeetingRecipientType 枚举来指定邮件的收件人是必需与会者、可选与会者还是资源（如会议室或设备）。

在下面的代码示例中，SetRecipientTypeForAppt 创建 **AppointmentItem** 对象，设置此对象的属性，并添加必需与会者和可选与会者。 它还添加会议的会议室。 请注意，[MeetingStatus](https://msdn.microsoft.com/library/bb611417\(v=office.15\)) 属性设置为 [olMeeting](https://msdn.microsoft.com/library/bb644590\(v=office.15\))，这表示约会是会议请求。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void SetRecipientTypeForAppt()
{
    Outlook.AppointmentItem appt =
        Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Customer Review";
    appt.MeetingStatus = Outlook.OlMeetingStatus.olMeeting;
    appt.Location = "36/2021";
    appt.Start = DateTime.Parse("10/20/2006 10:00 AM");
    appt.End = DateTime.Parse("10/20/2006 11:00 AM");
    Outlook.Recipient recipRequired =
        appt.Recipients.Add("Ryan Gregg");
    recipRequired.Type =
        (int)Outlook.OlMeetingRecipientType.olRequired;
    Outlook.Recipient recipOptional =
        appt.Recipients.Add("Peter Allenspach");
    recipOptional.Type =
        (int)Outlook.OlMeetingRecipientType.olOptional;
    Outlook.Recipient recipConf =
        appt.Recipients.Add("Conf Room 36/2021 (14) AV");
    recipConf.Type =
        (int)Outlook.OlMeetingRecipientType.olResource;
    appt.Recipients.ResolveAll();
    appt.Display(false);
}
```

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

