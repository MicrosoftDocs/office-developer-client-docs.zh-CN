---
title: 枚举文件夹中的隐藏项
TOCTitle: Enumerate hidden items in a folder
ms:assetid: dafad1fb-94ce-4584-b5d1-2de5fad2f72a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184645(v=office.15)
ms:contentKeyID: 55119888
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: b048ec7fb47a8cbf6b8b49115c59079754fd4ba6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406020"
---
# <a name="enumerate-hidden-items-in-a-folder"></a><span data-ttu-id="4c7f7-102">枚举文件夹中的隐藏项</span><span class="sxs-lookup"><span data-stu-id="4c7f7-102">Enumerate hidden items in a folder</span></span>

<span data-ttu-id="4c7f7-103">此代码示例展示了如何查找并枚举文件夹中的隐藏项。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-103">This example shows how to find and enumerate hidden items in a folder.</span></span>

## <a name="example"></a><span data-ttu-id="4c7f7-104">示例</span><span class="sxs-lookup"><span data-stu-id="4c7f7-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="4c7f7-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="4c7f7-106">[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示文件夹中的一组项，它的特征之一是其中可能包含隐藏项。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-106">One feature of the [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object, which represents a set of items in a folder, is that it may have hidden items.</span></span> <span data-ttu-id="4c7f7-107">若要返回文件夹中的隐藏项，请将 [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) 对象的 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法中的 *TableContents* 参数设置为 [olHiddenItems](https://msdn.microsoft.com/library/bb622801\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-107">To return hidden items in a folder, set the  *TableContents* parameter in the [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) method of the [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) object to [olHiddenItems](https://msdn.microsoft.com/library/bb622801\(v=office.15\)) .</span></span> <span data-ttu-id="4c7f7-108">在下面的代码示例中，TableForInboxHiddenItems 获取收件箱文件夹的隐藏项，并将每个隐藏项的 [Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)) 和 [MessageClass](https://msdn.microsoft.com/library/bb645845\(v=office.15\)) 属性的值写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-108">In the following code example,   obtains the hidden items of an Inbox folder, and writes the values of the Subject and MessageClass properties for each hidden item to the trace listeners of the Listeners collection.</span></span>

<span data-ttu-id="4c7f7-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="4c7f7-110">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-110">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="4c7f7-111">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="4c7f7-111">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void TableForInboxHiddenItems()
{
    // Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // Call GetTable with OlTableContents.olHiddenItems
    Outlook.Table table =
        folder.GetTable("",
        Outlook.OlTableContents.olHiddenItems);
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        // Test for null subject
        if (nextRow["Subject"] == null)
        {
            Debug.WriteLine(nextRow["MessageClass"]);
        }
        else
        {
            Debug.WriteLine(nextRow["Subject"] + " "
                + nextRow["MessageClass"]);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="4c7f7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c7f7-112">See also</span></span>

<span data-ttu-id="4c7f7-113">-[搜索和筛选](search-and-filter.md)</span><span class="sxs-lookup"><span data-stu-id="4c7f7-113">Search and Filter</span></span>
