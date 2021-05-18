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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320361"
---
# <a name="enumerate-the-entries-in-the-global-address-list"></a>枚举全局地址列表条目

此代码示例枚举全局地址列表 (GAL) 中的前 100 个主要简单邮件传输协议 (SMTP) 地址。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

在下面的代码示例中，通过以下方式获取 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象的 SMTP 地址：通过调用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 或 [GetExchangeDistributionList()](https://msdn.microsoft.com/library/bb624320\(v=office.15\)) 方法将该对象转换为 [ExchangeUser](https://msdn.microsoft.com/library/bb645260\(v=office.15\)) 或 [ExchangeDistributionList](https://msdn.microsoft.com/library/bb611805\(v=office.15\)) 对象。 如果 **AddressEntry** 对象表示 Exchange 用户，EnumerateGAL 返回公开 **AddressEntry** 对象属性的 **ExchangeUser** 对象。 使用 ExchangeUser 属性（如 [JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\))、[Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\))、[Alias](https://msdn.microsoft.com/library/bb610682\(v=office.15\))、[BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)) 或 [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\))）公开它们。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

[通讯簿](address-book.md)

