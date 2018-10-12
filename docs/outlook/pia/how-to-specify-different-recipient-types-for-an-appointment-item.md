---
title: 为约会项指定不同的收件人类型
TOCTitle: Specify different recipient types for an appointment item
ms:assetid: 83aedc8f-adc0-453d-8e71-1bb9aacc7993
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184622(v=office.15)
ms:contentKeyID: 55119807
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: c1f9e1d8e7b4c884853dda9b5c37cd7357d48b6c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405684"
---
# <a name="specify-different-recipient-types-for-an-appointment-item"></a><span data-ttu-id="b0f6f-102">为约会项指定不同的收件人类型</span><span class="sxs-lookup"><span data-stu-id="b0f6f-102">Uses the OlMeetingRecipientType enumeration to specify different recipient types for an appointment item.</span></span>

<span data-ttu-id="b0f6f-103">此代码示例展示了如何通过使用 [OlMeetingRecipientType](https://msdn.microsoft.com/library/bb623431\(v=office.15\)) 枚举，为约会项指定不同的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-103">This example shows how to use the [OlMeetingRecipientType](https://msdn.microsoft.com/library/bb623431\(v=office.15\)) enumeration to specify different recipient types for an appointment item.</span></span>

## <a name="example"></a><span data-ttu-id="b0f6f-104">示例</span><span class="sxs-lookup"><span data-stu-id="b0f6f-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="b0f6f-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="b0f6f-106">若要在表示会议请求的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象中添加收件人，可使用 OlMeetingRecipientType 枚举来指定邮件的收件人是必需与会者、可选与会者还是资源（如会议室或设备）。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-106">To add recipients to an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object that represents a meeting request, use the OlMeetingRecipientType enumeration to specify whether the recipient of the message is a required or optional attendee, or a resource (such as a room or equipment).</span></span>

<span data-ttu-id="b0f6f-107">在下面的代码示例中，SetRecipientTypeForAppt 创建 **AppointmentItem** 对象，设置此对象的属性，并添加必需与会者和可选与会者。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-107">In the following code example,   creates an AppointmentItem object, sets properties for that object, and adds required and optional attendees.</span></span> <span data-ttu-id="b0f6f-108">它还添加会议的会议室。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-108">It also adds a conference room for the meeting.</span></span> <span data-ttu-id="b0f6f-109">请注意，[MeetingStatus](https://msdn.microsoft.com/library/bb611417\(v=office.15\)) 属性设置为 [olMeeting](https://msdn.microsoft.com/library/bb644590\(v=office.15\))，这表示约会是会议请求。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-109">Note that the [MeetingStatus](https://msdn.microsoft.com/library/bb611417\(v=office.15\)) property is set to [olMeeting](https://msdn.microsoft.com/library/bb644590\(v=office.15\)) , indicating that the appointment is a meeting request.</span></span>

<span data-ttu-id="b0f6f-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="b0f6f-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-111">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="b0f6f-112">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b0f6f-112">The following line of code shows how to do the import and assignment in C#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b0f6f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0f6f-113">See also</span></span>

- [<span data-ttu-id="b0f6f-114">约会</span><span class="sxs-lookup"><span data-stu-id="b0f6f-114">Appointments</span></span>](appointments.md)

