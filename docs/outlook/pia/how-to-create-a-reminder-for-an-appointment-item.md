---
title: 创建约会项提醒
TOCTitle: Create a reminder for an appointment item
ms:assetid: 85e772f0-65ac-4abc-8286-9099882a2400
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184623(v=office.15)
ms:contentKeyID: 55119814
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1f5f31c480f31b01e53fec9651c8154765b581a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349495"
---
# <a name="create-a-reminder-for-an-appointment-item"></a><span data-ttu-id="7fd61-102">创建约会项提醒</span><span class="sxs-lookup"><span data-stu-id="7fd61-102">Create a reminder for an appointment item</span></span>

<span data-ttu-id="7fd61-103">此代码示例展示了如何使用 [ReminderSet](https://msdn.microsoft.com/library/bb624262\(v=office.15\)) 属性创建约会项提醒。</span><span class="sxs-lookup"><span data-stu-id="7fd61-103">This example shows how to use the [ReminderSet](https://msdn.microsoft.com/library/bb624262\(v=office.15\)) property to create a reminder for an appointment item.</span></span>

## <a name="example"></a><span data-ttu-id="7fd61-104">示例</span><span class="sxs-lookup"><span data-stu-id="7fd61-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="7fd61-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="7fd61-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="7fd61-106">借助 Outlook，可设置约会提醒，具体方法为使用 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象的 [ReminderSet](https://msdn.microsoft.com/library/bb624262\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="7fd61-106">Outlook provides a way to set a reminder for an appointment by using the [ReminderSet](https://msdn.microsoft.com/library/bb624262\(v=office.15\)) property of the [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object.</span></span> <span data-ttu-id="7fd61-107">此属性指明是否已创建约会提醒。</span><span class="sxs-lookup"><span data-stu-id="7fd61-107">This property indicates whether a reminder has been created for the appointment.</span></span> <span data-ttu-id="7fd61-108">将 ReminderSet 属性设置为 true 即可创建提醒，设置为 false 即可删除提醒。</span><span class="sxs-lookup"><span data-stu-id="7fd61-108">Setting the ReminderSet property to true creates a reminder, and setting it to false removes the reminder.</span></span>

<span data-ttu-id="7fd61-109">在下面的代码示例中，ReminderExample 为在加利福尼亚州纳帕市举办的品酒会这一私人约会创建提醒，并设置为在约会开始前提前两小时发出提醒。</span><span class="sxs-lookup"><span data-stu-id="7fd61-109">In the following code example, ReminderExample creates a reminder on a private appointment for wine tasting in Napa, California, and sets the reminder to occur two hours before the appointment starts.</span></span> <span data-ttu-id="7fd61-110">首先，ReminderExample 创建 Outlook **AppointmentItem** 对象。</span><span class="sxs-lookup"><span data-stu-id="7fd61-110">First, ReminderExample creates an Outlook **AppointmentItem** object.</span></span> <span data-ttu-id="7fd61-111">然后，它将项的 [Sensitivity](https://msdn.microsoft.com/library/bb623503\(v=office.15\)) 属性设置为 [olPrivate](https://msdn.microsoft.com/library/bb645125\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="7fd61-111">It then sets the [Sensitivity](https://msdn.microsoft.com/library/bb623503\(v=office.15\)) property for the item to [olPrivate](https://msdn.microsoft.com/library/bb645125\(v=office.15\)).</span></span> <span data-ttu-id="7fd61-112">这表示约会为私人约会。</span><span class="sxs-lookup"><span data-stu-id="7fd61-112">This indicates that the appointment is a private appointment.</span></span> <span data-ttu-id="7fd61-113">设置约会的其他属性（如 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 和 [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)) 时间）后，ReminderExample 设置 [ReminderMinutesBeforeStart](https://msdn.microsoft.com/library/bb644528\(v=office.15\)) 属性，指明在约会开始前提前多少分钟发出提醒。</span><span class="sxs-lookup"><span data-stu-id="7fd61-113">After setting other properties of the appointment, such as [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) and [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)) times, ReminderExample sets the [ReminderMinutesBeforeStart](https://msdn.microsoft.com/library/bb644528\(v=office.15\)) property to indicate the number of minutes that the reminder will appear before the start of the appointment.</span></span> <span data-ttu-id="7fd61-114">在此代码示例中，ReminderMinutesBeforeStart 设置为 120 分钟（两小时）。</span><span class="sxs-lookup"><span data-stu-id="7fd61-114">In this case, ReminderMinutesBeforeStart is set to 120 minutes (two hours).</span></span>

<span data-ttu-id="7fd61-115">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="7fd61-115">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="7fd61-116">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="7fd61-116">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="7fd61-117">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="7fd61-117">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void ReminderExample()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Wine Tasting";
    appt.Location = "Napa CA";
    appt.Sensitivity = Outlook.OlSensitivity.olPrivate;
    appt.Start = DateTime.Parse("10/21/2006 10:00 AM");
    appt.End = DateTime.Parse("10/21/2006 3:00 PM");
    appt.ReminderSet = true;
    appt.ReminderMinutesBeforeStart = 120;
    appt.Save();
}
```

## <a name="see-also"></a><span data-ttu-id="7fd61-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fd61-118">See also</span></span>

- [<span data-ttu-id="7fd61-119">约会</span><span class="sxs-lookup"><span data-stu-id="7fd61-119">Appointments</span></span>](appointments.md)

