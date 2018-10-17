---
title: 显示配置文件的地址列表
TOCTitle: Display the address lists for a profile
ms:assetid: ced8230b-110b-4ccb-a699-588798144154
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184643(v=office.15)
ms:contentKeyID: 55119802
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 9809603a7c54c9b1ce30c956ebef1a8fb9b6c208
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405943"
---
# <a name="display-the-address-lists-for-a-profile"></a><span data-ttu-id="b058b-102">显示配置文件的地址列表</span><span class="sxs-lookup"><span data-stu-id="b058b-102">Display the address lists for a profile</span></span>

<span data-ttu-id="b058b-103">此代码示例展示了如何显示当前配置文件的地址列表。</span><span class="sxs-lookup"><span data-stu-id="b058b-103">This example shows how to display the address lists for the current profile.</span></span>

## <a name="example"></a><span data-ttu-id="b058b-104">示例</span><span class="sxs-lookup"><span data-stu-id="b058b-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="b058b-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="b058b-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="b058b-p101">当前配置文件包含 [AddressLists](https://msdn.microsoft.com/library/bb611894\(v=office.15\)) 集合所表示的地址列表。若要获取 AddressLists 集合的实例，必须使用 [NameSpace](https://msdn.microsoft.com/library/bb624048\(v=office.15\)) 对象的 [AddressLists](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b058b-p101">The current profile contains address lists that are represented by the [AddressLists](https://msdn.microsoft.com/library/bb611894\(v=office.15\)) collection. To get an instance of the AddressLists collection, you must use the [AddressLists](https://msdn.microsoft.com/library/bb624048\(v=office.15\)) property of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object.</span></span>

<span data-ttu-id="b058b-108">在下面的代码示例中，EnumerateAddressLists 先使用 foreach 语句枚举 AddressLists 集合中的各个 [AddressList](https://msdn.microsoft.com/library/bb623538\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="b058b-108">In the following code example,   first enumerates each AddressList object in the AddressLists collection by using a   statement.</span></span> <span data-ttu-id="b058b-109">然后，此代码示例创建包含 [Name](https://msdn.microsoft.com/library/bb609849\(v=office.15\))、[ResolutionOrder](https://msdn.microsoft.com/library/bb646853\(v=office.15\))、[IsReadOnly](https://msdn.microsoft.com/library/bb612676\(v=office.15\)) 和 [IsInitialAddressList](https://msdn.microsoft.com/library/bb646646\(v=office.15\)) 属性的值的字符串。</span><span class="sxs-lookup"><span data-stu-id="b058b-109">The example then creates a string that contains the values of the [Name](https://msdn.microsoft.com/library/bb609849\(v=office.15\)) , [ResolutionOrder](https://msdn.microsoft.com/library/bb646853\(v=office.15\)) , [IsReadOnly](https://msdn.microsoft.com/library/bb612676\(v=office.15\)) , and [IsInitialAddressList](https://msdn.microsoft.com/library/bb646646\(v=office.15\)) properties.</span></span> <span data-ttu-id="b058b-110">最后，EnumerateAddressLists 将字符串写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="b058b-110">Finally,   writes the string to the trace listeners of the Listeners collection.</span></span> <span data-ttu-id="b058b-111">这会显示当前配置文件的每个地址列表。</span><span class="sxs-lookup"><span data-stu-id="b058b-111">This displays each address list for the current profile.</span></span>

<span data-ttu-id="b058b-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b058b-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="b058b-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b058b-113">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="b058b-114">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b058b-114">The following line of code shows how to do the import and assignment in C#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b058b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b058b-115">See also</span></span>

- [<span data-ttu-id="b058b-116">通讯簿</span><span class="sxs-lookup"><span data-stu-id="b058b-116">Address Book</span></span>](address-book.md)
