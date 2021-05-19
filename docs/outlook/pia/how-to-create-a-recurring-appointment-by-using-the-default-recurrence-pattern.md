---
title: 使用默认定期模式创建定期约会
TOCTitle: Create a recurring appointment by using the default recurrence pattern
ms:assetid: 157bf1ae-2efe-4783-99ea-606722dde204
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184589(v=office.15)
ms:contentKeyID: 55119809
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: de58523e663349c43cc358f5b76896987a0f23b3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332114"
---
# <a name="create-a-recurring-appointment-by-using-the-default-recurrence-pattern"></a><span data-ttu-id="124ac-102">使用默认定期模式创建定期约会</span><span class="sxs-lookup"><span data-stu-id="124ac-102">Create a recurring appointment by using the default recurrence pattern</span></span>

<span data-ttu-id="124ac-103">此代码示例展示了如何使用默认定期模式创建定期约会。</span><span class="sxs-lookup"><span data-stu-id="124ac-103">This example shows how to create a recurring appointment by using the default recurrence pattern.</span></span>

## <a name="example"></a><span data-ttu-id="124ac-104">示例</span><span class="sxs-lookup"><span data-stu-id="124ac-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="124ac-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="124ac-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="124ac-106">在 Outlook 中创建约会时，创建的是 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="124ac-106">When you create an appointment in Outlook, you are creating an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object.</span></span> <span data-ttu-id="124ac-107">如果 AppointmentItem 的 [IsRecurring](https://msdn.microsoft.com/library/bb609491\(v=office.15\)) 属性设置为 true，约会就是定期约会。</span><span class="sxs-lookup"><span data-stu-id="124ac-107">Your appointment is a recurring appointment if the [IsRecurring](https://msdn.microsoft.com/library/bb609491\(v=office.15\)) property of the AppointmentItem is set to true.</span></span> <span data-ttu-id="124ac-108">无法直接设置 IsRecurring。</span><span class="sxs-lookup"><span data-stu-id="124ac-108">IsRecurring cannot be set directly.</span></span> 

<span data-ttu-id="124ac-109">不过，可使用 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象创建定期约会。</span><span class="sxs-lookup"><span data-stu-id="124ac-109">However, you can create a recurring appointment by using the [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object.</span></span> <span data-ttu-id="124ac-110">若要以编程方式创建定期约会，请创建 **AppointmentItem** 对象，调用 **AppointmentItem** 对象的 [GetRecurrencePattern()](https://msdn.microsoft.com/library/bb652582\(v=office.15\)) 方法，再保存 **AppointmentItem** 对象。</span><span class="sxs-lookup"><span data-stu-id="124ac-110">To create a recurring appointment programmatically, create an **AppointmentItem** object, call the [GetRecurrencePattern()](https://msdn.microsoft.com/library/bb652582\(v=office.15\)) method of the **AppointmentItem** object, and then save the **AppointmentItem** object.</span></span> <span data-ttu-id="124ac-111">这会创建使用默认定期模式的约会，即约会在创建时设置的每周几发生一次，且没有结束日期。</span><span class="sxs-lookup"><span data-stu-id="124ac-111">This creates an appointment that uses the default recurrence pattern, which occurs weekly on the day of the week for which the appointment was created, and has no end date.</span></span> <span data-ttu-id="124ac-112">借助 RecurrencePattern 对象，可以创建采用指定时间间隔的定期约会（即每日、每周、每月或每年发生一次）。</span><span class="sxs-lookup"><span data-stu-id="124ac-112">The RecurrencePattern object allows you to create recurring appointments at specified intervals—daily, weekly, monthly, or yearly.</span></span> <span data-ttu-id="124ac-113">如果你没有指定 RecurrencePattern 对象的时间间隔，Outlook 便会使用默认定期模式。</span><span class="sxs-lookup"><span data-stu-id="124ac-113">If you do not specify intervals for the RecurrencePattern object, Outlook will use the default recurrence pattern.</span></span>

<span data-ttu-id="124ac-114">当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。</span><span class="sxs-lookup"><span data-stu-id="124ac-114">When you work with recurring appointment items, you should release any prior references, obtain new references to the recurring appointment item before you access or modify the item, and release these references as soon as you are finished and have saved the changes.</span></span> <span data-ttu-id="124ac-115">此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="124ac-115">This practice applies to the recurring **AppointmentItem** object, and any [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) or [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object.</span></span> <span data-ttu-id="124ac-116">若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。</span><span class="sxs-lookup"><span data-stu-id="124ac-116">To release a reference in Visual Basic, set that existing object to Nothing.</span></span> <span data-ttu-id="124ac-117">在 C\# 中，显式释放相应对象占用的内存。</span><span class="sxs-lookup"><span data-stu-id="124ac-117">In C\#, explicitly release the memory for that object.</span></span>

<span data-ttu-id="124ac-p104">请注意，即使是在您释放引用并尝试获取新引用之后，如果仍存在对以上对象之一的活动引用（由另一个加载项或 Outlook 保存），则新引用也仍将指向对象的过期副本。因此，在完成使用定期约会后立即释放引用非常重要。</span><span class="sxs-lookup"><span data-stu-id="124ac-p104">Note that even after you release your reference and attempt to obtain a new reference, if there is still an active reference (held by another add-in or Outlook) to one of the above objects, your new reference will still point to an out-of-date copy of the object. Therefore, it is important that you release your references as soon as you are finished with the recurring appointment.</span></span>

<span data-ttu-id="124ac-120">在下面的代码示例中，CreateRecurringAppointment 创建 **AppointmentItem** 对象。</span><span class="sxs-lookup"><span data-stu-id="124ac-120">In the following example, CreateRecurringAppointment creates an **AppointmentItem** object.</span></span> <span data-ttu-id="124ac-121">然后，它调用 GetRecurrencePattern。</span><span class="sxs-lookup"><span data-stu-id="124ac-121">It then calls GetRecurrencePattern.</span></span> <span data-ttu-id="124ac-122">GetRecurrencePattern 返回 RecurrencePattern 对象，并保存 AppointmentItem。</span><span class="sxs-lookup"><span data-stu-id="124ac-122">GetRecurrencePattern returns a RecurrencePattern object, and the AppointmentItem is saved.</span></span> <span data-ttu-id="124ac-123">这会创建使用默认定期模式的定期约会。</span><span class="sxs-lookup"><span data-stu-id="124ac-123">This creates a recurring appointment that uses the default recurrence pattern.</span></span>

<span data-ttu-id="124ac-124">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="124ac-124">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="124ac-125">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="124ac-125">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="124ac-126">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="124ac-126">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void CreateRecurringAppointment()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Weekly Extensibility Team Meeting";
    Outlook.RecurrencePattern pattern = appt.GetRecurrencePattern();
    appt.Save();
}
```

## <a name="see-also"></a><span data-ttu-id="124ac-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="124ac-127">See also</span></span>

- [<span data-ttu-id="124ac-128">约会</span><span class="sxs-lookup"><span data-stu-id="124ac-128">Appointments</span></span>](appointments.md)

