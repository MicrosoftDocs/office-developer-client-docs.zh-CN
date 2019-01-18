---
title: 枚举全局地址列表条目
TOCTitle: Enumerate the entries in the Global Address List
ms:assetid: f3dfe312-fe91-475d-8435-1c7a0bb2b725
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184654(v=office.15)
ms:contentKeyID: 55119801
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 98256ce539172b69c2ae94d495c4aab12e3b8cc4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701422"
---
# <a name="enumerate-the-entries-in-the-global-address-list"></a><span data-ttu-id="146b4-102">枚举全局地址列表条目</span><span class="sxs-lookup"><span data-stu-id="146b4-102">Enumerate the entries in the Global Address List</span></span>

<span data-ttu-id="146b4-103">此代码示例枚举全局地址列表 (GAL) 中的前 100 个主要简单邮件传输协议 (SMTP) 地址。</span><span class="sxs-lookup"><span data-stu-id="146b4-103">This example enumerates the first 100 primary Simple Mail Transfer Protocol (SMTP) addresses in the Global Address List (GAL).</span></span>

## <a name="example"></a><span data-ttu-id="146b4-104">示例</span><span class="sxs-lookup"><span data-stu-id="146b4-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="146b4-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="146b4-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="146b4-106">在下面的代码示例中，通过以下方式获取 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象的 SMTP 地址：通过调用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 或 [GetExchangeDistributionList()](https://msdn.microsoft.com/library/bb624320\(v=office.15\)) 方法将该对象转换为 [ExchangeUser](https://msdn.microsoft.com/library/bb645260\(v=office.15\)) 或 [ExchangeDistributionList](https://msdn.microsoft.com/library/bb611805\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="146b4-106">In the following code example, the SMTP address for an [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) object is obtained by casting it to an [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) or [ExchangeDistributionList](https://msdn.microsoft.com/library/bb624320\(v=office.15\)) object in a call to the [GetExchangeUser()](https://msdn.microsoft.com/library/bb645260\(v=office.15\)) or [GetExchangeDistributionList()](https://msdn.microsoft.com/library/bb611805\(v=office.15\)) methods.</span></span> <span data-ttu-id="146b4-107">如果 **AddressEntry** 对象表示 Exchange 用户，EnumerateGAL 返回公开 **AddressEntry** 对象属性的 **ExchangeUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="146b4-107">If the **AddressEntry** object represents an Exchange user, EnumerateGAL returns an **ExchangeUser** object that exposes properties of the **AddressEntry** object.</span></span> <span data-ttu-id="146b4-108">使用 ExchangeUser 属性（如 [JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\))、[Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\))、[Alias](https://msdn.microsoft.com/library/bb610682\(v=office.15\))、[BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)) 或 [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\))）公开它们。</span><span class="sxs-lookup"><span data-stu-id="146b4-108">Use ExchangeUser properties such as [JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\)), [Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\)), [Alias](https://msdn.microsoft.com/library/bb610682\(v=office.15\)), [BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)), or [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\)) to expose them.</span></span>

<span data-ttu-id="146b4-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="146b4-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="146b4-110">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="146b4-110">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="146b4-111">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="146b4-111">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void EnumerateGAL()
{
    Outlook.AddressList gal =
        Application.Session.GetGlobalAddressList();
    if (gal != null)
    {
        for (int i = 1; 
            i <= Math.Min(100, gal.AddressEntries.Count - 1); i++)
        {
            Outlook.AddressEntry addrEntry =
                gal.AddressEntries[i];
            if (addrEntry.AddressEntryUserType ==
                Outlook.OlAddressEntryUserType.
                olExchangeUserAddressEntry
                || addrEntry.AddressEntryUserType ==
                Outlook.OlAddressEntryUserType.
                olExchangeRemoteUserAddressEntry)
            {
                Outlook.ExchangeUser exchUser =
                    addrEntry.GetExchangeUser();
                Debug.WriteLine(exchUser.Name + " "
                    + exchUser.PrimarySmtpAddress);
            }
            if (addrEntry.AddressEntryUserType ==
                Outlook.OlAddressEntryUserType.
                olExchangeDistributionListAddressEntry)
            {
                Outlook.ExchangeDistributionList exchDL =
                    addrEntry.GetExchangeDistributionList();
                Debug.WriteLine(exchDL.Name + " "
                    + exchDL.PrimarySmtpAddress);
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="146b4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="146b4-112">See also</span></span>

[<span data-ttu-id="146b4-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="146b4-113">Address book</span></span>](address-book.md)

