---
title: 使用“即时搜索”在所有文件夹和所有存储中搜索主题包含某短语的项
TOCTitle: Use instant search to search all folders and all stores for a phrase in the subject
ms:assetid: d3152bfa-6e7d-4b68-8c7e-e2e155a92b49
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424478(v=office.15)
ms:contentKeyID: 55119923
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 07b0ba7a1d488dc1c7e1fcf0e9ae487b04b88755
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335369"
---
# <a name="use-instant-search-to-search-all-folders-and-all-stores-for-a-phrase-in-the-subject"></a><span data-ttu-id="b6842-102">使用“即时搜索”在所有文件夹和所有存储中搜索主题包含某短语的项</span><span class="sxs-lookup"><span data-stu-id="b6842-102">Use instant search to search all folders and all stores for a phrase in the subject</span></span>

<span data-ttu-id="b6842-103">本示例使用"即时搜索"在所有文件夹和所有存储区中搜索主题中的某个短语，并在资源管理器窗口中显示相应项目。</span><span class="sxs-lookup"><span data-stu-id="b6842-103">This example uses Instant Search to search all folders and all stores for a phrase in the subject, and then displays the items in an explorer window.</span></span>

## <a name="example"></a><span data-ttu-id="b6842-104">示例</span><span class="sxs-lookup"><span data-stu-id="b6842-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="b6842-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="b6842-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="b6842-106">“即时搜索”是一项 Microsoft Outlook 功能，便于用户通过发出根据内容返回结果的查询来执行搜索。</span><span class="sxs-lookup"><span data-stu-id="b6842-106">Instant Search is a feature of Microsoft Outlook that enables you to search by issuing queries that return results based on the content.</span></span> <span data-ttu-id="b6842-107">您的查询一经处理后，即会在各种对象中返回结果，包括 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象、 [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 集合和 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="b6842-107">Once your query has been processed, the results can be returned in a variety of objects, including the [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object, the [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) collection, and the [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) object.</span></span> <span data-ttu-id="b6842-108">您可以使用 Microsoft Windows 桌面搜索提供的高级查询语法 (AQS)，来编写使用即时搜索的代码。</span><span class="sxs-lookup"><span data-stu-id="b6842-108">You can write code that uses Instant Search by using the Advanced Query Syntax (AQS) that is offered by Microsoft Windows Desktop Search.</span></span> <span data-ttu-id="b6842-109">AQS 是 Outlook 支持的三种查询语言之一。</span><span class="sxs-lookup"><span data-stu-id="b6842-109">AQS is one of three query languages that Outlook supports.</span></span> <span data-ttu-id="b6842-110">它的功能很强大，但仅限于 [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) 对象的 [Search(String, OlSearchScope)](https://msdn.microsoft.com/library/bb610561\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="b6842-110">It is powerful, but limited to the [Search(String, OlSearchScope)](https://msdn.microsoft.com/library/bb610561\(v=office.15\)) method of the [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) object.</span></span> <span data-ttu-id="b6842-111">无法使用 AQS 限制 **Table** 或 **Item** 对象。</span><span class="sxs-lookup"><span data-stu-id="b6842-111">You cannot use AQS to provide a restriction for **Table** or **Item** objects.</span></span> <span data-ttu-id="b6842-112">此外，AQS 查询返回的结果只能显示在 Outlook 用户界面中。</span><span class="sxs-lookup"><span data-stu-id="b6842-112">In addition, the results returned by an AQS query can be displayed only in the Outlook user interface.</span></span> <span data-ttu-id="b6842-113">下表列出了 Outlook 支持的三种查询语言；不过，本主题介绍的是仅使用 AQS。</span><span class="sxs-lookup"><span data-stu-id="b6842-113">The following table lists the three query languages that Outlook supports; however, this topic will illustrate the use of only AQS.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b6842-114">查询语言</span><span class="sxs-lookup"><span data-stu-id="b6842-114">Query language</span></span></p></th>
<th><p><span data-ttu-id="b6842-115">说明</span><span class="sxs-lookup"><span data-stu-id="b6842-115">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6842-116">AQS</span><span class="sxs-lookup"><span data-stu-id="b6842-116">AQS</span></span></p></td>
<td><p><span data-ttu-id="b6842-117">AQS 由 Windows 桌面搜索使用，是针对 Outlook 中的即时搜索功能的查询语言。</span><span class="sxs-lookup"><span data-stu-id="b6842-117">AQS is used by Windows Desktop Search and is the query language for the Instant Search feature in Outlook.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6842-118">DASL</span><span class="sxs-lookup"><span data-stu-id="b6842-118">DASL</span></span></p></td>
<td><p><span data-ttu-id="b6842-p102">DAV 搜索和定位 (DASL) 查询语言基于 Outlook 中 DASL 的 Microsoft Exchange 实现。DASL 可用于在 <b>Table</b> 对象中返回结果。 </span><span class="sxs-lookup"><span data-stu-id="b6842-p102">DAV Search and Locating (DASL) query language is based on the Microsoft Exchange implementation of DASL in Outlook. DASL can be used to return results in the <b>Table</b> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6842-121">Jet</span><span class="sxs-lookup"><span data-stu-id="b6842-121">Jet</span></span></p></td>
<td><p><span data-ttu-id="b6842-p103">Jet 查询语言为 Outlook 提供简单的查询语言，它基于 Microsoft Jet Expression 服务。Jet 用于为 <b>Items</b> 集合和 <b>Table</b> 对象的 <b>Restrict</b> 方法创建筛选器字符串。</span><span class="sxs-lookup"><span data-stu-id="b6842-p103">Jet query language provides a simple query language for Outlook, and is based on the Microsoft Jet Expression Service. Jet is used to create filter strings for the <b>Restrict</b> methods of the <b>Items</b> collection and the <b>Table</b> object.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b6842-124">在下面的代码示例中，DemoInstantSearch 获取所有存储中的全部邮件文件夹，这些存储已使用 [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 对象的 [IsInstantSearchEnabled](https://msdn.microsoft.com/library/bb609793\(v=office.15\)) 属性启用索引。</span><span class="sxs-lookup"><span data-stu-id="b6842-124">In the following code example, DemoInstantSearch gets all mail folders in all stores where indexing is enabled by using the [IsInstantSearchEnabled](https://msdn.microsoft.com/library/bb609793\(v=office.15\)) property of the [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) object.</span></span> <span data-ttu-id="b6842-125">然后，它使用 **Explorer** 对象的 **Search** 方法，筛选出主题中包含确切短语“Office 2007”的上月收到的所有项。</span><span class="sxs-lookup"><span data-stu-id="b6842-125">It then uses the **Search** method of the **Explorer** object to filter for all items that contain the exact phrase “Office 2007” in the subject and that have been received in the last month.</span></span> <span data-ttu-id="b6842-126">最后，搜索结果显示在独立资源管理器窗口中。</span><span class="sxs-lookup"><span data-stu-id="b6842-126">The results of the search are finally displayed in a separate explorer window.</span></span>

<span data-ttu-id="b6842-127">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b6842-127">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="b6842-128">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b6842-128">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="b6842-129">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b6842-129">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoInstantSearch()
{
    if (Application.Session.DefaultStore.IsInstantSearchEnabled)
    {
        Outlook.Explorer explorer = Application.Explorers.Add(
            Application.Session.GetDefaultFolder(
            Outlook.OlDefaultFolders.olFolderInbox)
            as Outlook.Folder,
            Outlook.OlFolderDisplayMode.olFolderDisplayNormal);
        string filter = "subject:" +
            "\"" + "Office 2007" + "\"" +
            " received:(last month)";
        explorer.Search(filter,
            Outlook.OlSearchScope.olSearchScopeAllFolders);
        explorer.Display();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="b6842-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6842-130">See also</span></span>

- [<span data-ttu-id="b6842-131">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="b6842-131">Search and filter</span></span>](search-and-filter.md)

