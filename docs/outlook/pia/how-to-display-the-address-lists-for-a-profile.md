---
title: 显示配置文件的地址列表
TOCTitle: Display the address lists for a profile
ms:assetid: ced8230b-110b-4ccb-a699-588798144154
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184643(v=office.15)
ms:contentKeyID: 55119802
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b69ed930241dc058b22b75c6ccc9121f8856d28f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703718"
---
# <a name="display-the-address-lists-for-a-profile"></a>显示配置文件的地址列表

此代码示例展示了如何显示当前配置文件的地址列表。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

当前配置文件包含 [AddressLists](https://msdn.microsoft.com/library/bb611894\(v=office.15\)) 集合所表示的地址列表。若要获取 AddressLists 集合的实例，必须使用 [NameSpace](https://msdn.microsoft.com/library/bb624048\(v=office.15\)) 对象的 [AddressLists](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 属性。

在下面的代码示例中，EnumerateAddressLists 先使用 foreach 语句枚举 AddressLists 集合中的各个 [AddressList](https://msdn.microsoft.com/library/bb623538\(v=office.15\)) 对象。 然后，此代码示例创建包含 [Name](https://msdn.microsoft.com/library/bb609849\(v=office.15\))、[ResolutionOrder](https://msdn.microsoft.com/library/bb646853\(v=office.15\))、[IsReadOnly](https://msdn.microsoft.com/library/bb612676\(v=office.15\)) 和 [IsInitialAddressList](https://msdn.microsoft.com/library/bb646646\(v=office.15\)) 属性的值的字符串。 最后，EnumerateAddressLists 将字符串写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。 这会显示当前配置文件的每个地址列表。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void EnumerateAddressLists()
{
    Outlook.AddressLists addrLists =
         Application.Session.AddressLists;
    foreach (Outlook.AddressList addrList in addrLists)
    {
        StringBuilder sb = new StringBuilder();
        sb.AppendLine("Display Name: " + addrList.Name);
        sb.AppendLine("Resolution Order: "
            + addrList.ResolutionOrder.ToString());
        sb.AppendLine("Read-only : "
            + addrList.IsReadOnly.ToString());
        sb.AppendLine("Initial Address List: "
            + addrList.IsInitialAddressList.ToString());
        sb.AppendLine("");
        Debug.WriteLine(sb.ToString());
    }
}
```

## <a name="see-also"></a>另请参阅

- [通讯簿](address-book.md)

