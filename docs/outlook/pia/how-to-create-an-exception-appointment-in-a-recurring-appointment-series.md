---
title: 在定期约会系列中创建例外约会
TOCTitle: Create an exception appointment in a recurring appointment series
ms:assetid: b7cd0975-4f44-453a-b878-ec55feeedc4e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184635(v=office.15)
ms:contentKeyID: 55119813
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 70e491069fd3f178371e9e8e3e6bcd8dc08e729e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721841"
---
# <a name="create-an-exception-appointment-in-a-recurring-appointment-series"></a>在定期约会系列中创建例外约会

此代码示例使用 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 对象创建约会标准定期模式的例外。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

在你删除或更改定期约会的一个约会实例后，Outlook 便会创建 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 对象。 使用 Exception 对象，可创建标准定期模式的例外。 此对象的属性包含对约会实例所做的更改。 [Exceptions](https://msdn.microsoft.com/library/bb647601\(v=office.15\)) 集合包含定期约会的所有 Exception 对象，并与约会的 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象关联。

若要获取表示定期约会原始定期模式的例外的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象，请使用 Exception 的 [AppointmentItem](https://msdn.microsoft.com/library/bb645648\(v=office.15\)) 属性。 使用返回的 AppointmentItem 的方法和属性，可设置约会例外的属性。

当使用定期约会项目时，您应当先释放以前的所有引用，再获取对定期约会项目的新引用，然后才访问或修改项目，并在完成和保存更改后立即释放这些引用。 此做法适用于定期 **AppointmentItem** 对象，以及任何 [Exception](https://msdn.microsoft.com/library/bb610440\(v=office.15\)) 或 [RecurrencePattern](https://msdn.microsoft.com/library/bb608903\(v=office.15\)) 对象。 若要在 Visual Basic 中释放引用，请将现有对象设置为“Nothing”。 在 C\# 中，显式释放相应对象占用的内存。

请注意，即使在释放了您的引用并尝试获取新引用之后，如果其他外接程序或 Outlook 中仍有对以上某个对象的活动引用，您新的引用将仍指向该对象的过期副本。因此，您在完成定期约会后立即释放您的引用是非常重要的。

在下面的代码示例中，CreateExceptionExample 更改在主题[在定期约会系列中查找特定约会](how-to-find-a-specific-appointment-in-a-recurring-appointment-series.md)中创建的定期约会的主题，再使用生成的 Exception 对象的 AppointmentItem 属性，以检索与约会例外对应的 AppointmentItem。 然后，CreateExceptionExample 更改约会例外的开始时间和结束时间。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [约会](appointments.md)

