---
title: 检查经理对会议请求的响应
TOCTitle: Check a manager's response to a meeting request
ms:assetid: 7bdb2163-17e3-47b4-95e5-e051b90506c6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184618(v=office.15)
ms:contentKeyID: 55119847
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ba54ba740182eaffc92a0e1932a6fbed1d3804c8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359708"
---
# <a name="check-a-managers-response-to-a-meeting-request"></a><span data-ttu-id="a50e1-102">检查经理对会议请求的响应</span><span class="sxs-lookup"><span data-stu-id="a50e1-102">Check a manager's response to a meeting request</span></span>

<span data-ttu-id="a50e1-103">本示例阐释如何使用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 和 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法来检查当前用户的经理对会议请求的响应状态。</span><span class="sxs-lookup"><span data-stu-id="a50e1-103">This example illustrates how to use the [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) and [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) methods to check the status of the response of the current user's manager to a meeting request.</span></span>

## <a name="example"></a><span data-ttu-id="a50e1-104">示例</span><span class="sxs-lookup"><span data-stu-id="a50e1-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="a50e1-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="a50e1-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="a50e1-106">若要确定给定收件人是接受还是拒绝了请求的会议，需从 [AppointmentItem](https://msdn.microsoft.com/library/bb645283\(v=office.15\)) 对象关联的 [Recipients](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 集合中使用 [Recipient](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 对象的 [MeetingResponseStatus](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a50e1-106">To determine whether a given recipient has accepted or declined a requested meeting, use the [MeetingResponseStatus](https://msdn.microsoft.com/library/bb645283\(v=office.15\)) property of the [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) object from the [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) collection associated with the [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object.</span></span>

<span data-ttu-id="a50e1-107">在下面的代码示例中，CheckManagerResponseStatus 以参数形式获取 **AppointmentItem** 对象。</span><span class="sxs-lookup"><span data-stu-id="a50e1-107">In the following code example, CheckManagerResponseStatus takes in an **AppointmentItem** object as a parameter.</span></span> <span data-ttu-id="a50e1-108">CheckManagerResponseStatus 对当前用户调用 **GetExchangeUser** 方法，以获取 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="a50e1-108">CheckManagerResponseStatus gets the [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) object by calling the **GetExchangeUser** method on the current user.</span></span> <span data-ttu-id="a50e1-109">然后，CheckManagerResponseStatus 调用 **GetExchangeUserManager** 方法，以获取与当前用户的经理关联的 **ExchangeUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="a50e1-109">CheckManagerResponseStatus then gets the **ExchangeUser** object that is associated with the current user’s manager by calling the **GetExchangeUserManager** method.</span></span> <span data-ttu-id="a50e1-110">随后，此代码示例使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [CompareEntryIDs(String, String)](https://msdn.microsoft.com/library/bb646919\(v=office.15\)) 方法，检查与 **AppointmentItem** 对象关联的 **Recipient** 对象是否与表示用户的经理的 **ExchangeUser** 对象相同。</span><span class="sxs-lookup"><span data-stu-id="a50e1-110">By using the [CompareEntryIDs(String, String)](https://msdn.microsoft.com/library/bb646919\(v=office.15\)) method of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object, the example then checks whether the **Recipient** object associated with the **AppointmentItem** object is the same as the **ExchangeUser** object that represents the user’s manager.</span></span> <span data-ttu-id="a50e1-111">如果 **CompareEntryIDs** 返回 **true**，表示在 **Recipients** 集合中找到了用户的经理，然后 CheckManagerResponseStatus 便会返回经理的 **MeetingResponseStatus**。</span><span class="sxs-lookup"><span data-stu-id="a50e1-111">If **CompareEntryIDs** returns **true**, the user’s manager is found in the **Recipients** collection, and CheckManagerResponseStatus returns the manager’s **MeetingResponseStatus**.</span></span> <span data-ttu-id="a50e1-112">如果 **CompareEntryIDs** 返回 **false**，CheckManagerResponseStatus 返回空引用。</span><span class="sxs-lookup"><span data-stu-id="a50e1-112">If **CompareEntryIDs** returns **false**, CheckManagerResponseStatus returns a null reference.</span></span>

<span data-ttu-id="a50e1-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="a50e1-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="a50e1-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="a50e1-114">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="a50e1-115">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="a50e1-115">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private Object CheckManagerResponseStatus(Outlook.AppointmentItem appt)
{
    try
    {
        if (appt == null)
        {
            throw new ArgumentNullException();
        }
        Outlook.AddressEntry user =
            Application.Session.CurrentUser.AddressEntry;
        Outlook.ExchangeUser userEx = user.GetExchangeUser();
        if (userEx == null)
        {
            return null;
        }
        Outlook.ExchangeUser manager =
            userEx.GetExchangeUserManager();
        if (manager == null)
        {
            return null;
        }
        foreach (Outlook.Recipient recip in appt.Recipients)
        {
            if (Application.Session.CompareEntryIDs(
                recip.AddressEntry.ID, manager.ID))
            {
                return recip.MeetingResponseStatus;
            }
        }
        return null;
    }
    catch (Exception ex)
    {
        Debug.WriteLine(ex.Message);
        return null;
    }
}
```

## <a name="see-also"></a><span data-ttu-id="a50e1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a50e1-116">See also</span></span>

- [<span data-ttu-id="a50e1-117">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="a50e1-117">Exchange users</span></span>](exchange-users.md)

