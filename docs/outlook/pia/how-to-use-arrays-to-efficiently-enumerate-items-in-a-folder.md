---
title: 使用数组高效枚举文件夹中的项
TOCTitle: Use arrays to efficiently enumerate items in a folder
ms:assetid: 05a73225-ad0d-4d52-90b6-448d220348df
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184588(v=office.15)
ms:contentKeyID: 55119885
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: d165b27da58a4e99eabb897aac3d2dc03811f588
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407504"
---
# <a name="use-arrays-to-efficiently-enumerate-items-in-a-folder"></a><span data-ttu-id="a1b9c-102">使用数组高效枚举文件夹中的项</span><span class="sxs-lookup"><span data-stu-id="a1b9c-102">Use arrays to efficiently enumerate items in a folder</span></span>

<span data-ttu-id="a1b9c-103">此代码示例展示了如何使用 [GetArray(Int32)](https://msdn.microsoft.com/library/bb608928\(v=office.15\)) 方法高效枚举 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象中的项。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-103">This example shows how to efficiently enumerate items in a [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object by using the [GetArray(Int32)](https://msdn.microsoft.com/library/bb608928\(v=office.15\)) method.</span></span>

## <a name="example"></a><span data-ttu-id="a1b9c-104">示例</span><span class="sxs-lookup"><span data-stu-id="a1b9c-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="a1b9c-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="a1b9c-106">在下面的代码示例中，DemoGetArrayForTable 使用 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法，从 **Folder** 对象中获取 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-106">In the following code example,   gets a Table object from a Folder object by using the GetTable(Object, Object) method.</span></span> <span data-ttu-id="a1b9c-107">然后，DemoGetArrayForTable 使用 **GetArray** 方法，返回包含表中每行元素的 [Array](https://msdn.microsoft.com/library/system.array.aspx) 对象。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-107"> then uses the GetArray method to return an Array object that contains elements for every row in the table.</span></span> <span data-ttu-id="a1b9c-108">返回的 **Array** 对象是一个二维数组，表示 **Table** 中的一系列行值和列值。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-108">The returned **Array** object is a two-dimensional array that represents a set of row and column values from the **Table**.</span></span> <span data-ttu-id="a1b9c-109">此数组从 0 开始计数，与 Outlook 集合从 1 开始计数不同。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-109">The array is zero-based, instead of one-based as is the case with Outlook collections.</span></span> <span data-ttu-id="a1b9c-110">获取 **Array** 对象后，此代码便会使用 for 循环枚举整个表。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-110">Once the Array object is obtained, the code uses a   loop to enumerate through the table.</span></span>

<span data-ttu-id="a1b9c-111">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="a1b9c-112">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-112">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="a1b9c-113">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="a1b9c-113">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoGetArrayForTable()
{
    // Obtain Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    Outlook.Table table =
        folder.GetTable("", Outlook.OlTableContents.olUserItems);
    Array tableArray = table.GetArray(table.GetRowCount()) as Array;
    for (int i = 0; i <= tableArray.GetUpperBound(0); i++)
    {
        for (int j = 0; j <= tableArray.GetUpperBound(1); j++)
        {
            Debug.WriteLine(tableArray.GetValue(i, j));
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="a1b9c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1b9c-114">See also</span></span>

- [<span data-ttu-id="a1b9c-115">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="a1b9c-115">Search and Filter</span></span>](search-and-filter.md)
