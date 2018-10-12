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
# <a name="get-information-about-all-distribution-lists-of-which-the-current-user-is-a-member"></a>获取当前用户所属全部通讯组列表的相关信息

此代码示例使用 [GetMemberOfList()](https://msdn.microsoft.com/library/bb623397\(v=office.15\)) 方法，获取当前用户所属全部通讯组列表的相关信息。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

在下面的代码示例中，GetCurrentUserMembership 调用 **GetMemberOfList** 方法，以获取 Exchange 用户所属全部通讯组列表的 [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\)) 集合。 如果用户不属于任何通讯组列表，**GetMemberOfList** 返回计数为零的 **AddressEntries** 集合。 用户必须处于联机状态，这样 **GetMemberOfList** 才能返回 **AddressEntries** 集合；否则，**GetMemberOfList** 返回空引用。 为了测试用户是否联机，GetCurrentUserMembership 使用返回当前 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象的 [GetExchangeUser()](https://msdn.microsoft.com/library/bb645260\(v=office.15\)) 方法。 获取地址条目后，此代码示例将用户所属全部通讯组列表的相关信息写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [Exchange 用户](exchange-users.md)

