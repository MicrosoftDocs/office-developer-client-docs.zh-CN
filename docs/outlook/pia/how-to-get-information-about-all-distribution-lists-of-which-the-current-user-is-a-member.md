---
title: 获取当前用户所属全部通讯组列表的相关信息
TOCTitle: Get information about all distribution lists of which the current user is a member
ms:assetid: c5be6aa8-8d85-463e-a377-2a4d57e2106b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184638(v=office.15)
ms:contentKeyID: 55119836
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: f98d7a338866624e67d745e66a66e864fb9bbf99
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406762"
---
# <a name="get-information-about-all-distribution-lists-of-which-the-current-user-is-a-member"></a><span data-ttu-id="9f9f1-102">获取当前用户所属全部通讯组列表的相关信息</span><span class="sxs-lookup"><span data-stu-id="9f9f1-102">Get information about all distribution lists of which the current user is a member</span></span>

<span data-ttu-id="9f9f1-103">此代码示例使用 [GetMemberOfList()](https://msdn.microsoft.com/library/bb623397\(v=office.15\)) 方法，获取当前用户所属全部通讯组列表的相关信息。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-103">This example uses the [GetMemberOfList()](https://msdn.microsoft.com/library/bb623397\(v=office.15\)) method to get information about all distribution lists of which the current user is a member.</span></span>

## <a name="example"></a><span data-ttu-id="9f9f1-104">示例</span><span class="sxs-lookup"><span data-stu-id="9f9f1-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="9f9f1-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="9f9f1-106">在下面的代码示例中，GetCurrentUserMembership 调用 **GetMemberOfList** 方法，以获取 Exchange 用户所属全部通讯组列表的 [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\)) 集合。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-106">In the following example,   calls the GetMemberOfList method to get an AddressEntries collection for all distribution lists of which the Exchange user is a member.</span></span> <span data-ttu-id="9f9f1-107">如果用户不属于任何通讯组列表，**GetMemberOfList** 返回计数为零的 **AddressEntries** 集合。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-107">If the user is not a member of any distribution lists, **GetMemberOfList** returns an **AddressEntries** collection that has a count of zero.</span></span> <span data-ttu-id="9f9f1-108">用户必须处于联机状态，这样 **GetMemberOfList** 才能返回 **AddressEntries** 集合；否则，**GetMemberOfList** 返回空引用。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-108">The user must be online for **GetMemberOfList** to return an **AddressEntries** collection; otherwise, **GetMemberOfList** returns a null reference.</span></span> <span data-ttu-id="9f9f1-109">为了测试用户是否联机，GetCurrentUserMembership 使用返回当前 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象的 [GetExchangeUser()](https://msdn.microsoft.com/library/bb645260\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-109"> uses the GetExchangeUser() method, which returns the current ExchangeUser object, to test whether the user is online.</span></span> <span data-ttu-id="9f9f1-110">获取地址条目后，此代码示例将用户所属全部通讯组列表的相关信息写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-110">Once the address entries are obtained, the example writes information about each of the user's distribution lists to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="9f9f1-111">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="9f9f1-112">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-112">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="9f9f1-113">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="9f9f1-113">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetCurrentUserMembership()
{
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser exchUser =
            currentUser.GetExchangeUser();
        if (exchUser != null)
        {
            Outlook.AddressEntries addrEntries =
                exchUser.GetMemberOfList();
            if (addrEntries != null)
            {
                foreach (Outlook.AddressEntry addrEntry
                    in addrEntries)
                {
                    Debug.WriteLine(addrEntry.Name);
                }
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9f9f1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f9f1-114">See also</span></span>

- [<span data-ttu-id="9f9f1-115">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="9f9f1-115">Exchange Users</span></span>](exchange-users.md)
