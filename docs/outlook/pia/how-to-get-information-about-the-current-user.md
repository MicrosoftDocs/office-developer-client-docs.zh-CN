---
title: 获取当前用户的相关信息
TOCTitle: Get information about the current user
ms:assetid: 3802523a-3ccf-4cca-a348-abe2645a0d9c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184601(v=office.15)
ms:contentKeyID: 55119840
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3b169eb1baadee92c08bcb68726ae4d18a9d79d6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723066"
---
# <a name="get-information-about-the-current-user"></a>获取当前用户的相关信息

此代码示例展示了如何获取当前用户的相关信息（如姓名、职务和电话号码）。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

若要从 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象获取 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象，请对 **AddressEntry** 对象调用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 方法。 在下面的过程中，GetCurrentUserInfo 使用 [CurrentUser](https://msdn.microsoft.com/library/bb622574\(v=office.15\)) 属性，以获取 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象的 [AddressEntry](https://msdn.microsoft.com/library/bb644359\(v=office.15\)) 属性。 如果 **AddressEntry** 对象表示 Exchange 邮箱用户，GetCurrentUserInfo 调用 **GetExchangeUser** 方法，并返回 **ExchangeUser** 对象。 [Name](https://msdn.microsoft.com/library/bb622941\(v=office.15\))、[PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\))、[JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\))、[Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\))、[OfficeLocation](https://msdn.microsoft.com/library/bb611429\(v=office.15\))、[BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)) 和 [MobileTelephoneNumber](https://msdn.microsoft.com/library/bb609292\(v=office.15\)) 属性被写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [Exchange 用户](exchange-users.md)

