---
title: 在枚举文件夹中的项时筛选并显示多值属性
TOCTitle: Filter and display multivalued properties when enumerating items in a folder
ms:assetid: 62dd2120-5c85-44b3-89ec-c4ca85aa2964
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184613(v=office.15)
ms:contentKeyID: 55119887
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d6242506bac081ee16d125ea92fbed69939c6abc
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542623"
---
# <a name="filter-and-display-multivalued-properties-when-enumerating-items-in-a-folder"></a><span data-ttu-id="f0996-102">在枚举文件夹中的项时筛选并显示多值属性</span><span class="sxs-lookup"><span data-stu-id="f0996-102">Filter and display multivalued properties when enumerating items in a folder</span></span>

<span data-ttu-id="f0996-103">此代码示例展示了如何在枚举文件夹中的项时筛选并显示多值属性。</span><span class="sxs-lookup"><span data-stu-id="f0996-103">This example shows how to filter and display multivalued properties while enumerating items in a folder.</span></span>

## <a name="example"></a><span data-ttu-id="f0996-104">示例</span><span class="sxs-lookup"><span data-stu-id="f0996-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="f0996-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="f0996-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="f0996-p101">[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 或 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象中的一组项目数据。首次将二进制、日期或多值属性添加到 **Table** 对象时，此类属性的引用方式将影响其类型和格式。因为内置名称引用有时会返回与命名空间引用不同的列值，所以您应确定属性是由其显式内置名称（如果具有这样一个名称）引用，还是由命名空间引用（无论是否存在显式内置名称）。下表显示了每个原始属性类型的属性值表示形式（类型和格式方面）的差异。</span><span class="sxs-lookup"><span data-stu-id="f0996-p101">The [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object represents a set of item data from a [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) or [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) object. When a binary, date, or multivalued property is first added to a **Table** object, the way the property is referenced affects its type and format. Because built-in name references sometimes return a different column value than a namespace reference, you should determine whether the property is referenced by its explicit built-in name (if it has one), or by namespace (regardless of the existence of an explicit built-in name). The following table shows the difference in the property value representation (in terms of type and format) per original property type.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f0996-110">类型</span><span class="sxs-lookup"><span data-stu-id="f0996-110">Type</span></span></p></th>
<th><p><span data-ttu-id="f0996-111">指定的属性使用内置名称时的返回类型</span><span class="sxs-lookup"><span data-stu-id="f0996-111">Return type if the specified property uses a built-in name</span></span></p></th>
<th><p><span data-ttu-id="f0996-112">指定属性使用命名空间时的返回类型</span><span class="sxs-lookup"><span data-stu-id="f0996-112">Return type if the specified property uses a namespace</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0996-113">二进制 <b>(PT_BINARY)</b></span><span class="sxs-lookup"><span data-stu-id="f0996-113">Binary <b>(PT_BINARY)</b></span></span></p></td>
<td><p><span data-ttu-id="f0996-114">字符串</span><span class="sxs-lookup"><span data-stu-id="f0996-114">String</span></span></p></td>
<td><p><span data-ttu-id="f0996-115">字节数组</span><span class="sxs-lookup"><span data-stu-id="f0996-115">Byte array</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0996-116">日期 <b>(PT_SYSTIME)</b></span><span class="sxs-lookup"><span data-stu-id="f0996-116">Date <b>(PT_SYSTIME)</b></span></span></p></td>
<td><p><span data-ttu-id="f0996-117">本地 <b>DateTime</b></span><span class="sxs-lookup"><span data-stu-id="f0996-117">Local <b>DateTime</b></span></span></p></td>
<td><p><span data-ttu-id="f0996-118">UTC <b>DateTime</b></span><span class="sxs-lookup"><span data-stu-id="f0996-118">UTC <b>DateTime</b></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0996-119">多值类型（亦称为“关键字类型”），如 <b>Categories</b> 属性 <b>(PT_MV_STRING8)</b></span><span class="sxs-lookup"><span data-stu-id="f0996-119">Multivalued (also known as keyword type) such as <b>Categories</b> property <b>(PT_MV_STRING8)</b></span></span></p></td>
<td><p><span data-ttu-id="f0996-120">包含逗号分隔值的字符串</span><span class="sxs-lookup"><span data-stu-id="f0996-120">String that contains comma-separated values</span></span></p></td>
<td><p><span data-ttu-id="f0996-121">所含每个关键字对应一个元素的一维数组</span><span class="sxs-lookup"><span data-stu-id="f0996-121">One-dimensional array that contains one element for each keyword</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f0996-122">下面的代码示例阐释如何将 MAPI 字符串命名空间属性添加到 **Table** 对象，以及多值属性如何影响 [Column](https://msdn.microsoft.com/library/bb609646\(v=office.15\)) 对象中返回的值。</span><span class="sxs-lookup"><span data-stu-id="f0996-122">The following code example illustrates how to add a MAPI string namespace property to the **Table** object and how multivalued properties affect the values returned in a [Column](https://msdn.microsoft.com/library/bb609646\(v=office.15\)) object.</span></span> <span data-ttu-id="f0996-123">TableMultiValuedProperties 过程从 **Table** 对象中筛选出 [Categories](https://msdn.microsoft.com/library/bb646607\(v=office.15\)) 属性不是空引用的行。</span><span class="sxs-lookup"><span data-stu-id="f0996-123">The TableMultiValuedProperties procedure filters the **Table** object for rows where the [Categories](https://msdn.microsoft.com/library/bb646607\(v=office.15\)) property is not a null reference.</span></span> <span data-ttu-id="f0996-124">**Categories** 属性由使用 MAPI 字符串命名空间的属性表示。</span><span class="sxs-lookup"><span data-stu-id="f0996-124">The **Categories** property is represented by a property that uses the MAPI string namespace.</span></span> <span data-ttu-id="f0996-125">DAV 搜索和定位 (DASL) 筛选器是针对具有类别的项目而构造的（实际筛选器返回不具有 null 引用的类别）。</span><span class="sxs-lookup"><span data-stu-id="f0996-125">A DAV Searching and Locating (DASL) filter is constructed for items that have categories (the actual filter returns categories that do not have a null reference).</span></span> <span data-ttu-id="f0996-126">然后，通过连接类型说明符 0000001f 和 categoriesProperty 常量，将 **Categories** 列添加到 **Table** 对象中。</span><span class="sxs-lookup"><span data-stu-id="f0996-126">A **Categories** column is then added to the **Table** object by concatenating the type specifier, 0000001f, with the categoriesProperty constant.</span></span> <span data-ttu-id="f0996-127">表示 **Categories** 属性的 **Column** 对象最后会包含一个一维字符串数组，其中数组的每个元素都表示一个分配给相应项目的类别。</span><span class="sxs-lookup"><span data-stu-id="f0996-127">Finally, the **Column** object that represents the **Categories** property contains a one-dimensional string array where each element of the array represents a category assigned to the item.</span></span> <span data-ttu-id="f0996-128">项的 **Categories** 和 **Subject** 属性均被写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="f0996-128">Both the item’s **Categories** and **Subject** properties are written to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="f0996-129">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="f0996-129">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="f0996-130">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="f0996-130">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="f0996-131">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="f0996-131">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void TableMultiValuedProperties()
{
    const string categoriesProperty =
        "http://schemas.microsoft.com/mapi/string/"
        + "{00020329-0000-0000-C000-000000000046}/Keywords";
    // Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // Call GetTable with filter for categories
    string filter = "@SQL="
        + "Not(" + "\"" + categoriesProperty
        + "\"" + " Is Null)";
    Outlook.Table table =
        folder.GetTable(filter,
        Outlook.OlTableContents.olUserItems);
    // Add categories column and append type specifier
    table.Columns.Add(categoriesProperty + "/0000001F");
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        string[] categories =
            (string[])nextRow[categoriesProperty + "/0000001F"];
        Debug.WriteLine("Subject: " + nextRow["Subject"]);
        Debug.Write("Categories: ");
        foreach (string category in categories)
        {
            Debug.Write("\t" + category);
        }
        Debug.WriteLine("\n");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f0996-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0996-132">See also</span></span>

- [<span data-ttu-id="f0996-133">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="f0996-133">Search and filter</span></span>](search-and-filter.md)

