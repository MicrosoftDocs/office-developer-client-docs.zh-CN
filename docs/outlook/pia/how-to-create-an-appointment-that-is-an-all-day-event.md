---
title: 创建属于全天事件的约会
TOCTitle: Create an appointment that is an all-day event
ms:assetid: a0d3baeb-6ed5-41b6-bef5-d6c1bb56fee3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184629(v=office.15)
ms:contentKeyID: 55119806
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b5065395afe39247f8113bc5223b0e3e403a02fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349474"
---
# <a name="create-an-appointment-that-is-an-all-day-event"></a><span data-ttu-id="95b8b-102">创建属于全天事件的约会</span><span class="sxs-lookup"><span data-stu-id="95b8b-102">Create an appointment that is an all-day event</span></span>

<span data-ttu-id="95b8b-103">此代码示例展示了如何使用 [AllDayEvent](https://msdn.microsoft.com/library/bb610279\(v=office.15\)) 属性创建属于全天事件的约会。</span><span class="sxs-lookup"><span data-stu-id="95b8b-103">This example shows how use the [AllDayEvent](https://msdn.microsoft.com/library/bb610279\(v=office.15\)) property to create an appointment that is an all-day event.</span></span>

## <a name="example"></a><span data-ttu-id="95b8b-104">示例</span><span class="sxs-lookup"><span data-stu-id="95b8b-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="95b8b-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="95b8b-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="95b8b-p101">事件不同于常规约会，因为它是持续 24 小时或更长时间的活动。事件示例包括贸易展览、讨论会或节假日。事件和年度事件在用户日历中不显示为占用的时间段，而是显示为横幅。可在日历的天视图或周视图顶部看到横幅。对于全天约会，默认情况下，在其他人查看时，用户时间显示为忙碌；但对于事件或年度事件，用户时间显示为空闲。</span><span class="sxs-lookup"><span data-stu-id="95b8b-p101">An event is different from a regular appointment because it is an activity that lasts 24 hours or longer. Examples of events include trade shows, seminars, or vacations. Events and annual events do not appear as occupied blocks of time in the user’s calendar. Instead, they appear as banners. You can see the banners at the top of a calendar day or week view. For an all-day appointment, by default, the user’s time is displayed as busy when viewed by other people, but the user’s time is displayed as free for an event or annual event.</span></span>

<span data-ttu-id="95b8b-112">若要以编程方式创建全天事件，请将 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象的 [AllDayEvent](https://msdn.microsoft.com/library/bb610279\(v=office.15\)) 属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="95b8b-112">To create an all-day event programmatically, set the [AllDayEvent](https://msdn.microsoft.com/library/bb610279\(v=office.15\)) property of the [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object to true.</span></span> <span data-ttu-id="95b8b-113">然后，设置 AppointmentItem 的 [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) 和 [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="95b8b-113">Then set the [Start](https://msdn.microsoft.com/library/bb647263\(v=office.15\)) and [End](https://msdn.microsoft.com/library/bb623715\(v=office.15\)) properties of the AppointmentItem.</span></span> <span data-ttu-id="95b8b-114">如果将 AllDayEvent 属性设置为 true 而没有设置 Start 和 End 属性，则事件会在今天发生，并且它会成为约会，在日历上显示忙碌状态。</span><span class="sxs-lookup"><span data-stu-id="95b8b-114">If you set the AllDayEvent property to true and do not set the Start and End properties, the event will occur today, and it will be an appointment, showing a busy status on your calendar.</span></span> <span data-ttu-id="95b8b-115">若要创建未来发生的事件，必须设置 Start 和 End 属性。</span><span class="sxs-lookup"><span data-stu-id="95b8b-115">You must set the Start and End properties if you want the event to occur on a future date.</span></span>

> [!NOTE]
> <span data-ttu-id="95b8b-116">若要创建属于全天事件的约会，必须将 Start 属性设置为所需事件开始日期当天的凌晨 12:00</span><span class="sxs-lookup"><span data-stu-id="95b8b-116">To make the appointment an all-day event, you must set the Start property to 12:00 A.M.</span></span> <span data-ttu-id="95b8b-117">（午夜），并将 End 属性设置为</span><span class="sxs-lookup"><span data-stu-id="95b8b-117">(midnight) on the day you want the event to begin, and set End property to 12:00 A.M.</span></span> <span data-ttu-id="95b8b-118">所需事件结束日期后一天的凌晨 12:00。</span><span class="sxs-lookup"><span data-stu-id="95b8b-118">on the day after you want the event to end.</span></span> <span data-ttu-id="95b8b-119">如果你将 Start 或 End 时间设置为除凌晨 12:00 以外的其他日期和时间值，约会便成为多天约会，而不是全天事件。</span><span class="sxs-lookup"><span data-stu-id="95b8b-119">If you set the Start or End time to a date and time value other than 12:00 A.M., the appointment will become a multiday appointment instead of an all-day event.</span></span> 
>
> <span data-ttu-id="95b8b-120">例如，如果事件持续时间只有一天，请将 Start 属性设置为所需事件开始日期当天的凌晨 12:00，</span><span class="sxs-lookup"><span data-stu-id="95b8b-120">For example, if your event duration is only one day, set the Start property to 12:00 A.M.</span></span> <span data-ttu-id="95b8b-121">并将 End 属性设置为后一天的</span><span class="sxs-lookup"><span data-stu-id="95b8b-121">on the day you want the event to begin, and set the End property to 12:00 A.M.</span></span> <span data-ttu-id="95b8b-122">凌晨 12:00。</span><span class="sxs-lookup"><span data-stu-id="95b8b-122">on the following day.</span></span> <span data-ttu-id="95b8b-123">应始终将 End 属性设置为</span><span class="sxs-lookup"><span data-stu-id="95b8b-123">You should always set the End property to 12:00 A.M.</span></span> <span data-ttu-id="95b8b-124">开始日期后一天的凌晨 12:00。</span><span class="sxs-lookup"><span data-stu-id="95b8b-124">on a date that is more than one day after the start date.</span></span>

<span data-ttu-id="95b8b-p105">在下面的代码示例中，AllDayEventExample 创建 2007 年 6 月 11 日开始，2007 年 6 月 15 日结束的全天事件。请注意，约会的 End 属性设置为 2007 年 6 月 16 日的午夜 12:00。</span><span class="sxs-lookup"><span data-stu-id="95b8b-p105">In the following code example, AllDayEventExample creates an all-day event that begins on June 11, 2007, and ends on June 15, 2007. Note that the End property for the appointment is set to 12:00 A.M. on June 16, 2007.</span></span>

<span data-ttu-id="95b8b-128">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="95b8b-128">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="95b8b-129">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="95b8b-129">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="95b8b-130">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="95b8b-130">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void AllDayEventExample()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Developer's Conference";
    appt.AllDayEvent = true;
    appt.Start = DateTime.Parse("6/11/2007 12:00 AM");
    appt.End = DateTime.Parse("6/16/2007 12:00 AM");
    appt.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="95b8b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95b8b-131">See also</span></span>

- [<span data-ttu-id="95b8b-132">约会</span><span class="sxs-lookup"><span data-stu-id="95b8b-132">Appointments</span></span>](appointments.md)

