---
title: 获取当前用户的经理信息
TOCTitle: Get information about the current user's manager
ms:assetid: 3a77fa51-e2e3-4544-849f-4267b1762270
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184603(v=office.15)
ms:contentKeyID: 55119846
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fd5b49a2b1f1e494a494cf1bea4e105fa261e053
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349439"
---
# <a name="get-information-about-the-current-users-manager"></a><span data-ttu-id="a2709-102">获取当前用户的经理信息</span><span class="sxs-lookup"><span data-stu-id="a2709-102">Get information about the current user's manager</span></span>

<span data-ttu-id="a2709-103">此代码示例展示了如何获取当前用户的经理信息（如姓名、职务和电话号码）。</span><span class="sxs-lookup"><span data-stu-id="a2709-103">This example shows how to get information (such as name, job title, and phone numbers) about the current user’s manager.</span></span>

## <a name="example"></a><span data-ttu-id="a2709-104">示例</span><span class="sxs-lookup"><span data-stu-id="a2709-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="a2709-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="a2709-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="a2709-106">在下面的过程中，GetManagerInfo 调用 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法，以获取表示 **ExchangeUser** 在组织层次结构中的经理的 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="a2709-106">In the following procedure, GetManagerInfo calls the [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) method to obtain an [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) object that represents the manager of an **ExchangeUser** in the organizational hierarchy.</span></span> <span data-ttu-id="a2709-107">此过程测试已登录用户是否处于联机状态，以确保 **GetExchangeUserManager** 可以返回 **ExchangeUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="a2709-107">The procedure tests whether the logged-on user is online to ensure that **GetExchangeUserManager** can return an **ExchangeUser** object.</span></span> <span data-ttu-id="a2709-108">如果用户处于脱机状态，**GetExchangeUserManager** 返回空引用。</span><span class="sxs-lookup"><span data-stu-id="a2709-108">If the user is not online, **GetExchangeUserManager** will return a null reference.</span></span> <span data-ttu-id="a2709-109">然后，GetManagerInfo 将管理员信息写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="a2709-109">GetManagerInfo then writes manager information to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="a2709-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="a2709-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="a2709-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="a2709-111">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="a2709-112">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="a2709-112">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetManagerInfo()
{
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser manager =
            currentUser.GetExchangeUser().GetExchangeUserManager();
        if (manager != null)
        {
            StringBuilder sb = new StringBuilder();
            sb.AppendLine("Name: "
                + manager.Name);
            sb.AppendLine("STMP address: "
                + manager.PrimarySmtpAddress);
            sb.AppendLine("Title: "
                + manager.JobTitle);
            sb.AppendLine("Department: "
                + manager.Department);
            sb.AppendLine("Location: "
                + manager.OfficeLocation);
            sb.AppendLine("Business phone: "
                + manager.BusinessTelephoneNumber);
            sb.AppendLine("Mobile phone: "
                + manager.MobileTelephoneNumber);
            Debug.WriteLine(sb.ToString());
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="a2709-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2709-113">See also</span></span>

- [<span data-ttu-id="a2709-114">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="a2709-114">Exchange users</span></span>](exchange-users.md)

