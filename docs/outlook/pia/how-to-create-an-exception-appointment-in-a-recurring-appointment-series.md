---
title: 在定期约会系列中创建例外约会
TOCTitle: Create an exception appointment in a recurring appointment series
ms:assetid: b7cd0975-4f44-453a-b878-ec55feeedc4e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184635(v=office.15)
ms:contentKeyID: 55119813
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 1344188ad8947245ec0a6d54efff603b9e7755e7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405978"
---
# <a name="create-an-exception-appointment-in-a-recurring-appointment-series"></a><span data-ttu-id="d02d8-102">在定期约会系列中创建例外约会</span><span class="sxs-lookup"><span data-stu-id="d02d8-102">Create an exception appointment in a recurring appointment series</span></span>

<span data-ttu-id="d02d8-103">此代码示例使用 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 对象创建约会标准定期模式的例外。</span><span class="sxs-lookup"><span data-stu-id="d02d8-103">This example uses an [T:Microsoft.Office.Interop.Outlook.Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) object to create an exception to a standard recurrence pattern for an appointment.</span></span>

## <a name="example"></a><span data-ttu-id="d02d8-104">示例</span><span class="sxs-lookup"><span data-stu-id="d02d8-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="d02d8-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="d02d8-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="d02d8-106">在你删除或更改定期约会的一个约会实例后，Outlook 便会创建 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="d02d8-106">Once you delete or change one appointment instance of a recurring appointment, Outlook creates an [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) object.</span></span> <span data-ttu-id="d02d8-107">使用 Exception 对象，可创建标准定期模式的例外。</span><span class="sxs-lookup"><span data-stu-id="d02d8-107">Uses an Exception object to create an exception to a standard recurrence pattern for an appointment.</span></span> <span data-ttu-id="d02d8-108">此对象的属性包含对约会实例所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d02d8-108">The object’s properties contain the changes that were made to the appointment instance.</span></span> <span data-ttu-id="d02d8-109">[Exceptions](https://msdn.microsoft.com/library/bb647601\(v=office.15\)) 集合包含定期约会的所有 Exception 对象，并与约会的 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象关联。</span><span class="sxs-lookup"><span data-stu-id="d02d8-109">The [Exceptions](https://msdn.microsoft.com/library/bb647601\(v=office.15\)) collection contains all of the Exception objects for a recurring appointment, and is associated with the appointment’s [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object.</span></span>

<span data-ttu-id="d02d8-110">若要获取表示定期约会原始定期模式的例外的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象，请使用 Exception 的 [AppointmentItem](https://msdn.microsoft.com/library/bb645648\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d02d8-110">To get the T:Microsoft.Office.Interop.Outlook.AppointmentItem object that represents the exception to the original recurrence pattern of the recurring appointment, use the P:Microsoft.Office.Interop.Outlook.Exception.AppointmentItem property of the Exception. By using the methods and properties of the returned AppointmentItem, you can set the properties of the appointment exception.</span></span> <span data-ttu-id="d02d8-111">使用返回的 AppointmentItem 的方法和属性，可设置约会例外的属性。</span><span class="sxs-lookup"><span data-stu-id="d02d8-111">By using the methods and properties of the returned AppointmentItem, you can set the properties of the appointment exception.</span></span>

<span data-ttu-id="d02d8-112">当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。</span><span class="sxs-lookup"><span data-stu-id="d02d8-112">When you work with recurring appointment items, you should release any prior references, obtain new references to the recurring appointment item before you access or modify the item, and release these references as soon as you are finished and have saved the changes.</span></span> <span data-ttu-id="d02d8-113">此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="d02d8-113">This practice applies to the recurring **AppointmentItem** object, and any [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) or [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) object.</span></span> <span data-ttu-id="d02d8-114">若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。</span><span class="sxs-lookup"><span data-stu-id="d02d8-114">To release a reference in Visual Basic, set that existing object to Nothing.</span></span> <span data-ttu-id="d02d8-115">在 C\# 中，显式释放相应对象占用的内存。</span><span class="sxs-lookup"><span data-stu-id="d02d8-115">In C#, explicitly release the memory for that object.</span></span>

<span data-ttu-id="d02d8-p104">请注意，即使在释放了您的引用并尝试获取新引用之后，如果其他外接程序或 Outlook 中仍有对以上某个对象的活动引用，您新的引用将仍指向该对象的过期副本。因此，您在完成定期约会后立即释放您的引用是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="d02d8-p104">Note that even after you release your reference and attempt to obtain a new reference, if there is still an active reference, held by another add-in or Outlook, to one of the above objects, your new reference will still point to an out-of-date copy of the object. Therefore, it is important that you release your references as soon as you are finished with the recurring appointment.</span></span>

<span data-ttu-id="d02d8-118">在下面的代码示例中，CreateExceptionExample 更改在主题[在定期约会系列中查找特定约会](how-to-find-a-specific-appointment-in-a-recurring-appointment-series.md)中创建的定期约会的主题，再使用生成的 Exception 对象的 AppointmentItem 属性，以检索与约会例外对应的 AppointmentItem。</span><span class="sxs-lookup"><span data-stu-id="d02d8-118">In the following code example, CreateExceptionExample changes the subject of the recurring appointment that was created in the topic How to: Find a Specific Appointment in a Recurring Appointment Series, and then uses the AppointmentItem property of the resulting Exception object to retrieve the AppointmentItem that corresponds to the appointment exception. CreateExceptionExample then changes the start and end times of the appointment exception.</span></span> <span data-ttu-id="d02d8-119">然后，CreateExceptionExample 更改约会例外的开始时间和结束时间。</span><span class="sxs-lookup"><span data-stu-id="d02d8-119">CreateExceptionExample then changes the start and end times of the appointment exception.</span></span>

<span data-ttu-id="d02d8-120">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d02d8-120">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="d02d8-121">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d02d8-121">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="d02d8-122">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d02d8-122">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void CreateExceptionExample()
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
            Outlook.AppointmentItem myInstance =
                pattern.GetOccurrence(DateTime.Parse(
                "7/21/2006 2:00 PM"))
                as Outlook.AppointmentItem;
            if (myInstance != null)
            {
                myInstance.Subject = "My Exception";
                myInstance.Save();
                Outlook.RecurrencePattern newPattern =
                    appt.GetRecurrencePattern();
                Outlook.Exception myException =
                    newPattern.Exceptions[1];
                if (myException != null)
                {
                    Outlook.AppointmentItem myNewInstance =
                        myException.AppointmentItem;
                    myNewInstance.Start =
                        DateTime.Parse("7/21/2006 1:00 PM");
                    myNewInstance.End =
                        DateTime.Parse("7/21/2006 2:00 PM");
                    myNewInstance.Save();
                }
            }
        }
        catch (Exception ex)
        {
            Debug.WriteLine(ex.Message);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d02d8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d02d8-123">See also</span></span>

- [<span data-ttu-id="d02d8-124">约会</span><span class="sxs-lookup"><span data-stu-id="d02d8-124">Appointments</span></span>](appointments.md)

