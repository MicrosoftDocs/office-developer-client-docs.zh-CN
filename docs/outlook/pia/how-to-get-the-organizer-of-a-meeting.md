---
title: 获取会议组织者
TOCTitle: Get the organizer of a meeting
ms:assetid: 6a33db84-573b-4d1b-a91a-903f30630ec9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184615(v=office.15)
ms:contentKeyID: 55119872
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e19b293b581984e9dbb1fe27c9564cb78a73caa1
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542533"
---
# <a name="get-the-organizer-of-a-meeting"></a>获取会议组织者

此代码示例展示了如何以编程方式返回会议组织者。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

在下面的代码示例中，GetMeetingOrganizer 需要使用表示会议的 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 类型参数，并使用 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象和 [GetProperty(String)](https://msdn.microsoft.com/library/bb645726\(v=office.15\)) 方法来获取 **AppointmentItem** 对象的 [EntryID](https://msdn.microsoft.com/library/bb645980\(v=office.15\))。 获取 **EntryID** 后，此代码示例使用 [GetAddressEntryFromID(String)](https://msdn.microsoft.com/library/ff185034\(v=office.15\)) 方法，返回表示会议组织者的 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private Outlook.AddressEntry GetMeetingOrganizer(Outlook.AppointmentItem appt)
{
    if (appt == null)
    {
        throw new ArgumentNullException();
    }
    string PR_SENT_REPRESENTING_ENTRYID =
        @"http://schemas.microsoft.com/mapi/proptag/0x00410102";
    string organizerEntryID =
        appt.PropertyAccessor.BinaryToString(
            appt.PropertyAccessor.GetProperty(
            PR_SENT_REPRESENTING_ENTRYID));
    Outlook.AddressEntry organizer =
        Application.Session.
        GetAddressEntryFromID(organizerEntryID);
    if (organizer != null)
    {
        return organizer; 
    }
    else
    {
        return null;
    }
}
```

## <a name="see-also"></a>另请参阅

- [会议请求](meeting-requests.md)

