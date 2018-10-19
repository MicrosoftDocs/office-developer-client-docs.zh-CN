---
title: 检查经理对会议请求的响应
TOCTitle: Check a manager's response to a meeting request
ms:assetid: 7bdb2163-17e3-47b4-95e5-e051b90506c6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184618(v=office.15)
ms:contentKeyID: 55119847
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 14d78a88a0df514bca6782a84bd2c030fc140093
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406349"
---
# <a name="check-a-managers-response-to-a-meeting-request"></a>检查经理对会议请求的响应

本示例阐释如何使用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 和 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法来检查当前用户的经理对会议请求的响应状态。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

若要确定给定收件人是接受还是拒绝了请求的会议，需从 [AppointmentItem](https://msdn.microsoft.com/library/bb645283\(v=office.15\)) 对象关联的 [Recipients](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 集合中使用 [Recipient](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 对象的 [MeetingResponseStatus](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 属性。

在下面的代码示例中，CheckManagerResponseStatus 以参数形式获取 **AppointmentItem** 对象。 CheckManagerResponseStatus 对当前用户调用 **GetExchangeUser** 方法，以获取 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象。 然后，CheckManagerResponseStatus 调用 **GetExchangeUserManager** 方法，以获取与当前用户的经理关联的 **ExchangeUser** 对象。 随后，此代码示例使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [CompareEntryIDs(String, String)](https://msdn.microsoft.com/library/bb646919\(v=office.15\)) 方法，检查与 **AppointmentItem** 对象关联的 **Recipient** 对象是否与表示用户的经理的 **ExchangeUser** 对象相同。 如果 **CompareEntryIDs** 返回 **true**，表示在 **Recipients** 集合中找到了用户的经理，然后 CheckManagerResponseStatus 便会返回经理的 **MeetingResponseStatus**。 如果 **CompareEntryIDs** 返回 **false**，CheckManagerResponseStatus 返回空引用。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [Exchange 用户](exchange-users.md)

