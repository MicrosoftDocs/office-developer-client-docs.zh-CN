---
title: 获取会议组织者
TOCTitle: Get the organizer of a meeting
ms:assetid: 6a33db84-573b-4d1b-a91a-903f30630ec9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184615(v=office.15)
ms:contentKeyID: 55119872
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b34b79ac05530ec30e611c50bce8e81ce0470f02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320109"
---
# <a name="get-the-organizer-of-a-meeting"></a><span data-ttu-id="d6836-102">获取会议组织者</span><span class="sxs-lookup"><span data-stu-id="d6836-102">Get the organizer of a meeting</span></span>

<span data-ttu-id="d6836-103">此代码示例展示了如何以编程方式返回会议组织者。</span><span class="sxs-lookup"><span data-stu-id="d6836-103">This example shows how to programmatically return the organizer of a meeting.</span></span>

## <a name="example"></a><span data-ttu-id="d6836-104">示例</span><span class="sxs-lookup"><span data-stu-id="d6836-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="d6836-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="d6836-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="d6836-106">在下面的代码示例中，GetMeetingOrganizer 需要使用表示会议的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 类型参数，并使用 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象和 [GetProperty(String)](https://msdn.microsoft.com/library/bb645726\(v=office.15\)) 方法来获取 **AppointmentItem** 对象的 [EntryID](https://msdn.microsoft.com/library/bb645980\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="d6836-106">In the following code example, GetMeetingOrganizer takes a parameter of type [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) that represents a meeting, and uses the [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) object and the [GetProperty(String)](https://msdn.microsoft.com/library/bb645726\(v=office.15\)) method to obtain the [EntryID](https://msdn.microsoft.com/library/bb645980\(v=office.15\)) for the **AppointmentItem** object.</span></span> <span data-ttu-id="d6836-107">获取 **EntryID** 后，此代码示例使用 [GetAddressEntryFromID(String)](https://msdn.microsoft.com/library/ff185034\(v=office.15\)) 方法，返回表示会议组织者的 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="d6836-107">Once the **EntryID** is obtained, the example uses the [GetAddressEntryFromID(String)](https://msdn.microsoft.com/library/ff185034\(v=office.15\)) method to return the [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) object that represents the organizer of the meeting.</span></span>

<span data-ttu-id="d6836-108">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d6836-108">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="d6836-109">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d6836-109">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="d6836-110">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d6836-110">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private Outlook.AddressEntry GetMeetingOrganizer(Outlook.AppointmentItem appt)
{
    if (appt == null)
    {
        throw new ArgumentNullException();
    }
    string PR_SENT_REPRESENTING_ENTRYID =
        @"https://schemas.microsoft.com/mapi/proptag/0x00410102";
    string organizerEntryID =
        appt.PropertyAccessor.BinaryToString(
            appt.PropertyAccessor.GetProperty(
            PR_SENT_REPRESENTING_ENTRYID));
    Outlook.AddressEntry organizer =
        Application.Session.
        GetAddressEntryFromID(organizerEntryID);
    if (organizer != null)
    {
        return organizer; 
    }
    else
    {
        return null;
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d6836-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6836-111">See also</span></span>

- [<span data-ttu-id="d6836-112">会议请求</span><span class="sxs-lookup"><span data-stu-id="d6836-112">Meeting requests</span></span>](meeting-requests.md)

