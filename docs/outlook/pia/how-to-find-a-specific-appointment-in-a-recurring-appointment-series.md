---
title: 在定期约会系列中查找特定约会
TOCTitle: Find a specific appointment in a recurring appointment series
ms:assetid: 01f55f04-7245-4325-a354-50a6eb270a31
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184586(v=office.15)
ms:contentKeyID: 55119812
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 19502895996d4777f2d1a6887aa80883a5398a09
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320249"
---
# <a name="find-a-specific-appointment-in-a-recurring-appointment-series"></a><span data-ttu-id="07eb4-102">在定期约会系列中查找特定约会</span><span class="sxs-lookup"><span data-stu-id="07eb4-102">Find a specific appointment in a recurring appointment series</span></span>

<span data-ttu-id="07eb4-103">此代码示例展示了如何返回代表定期约会系列中特定约会的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="07eb4-103">This example shows how to return an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object that represents a specific appointment in a recurring appointment series.</span></span>

## <a name="example"></a><span data-ttu-id="07eb4-104">示例</span><span class="sxs-lookup"><span data-stu-id="07eb4-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="07eb4-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="07eb4-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="07eb4-106">若要查找在指定日期和时间发生的定期约会的实例，请使用 [RecurrencePattern](https://msdn.microsoft.com/library/bb622806\(v=office.15\)) 对象的 [GetOccurrence(DateTime)](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 方法返回 **AppointmentItem** 对象。</span><span class="sxs-lookup"><span data-stu-id="07eb4-106">To find an instance of a recurring appointment that occurs at a specified date and time, use the [GetOccurrence(DateTime)](https://msdn.microsoft.com/library/bb622806\(v=office.15\)) method of the [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object to return an **AppointmentItem** object.</span></span>

<span data-ttu-id="07eb4-107">当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。</span><span class="sxs-lookup"><span data-stu-id="07eb4-107">When you work with recurring appointment items, you should release any prior references, obtain new references to the recurring appointment item before you access or modify the item, and release these references as soon as you are finished and have saved the changes.</span></span> <span data-ttu-id="07eb4-108">此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="07eb4-108">This practice applies to the recurring **AppointmentItem** object, and any [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) or [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object.</span></span> <span data-ttu-id="07eb4-109">若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。</span><span class="sxs-lookup"><span data-stu-id="07eb4-109">To release a reference in Visual Basic, set that existing object to Nothing.</span></span> <span data-ttu-id="07eb4-110">在 C\# 中，显式释放相应对象占用的内存。</span><span class="sxs-lookup"><span data-stu-id="07eb4-110">In C\#, explicitly release the memory for that object.</span></span>

<span data-ttu-id="07eb4-p102">请注意，即使是在您释放引用并尝试获取新引用之后，如果仍存在对以上对象之一的活动引用（由另一个加载项或 Outlook 保存），则新引用也仍将指向对象的过期副本。因此，在完成使用定期约会后立即释放引用非常重要。</span><span class="sxs-lookup"><span data-stu-id="07eb4-p102">Note that even after you release your reference and attempt to obtain a new reference, if there is still an active reference (held by another add-in or Outlook) to one of the above objects, your new reference will still point to an out-of-date copy of the object. Therefore, it is important that you release your references as soon as you are finished with the recurring appointment.</span></span>

<span data-ttu-id="07eb4-113">在下面的代码示例中，CheckOccurrenceExample 使用在[创建模式为每周一次的定期约会](how-to-create-a-recurring-appointment-that-has-a-weekly-pattern.md)的代码示例中创建的定期约会。</span><span class="sxs-lookup"><span data-stu-id="07eb4-113">In the following code example, CheckOccurrenceExample uses the recurring appointment that was created in the code example in [Create a Recurring Appointment That Has a Weekly Pattern](how-to-create-a-recurring-appointment-that-has-a-weekly-pattern.md).</span></span> <span data-ttu-id="07eb4-114">然后，它调用 GetOccurrence 方法，以确定定期约会的开始日期和时间是否为指定值。</span><span class="sxs-lookup"><span data-stu-id="07eb4-114">It then calls the GetOccurrence method to determine whether the recurring appointment starts on the specified date and time.</span></span> <span data-ttu-id="07eb4-115">为了确保过程在提供的信息与定期约会实例的开始日期和时间不匹配时仍可继续执行，此示例使用 try…catch 块。</span><span class="sxs-lookup"><span data-stu-id="07eb4-115">To ensure that the procedure will continue even if the provided information does not match the start date and time of an instance of the recurring appointment, the example uses a try…catch block.</span></span> <span data-ttu-id="07eb4-116">对定期约会系列中的每个约会调用 GetOccurrence 方法后，CheckOccurrenceExample 测试 singleAppt 变量，以确定它是否设置为空引用（表明方法失败且未返回 **AppointmentItem** 对象）。</span><span class="sxs-lookup"><span data-stu-id="07eb4-116">After calling the GetOccurrence method on every appointment in the recurring appointment series, CheckOccurrenceExample tests the singleAppt variable to determine whether it is set to a null reference, indicating that the method failed and did not return an **AppointmentItem** object.</span></span>

<span data-ttu-id="07eb4-117">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="07eb4-117">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="07eb4-118">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="07eb4-118">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="07eb4-119">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="07eb4-119">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void CheckOccurrenceExample()
{
    Outlook.AppointmentItem appt = Application.Session.
        GetDefaultFolder(Outlook.OlDefaultFolders.olFolderCalendar).
        Items.Find(
        "[Subject]='Recurring Appointment DaysOfWeekMask Example'")
        as Outlook.AppointmentItem;
    if (appt != null)
    {
        try
        {
            Outlook.RecurrencePattern pattern =
                appt.GetRecurrencePattern();
            Outlook.AppointmentItem singleAppt =
                pattern.GetOccurrence(DateTime.Parse(
                "7/21/2006 2:00 PM"))
                as Outlook.AppointmentItem;
            if (singleAppt != null)
            {
                Debug.WriteLine("7/21/2006 2:00 PM occurrence found.");
            }
        }
        catch (Exception ex)
        {
            Debug.WriteLine(ex.Message);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="07eb4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07eb4-120">See also</span></span>

- [<span data-ttu-id="07eb4-121">约会</span><span class="sxs-lookup"><span data-stu-id="07eb4-121">Appointments</span></span>](appointments.md)

