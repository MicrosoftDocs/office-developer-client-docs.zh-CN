---
title: 根据上次修改时间枚举收件箱中的项
TOCTitle: Enumerate items in the Inbox based on the last modification time
ms:assetid: 93a25143-def6-4832-bac2-3744558c2736
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184626(v=office.15)
ms:contentKeyID: 55119920
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: ecc4ed8f2fb207b8952fef41481738dd8be0ee02
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406041"
---
# <a name="enumerate-items-in-the-inbox-based-on-the-last-modification-time"></a><span data-ttu-id="bfa03-102">根据上次修改时间枚举收件箱中的项</span><span class="sxs-lookup"><span data-stu-id="bfa03-102">Enumerate items in the Inbox based on the last modification time</span></span>

<span data-ttu-id="bfa03-103">此代码示例展示了如何根据上次修改时间枚举“收件箱”文件夹中的项。</span><span class="sxs-lookup"><span data-stu-id="bfa03-103">This example shows how to enumerate items in the Inbox folder based on the last modification time.</span></span>

## <a name="example"></a><span data-ttu-id="bfa03-104">示例</span><span class="sxs-lookup"><span data-stu-id="bfa03-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="bfa03-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="bfa03-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="bfa03-106">[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 或 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象中的一组项。</span><span class="sxs-lookup"><span data-stu-id="bfa03-106">The [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object represents a set of items from a [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) or [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) object.</span></span> <span data-ttu-id="bfa03-107">若要获取 **Table**，请对 **Folder** 或 **Search** 对象调用 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="bfa03-107">To obtain a **Table**, call the [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) method on a **Folder** or **Search** object.</span></span> <span data-ttu-id="bfa03-108">返回的 **Table** 中的每一项都只包含项属性的默认子集。</span><span class="sxs-lookup"><span data-stu-id="bfa03-108">Each item in the returned **Table** contains only a default subset of the item's properties.</span></span> <span data-ttu-id="bfa03-109">可以将每个 [Row](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) 对象视为文件夹中的项，并将每个 [Column](https://msdn.microsoft.com/library/bb609646\(v=office.15\)) 对象视为项属性。</span><span class="sxs-lookup"><span data-stu-id="bfa03-109">Each [Row](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) object can be regarded as an item in the folder, and each [Column](https://msdn.microsoft.com/library/bb609646\(v=office.15\)) object as a property of an item.</span></span> <span data-ttu-id="bfa03-110">**Table** 中不支持删除、添加或更改行。</span><span class="sxs-lookup"><span data-stu-id="bfa03-110">Removing, adding, or changing rows is not supported in the **Table**.</span></span> <span data-ttu-id="bfa03-111">若要枚举 **Table** 中的各项目，需首先使用 [EndOfTable](https://msdn.microsoft.com/library/bb647715\(v=office.15\)) 属性来查看您的当前位置是否位于表结尾处。</span><span class="sxs-lookup"><span data-stu-id="bfa03-111">To enumerate items in a **Table**, first use the [EndOfTable](https://msdn.microsoft.com/library/bb647715\(v=office.15\)) property to see whether your current position is at the end of the table.</span></span> <span data-ttu-id="bfa03-112">如果 **EndOfTable** 返回 **false**，则使用 [GetNextRow()](https://msdn.microsoft.com/library/bb609740\(v=office.15\)) 方法来返回包含默认数量的 **Column** 对象的 **Row**。</span><span class="sxs-lookup"><span data-stu-id="bfa03-112">If **EndOfTable** returns **false**, use the [GetNextRow()](https://msdn.microsoft.com/library/bb609740\(v=office.15\)) method to return a **Row**, which contains a default number of **Column** objects.</span></span> <span data-ttu-id="bfa03-113">通过调用 **GetNextRow**，继续直接循环访问 **Table**，直至 **EndOfTable** 返回 **true**。</span><span class="sxs-lookup"><span data-stu-id="bfa03-113">You continue iterating in a forward manner through the **Table** by calling **GetNextRow** until **EndOfTable** returns **true**.</span></span>

<span data-ttu-id="bfa03-114">在下面的代码示例中，DemoTableForInbox 获取“收件箱”文件夹的 **Table** 对象，使用 **LastModificationTime** 属性和 [Sort(String, Object)](https://msdn.microsoft.com/library/bb652667\(v=office.15\)) 方法对 **Table** 对象进行排序，并循环访问表，以将每一项的主题写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="bfa03-114">In the following code example,   obtains a Table object for the Inbox folder, sorts the Table object by using the LastModificationTime property and Sort(String, Object) method, and iterates through the table to write the subject of each item to the trace listeners of the Listeners collection.</span></span>

<span data-ttu-id="bfa03-115">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="bfa03-115">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="bfa03-116">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="bfa03-116">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="bfa03-117">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="bfa03-117">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoTableForInbox()
{
    //Obtain Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    //Obtain Table using defaults
    Outlook.Table table =
        folder.GetTable(Type.Missing, Type.Missing);
    table.Sort("LastModificationTime",
        Outlook.OlSortOrder.olDescending);
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        Debug.WriteLine(nextRow["Subject"]);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="bfa03-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfa03-118">See also</span></span>

- [<span data-ttu-id="bfa03-119">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="bfa03-119">Search and Filter</span></span>](search-and-filter.md)

