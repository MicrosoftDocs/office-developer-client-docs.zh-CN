---
title: 获取配置文件中的存储的相关信息
TOCTitle: Get information about stores in a profile
ms:assetid: e88222d2-e1b7-4393-aac4-5ce9d24d5d5b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184648(v=office.15)
ms:contentKeyID: 55119893
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2044fc52370bdadd5c7f01debbd02c88dd881715
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717193"
---
# <a name="get-information-about-stores-in-a-profile"></a><span data-ttu-id="e0d0f-102">获取配置文件中的存储的相关信息</span><span class="sxs-lookup"><span data-stu-id="e0d0f-102">Get information about stores in a profile</span></span>

<span data-ttu-id="e0d0f-103">此代码示例展示了如何获取并枚举配置文件中的存储。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-103">This example shows how to get and enumerate stores in a profile.</span></span>

## <a name="example"></a><span data-ttu-id="e0d0f-104">示例</span><span class="sxs-lookup"><span data-stu-id="e0d0f-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="e0d0f-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="e0d0f-106">可使用 [Stores](https://msdn.microsoft.com/library/bb622944\(v=office.15\)) 集合来枚举给定配置文件的存储。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-106">You can use the [Stores](https://msdn.microsoft.com/library/bb622944\(v=office.15\)) collection to enumerate the stores for a given profile.</span></span> <span data-ttu-id="e0d0f-107">**Stores** 集合提供用于公开每个 [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 对象的相关信息（例如，何时添加了 **Store** 对象或即将何时从当前配置文件中移除 **Store** 对象）的成员。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-107">The **Stores** collection provides members that expose information about each [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) object, such as when a **Store** object has been added or when a **Store** object is about to be removed in the current profile.</span></span> <span data-ttu-id="e0d0f-108">在下面的代码示例中，EnumerateStores 获取表示当前配置文件中的存储的 **Stores** 对象，并枚举这些存储。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-108">In the following code example, EnumerateStores gets the **Stores** object that represents stores in the current profile, and enumerates the stores.</span></span> <span data-ttu-id="e0d0f-109">EnumerateStores 检查 **Stores** 集合中的每个 **Store** 对象。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-109">EnumerateStores examines each **Store** object in the **Stores** collection.</span></span> <span data-ttu-id="e0d0f-110">如果 [IsDataFileStore](https://msdn.microsoft.com/library/bb624116\(v=office.15\)) 属性返回 **true**，则指示该存储区是一个 .pst 或 .ost 存储区，[DisplayName](https://msdn.microsoft.com/library/bb612209\(v=office.15\)) 和 [FilePath](https://msdn.microsoft.com/library/bb646113\(v=office.15\)) 属性将写入 [侦听器](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx)集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-110">If the [IsDataFileStore](https://msdn.microsoft.com/library/bb624116\(v=office.15\)) property returns **true**, indicating that it is a .pst or .ost store, the [DisplayName](https://msdn.microsoft.com/library/bb612209\(v=office.15\)) and [FilePath](https://msdn.microsoft.com/library/bb646113\(v=office.15\)) properties are written to the trace listeners in the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="e0d0f-111">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="e0d0f-112">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-112">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="e0d0f-113">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="e0d0f-113">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e0d0f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0d0f-114">See also</span></span>

- [<span data-ttu-id="e0d0f-115">存储</span><span class="sxs-lookup"><span data-stu-id="e0d0f-115">Stores</span></span>](stores.md)

