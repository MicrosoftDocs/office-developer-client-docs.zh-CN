---
title: 获取当前用户的经理的直接下属的相关信息
TOCTitle: Get information about direct reports of the current user's manager
ms:assetid: 768bf573-1b10-4776-8947-a7f8dc3ebde0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184617(v=office.15)
ms:contentKeyID: 55119842
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 6237b3455eea449460133fb52a79ef87bcaebc1f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406699"
---
# <a name="get-information-about-direct-reports-of-the-current-users-manager"></a><span data-ttu-id="3dbc8-102">获取当前用户的经理的直接下属的相关信息</span><span class="sxs-lookup"><span data-stu-id="3dbc8-102">Get information about direct reports of the current user's manager</span></span>

<span data-ttu-id="3dbc8-103">该示例获取当前用户的经理的直接下属（如果有），然后显示每名经理的直接下属的信息。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-103">This example gets the direct reports of the current user’s manager, if any, and then displays information about each of the manager’s direct reports.</span></span>

## <a name="example"></a><span data-ttu-id="3dbc8-104">示例</span><span class="sxs-lookup"><span data-stu-id="3dbc8-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="3dbc8-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="3dbc8-106">在下面的代码示例中，GetManagerDirectReports 过程调用 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法，以获取用户的经理（由 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象表示）。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-106">In the following example, the   procedure calls the GetExchangeUserManager() method to get the user's manager, represented by an ExchangeUser object.</span></span> <span data-ttu-id="3dbc8-107">如果当前用户有经理，此代码示例便会调用 [GetDirectReports()](https://msdn.microsoft.com/library/bb647204\(v=office.15\))，以返回 [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\)) 集合（表示用户的经理的所有直接下属的地址条目）。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-107">If the current user has a manager, [GetDirectReports()](https://msdn.microsoft.com/library/bb647204\(v=office.15\)) is called to return an [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\)) collection that represents the address entries for all the direct reports of user's manager.</span></span> <span data-ttu-id="3dbc8-108">如果经理没有直接下属，**GetDirectReports** 返回计数为零的 **AddressEntries** 集合。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-108">If the manager has no direct reports, **GetDirectReports** returns an **AddressEntries** collection that has a count of zero.</span></span> <span data-ttu-id="3dbc8-109">获取经理的直接下属后，GetManagerDirectReports 将每个经理的直接下属的相关信息写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-109">Once the manager's direct reports are obtained,   writes information about each of the manager's direct reports to the trace listeners of the Listeners collection.</span></span>


> [!NOTE]
> <span data-ttu-id="3dbc8-110">已登录用户必须处于联机状态，此方法才能返回 **AddressEntries** 集合；否则，**GetDirectReports** 返回空引用。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-110">The logged-on user must be online for this method to return an **AddressEntries** collection; otherwise, **GetDirectReports** returns a null reference.</span></span> <span data-ttu-id="3dbc8-111">对于生产代码，必须针对多种 Exchange 方案，使用 [\_NameSpace.ExchangeConnectionMode](https://msdn.microsoft.com/library/bb647638(v=office.15)) 属性或 [\_Account.ExchangeConnectionMode](https://msdn.microsoft.com/library/ff185249(v=office.15)) 属性对脱机用户进行测试。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-111">For production code, you must test for the user being offline by using the _NameSpace.ExchangeConnectionMode property, or the _Account.ExchangeConnectionMode property for multiple Exchange scenarios.</span></span>

<span data-ttu-id="3dbc8-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="3dbc8-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-113">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="3dbc8-114">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-114">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetManagerDirectReports()
{
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser manager =
            currentUser.GetExchangeUser().GetExchangeUserManager();
        if (manager != null)
        {
            Outlook.AddressEntries addrEntries =
                manager.GetDirectReports();
            if (addrEntries != null)
            {
                foreach (Outlook.AddressEntry addrEntry
                    in addrEntries)
                {
                    Outlook.ExchangeUser exchUser =
                        addrEntry.GetExchangeUser();
                    StringBuilder sb = new StringBuilder();
                    sb.AppendLine("Name: "
                        + exchUser.Name);
                    sb.AppendLine("Title: "
                        + exchUser.JobTitle);
                    sb.AppendLine("Department: "
                        + exchUser.Department);
                    sb.AppendLine("Location: "
                        + exchUser.OfficeLocation);
                    Debug.WriteLine(sb.ToString());
                }
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="3dbc8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dbc8-115">See also</span></span>

- [<span data-ttu-id="3dbc8-116">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="3dbc8-116">Exchange Users</span></span>](exchange-users.md)

