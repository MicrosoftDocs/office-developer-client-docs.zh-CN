---
title: 获取配置文件中的存储的相关信息
TOCTitle: Get information about stores in a profile
ms:assetid: e88222d2-e1b7-4393-aac4-5ce9d24d5d5b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184648(v=office.15)
ms:contentKeyID: 55119893
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 0229294cd6655f9017780ee0d9a7a23de76f2362
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406566"
---
# <a name="get-information-about-stores-in-a-profile"></a>获取配置文件中的存储的相关信息

此代码示例展示了如何获取并枚举配置文件中的存储。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

可使用 [Stores](https://msdn.microsoft.com/library/bb622944\(v=office.15\)) 集合来枚举给定配置文件的存储。 **Stores** 集合提供用于公开每个 [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 对象的相关信息（例如，何时添加了 **Store** 对象或即将何时从当前配置文件中移除 **Store** 对象）的成员。 在下面的代码示例中，EnumerateStores 获取表示当前配置文件中的存储的 **Stores** 对象，并枚举这些存储。 EnumerateStores 检查 **Stores** 集合中的每个 **Store** 对象。 如果 [IsDataFileStore](https://msdn.microsoft.com/library/bb624116\(v=office.15\)) 属性返回 **true**，则指示该存储区是一个 .pst 或 .ost 存储区，[DisplayName](https://msdn.microsoft.com/library/bb612209\(v=office.15\)) 和 [FilePath](https://msdn.microsoft.com/library/bb646113\(v=office.15\)) 属性将写入 [侦听器](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx)集合的跟踪侦听器中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void EnumerateStores()
{
    Outlook.Stores stores = Application.Session.Stores;
    foreach (Outlook.Store store in stores)
    {
        if (store.IsDataFileStore == true)
        {
            Debug.WriteLine(String.Format("Store: "
            + store.DisplayName
            + "\n" + "File Path: "
            + store.FilePath + "\n"));
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [存储](stores.md)

