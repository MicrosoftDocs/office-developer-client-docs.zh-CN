---
title: 获取当前用户的相关信息
TOCTitle: Get information about the current user
ms:assetid: 3802523a-3ccf-4cca-a348-abe2645a0d9c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184601(v=office.15)
ms:contentKeyID: 55119840
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 7ac10c01d205f4f4590183bcef8006e8f1344cbd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406972"
---
# <a name="get-information-about-the-current-user"></a><span data-ttu-id="9fdc2-102">获取当前用户的相关信息</span><span class="sxs-lookup"><span data-stu-id="9fdc2-102">Get information about the current user</span></span>

<span data-ttu-id="9fdc2-103">此代码示例展示了如何获取当前用户的相关信息（如姓名、职务和电话号码）。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-103">This example shows how to get the current user’s information, such as name, job title, and telephone number.</span></span>

## <a name="example"></a><span data-ttu-id="9fdc2-104">示例</span><span class="sxs-lookup"><span data-stu-id="9fdc2-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="9fdc2-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="9fdc2-106">若要从 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象获取 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象，请对 **AddressEntry** 对象调用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-106">To obtain an [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) object from an [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) object, call the [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) method on the **AddressEntry** object.</span></span> <span data-ttu-id="9fdc2-107">在下面的过程中，GetCurrentUserInfo 使用 [CurrentUser](https://msdn.microsoft.com/library/bb622574\(v=office.15\)) 属性，以获取 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象的 [AddressEntry](https://msdn.microsoft.com/library/bb644359\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-107">In the following procedure,   gets the AddressEntry property for the Recipient object by using the CurrentUser property.</span></span> <span data-ttu-id="9fdc2-108">如果 **AddressEntry** 对象表示 Exchange 邮箱用户，GetCurrentUserInfo 调用 **GetExchangeUser** 方法，并返回 **ExchangeUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-108">If the AddressEntry object represents an Exchange mailbox user,   calls the GetExchangeUser method and an ExchangeUser object is returned.</span></span> <span data-ttu-id="9fdc2-109">[Name](https://msdn.microsoft.com/library/bb622941\(v=office.15\))、[PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\))、[JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\))、[Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\))、[OfficeLocation](https://msdn.microsoft.com/library/bb611429\(v=office.15\))、[BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)) 和 [MobileTelephoneNumber](https://msdn.microsoft.com/library/bb609292\(v=office.15\)) 属性被写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-109">The [Name](https://msdn.microsoft.com/library/bb622941\(v=office.15\)) , [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\)) , [JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\)) , [Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\)) , [OfficeLocation](https://msdn.microsoft.com/library/bb611429\(v=office.15\)) , [BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)) , and [MobileTelephoneNumber](https://msdn.microsoft.com/library/bb609292\(v=office.15\)) properties are written to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="9fdc2-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="9fdc2-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-111">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="9fdc2-112">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="9fdc2-112">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetCurrentUserInfo()
{
    Outlook.AddressEntry addrEntry =
        Application.Session.CurrentUser.AddressEntry;
    if (addrEntry.Type == "EX")
    {
        Outlook.ExchangeUser currentUser =
            Application.Session.CurrentUser.
            AddressEntry.GetExchangeUser();
        if (currentUser != null)
        {
            StringBuilder sb = new StringBuilder();
            sb.AppendLine("Name: "
                + currentUser.Name);
            sb.AppendLine("STMP address: "
                + currentUser.PrimarySmtpAddress);
            sb.AppendLine("Title: "
                + currentUser.JobTitle);
            sb.AppendLine("Department: "
                + currentUser.Department);
            sb.AppendLine("Location: "
                + currentUser.OfficeLocation);
            sb.AppendLine("Business phone: "
                + currentUser.BusinessTelephoneNumber);
            sb.AppendLine("Mobile phone: "
                + currentUser.MobileTelephoneNumber);
            Debug.WriteLine(sb.ToString());
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9fdc2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fdc2-113">See also</span></span>

- [<span data-ttu-id="9fdc2-114">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="9fdc2-114">Exchange Users</span></span>](exchange-users.md)

