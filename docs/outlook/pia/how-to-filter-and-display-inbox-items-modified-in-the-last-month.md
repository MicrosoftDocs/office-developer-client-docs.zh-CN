---
title: 筛选并显示上月修改的收件箱项目
TOCTitle: Filter and display Inbox items modified in the last month
ms:assetid: ef6004dc-0b5a-4d1f-8937-1384d1dfc1ca
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424482(v=office.15)
ms:contentKeyID: 55119886
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 77fe6e7df4cf67ed1ca2d62b8cf48f1b2873ccbe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320291"
---
# <a name="filter-and-display-inbox-items-modified-in-the-last-month"></a><span data-ttu-id="dc4f9-102">筛选并显示上月修改的收件箱项目</span><span class="sxs-lookup"><span data-stu-id="dc4f9-102">Filter and display Inbox items modified in the last month</span></span>

<span data-ttu-id="dc4f9-103">此示例展示如何筛选并显示上月修改的收件箱项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-103">This example shows how to filter and display Inbox items that were modified in the last month.</span></span>

## <a name="example"></a><span data-ttu-id="dc4f9-104">示例</span><span class="sxs-lookup"><span data-stu-id="dc4f9-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="dc4f9-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="dc4f9-106">DAV 搜索和定位 (DASL) 查询语言基于 Outlook 中 DASL 的 Microsoft Exchange 实现。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-106">DAV Searching and Locating (DASL) query language is based on the Microsoft Exchange implementation of DASL in Outlook.</span></span> <span data-ttu-id="dc4f9-107">它可用于在对文件夹数据的项目级搜索中返回基于属性的结果，例如使用 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象代表的结果。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-107">It can be used to return property-based results for item-level searches in folder data, such as that represented by a [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object.</span></span> <span data-ttu-id="dc4f9-108">通过使用等号 (=) 运算符，DASL 筛选器支持字符串比较，其中包括等价、前缀、短语和子字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-108">DASL filters support string comparisons, including equivalence, prefix, phrase, and substring matching, by using the equal (=) operator.</span></span> <span data-ttu-id="dc4f9-109">DASL 查询可用于执行日期/时间比较和筛选。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-109">You can use DASL queries to perform date-time comparison and filtering.</span></span>

<span data-ttu-id="dc4f9-p102">由于 DASL 查询始终采用协调世界时 (UTC) 形式执行 **DateTime** 比较，因此如果希望查询能够正确运行，则必须将本地时间值转换为 UTC。因 DASL 筛选器支持字符串比较的缘故，还必须将 **DateTime** 值转换成字符串表现形式。可以通过两种方式进行 **DateTime** 转换：使用 [Row](https://msdn.microsoft.com/library/bb645832\(v=office.15\)) 对象的 [LocalTimeToUTC(Object)](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) 方法，或使用 Outlook **DateTime** 宏进行转换。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-p102">Because DASL queries always perform **DateTime** comparisons in Coordinated Universal Time (UTC), you must convert the local time value to UTC if you want the query to operate correctly. You must also convert the **DateTime** value to a string representation because DASL filters support string comparisons. You can make the **DateTime** conversion in two ways: by using the [LocalTimeToUTC(Object)](https://msdn.microsoft.com/library/bb645832\(v=office.15\)) method of the [Row](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) object, or by using Outlook **DateTime** macros to make the conversion.</span></span>

<span data-ttu-id="dc4f9-113">下面的代码行演示如何使用 **LocalTimeToUTC** 方法将 **LastModificationTime** 属性（所有 **Item** 对象中的默认列）的值转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-113">The following line of code shows how to use the **LocalTimeToUTC** method to convert the value of the **LastModificationTime** property (which is a default column in all **Item** objects) to UTC.</span></span>

```csharp
DateTime modified = nextRow.LocalTimeUTC(“LastModificationTime”);
```

<span data-ttu-id="dc4f9-114">下表列出了可用来返回筛选后的字符串的 **DateTime** 宏，这些字符串是将给定的 **DateTime** 属性值与 UTC 中指定的相对日期或时间范围加以比较的结果。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-114">The following table lists the **DateTime** macros you can use to return filtered strings that compare the value of a given **DateTime** property with a specified relative date or date range in UTC.</span></span> <span data-ttu-id="dc4f9-115">SchemaName 属性值表示由命名空间引用的任何有效的 **DateTime** 属性。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-115">The SchemaName property value represents any valid **DateTime** property referenced by namespace.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="dc4f9-116">宏</span><span class="sxs-lookup"><span data-stu-id="dc4f9-116">Macro</span></span></p></th>
<th><p><span data-ttu-id="dc4f9-117">语法</span><span class="sxs-lookup"><span data-stu-id="dc4f9-117">Syntax</span></span></p></th>
<th><p><span data-ttu-id="dc4f9-118">说明</span><span class="sxs-lookup"><span data-stu-id="dc4f9-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc4f9-119">今天</span><span class="sxs-lookup"><span data-stu-id="dc4f9-119">today</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-120">%today(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-120">%today(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-121">限制为 SchemaName 属性值等于今天的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-121">Restricts for items with a SchemaName property value equal to today.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4f9-122">tomorrow</span><span class="sxs-lookup"><span data-stu-id="dc4f9-122">tomorrow</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-123">%tomorrow(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-123">%tomorrow(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-124">限制为 SchemaName 属性值等于明天的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-124">Restricts for items with a SchemaName property value equal to tomorrow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc4f9-125">yesterday</span><span class="sxs-lookup"><span data-stu-id="dc4f9-125">yesterday</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-126">%yesterday(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-126">%yesterday(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-127">限制为 SchemaName 属性值等于昨天的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-127">Restricts for items with a SchemaName property value equal to yesterday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4f9-128">next7days</span><span class="sxs-lookup"><span data-stu-id="dc4f9-128">next7days</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-129">%next7days(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-129">%next7days(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-130">限制为 SchemaName 属性值在接下来七天范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-130">Restricts for items with SchemaName property values in a range equivalent to the next seven days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc4f9-131">last7days</span><span class="sxs-lookup"><span data-stu-id="dc4f9-131">last7days</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-132">%last7days(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-132">%last7days(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-133">限制为 SchemaName 属性值在过去七天范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-133">Restricts for items with SchemaName property values in a range equivalent to the last seven days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4f9-134">nextweek</span><span class="sxs-lookup"><span data-stu-id="dc4f9-134">nextweek</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-135">%nextweek(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-135">%nextweek(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-136">限制为 SchemaName 属性值在下一周范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-136">Restricts for items with SchemaName property values in a range equivalent to next week.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc4f9-137">thisweek</span><span class="sxs-lookup"><span data-stu-id="dc4f9-137">thisweek</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-138">%thisweek(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-138">%thisweek(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-139">限制为 SchemaName 属性值在当周范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-139">Restricts for items with SchemaName property values in a range equivalent to this week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4f9-140">lastweek</span><span class="sxs-lookup"><span data-stu-id="dc4f9-140">lastweek</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-141">%lastweek(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-141">%lastweek(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-142">限制为 SchemaName 属性值在上一周范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-142">Restricts for items with SchemaName property values in a range equivalent to last week.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc4f9-143">nextmonth</span><span class="sxs-lookup"><span data-stu-id="dc4f9-143">nextmonth</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-144">%nextmonth(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-144">%nextmonth(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-145">限制为 SchemaName 属性值在下个月范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-145">Restricts for items with SchemaName property values in a range equivalent to next month.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc4f9-146">thismonth</span><span class="sxs-lookup"><span data-stu-id="dc4f9-146">thismonth</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-147">%thismonth(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-147">%thismonth(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-148">限制为 SchemaName 属性值在当月范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-148">Restricts for items with SchemaName property values in a range equivalent to this month.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc4f9-149">lastmonth</span><span class="sxs-lookup"><span data-stu-id="dc4f9-149">lastmonth</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-150">%lastmonth(“SchemaName”)%</span><span class="sxs-lookup"><span data-stu-id="dc4f9-150">%lastmonth(“SchemaName”)%</span></span></p></td>
<td><p><span data-ttu-id="dc4f9-151">限制为 SchemaName 属性值在上个月范围内的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-151">Restricts for items with SchemaName property values in a range equivalent to last month.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc4f9-152">在下面的示例中，DemoDASLDateMacro 会创建一个 DASL 查询，该查询使用 **lastmonthDateTime** 宏在用户的收件箱中筛选上个月修改的项目。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-152">In the following example, DemoDASLDateMacro creates a DASL query that uses the **lastmonthDateTime** macro to filter for items in the user’s Inbox that were modified in the last month.</span></span> <span data-ttu-id="dc4f9-153">然后，它会使用该筛选器创建 **Table**，并枚举和显示受限 **Table** 对象中的各行。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-153">It then creates a **Table** object with that filter, and enumerates and displays the rows in the restricted **Table** object.</span></span>

<span data-ttu-id="dc4f9-154">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-154">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="dc4f9-155">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-155">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="dc4f9-156">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-156">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoDASLDateMacro()
{
    string filter = "@SQL=" + "%lastmonth(" + "\"" +
        "DAV:getlastmodified" + "\"" + ")%";
    Outlook.Table table = Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).GetTable(
        filter, Outlook.OlTableContents.olUserItems);
    while (!table.EndOfTable)
    {
        Outlook.Row row = table.GetNextRow();
        Debug.WriteLine(row["Subject"]);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="dc4f9-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc4f9-157">See also</span></span>

- [<span data-ttu-id="dc4f9-158">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="dc4f9-158">Search and filter</span></span>](search-and-filter.md)

